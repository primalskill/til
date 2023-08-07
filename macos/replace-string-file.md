# Replace String in a File

Use `sed`: 


```shell
sed -i '' "s/old string/new string/g" myfile.txt
```

On Linux use:

```shell
sed -i 's/old string/new string/g' myfile.txt
```

_NOTE: Replacements are case sensitive._

--- 

#### Refs

- Docs: https://linux.die.net/man/1/sed
