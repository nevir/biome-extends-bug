# biome-extends-bug

Biome's `"extends"` configuration clause appears to not work for already-extended configuration files.

## Example Failure (doublly-nested config)

> [!NOTE]
> That this example has configuration chained as:
> 
> `biome.json` extends `parent.json` extends `grandparent.json`

Run the following:

```
cd ./examples/doubly-nested && yarn run biome check example.json
```

And observe that it is unable to parse the file:

```
Expected a property but instead found '// Recommendations'
…
```

## Example Success (singly-nested config)

> [!NOTE]
> That this example has configuration chained as:
> 
> `biome.json` extends `parent.json`

Observe that biome is able to correctly parse the example file in this scenario:

```
cd ./examples/singly-nested && yarn run biome check example.json
```

## Example Success (config w/o extends)

> [!NOTE]
> That this example has no configuration extension

Observe that biome is able to correctly parse the example file in this scenario:

```
cd ./examples/no-nesting && yarn run biome check example.json
```


