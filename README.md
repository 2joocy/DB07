# DB07

Made by:
 - Viktor Kim Christiansen
 - Christopher Rosendorf
 - William Pfaffe

## Introduction

## 01
### 1st Normal Form
Table has concatinated values
### 2nd Normal
2nd Normal Form states following:
```
The table is in 1st normal form, and
All the non-key columns are dependent on the table’s primary key.
```
The table also shows redundant info and most of the info like the sales rep, should be in it's own table, showing both customer and sales rep in a non-intuitive way.
### 3rd Normal
The rep coloums are unrelated to the customer, therefore 3rd form is not satisfied.

## 02
Given that the customer is a company, and we assume that the customer name is unique (as no 2 companies can be named the same), we could use the customer name as a key. The norms would change in this case, as you'd only get what's relevant to the customer, and not everything else (The 2nd norm is then no longer valid). The case for the first norm would be the same as we concatinate certain values from the customer.
## 03
I am abit unsure what the reference is suppose to be there for. The employee has no other key, referencing the customer other than the customer ID. In order to "use" the table in assignment 2, I'd have to change all referenced values to the name (which assignment 2 doesn't state you need to do). I'll continue using the original table in this example.

```
UPDATE employees
SET repPhone = 85858585
WHERE employees.employeeNumber = ?;
```

Now, if you'd want it to be updated using the "new" table, you'd do it as such:

```
UPDATE employees
SET repPhone = 85858585
WHERE employees.customerName = ?;
```


From what is understood by a "safe" update, is referencing specific data that cannot resolve into unintended changes. Referencing a table by it's identifier (Which should be unique) will change that value, and only that value.
