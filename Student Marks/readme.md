### Student marks

### Count of all the female students

```bash
db["students"].find({gender : "Female"}).count()
```

### Count of all male students who scored more that 85 in maths, science and english

```bash
db["students"].find({gender : "Male", maths : {$gt : 85}, science : {$gt : 85}, english : {$gt : 85}}).count()
```

### Count of all students who scored between 50 and 75 marks in maths and english

```bash
db["students"].find({maths : {$gt : 50, $lt : 75}, english : {$gt : 50, $lt : 75}}).count()
```

### Count of students from class I to class V who score more that 50 in all subjects

```bash
db["students"].find({maths : {$gt : 50}, science : {$gt : 50}, english : {$gt : 50}, class : {$in : ["I", "II", "III", "IV", "V"]}}).count()
```

### Find all the female students from grade X section A who scored less that 25 in all subjects

```bash
db["students"].find({maths : { $lt : 25}, english : {$lt : 25}, science : {$lt : 25}, gender : "Female" , class : "X" , section : "A" }).count()
```

### Top 3 students in grade V based on maths score

```bash
db["students"].find({class : "V"}).sort({"maths" : -1}).limit(3)
```

### Bottom 5 students in grade I based on science score

```bash
db["students"].find({class : "I"}).sort({science : 1}).limit(5)
```

### Students from section A who scored less than 50 in all the subjects

```bash
db["students"].find({maths : {$lt : 50}, science : {$lt : 50}, english : {$lt : 50}, section : "A"})
```

### Students from section C who scored more that 75 in all the subjects

```bash
db["students"].find({maths : {$gt : 75}, science : {$gt : 75}, english : {$gt : 75}, section : "C"})
```

### Students who will fall in page 3 if ordered by increasing order of maths scores (Assume 10 results per page)

```bash
db["students"].find({}).sort({"maths" : 1}).skip(20).limit(10)
```

### Students who will fall in page 5 if ordered by descreasing order of science scores (Assume 20 results per page)

```bash
db["students"].find({}).sort({"science" : -1}).skip(80).limit(20)
```

### Female Students who will fall in page 4 if ordered by increasing order of science scores and maths scores (Assume 5 results per page)
```bash
db["students"].find({gender : "Female"}).sort({"science" : 1, "maths": 1}).skip(15).limit(5)
```


### Male Students who will fall in page 3 if ordered by decreasing order of science, maths and english scores (Assume 15 results per page)
```bash
db["students"].find({gender : "Male"}).sort({"science" : -1, "maths": -1, english : -1}).skip(30).limit(15)
```
