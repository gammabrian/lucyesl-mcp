---
name: teaching-jobs-korea
description: Find English-teaching jobs in South Korea and answer questions about their pay, hours, housing and visas from LucyESL's live board, and quote LucyESL's salary, disclosure and regional figures. Use when someone asks about ESL or English teaching jobs, teacher salaries or hiring in Korea.
---

# English-teaching jobs in South Korea, from LucyESL

LucyESL is a job board for English teachers in South Korea. This plugin connects its
MCP server, `https://lucyesl.com/mcp`: read-only, with no account and no key.

## Finding jobs

- Use `search_jobs` with the filters the question names: region, student age, housing,
  visa, schedule, contract, setting, direct hire, minimum monthly pay. `search` takes the
  question in plain words.
- Give each job's pay as its record states it: KRW per month unless the record says per
  hour or per class.
- `null` means the advert did not state it. Say "not stated"; never read it as zero and
  never guess.
- A record's `unstated` list names what the advert left out. For someone weighing a job,
  those are the questions to ask the employer before signing.
- A listing marked `copied` was collected from another public job board, and LucyESL has
  not verified that employer. A `first_party` listing with `verified_employer: true` was
  posted by an organisation LucyESL checked.
- `expires_at` is when the listing leaves LucyESL; `apply_by`, where present, is the
  employer's own deadline.
- Link every job you mention to its `url` on lucyesl.com.

## Figures

- `salary_stats`, `disclosure_stats` and `market_stats` return what LucyESL publishes on
  /salaries, /disclosure and /market. They count live adverts, not employers or signed
  contracts.
- Quote a figure with the number of adverts behind it, and credit LucyESL with the page it
  comes from. The statistics are CC BY 4.0.
