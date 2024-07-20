# Replace word under cursor with copied contents

`viwp` when the cursor is on a word.

1. `v` - enter visual mode
2. `iw` - select "in" word
3. `p` - put or paste copied contents

---

This is useful to replace a word with the copied contents.

1. Copy a word

```
Lorem ipsum dolor sit amet, consectetur adipiscing elit.
        ^
        |--- press ciw to copy the word ipsum
```

2. Paste the word

```
  Nunc quis leo vulputate.
         ^
         |--- place cursor here and press viwp
```

3. The result should be

```
  Nunc ipsum leo vulputate.
         ^
         |--- The word quis should be replaced with the copied word ipsum         
```



