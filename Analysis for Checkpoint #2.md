# GROUP Project SYNTHESIS (report/script) WIP 

## Introduction 

Welcome to Group 1’s Course Project for ADEC 7900 Software Tools for Data Analysis.

Over several weeks we considered various research project ideas, each playing to our strengths, reading, finding potential data sources, and corresponding with potential resources.

By consensus we determined that the best research project topic with the greatest potential for available data would be to address a policy maker working on underemployment and its
impact on the economic welfare of their constituents. 

Our lead question came from "It’s Not Just Wages. Retailers Are Mistreating Workers in a More Insidious Way." Feb. 19, 2024 By Adelle Waldman. https://www.nytimes.com/2024/02/19/opinion/part-time-workers-usa.html
Ms. Waldman’s forthcoming novel, “Help Wanted,” takes place in a big-box store.

### INSERT two graphs
  
We can see in these graphs that the Retail Industry dominates the category “Could only find part-time employment” as a “Percent of Part-time workers” for the 20 year period 
2005 - 2024 and second only to “Private households, personal services” for the most recent period from2023 to 20024.

## Reiterate problem with details

But if retail is often the first job for students and frequently just a temporary
position until they find a “real job” is part-time retail employment really a
problem? Is part-time retail work an insidious problem?

Although we do think of retail as a way station en route to a “real career”, 
according to the National Retail Federation, “As the nation's largest 
private-sector employer, retail supports more than one in four U.S. jobs — 52
million working Americans. Retail is everywhere!”
https://nrf.com/research-insights/retails-impact#:~:text=As%20the%20nation's%20largest%20private,quick%20look%20at%20retail's%20impact.&text=Note%3A%20Updated%20data%20is%20coming%20soon%20in%202024.

According to the US Census Bureau, “Despite the decreases in the number and share
of retail workers, retail remains a common occupation. In 2022, 3.1 million
workers were retail salespersons and cashiers and around 3 million were 
first-line supervisors of retail sales workers.” https://www.census.gov/library/stories/2023/12/holiday-retail-workers.html#:~:text=In%202022%2C%20their%20median%20earnings,2010%20to%205.6%25%20in%202022.

Drew Abrahamson created  this ALICE Economic Viability Dashboard 
https://www.unitedforalice.org/alice-evd
on Tableau Public https://public.tableau.com/app/profile/drew7327/viz/EVD_working/EVD-Page1

“The ALICE Economic Viability Dashboard reveals the economic and community conditions of people who are struggling financially — those below the ALICE Threshold. This 
includes people in households with income below the Federal Poverty Level (FPL) and those who are ALICE (Asset Limited, Income Constrained, Employed), with income above 
the FPL but below the cost of basics.” EVD_working by Drew Abrahamson on Tableau.com

The retail Industry leads with the highest number of workers below the ALICE threshold with 5,645,233 of whom 53% are full-time and 47% are part-time.

### insert first graph from ALICE EVD
From https://www.unitedforalice.org/alice-evd

### insert 
There is a significant discrepancy between the NRF data claiming that retail 
supports more than one in four U.S. jobs — 52 million working Americans and the 
Bureau of Labor Statistics Employment of industry report:

This is a good concept to raise...this is why I omitted WHYPTLWK "Reason for working part time" codes such as "123 School/training" and "120 Too busy with house, school, etc" from the numerator of my analysis.

Agreed! Maybe we can put in a short sentence about data for this reason was excluded because this is not the group we wanted to explore (not necessarily here, but when describing our methods)

### insert BLS graph
From https://www.bls.gov/charts/employment-situation/employment-levels-by-industry.htm
Graphics for Economic News Releases, Emlpoyment by Industry

I think the explanation of how this impacted the data analysis belongs at the end of this section "reiterate problem with details" and Real Wage Value and Purchasing Power.

## Real Wage Value and Purchasing Power

Comparing wages in retail to their real wage value and purchasing power

According to the BLS https://www.bls.gov/oes/current/oes412031.htm, May 2023, category 41-2031 Retail Salespersons sell merchandise, such as furniture, motor vehicles, appliances, 
or apparel to consumers average wage $36,690. Excludes “Cashiers” (41-2011).

Whereas according to the Census Bureau, https://www.census.gov/library/stories/2023/12/holiday-retail-workers.html#:~:text=In%202022%2C%20their%20median%20earnings,2010%20to%205.6%25%20in%202022 
Cashiers were among the lowest-paid members of the retail workforce. In 2023, 
their median earnings ($30,710) were around 47% less than those of all full-time,
year-round workers ($57,216).

