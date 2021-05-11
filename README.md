#### Json para criar o button de execução do flow

```
{
    "$schema": "https: //developer.microsoft.com/en-us/json-schemas/sp/column-formatting.schema.json",
    "elmType": "span",
    "style": {
        "color": "#0078d7"
    },
    "children": [
        {
            "elmType": "button",
            "style": {
                "border": "1px solid black",
                "background-color": "#eee",
                "color": "#0078d7",
                "cursor": "pointer",
                "padding": "10px"
            },
            "txtContent": {
                "operator": "+",
                "operands": [
                    "[$CustomAction]",
                    " Approval"
                ]
            },
            "elmType": "button",
            "txtContent": "Get Approved",
            "customRowAction": {
                "action": "executeFlow",
                "actionParams": "{\"id\": \"30bcd163-d777-4e01-8c63-ef9951849024\"}"
            }
        }
    ]
}
```

#### Expressions

Expressão para pegar o nome do site collection
```
substring(variables('varItemURL'),length(variables('varSiteRoot')),indexOf(substring(variables('varItemURL'),length(variables('varSiteRoot'))),'/'))

```

Expressão para pegar o ID da lista
```
split(split(uriQuery(variables('varItemURL')), '%7B')[1],'%7D')
```
