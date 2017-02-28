## ES Operations

### Create a New Index

```
curl -XPOST http://<ES_HOST>:7104/commuter -d @src/resources/commuter.es.mapping.json
```

### Update Alias

```
curl -XPOST http://<ES_HOST>:7104/_aliases -d '
{
    "actions": [
        { "remove": {
            "alias": "commuter",
            "index": "<OLD_INDEX>"
        }},
        { "add": {
            "alias": "commuter",
            "index": "<NEW_INDEX>"
        }}
    ]
}'
```

### Delete Index

```
curl -XDELETE http://<ES_HOST>:7104/commuter
```
