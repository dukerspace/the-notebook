### Typescript

#### Union Type
-
(type1 | type2 | type3 | .. | typeN)
```
let code: (string | number)
```


#### Literal type
- [link](https://mariusschulz.com/blog/more-literal-types-in-typescript)
```
let resultConversion: 'as-number' | 'as-text'
```

#### Aliases type
```
type User {
    name: string,
    age: number
}
```