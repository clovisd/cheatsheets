---
title: Cron
category: CLI
layout: 2017/sheet
updated: 2018-05-20
weight: -3
---

## Format
{: .-two-column}

### Format

```
Min  Hour Day  Mon  Weekday
```
{: .-setup}

```
*    *    *    *    *  command to be executed
```

```
┬    ┬    ┬    ┬    ┬
│    │    │    │    └─  Weekday  (0=Sun .. 6=Sat)
│    │    │    └──────  Month    (1..12)
│    │    └───────────  Day      (1..31)
│    └────────────────  Hour     (0..23)
└─────────────────────  Minute   (0..59)
```

### Special Strings

| String | Meaning |
| --- | --- |
| `@reboot` | Run once, at startup. |
| `@yearly` | Run once a year, `0 0 1 1 *`. |
| `@annually` | (same as @yearly) |
| `@monthly` | Run once a month, `0 0 1 * *`. |
| `@weekly` | Run once a week, `0 0 * * 0`. |
| `@daily` | Run once a day, `0 0 * * *`. |
| `@midnight` | (same as @daily) |
| `@hourly` | Run once an hour, `0 * * * *`. |

{: .-setup.-box-chars}

### Examples

| Example        | Description           |
| ---            | ---                   |
| `0 * * * *`    | every hour            |
| `*/15 * * * *` | every 15 mins         |
| `0 */2 * * *`  | every 2 hours         |
| `0 0 0 * 0`    | every Sunday midnight |
| ---            | ---                   |
| `@reboot`      | every reboot          |

### Crontab

```bash
# Adding tasks easily
echo "@reboot echo hi" | crontab
```

```bash
# Open in editor
crontab -e
```

```bash
# List tasks
crontab -l [-u user]
```
