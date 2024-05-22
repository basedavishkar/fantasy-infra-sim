# cron jobs, not microservices.

🚨 this file is chaos. don't clean it yet. just keep adding shit.

---

🧠 brain dump:

- match ingestion every 15 min — should be idempotent.
- scoring script (post-match) → needs reliable trigger.
- payout executor = not cron? maybe pub/sub or manual? needs thinking.

---

🕒 what needs cron rn:

[] fetch matches from provider
[] mark contest status: upcoming → live → locked → completed
[] scoring + payouts
[] reconcile wallets (maybe daily, maybe hourly?)
[] refund failed contests

---

questions:

- do we need a scheduler lib or just raw `sleep + while` for now?
- where do we log fails? cloudwatch? s3 bucket of shame?
- can we test these end-to-end with fake match IDs?

---

future me: please don't dockerize this yet. it's not worth it.
