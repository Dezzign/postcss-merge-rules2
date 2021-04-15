# [postcss][postcss]-merge-rules2

> Merge CSS rules with PostCSS ihherited from postcss-merge-rules which already deprecated. Only different is postcss-merge-rules2 will merge the css even if 2 css is not nearby. This action may bring some risk which mentioned in postcss-merge-rule issue discussion, but most of time is safed to use it and we still have requirement to use this feature becuase we know what we are doing.


## Install

With [npm](https://npmjs.org/package/postcss-merge-rules2) do:

```
npm i git+https://github.com/gdvyas/postcss-merge-rules2.git --save-d
```

## Differenet betten postcss-merge-rule and postcss-merge-rule2
#### Input
```css
a {
    color: blue;
    font-weight: bold
}
b {
    color: red
}
p {
    color: blue;
    font-weight: bold
}
```

#### Output
    postcss-merge-rules: output same as input

```css
postcss-merge-rules2: 
a,p {
    color: blue;
    font-weight: bold
}
b {
    color: red
}
```

## Below is postcss-merge-rule readme and still useful

## Examples

This module will attempt to merge *adjacent* CSS rules:

### By declarations

#### Input

```css
a {
    color: blue;
    font-weight: bold
}

p {
    color: blue;
    font-weight: bold
}
```

#### Output

```css
a,p {
    color: blue;
    font-weight: bold
}
```

### By selectors

#### Input

```css
a {
    color: blue
}

a {
    font-weight: bold
}
```

#### Output

```css
a {
    color: blue;
    font-weight: bold
}
```

### By partial declarations

#### Input

```css
a {
    font-weight: bold
}

p {
    color: blue;
    font-weight: bold
}
```

#### Output

```css
a,p {
    font-weight: bold
}

p {
    color: blue
}
```

## Usage

See the [PostCSS documentation](https://github.com/postcss/postcss#usage) for
examples for your environment.

## Contributing

Pull requests are welcome. If you add functionality, then please add unit tests
to cover it.

## License

MIT © [Ben Briggs](http://beneb.info)

[ci]:      https://travis-ci.org/ben-eb/postcss-merge-rules
[deps]:    https://gemnasium.com/ben-eb/postcss-merge-rules
[npm]:     http://badge.fury.io/js/postcss-merge-rules
[postcss]: https://github.com/postcss/postcss
