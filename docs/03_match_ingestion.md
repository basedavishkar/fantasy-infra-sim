# match ingestion notes

- poll match api every 60s (espncricinfo or dream11 source?)
- cache latest scores → push to redis (ttl = 120s)
- retry failed pulls with delay (basic backoff)
- cron job via celery beat or just use systemd?

- store raw api response → db table: match_snapshots
- clean parser extracts: runs, wickets, overs, player stats
- calculate fantasy points in separate worker

// todo: need to validate if api hits are rate limited
// maybe fallback to scraper if quota hits?