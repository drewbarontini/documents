MVCSS Comment Template
======================

It's sometimes useful to add the expected markup for your module as a comment block at the top of the file. Since we always us Haml, that's the format used.

```sass
// *************************************
//
//   Component/Structure
//   -> Description
//
// -------------------------------------
//   Template (Haml)
// -------------------------------------
//
// .element[.element--modifier|modifier](.is-state)
//   [%p].element-scaffolding Content
//
// *************************************
```

In practice, this is what it would look like:

```sass
// *************************************
//
//   Dropdown
//   -> Dropdown menus
//
// -------------------------------------
//   Template (Haml)
// -------------------------------------
//
// .dropdown[.dropdown--s](.is-active)
//   %a.dropdown-btn{href: '#'} Button
//   %ul.dropdown-menu
//     %li.dropdown-item(.is-active)
//       %a.dropdown-link{href: '#'} Item
//     %li.dropdown-item
//       %a.dropdown-link{href: '#'} Item
//
// *************************************
```
