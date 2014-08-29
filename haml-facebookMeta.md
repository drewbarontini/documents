Facebook Meta
=============

To get proper sharing of your site on Facebook, you'll need to add Open Graph tags (`meta` tags) in the `head` of your HTML document.

```haml
%meta{ :property => 'og:title', :content => 'Article/Site Title' }
%meta{ :property => 'og:site_name', :content => 'Site Name' }
%meta{ :property => 'og:url', :content => 'http://www.example.com' }
%meta{ :property => 'og:description', :content => 'Site Description' }
%meta{ :property => 'og:image', :content => 'http://www.example.com/images/og.png' }
```
