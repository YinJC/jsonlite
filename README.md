# jsonlite
TeX JSON reader

# Interface

* `\readJson { tokenlist } { balanced text }`

    parse and keep JSON object in the tokenlist.

* `\readJsonValueById { tokenlist } { tokenlist(parsed JSON) } { text }`

    read value from a parsed JSON, which has "text" as its name. 
    
* `\showJsonValueById { tokenlist(parsed JSON) } { text }`

    remain value of a parsed JSON in the current stream.

# Example

```
\readJson{\json}{{"id":[1,2,3], "class":"foo", "data":{id:456}, "info":"Is this a text?"}}
\readJsonValueById{\jsonId}{\json}{"id"}     %=> expl3 sequence
\readJsonValueById{\jsonData}{\json}{"data"} %=> id:456

\readJson{\jsonJsonData}{{\jsonData}}
\showJsonValueById{\jsonJsonData}{"id"}      %=> 456
```

# Restriction

It doesn't distinguish number and string.
