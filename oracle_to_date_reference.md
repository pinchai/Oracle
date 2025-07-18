
# Oracle TO_DATE Function

## Purpose
Converts a string to a **DATE** value using a specified date format.

---

## Syntax

```sql
TO_DATE(char, format_model [, nls_language])
```

- **char**: String to convert.
- **format_model**: The date format to use.
- **nls_language**: (Optional) Language for month/day names.

---

## Common Format Models

| Pattern   | Meaning                         | Example Output         |
|-----------|---------------------------------|-----------------------|
| YYYY      | 4-digit year                    | 2025                  |
| YY        | Last 2 digits of year           | 25                    |
| MM        | Month (01-12)                   | 07                    |
| MON       | Abbreviated month name          | JUL                   |
| MONTH     | Full month name                 | JULY                  |
| DD        | Day of month (01-31)            | 18                    |
| DY        | Abbreviated day of week         | FRI                   |
| DAY       | Full day of week                | FRIDAY                |
| HH24      | Hour (24-hour)                  | 18                    |
| HH        | Hour (12-hour)                  | 06                    |
| MI        | Minutes                         | 33                    |
| SS        | Seconds                         | 45                    |
| AM, PM    | Meridian indicator              | PM                    |

---

## Basic Example

```sql
SELECT TO_DATE('2025-07-18', 'YYYY-MM-DD') FROM dual;
```

---

## Using Time

```sql
SELECT TO_DATE('2025-07-18 19:15:00', 'YYYY-MM-DD HH24:MI:SS') FROM dual;
```

---

## With Month/Day Names

```sql
SELECT TO_DATE('18-JUL-2025', 'DD-MON-YYYY') FROM dual;
SELECT TO_DATE('July 18, 2025', 'Month DD, YYYY') FROM dual;
```

---

## With NLS Language

```sql
SELECT TO_DATE('18 Juillet 2025', 'DD Month YYYY', 'NLS_DATE_LANGUAGE=FRENCH') FROM dual;
```

---

## Invalid Date Handling

If the format does **not** match the input, Oracle will raise an error:

```sql
SELECT TO_DATE('2025-18-07', 'YYYY-MM-DD') FROM dual; -- Error!
```

---

## All Common Format Models

| Model     | Meaning                  |
|-----------|--------------------------|
| YYYY      | 4-digit year             |
| YY        | 2-digit year             |
| MM        | Month (01-12)            |
| MON       | Abbreviated month name   |
| MONTH     | Full month name          |
| DD        | Day (01-31)              |
| DDD       | Day of year (001-366)    |
| DY        | Abbreviated day name     |
| DAY       | Full day name            |
| HH, HH12  | Hour (1-12)              |
| HH24      | Hour (0-23)              |
| MI        | Minute (0-59)            |
| SS        | Second (0-59)            |
| SSSSS     | Seconds past midnight    |
| AM, PM    | Meridian indicator       |
| Q         | Quarter (1-4)            |
| W         | Week in month            |
| WW        | Week in year             |
| RM        | Roman month (I-XII)      |
| TZD       | Time zone abbreviation   |
| TZH       | Time zone hour           |
| TZM       | Time zone minute         |

---

## Practical Tips

- **Always specify format:** Use explicit format to avoid NLS issues.
- **For timestamp:** Use `TO_TIMESTAMP` instead of `TO_DATE` for fractional seconds.

---