We did our own analysis of average real wages using data from FRED and a manual
calculation to adjust for inflation (insert formula). Per our results, real wages
for retailers appear to be cyclical and not trending in any specific direction." 

### insert a sentence or two more after adjusting the graph to include the ranges for the real wages and the nominal wages

### insert Haylee's graph

Calculating the real wage and purchasing power for each wage data point provided by FRED

Similarly, when determining if trends in PT are voluntary or forced, we can look at other quality of life indicators

## Health Care Insurance
Here we can compare health care insurance coverage by type. Notice that “non-group” reports insurance purchased independently rather than through an employer's group coverage. It 
includes the Affordable Health Care marketplace for insurance ACA coverage.

### insert table of graphs

# Is this really an insidious problem? How long has this been going on?

We looked at the last 20 years, creating a Time Series by Industry for 2005-2024 finding that the % of part-time workers who can only find part-time work fluctuates similarly 
across most industries (data provided by IPUMS.org; see Appendix 1 with a link to our RPubs publication).

### insert table of graphs for all sectors

The Retail Industry appears to sustain a higher level of workers who can only find part-time work, which is the origin of our first graph.

### NOTES: 
The dashed reference line at 5% helps emphasize this.
The x-axis is marked at 2.5 year intervals.
 
### insert larger graph of retail sector

How did we get here? UPDATE labels on ZOOMED graph and be sure to include 5% reference line.

# HOW DID WE GET HERE?

The St Louis Economic Research data goes back 30 years,

