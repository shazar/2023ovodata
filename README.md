# 2023 Oy ve Ötesi Verileri

Oy ve Ötesi web sitesinden scrape edilen verileri SQLite formatında alıp üzerinde oynamak için kullanabilirsiniz.

Amacım [Observable](https://observablehq.com) ile bir kaç [deneme](https://observablehq.com/d/f0479e94b2b78585) yapmaktı.

Database formatı hızlıca SQL deneyleri yapabilmek adına çok yalındır. Observable üzerinde kullanailmek için, 50MB altında bir de light versiyonu var.

## Database Schema

```sql
CREATE TABLE district(id INTEGER PRIMARY KEY, city_id INTEGER, name TEXT);
CREATE TABLE city(id INTEGER PRIMARY KEY, name TEXT);
CREATE TABLE neighborhood(id INTEGER PRIMARY KEY, city_id INTEGER, district_id INTEGER, name TEXT);
CREATE TABLE school(id INTEGER PRIMARY KEY, city_id INTEGER, district_id INTEGER, neighborhood_id INTEGER, name TEXT);
CREATE TABLE cm_candidate(id INTEGER PRIMARY KEY, name TEXT);
CREATE TABLE mv_candidate(id INTEGER PRIMARY KEY, name TEXT);
CREATE TABLE ballotbox(number INTEGER, city_id INTEGER, district_id INTEGER, neighborhood_id INTEGER, school_id INTEGER, cm_result TEXT, mv_result TEXT);
```
