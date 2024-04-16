### draft report, script

## Welcome to Group 1’s Course Project for ADEC 7900 Software Tools for Data Analysis.

Over several weeks we considered various research project ideas, each playing to our strengths, reading, finding potential data sources, and 
corresponding with potential resources.

By consensus we determined that the best research project topic with the greatest potential for available data would be to address a policy maker working 
on underemployment and its impact on the economic welfare of their constituents. 

Our lead question came from "It’s Not Just Wages. Retailers Are Mistreating Workers in a More Insidious Way." https://www.nytimes.com/2024/02/19/opinion/part-time-workers-usa.html
Feb. 19, 2024 By Adelle Waldman. Ms. Waldman’s 
forthcoming novel, “Help Wanted,” takes place in a big-box store.

Look at mean values during full time period
Retail ranks high. This, along with the previous time series, shows retail workers who can only find part-time work are not a new phenomenon.

# Bar Plots
data_summary6 %>% filter(Industry!="NA")%>% group_by(Industry) %>% 
  summarize(meanInvolPctofPT=mean(involPctofPT))%>%
  ggplot(data =., aes(x=reorder(Industry, -meanInvolPctofPT), y=meanInvolPctofPT, fill=Industry)) + 
  geom_col() + 
  theme(axis.text.x = element_text(angle = 90, vjust = 0.5, hjust = 1, size = 7)) +
  scale_x_discrete(labels = function(x) str_wrap(x, width = 25)) +
  scale_fill_manual(values = c("Retail Trade" = "red")) +
  ggtitle("Could only find part-time work", subtitle="% of Total Part-Time Workers by Industry: 2005 - Feb 2024")+
  labs(x = "Industry", y = "% of Part-Time Workers")+
  guides(fill = "none")


We can see in this first graph that the Retail Industry dominates the category “Could only find part-time employment” as a “Percent of Part-time workers” 
second only to “Private households, personal services” for the 20 year period from 2005 to 20024.

But if retail is often the first job for students and frequently just temporary positions until they find a “real job” is part-time retail employment really a problem?
Is part-time retail work insidious?

Although we do think of retail as a way station en route to a “real career”, according to the National Retail Federation, “As the nation's largest private-sector employer, 
retail supports more than one in four U.S. jobs — 52 million working Americans. Retail is everywhere!” 
https://nrf.com/research-insights/retails-impact#:~:text=As%20the%20nation's%20largest%20private,quick%20look%20at%20retail's%20impact.&text=Note%3A%20Updated%20data%20is%20coming%20soon%20in%202024.

Yet many retail jobs do not pay a living wage. According to the Bureau of Labor Statistics, “In 2022, their median earnings ($27,174) were around 47% less than
those of all full-time, year-round workers ($57,216). Since 2010, the relative number of U.S. retail workers remained over 9 million, but their share of the 
total workforce fell from 6.9% in 2010 to 5.6% in 2022. https://www.bls.gov/oes/2019/may/oes412031.htm

Drew Abrahamson created  this ALICE Economic Viability Dashboard https://www.unitedforalice.org/alice-evd on Tableau Public 
https://public.tableau.com/app/profile/drew7327/viz/EVD_working/EVD-Page1

“The ALICE Economic Viability Dashboard reveals the economic and community conditions of people who are struggling financially — those below the ALICE Threshold. 
This includes people in households with income below the Federal Poverty Level (FPL) and those who are ALICE (Asset Limited, Income Constrained, Employed), with
income above the FPL but below the cost of basics.” EVD_working by Drew Abrahamson on Tableau.com 

The retail Industry leads with the highest number of workers below the ALICE threshold with 5,645,233 of whom 53% are full-time and 47% are part-time.

## can we insert a tableau graph in this read me file?

# Is this really an insidious problem? How long has this been going on?

We looked at the last 20 years, creating a Time Series by Industry for 2005-2024 finding that the % of part-time workers who can only find part-time 
work fluctuates similarly across most industries.

Look at Time Series by Industry 2005-2024
The % of part-time workers who can only find part-time work fluctuates with a similar trend across most industries. The Retail Industry appears to sustain a higher level of workers who can only find part-time work. The dashed reference line at 5% helps emphasize this.

data_summary6<-data6 %>% group_by(date,Industry) %>%
  summarize(involPT=sum(W_OFPTW), partTotal=sum(W_PTW)) %>%
  mutate(involPctofPT = round((involPT/partTotal)*100,2))
## `summarise()` has grouped output by 'date'. You can override using the `.groups`
## argument.
# Time Series
ggplot(data_summary6, aes(x=date, y=involPctofPT))+geom_line()+facet_wrap(~ str_wrap(Industry, width = 20)) +
  labs(title = "Could only Find Part-Time Work", subtitle="% of Part-Time Workers by Industry: 2005-2024",x="2005-2024 Time Period", y="% of Part-Time Workers")+
  theme(axis.text.x = element_blank()) +
  theme(axis.ticks.x = element_blank()) +
  geom_hline(yintercept = 5, linetype = "dashed", color = "red")

The Retail Industry appears to sustain a higher level of workers who can only find part-time work, which is the origin of our first graph.

NOTES: 
The dashed reference line at 5% helps emphasize this.
The x-axis is marked at 2.5 year intervals.

## Can we insert the retail section of the above table of graphs?

# How did we get here?