Big Picture (U6 rate https://fred.stlouisfed.org/series/U6RATE) for 30 years

## Insert FRED graph for 30 years

But since the data we were able to use for our analysis only went back to 2005, this is a better reference for our purposes.
U6 rate 2005-2024 https://fred.stlouisfed.org/series/U6RATE

## Insert FRED graph for 20 years

# Policy Actions - history

The US has a long history of entrepreneurship and an equally long history of legislation favoring business and property owners over labor.

From the earliest indentured servants and slaves, through 19th century post civil war enforced labor during incarceration, 20th century deadly suppression of labor unions, and the current state of lobbying by businesses and their representatives.

1. Employee or Independent Contractor Classification Under the Fair Labor Standards Act
A Rule by the Wage and Hour Division on 01/10/2024 
https://www.federalregister.gov/documents/2024/01/10/2024-00067/employee-or-independent-contractor-classification-under-the-fair-labor-standards-act
	
2. The U.S. Department of Labor is modifying Wage and Hour Division regulations to replace its analysis for determining employee or independent contractor classification under the Fair Labor Standards Act (FLSA or Act) with an analysis that is more consistent with judicial precedent and the Act's text and purpose.

United States labor law https://en.wikipedia.org/wiki/United_States_labor_law last edited  April 1, 2024
“Over the 20th century, federal law created minimum social and economic rights, and encouraged state laws to go beyond the minimum to favor employees.[2] The Fair Labor Standards Act of 1938 requires a federal minimum wage, currently $7.25 but higher in 29 states and D.C., and discourages working weeks over 40 hours through time-and-a-half overtime pay. There are no federal laws, and few state laws, requiring paid holidays or paid family leave. The Family and Medical Leave Act of 1993 creates a limited right to 12 weeks of unpaid leave in larger employers. There is no automatic right to an occupational pension beyond federally guaranteed Social Security,[3] but the Employee Retirement Income Security Act of 1974 requires standards of prudent management and good governance if employers agree to provide pensions, health plans or other benefits. The Occupational Safety and Health Act of 1970 requires employees have a safe system of work.”

3. The U.S. Department of Labor https://www.dol.gov/general/aboutdol/history/dolhistoxford
By Judson MacLaury - The organic act establishing the Department of Labor was signed on March 4, 1913, by a reluctant President William Howard Taft, the defeated and departing incumbent, just hours before Woodrow Wilson took office. A Federal Department of Labor was the direct product of a half-century campaign by organized labor for a "Voice in the Cabinet," and an indirect product of the Progressive Movement. In the words of the organic act, the Department's purpose is "to foster, promote and develop the welfare of working people, to improve their working conditions, and to enhance their opportunities for profitable employment."

# Employer Practices - history 

1. Every CEO in office will have read one of the HBR succession planning Case Studies. https://hbr.org/topic/subject/succession-planning and understands the
UMassGolabl.edu article "Three Ways businesses that promote from within can benefit" https://www.umassglobal.edu/news-and-events/blog/promoting-from-within

Promoting from within can save time and money
Internal mobility can help with retention and motivation
There’s less risk involved with internal promotions. Creating a pipeline for full time store personnel to join the executive training program should be cost effective. It could also generate a good public relations opportunity.

2. Some of the biggest retailers have offered tuition reimbursement and better work schedules including consistency and full-time schedules, and then withdrawn those benefits.

Target Is Doing The Right Thing By Investing Heavily In Employees And Customers
https://www.forbes.com/sites/shelleykohan/2020/06/18/target-is-doing-the-right-thing-by-investing-heavily-in-employees-and-customers/?sh=54fb8fb15045

Target raised wages. Then it cut workers' hours and doubled their workload
https://www.forbes.com/sites/shelleykohan/2020/06/18/target-is-doing-the-right-thing-by-investing-heavily-in-employees-and-customers/?sh=54fb8fb15045

Walmart makes more workers full-time in effort to retain employees
https://www.cnbc.com/2021/04/14/walmart-makes-more-workers-full-time-in-effort-to-retain-employees.html

About Working at Walmart
https://corporate.walmart.com/about


3. According to the BLS many retail jobs do not pay a living wage. Our analysis
of data from IPUMS.org  https://corporate.walmart.com/about
has found that retail consistently sustains a higher level of part-time workers
when compared with other sectors.

# Openings and Quit Rates in Sector by Month

HELP - I need a spark
Brain storming
Can we assume that people who quit are dissatisfied?
Should we assume people leave a job for a better opportunity?
Is much of this turn over due to poaching and headhunting?
How do I tie this together to connect the CEO HBR succession planning with the dissatisfied part time employee who is struggling to pay their bills, care for their family and secure appropriate health care benefits?


From Dan’s report Over the past year, 
Retail has maintained a high percentage of workers who are forced to work part-time because they could only find part-time work. Retail also has relatively low Job Openings and a higher Quit Rate. We can continue to analyze these dynamics.

### insert 2 bar graphs Job Openings and Quit Rates

Retailers do have cyclical hiring patterns and many young people depend on seasonal work for SUMMER and end of year HOLIDAY jobs. 

### insert Haylee's Open and Quit rates by sector by month

What else can we see when the opening and quit rates and reported side by side for each month?

# Our key takeaways 

The US Census Bureau https://corporate.walmart.com/about
reports that  “the relative number of U.S. retail workers remained over 9 
million, but their share of the total workforce fell from 6.9% in 2010 to 5.6% 
in 2022.”

In 2023-2024 data retail represents 5% of all part-time labor which is down 
from 8% for 2005-2024

Part-time labor in retail peaked between 2008 and 2015 when it remained above
10% and visited 13% repeatedly.

Part-time labor dropped below 5% in 2020, presumably when COVID shut down many
in person shopping venues.

Part-time retail labor has hovered around 5% of total labor since 2020.

Even though only 5% of retail labor is part-time, 47 % of those part-timers are
designated ALICE according to the Economic Viability Dashboard.

80% of retail workers have HEALTH INSURANCE, but the variance by state remains significant.

### insert second ALICE EVD graph


# Conclusions or Recommendations?

What (if any) work is there still to be done?

Even if we determine that this retail industry practice of hiring part-time workers and then subjecting them to dynamic schedules which confounds a worker’s ability to manage 
caring for family or scheduling a second job, and then choosing to hire more part-time workers rather than increasing the work hours of existing staff is truly insidious

## WHAT ARE WE GOING TO RECOMMEND?

Do we want to pursue ACA Full Time Equivalent calculations and suggest that 
companies with a threshold of full time hours convert workers from part time 
status to full time with benefits?

Do we want to target states that have lower rates of health care benefits like 
Texas, Mississippi, and Nevada and examine how they implemented the Affordable 
Care Act? 

Actual 2022 and Anticipated 2024

County by County Plan Year 2022 Insurer Participation in Health Insurance 
Exchanges
https://www.cms.gov/cciio/programs-and-initiatives/health-insurance-marketplaces/downloads/10-16-2020-county-coverage-map.pdf

County by County Plan Year 2024 Insurer Participation in Health Insurance 
Exchanges
https://www.cms.gov/files/document/cms-cciio-draft-py-24-public-facing-map10262023v1.pdf

Nevada will get worse with less exchange particpation. Mississippi will get better, Texas appears to be improving in some counties, but getting worse in others. While Colorado and New Mexico appear to be losing ground.
