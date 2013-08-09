# {{.Title}} - {{.QueueDomain}}

## New

Create a new queue,
return the queue name

### Url
```
GET {{.QueueRootUrl}}/new
```

### Result Example
```
{"name": "6489f3211586b2699658970aba26ff23"}
```


## Count

Return the queue size

### Url
```
GET {{.QueueRootUrl}}/count?name=<queue_name>
```

### Result Example
```
{"name":"6489f3211586b2699658970aba26ff23","count":42}
```


## Push

Push a new item to queue,
return the queue size

### Url
```
GET {{.QueueRootUrl}}/push?name=<queue_name>[&uniq=(true|false)]&value=<value1>[&value=<value2> ...]
```

### Example
```
GET {{.QueueRootUrl}}/push?name=6489f3211586b2699658970aba26ff23&value=patate%20!
```

### Result
```
{"name":"6489f3211586b2699658970aba26ff23","count":43}
```


## Pop

Pop the first item,
return the value (not encoded) and the queue size

### Url
```
GET {{.QueueRootUrl}}/pop?name=<queue_name>[&count=n]
```

### Result Example
```
GET {{.QueueRootUrl}}/pop?name=cb90c44eac6a0b5aff69e26c909b2207&count=3
{"name":"cb90c44eac6a0b5aff69e26c909b2207","count":40,"values":["plop !","toto","titi"]}
```


## Find

### Url
```
GET {{.QueueRootUrl}}/find?name=<queue_name>&value=<value1>[&value=<value2> ...]
```

### Result Example
```
{"name":"6489f3211586b2699658970aba26ff23","count":40,"offsets":{"patate !":42,"test":6}}
```


## Export

Export the queue,
return an error if the queue size exceed the limit.

### Url
```
GET {{.QueueRootUrl}}/export?name=<queue_name>
```

### Result Example
```
{"name":"6489f3211586b2699658970aba26ff23","count":3,"queue":["toto","titi","tata"]}
```

