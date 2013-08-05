# {{.Title}} - {{.DateDomain}}

## Date

Return curent UTC time 

### Url
```
GET {{.DateRootUrl}}/date
```

### Result Example
```
2013-08-05 14:43:38.174604892 +0000 UTC
```

## Timer new

Create a new timer, return the timer id

### Url
```
GET {{.DateRootUrl}}/timer/new
```

### Result Example
```
4221
```

## Timer count

Return the number of timer ever created

### Url
```
GET {{.DateRootUrl}}/timer/count
```

### Result Example
```
4222
```

## Timer get

### Url
```
GET {{.DateRootUrl}}/timer/get?id=<id1>[&id=<idn>]
```

### Example
```
GET {{.DateRootUrl}}/timer/get?id=4221
```

### Result
```
{"4221":"94h52m23.029381783s"}
```

