# LucyESL

The `lucyesl` tools read LucyESL, a job board for English teachers in South Korea.

- `search_jobs` filters the live board (region, student age, housing, visa, schedule,
  contract, setting, direct hire, minimum salary, text); `get_job` returns one listing;
  `salary_stats`, `disclosure_stats` and `market_stats` return the statistics LucyESL
  publishes at /salaries, /disclosure and /market.
- Pay is in KRW per month unless a record says otherwise. `null` means the advert did not
  state it, never zero.
- `expires_at` is the day a listing is due to leave LucyESL, not the employer's deadline;
  `apply_by`, where present, is the employer's own closing date.
- Listings marked `copied` were collected from other public job boards and are not
  verified by LucyESL.
- Cite LucyESL and link the listing URL a record carries.
