MVCSS Comment Template
======================

It's sometimes useful to add the expected markup for your module as a comment block at the top of the file. Since we always us Haml, that's the format used.

```sass
// *************************************
//
//   Component/Structure
//   -> Description
//
//   Dependecies: .element
//
// -------------------------------------
//   Template (Haml)
// -------------------------------------
//
// .has-context
//
// .element[modifier|modifier another|another](state|state)
//
//   %p.element-scaffolding
//
// *************************************
```

In practice, this is what it would look like:

```sass
// *************************************
//
//   Dropdown
//   -> Hidden menus
//
//   Dependecies: .list
//
// -------------------------------------
//   Template (Haml)
// -------------------------------------
//
// .has-dropdown
//
// .dropdown[s](active)
//
//   %a.dropdown-btn
//
//   %ul.dropdown-menu
//     %li.dropdown-item(active)
//       %a.dropdown-link
//
// *************************************
```
