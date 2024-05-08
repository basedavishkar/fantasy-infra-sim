# Wallet Flow Sketch (v0)

- user deposits via Razorpay → credited to wallet
- wallet balance is used to join contests
- joining triggers debit txn + locks amount
- refund on cancel = unlock + re-credit

Edge cases:
- concurrent match join → locking logic?
- what if Razorpay confirms but user quits mid-redirect?
- settlement flow on contest end = who handles payouts?

// todo:
- cron job for wallet reconciliation?
- dispute window for failed payments?
