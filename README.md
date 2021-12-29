### For 2-way binding

Use ref, not reactive, as

```
  @update:modelValue="(x) => var=x"
  :value="x"
```

equals

```
  v-model="x"
```

but does not equal

```
  @update:modelValue="(x) => reass9(var, x)"
  :value="x"
```
