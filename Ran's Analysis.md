# Testing
Testing


library(ggplot2)
library(reshape2)


data <- read.csv("JOLTS.csv", header = TRUE)

colnames(data)[1] <- "Sector"
data$Sector <- as.factor(data$Sector)
data$Type <- ifelse(grepl("Opening", data$Sector), "Opening Rate", "Quit Rate")
data$Sector <- gsub("_Rate", "", data$Sector)
data$Sector <- gsub("Opening_Rate", "", data$Sector)
data$Sector <- gsub("Quit_Rate", "", data$Sector)


data_melted <- melt(data, id.vars = c("Sector", "Type"), variable.name = "Month", value.name = "Rate")


ggplot(data_melted, aes(x = Month, y = Rate, color = Type)) + 
  geom_line() + 
  facet_wrap(~ Sector, scales = "free_y") + 
  theme_minimal() + 
  theme(axis.text.x = element_text(angle = 90, hjust = 1)) + 
  labs(title = "Trend of Opening and Quit Rates by Sector", y = "Rate (%)", x = "Month")


ggplot(data_melted, aes(x = Sector, y = Rate, fill = Type)) + 
  geom_bar(stat = "identity", position = position_dodge()) + 
  facet_wrap(~ Month, scales = "free_y") + 
  theme_minimal() + 
  theme(axis.text.x = element_text(angle = 90, hjust = 1)) + 
  labs(title = "Opening and Quit Rates by Sector and Month", y = "Rate (%)", x = "Sector")


opening_rates <- subset(data_melted, Type == "Opening Rate")
ggplot(opening_rates, aes(x = Month, y = Sector, fill = Rate)) + 
  geom_tile() + 
  scale_fill_gradient(low = "blue", high = "red") + 
  theme_minimal() + 
  theme(axis.text.x = element_text(angle = 90, hjust = 1)) + 
  labs(title = "Heat Map of Opening Rates", y = "Sector", x = "Month")


