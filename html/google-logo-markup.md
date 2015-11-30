[Google Logo Markup](http://googlewebmastercentral.blogspot.com/2013/05/using-schemaorg-markup-for-organization.html)
=====================================================================================================================

HTML
----

```html
<div itemscope itemtype="http://schema.org/Organization">
  <a itemprop="url" href="http://www.example.com/">
    <img itemprop="logo" src="http://www.example.com/logo.png" />
  </a>
</div>
```

Haml
----

```haml
%div(itemscope itemtype="http://schema.org/Organization")
  %a(itemprop="url" href="http://www.example.com/")
    %img(itemprop="logo" src="http://www.example.com/logo.png")
```
