### Employee Salary

### Count of Men in Engineering

```bash
db["employees"].find({gender : "Male", department : "Engineering"}).count()
```

### Count of Women in Engineering who earn less than one million

```bash
db["employees"].find({gender : "Female", department : "Engineering" , salary : {$lt : 1000000}})
```

### Count of people make less than 80k

```bash
db["employees"].find({salary : {$lt : 80000}}).count()
```

### People who belong Accounting and Legal who make less than 100k

```bash
db["employees"].find({$and : [{salary : {$lt : 100000}},{$or : [{department : "Legal"}, {department : "Accounting"}]}]})
```

### Top 10 earning Men

```bash
db["employees"].find({gender : "Male"}).sort({"salary" : -1}).limit(10)
```

### Bottom 10 earning Women

```bash
db["employees"].find({gender : "Female"}).sort({"salary" : 1}).limit(10)
```

### Top 5 earning Engineering people

```bash
db["employees"].find({department : "Engineering"}).sort({"salary" : -1}).limit(5)
```

### Bottom 5 earning Legal people

```bash
db["employees"].find({department : "Legal"}).sort({"salary" : 1}).limit(5)
```

### Women ranked 30 to 50 in terms of salary earned

```bash
db["employees"].find({gender : "Female"}).sort({"salary" : -1}).skip(29).limit(21)
```

### Men ranked 50 to 100 in terms of salary earned

```bash
db["employees"].find({gender : "Male"}).sort({"salary" : -1}).skip(49).limit(51)
```

### Bottom 50 earning women in Engineering

```bash
db["employees"].find({gender : "Female", department : "Engineering"}).sort({"salary" : 1}).limit(50)
```

### Top 50 earning men in Human Resources

```bash
db["employees"].find({gender : "Male", department : "Human Resources"}).sort({"salary" : -1}).limit(50)
```