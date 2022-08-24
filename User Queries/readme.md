### Users

### Find all the female users

```bash
db["users"].find({gender : "Female"})
```

### Find all the female users who speak one of the two languages Kannada, Hindi

```bash
db["users"].find({$or : [{language : "Kannada"},{language : "Hindi"}], gender : "Female"})
```

### Find all the male users who can speak Hindi and female users who can speak Kannada

```bash
db["users"].find({$or : [{language : "Hindi", gender : "Male"},{language : "Kannada", gender : "Female"}]})
```

### Find all the users who wear the shirt size S

```bash
db["users"].find({shirt_size : "S"})
```

### Find all the female users who wear the shirt size XL

```bash
db["users"].find({gender : "Female", shirt_size : "XL"})
```

### Find all the English speaking male users and Hindi speaking female users

```bash
db["users"].find({$or : [{language : "Hindi", gender : "Female"},{language : "English", gender : "Male"}]})
```

### Find all the male users who can speak Hindi or English and female users who can speak Kannada or German

```bash
db["users"].find({$or : [{$or : [{language : "Hindi", gender : "Male"},{language : "English", gender : "Male"}]},{$or : [{language : "Kannada", gender : "Female"},{language : "German", gender : "Female"}]}]})
```

### Find all the female users who can speak Bengali who wear shirt size XL and male users who speak German and wear shirt size either L or M

```bash
db["users"].find({$or : [{shirt_size : "XL", gender : "Female", language : "Bengali"},{$or : [{shirt_size : "M"},{shirt_size : "L"}], gender : "Male", language : "German"} ]})
```


### Find all the female users who speak any of the Indian languages (Hindi, Punjabi, Bengali, Gujarati, Tamil, Malayalam)

```bash
db["users"].find({$and : [{gender : "Female"}, {$or : [{language : "Hindi"},{language : "Punjabi"},{language : "Bengali"},{language : "Gujarati"},{language : "Tamil"},{language : "Malayalam"}]}]})
```


### Men who can speak Korean

```bash
db["users"].find({gender : "Male", language : "Korean"})
```
