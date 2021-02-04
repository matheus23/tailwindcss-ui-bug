# Update

This issue occurs when using the `@tailwindcss/ui` plugin together with tailwindcss version 2.0. The 2.0 version made the ui plugin redundant, though, so just removing it will solve this issue. :+1:

## How to reproduce

```
$ yarn
$ yarn start
$ cat output.css | grep "\[object Object\]"
```

The generated output.css file contains e.g. this css:

```css
.form-textarea {
  appearance: none;
  background-color: #ffffff;
  border-color: #d2d6dc;
  border-radius: 0.375rem;
  padding-top: 0.5rem;
  padding-right: 0.75rem;
  padding-bottom: 0.5rem;
  padding-left: 0.75rem;
  font-size: 1rem;
  font-size: [object Object];
  line-height: 1.5;
}
```

For some reason the "font-size" property is duplicated, once with a `[object Object]` value.
