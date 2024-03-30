# Software-Tools-Spring-2024
# README
The purpose of this README document is to provide the research question being addressed and the data, tools, and methods used. 

## Research Question
Our research questions is currently in development, but we are considering the following items:

1. Has the rate of part-time retail positions changed over time?
2. Is this “insidious” problem really new?
3. Can we compare other industries that were able to argue for consultants and independent contractors to be converted to full-time employees with benefits?
4. What harms might such a change create?
   a. Consider the increase of minimum wage and possible reduction in the number of jobs and/or hours of work? (see UW Evans School of Public Policy & Governance December 3, 2021 report)

## Decision Maker and Decision Being Made
We are currently undecided, but will likely be one of the following:

### CEO
Retail represents 1 out of 4 US jobs. In a low unemployment market does our CEO need to consider sweetening the pot by offering more Full Time positions with benefits to attract and retain personnel, reducing turnover, increasing institutional knowledge, and developing internal job growth? Note increase in minimum wage and industry rate of tuition reimbursement programs.

Any CEO in office now will have read one of the Harvard Business Review’s case studies on Succession Planning ( https://hbr.org/topic/subject/succession-planning ). They will be fully aware that the cost of hiring is greater than the cost to promote from within: See UMassGolabl.edu article ( https://www.umassglobal.edu/news-and-events/blog/promoting-from-within ) "Three Ways businesses that promote from within can benefit":
1. Promoting from within can save time and money
2. Internal mobility can help with retention and motivation
3. There’s less risk involved with internal promotions
Creating a pipeline for full time store personnel to join the executive training program should be cost effective. It could also generate a good public relations opportunity. 


### Policy Makers 
Our Alternative consideration regards the reality that of US Health Insurance is provided by employers to the vast majority of Americans (86% according to the US Census Bureau https://www.census.gov/library/stories/2024/02/health-care-costs.html#:~:text=About%2086%25%20of%20U.S.%20private,Survey%20(MEPS%2DIC).) and the standard business practice that most employers do not offer health benefits to part-time employees. 

In particular, are retailers exploiting part-time workers by denying them opportunities to work full time schedules with access to full benefits? Should employers be required to make some portion of their labor full time with benefits? What thresholds should be set? See ACA formula.

According to ADP, https://www.adp.com/resources/articles-and-insights/articles/p/part-time-benefits.aspx "The ACA does not mandate coverage for part-time employees, but it does factor them into full-time equivalent (FTE) employee calculations. Depending on the number of part-time employees a business has and how many hours they work, it may meet the 50 FTE employee minimum and be required to provide health insurance for its full-time employees." 

I the same report ADP answers the question "How many hours do you need to work to qualify for benefits?"

"Under the Affordable Care Act, employers with 50 or more full-time equivalent employees are required to provide health insurance only to those who work 30 hours per week or 130 hours per month. They can choose to extend benefits to employees who work less than that, but states and insurance companies may have minimum hourly requirements of their own." 

According to Health Insurance.org https://www.healthinsurance.org/glossary/full-time-equivalent/  “The full-time equivalent is used to determine employer size under the ACA. Any employee working at least 30 hours per week is considered full time. In addition, part-time employees are counted using the full-time equivalent method of adding the total number of hours worked by all part time employees in a month, and dividing by 120.”

From the FLSA website (https://www.dol.gov/general/topic/workhours/full-time)
The Fair Labor Standards Act (FLSA) does not define full-time employment or part-time employment. This is a matter generally to be determined by the employer. Whether an employee is considered full-time or part-time does not change the application of the FLSA, nor does it affect application of the Service Contract Act or Davis-Bacon and Related Acts wage and fringe benefit requirements.

From The Department of Labor’s Wage and Hour Division’s home page:  On August 30, 2023, the Department of Labor announced issuance of a Notice of Proposed Rulemaking (NPRM), Defining and Delimiting the Exemptions for Executive, Administrative, Professional, Outside Sales, and Computer Employees. https://www.dol.gov/agencies/whd/overtime/rulemaking

And on January 10, 2024, the U.S. Department of Labor published a final rule Employee or Independent Contractor Classification Under the Fair Labor Standards Act, effective March 11, 2024. https://www.federalregister.gov/public-inspection/2024-00067/employee-or-independent-contractor-classification-under-the-fair-labor-standards-act Both could be useful references for our research.


## Description of Data Set 

We have pulled data from the [**U.S. Census Current Population Survey (CPS)**](https://www.census.gov/data/datasets/time-series/demo/cps/cps-basic.2023.html#list-tab-1979780401)
This is a monthly data set that includes data about people's employment status and industry
This is the census2324ind.csv file.

[**BLS Job Openings and Labor Turnover Survey**](https://www.bls.gov/jlt/data.htm)
This shows monthly Job Opening and Quit data across industries
This is the JOLTS.csv file.

Also consulted [**BLS Persons at work in nonagricultural industries by class of worker and usual full- or part-time status**](https://www.bls.gov/cps/cpsaat21.htm)

Lastly, we are examining data provided by consulted [**Bureau of Economic Analysis (BEA)**](https://www.bea.gov/data)
The BEA, an agency of the U.S. Department of Commerce, provides economic accounts statistics that enable government and business decision-makers to follow and understand the performance of the U.S. economy. 

## Tools and Methods Used
R - GGPlOT to create visualizations