Big Picture (U6 rate https://fred.stlouisfed.org/series/U6RATE) for 30 years

U6 rate 2005-2024 https://fred.stlouisfed.org/series/U6RATE

Policies?

The US has a long history of entrepreneurship favoring business and property owners over labor. 


# 1. Employee or Independent Contractor Classification Under the Fair Labor Standards Act
A Rule by the Wage and Hour Division on 01/10/2024 
https://www.federalregister.gov/documents/2024/01/10/2024-00067/employee-or-independent-contractor-classification-under-the-fair-labor-standards-act
	Employer practices? 
The U.S. Department of Labor is modifying Wage and Hour Division regulations to replace its analysis for determining employee or independent contractor classification under the Fair Labor Standards Act (FLSA or Act) with an analysis that is more consistent with judicial precedent and the Act's text and purpose.

# 2. United States labor law https://en.wikipedia.org/wiki/United_States_labor_law last edited  April 1, 2024
“Over the 20th century, federal law created minimum social and economic rights, and encouraged state laws to go beyond the minimum to favor employees.[2] The Fair Labor Standards Act of 1938 requires a federal minimum wage, currently $7.25 but higher in 29 states and D.C., and discourages working weeks over 40 hours through time-and-a-half overtime pay. There are no federal laws, and few state laws, requiring paid holidays or paid family leave. The Family and Medical Leave Act of 1993 creates a limited right to 12 weeks of unpaid leave in larger employers. There is no automatic right to an occupational pension beyond federally guaranteed Social Security,[3] but the Employee Retirement Income Security Act of 1974 requires standards of prudent management and good governance if employers agree to provide pensions, health plans or other benefits. The Occupational Safety and Health Act of 1970 requires employees have a safe system of work.”

# 3. The U.S. Department of Labor https://www.dol.gov/general/aboutdol/history/dolhistoxford
By Judson MacLaury - The organic act establishing the Department of Labor was signed on March 4, 1913, by a reluctant President William Howard Taft, the defeated and departing incumbent, just hours before Woodrow Wilson took office. A Federal Department of Labor was the direct product of a half-century campaign by organized labor for a "Voice in the Cabinet," and an indirect product of the Progressive Movement. In the words of the organic act, the Department's purpose is "to foster, promote and develop the welfare of working people, to improve their working conditions, and to enhance their opportunities for profitable employment."

Employer ACTIONS or PRACTICES (?)

# 1. Every CEO in office will have read one of the HBR succession planning Case Studies. https://hbr.org/topic/subject/succession-planning and understand the
UMassGolabl.edu article "Three Ways businesses that promote from within can benefit" https://www.umassglobal.edu/news-and-events/blog/promoting-from-within

# Promoting from within can save time and money
# Internal mobility can help with retention and motivation
# There’s less risk involved with internal promotions. Creating a pipeline for full time store personnel to join the executive training program should be cost effective. It could also generate a good public relations opportunity.

# 2. Some of the biggest retailers have offered tuition reimbursement and better work schedules including consistency and full-time schedules, and then withdrawn those benefits.

Target Is Doing The Right Thing By Investing Heavily In Employees And Customers
https://www.forbes.com/sites/shelleykohan/2020/06/18/target-is-doing-the-right-thing-by-investing-heavily-in-employees-and-customers/?sh=54fb8fb15045

Target raised wages. Then it cut workers' hours and doubled their workload
https://www.forbes.com/sites/shelleykohan/2020/06/18/target-is-doing-the-right-thing-by-investing-heavily-in-employees-and-customers/?sh=54fb8fb15045

Walmart makes more workers full-time in effort to retain employees
https://www.forbes.com/sites/shelleykohan/2020/06/18/target-is-doing-the-right-thing-by-investing-heavily-in-employees-and-customers/?sh=54fb8fb15045

About Working at Walmart
https://www.forbes.com/sites/shelleykohan/2020/06/18/target-is-doing-the-right-thing-by-investing-heavily-in-employees-and-customers/?sh=54fb8fb15045

# 3. According to the BLS many retail jobs do not pay a living wage. Our analysis of data from [NAME SOURCES] has found that retail consistently sustains a higher level of part-time workers when compared with other sectors.

### What effects can be attributed to which actions?
### What (if any) work is there still to be done?

# Work In Progress (WIP) from Haylee's R Pub doc

Comparing wages in retail to their real wage value and purchasing power

Calculating the real wage and purchasing power for each wage data point provided by FRED

Similarly, when determining if trends in PT are voluntary or forced, we can look at other quality of life indicators

### Our key takeaways 
In 2023-2024 data retail represents 5% of all part-time labor which is down from 8% for 2005-2024.
Part-time labor in retail peaked between 2008 and 2015 when it remained above 10% and visited 13% repeatedly.
Part-time labor dropped below 5% in 2020, presumably when COVID shut down many in person shopping venues.
Part-time retail labor has hovered around 5% of total labor since 2020.

# NEEDS work 

Even though only 5% of retail labor is part-time,% of those part-timers are designated ALICE according to the Economic Viability Dashboard.

HELP I am struggling to understand what this graph (can we insert Tableau graph?) is trying to tell me!

What is 80% ???

Are 80% of retail workers UNABLE TO FIND HEALTH INSURANCE? 

OR

Are 80% of retail workers COVERED BY HEALTH INSURANCE?

# FINALLY,

Even if we determine that this retail industry practice of hiring part-time workers and then subjecting them to dynamic schedules which confounds a 
worker’s ability to manage caring for family or scheduling a second job, and then choosing to hire more part-time workers rather than increasing the 
work hours of existing staff is truly insidious;

There is a significant discrepancy between the NRF data claiming that retail supports more than one in four U.S. jobs — 52 million working Americans 
and the Bureau of Labor Statistics Employment of industry report https://www.bls.gov/charts/employment-situation/employment-levels-by-industry.htm

# can we insert BLS.gov graph?












