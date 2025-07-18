## `TO_CHAR` — Datetime Formatting Examples

## 1. Display Full Date and Time

```sql
SELECT TO_CHAR(hire_date, 'YYYY-MM-DD HH24:MI:SS') AS full_datetime
FROM employees;
```

> Example Output: `2023-07-18 16:30:45`

---

## 2. Custom Date Formats

**a. Month Name and Year**

```sql
SELECT TO_CHAR(hire_date, 'Month YYYY') AS month_year
FROM employees;
```

> Output: `July     2023`\

**b. Day of Week**

```sql
SELECT TO_CHAR(hire_date, 'Day') AS day_name
FROM employees;
```

> Output: `Tuesday   `\


---

## 3. Extracting Specific Parts

**a. Only the Year**

```sql
SELECT TO_CHAR(hire_date, 'YYYY') AS year_only
FROM employees;
```

> Output: `2023`

**b. Only the Hour and Minute**

```sql
SELECT TO_CHAR(hire_date, 'HH24:MI') AS hour_minute
FROM employees;
```

> Output: `16:30`

---

## 4. Localization / AM-PM Format

**a. 12-hour Time with AM/PM**

```sql
SELECT TO_CHAR(hire_date, 'YYYY-MM-DD HH:MI:SS AM') AS datetime_ampm
FROM employees;
```

> Output: `2023-07-18 04:30:45 PM`

---

## 5. Day, Month Name, and Year in One Line

```sql
SELECT TO_CHAR(hire_date, 'DDth "of" Month YYYY') AS full_date
FROM employees;
```

> Output: `18th of July 2023`

---

## 6. ISO 8601 Standard Format

```sql
SELECT TO_CHAR(hire_date, 'YYYY-MM-DD"T"HH24:MI:SS') AS iso_format
FROM employees;
```

> Output: `2023-07-18T16:30:45`

---

## 7. Show Milliseconds (for TIMESTAMP)

```sql
SELECT TO_CHAR(SYSTIMESTAMP, 'YYYY-MM-DD HH24:MI:SS.FF3') AS timestamp_with_ms
FROM dual;
```

> Output: `2025-07-18 18:22:30.123`

---

## 8. Local Language Example

```sql
SELECT TO_CHAR(hire_date, 'DD Month YYYY', 'NLS_DATE_LANGUAGE=FRENCH') AS date_in_french
FROM employees;
```

> Output: `18 Juillet 2023`

---

## 9. Display Date with Timezone (for TIMESTAMP WITH TIME ZONE)

```sql
SELECT TO_CHAR(SYSTIMESTAMP, 'YYYY-MM-DD HH24:MI:SS TZR') AS datetime_tz
FROM dual;
```

> Output: `2025-07-18 18:24:15 ASIA/PHNOM_PENH`

---
