Haml Spacing
============

To help keep some level of sanity, use the Layout/Root/Interior (`LRI`) method of spacing in `Haml` files:

Layout
------

**Layout** elements are grouped together and followed by a single-line space.

```haml
/ Layout
.row
  .cell.well
  
    / ...
    
/ Layout
.row
  .cell.well
    .g
      .g-b.g-b--1of2
  
        / ...
        
      .g-b.g-b--1of2
  
        / ...
```

Root
----

**Root** elements inside of **Layout** elements receive a single-line space after each element.

```haml
/ Layout
.row
  .cell.well
  
    / Root
    %ul.list
      %li.list-item Item
      %li.list-item Item
      %li.list-item Item
      %li.list-item Item
      
    / Root
    %ul.list
      %li.list-item Item
      %li.list-item Item
      %li.list-item Item
      %li.list-item Item
```

Interior
--------

**Interior** elements inside of **Root** elements receive a single-line space in between.

**Note**: If there is a _single_ **Interior** element inside of a **Root** element, you can opt to omit the space, only adding it once there are more **Interior** elements.

```haml
/ Layout
.row
  .cell.well
    .g
      .g-b.g-b--1of2
      
        / Root
        .card.card--a
          
          / Interior
          %ul.list
            %li.list-item Item
            %li.list-item Item
            %li.list-item Item
            %li.list-item Item
          
      / Layout
      .g-b.g-b--1of2
      
        / Root
        .card.card--a
        
          / Interior
          %ul.list
            %li.list-item Item
            %li.list-item Item
            %li.list-item Item
            %li.list-item Item
            
          / Interior
          %p This is another element.
          
          / Interior
          %a{ href: '#' } And a link!
```
