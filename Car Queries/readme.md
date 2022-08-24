# Car Queries

### Men who own a Pink car

```bash
db["cars"].find({car_color : "Pink", gender : "Male"})
```

### Women who own a Red or a Blue Car

```bash
db["cars"].find({$or : [{car_color : "Red"}, {car_color : "Blue"}],  gender : "Female"})
```

### Men who purchased the car in the year 1998

```bash
db["cars"].find({$and : [{purchase_year : "1998"}, {gender : "Male"}]})
```

### Women who purchased a Yellow car in the year 1985

```bash
db["cars"].find({$and: [{car_color : "Yellow"},{gender : "Female"},{purchase_year : "1985"}]})
```

### Men who either have a Red or Green car and either live in Germany or Kenya

```bash
db["cars"].find({$and : [{ $or : [{car_color : "Green"},{car_color : "Red"}] },{ $or : [{country : "Germany"},{country : "Kenya"}] },{gender : "Male"}]})
```
 

### People from India who purchased cars in the year 2001

```bash
db["cars"].find({country: "India",purchase_year:"2001"})
```

### People from Germany or Egypt who purchased cars in the year 1998 or 1992

```bash
db["cars"].find({$and : [{gender : "Male"}, {$or : [{ purchase_year : "1992"},{ purchase_year : "1998"}]},{$or : [{ country : "Egypt"},{ country : "Germany"}]} ]})
```

### Women from India who own a Blue car

```bash
db["cars"].find({gender: "Female", country: "India", car_color:"Blue"})
```

### Men from Germany who purchased cars in 1998 and Men from Egypt who purchased cars in 1992

```bash
db["cars"].find({$and : [{gender : "Male"}, {$or : [{ purchase_year : "1992", country : "Egypt"},{ purchase_year : "1998", country : "Germany"}]}]})
```

### Women who own a Green car and are not from Pakistan

```bash
db["cars"].find({gender : "Female", car_color : "Green", country: {$ne: ["Pakistan"]}})
```