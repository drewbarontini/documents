Sass Spacing
============

Use single-line spaces for separating style declarations.

```sass
.element
    // ...

.another-element
    // ...
```
    
Use single-line spaces for nested blocks.

```sass
.element
    // ...
    
    &:hover,
    &:focus
      // ...

    &:last-child
      // ...

    +respond-to()
      // ...
```

Use single-line spaces after loops (`@each`, `@for`).

```sass
@each $item in $list

  // ...

@for $i from 1 through length($list)

  // ...
```

**DO NOT** use a single-line space for conditionals.

```sass
.element
  // ...
  @if $something
    // ...
  @else
    // ...
```
