@'
# Investor Behaviour Analysis: Power BI

**I analysed a survey of 40 investors in Power BI to find out who invests, in what, why, for how long, and where
they get their information, across 7 tasks ending in one combined dashboard.**

*Built during my data analytics internship at Cognifyz.*

`Power BI` · `DAX` · `Data modelling` · `Dashboard design` · `Survey analysis`

---

## The problem

Before designing investment products or campaigns, a firm needs to understand its investors. The raw survey
(40 people, 24 questions) can't answer these questions on its own:

- Who are the investors (age, gender), and how many actually invest?
- Which investment options do they prefer, and does it differ by gender?
- What are their goals, how long do they invest for, and how often do they check?
- Why do they choose mutual funds, and where do they get their information?

## How I solved it

| Task | Question answered | What I built |
|---|---|---|
| 1. Data exploration | Who are the respondents? | Cards for average age and investors vs non-investors; savings-goal chart |
| 2. Gender analysis | Do men and women invest differently? | Charts by gender for mutual funds, equity and bonds |
| 3. Objective analysis | Do goals relate to the chosen investment? | Objective vs investment chart, a DAX correlation measure, slicer |
| 4. Duration and frequency | How long and how often? | Duration and monitoring charts, counts per investment type |
| 5. Reasons | Why mutual funds? | Reason counts by duration and monitoring frequency |
| 6. Information sources | Where do they learn? | Source vs investment charts with a slicer |
| 7. Final dashboard | All of the above on one page | Combined interactive dashboard |

**DAX measures written:** average age, investor / non-investor counts, male / female counts, counts per investment
type and per mutual-fund reason, and a Pearson correlation measure.

## Results

| Who they are | |
|---|---|
| Respondents | 40 (25 male, 15 female) |
| Average age | 27.8 years (range 21–35) |
| Invest today | 37 of 40 (92.5%) |

**What the data shows:**

- **Top choice: Mutual funds.** 18 of 40 name mutual funds as their main investment, then equity (10), fixed
  deposits (9) and PPF (3).
- **Most preferred overall: PPF.** When ranking all 7 options, 24 of 40 put **PPF first**; gold and debentures
  ranked last on average.
- **Goal: grow money for retirement.** 26 aim for capital appreciation; 24 save for retirement; 32 expect 20–30%
  returns.
- **Mid-term, monthly investors.** 37 of 40 invest for 1–5 years; 29 of 40 check their investments monthly.
- **Why mutual funds:** better returns (24), fund diversification (13), tax benefits (3).
- **Where they learn:** financial consultants (16) and newspapers/magazines (14) lead; the internet is last (4).

**Business takeaway:** this is a young, retirement-focused group that trusts advisers. Mutual-fund products sold
through financial consultants, framed around returns over 1–5 years, fit them best.

## What I'd fix in the reports

Reviewing my own work later, I found these issues:

- **The 7 investment columns are rankings (1 = most preferred, 7 = least), not money amounts.** In Tasks 1, 2 and
  7, I summed them and called them "investment amounts". A higher sum actually means *less* preferred. The results
  above use the correct reading (average rank and first choices).
- **Pearson correlation measure (Task 3):** the DAX formula is missing the row-count term, and objective and
  investment type are categories, so a correlation number isn't meaningful here. A count chart or a
  cross-tab answers the question better.
- **Small sample:** 40 people is enough to practise analysis, not to generalise about all investors.
- The final dashboard's title says "Task 6"; it should say "Task 7".

## Dashboard

Open `Task 7 Combine Insights into a Dashboard.pbix` in Power BI Desktop to explore it.

---

<details>
<summary>Files</summary>

| File | Contents |
|---|---|
| `Task 1 Data Exploration and Summary.pbix` | Respondent profile |
| `Task 2 Gender Based Analysis.pbix` | Gender comparison |
| `Task 3 Objective Analysis.pbix` | Goals vs investment choice |
| `Task 4 Investment Duration and Frequency.pbix` | Duration and monitoring |
| `Task 5 Reasons of Investments.pbix` | Reasons for mutual funds |
| `Task 6 Source of Information.pbix` | Information sources |
| `Task 7 Combine Insights into a Dashboard.pbix` | Final combined dashboard |

Open any `.pbix` file in Power BI Desktop (free) to explore it.

</details>
'@ | Set-Content -Path README.md -Encoding UTF8
