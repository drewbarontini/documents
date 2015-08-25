Today I Learned
===============

General
-------

If you use `rsync` for deployment, and you're repeatedly asked to enter your password, you have to paste your public key into `.ssh/authorized_keys` on your server.

***

If you select text in Chrome, you can click and drag the text into the tab bar, which will open a new tab and search Google with that selected text.

JavaScript
----------

JavaScript has an `every` ([MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/every)) method on Arrays that accepts a callback function to check if each element in the array passes that validation and then returns a Boolean, if so.

```javascript
[0, 1, 2, 3, 4].every( function( element, index, array ) {
  return element < 5;
} ); // returns true
```

jQuery
------

If you are using nested objects and `$.extend()`, pass `true` as the first parameter to make a recursive copy.

***

The `$.ajax` method returns a Promise, so you can do something like this:

```coffeescript
myFunction = ->
  # ...
  
  call = $.ajax({
    # ...
  })
  
  return call
  
myFunction().done( (data) ->
  # ...
)
```

Haml
----

Putting `-#` (Ruby comment) and nesting inside of it will comment out an entire block of Haml without having to comment out each line individually.

```haml
-#
  %h1 This Block
  %p Is now commented out.
```

OS X
----

`Command+Option+H` hides all windows but the currently focused one.

Ruby & Ruby on Rails
--------------------

In the console, you can type `_` as the previous command.

```
User.find(1)
u = _
```

***

In Haml, to add punctuation after a `link_to`:

```haml
# Option 1:
= link_to('Text', '#') + '.'

# Option 2:
= succeed '.' do
  = link_to 'Text', '#'
```

***

If you have a merge conflict with `db/schema.rb`, you can just run `rake db:migrate` to clear up the file.

***

In Ruby, you can store regular expressions in variables like so:

```ruby
regex = '^Hello'

file.gsub(/#{ regex }/, 'Goodbye')
```

Terminal/iTerm on OS X
----------------------

`CTRL+R` does a reverse search on the previous commands you've entered.

***

`xargs` allows you to run another command on a set of arguments (e.g. `git tag -l | xargs git tag -d`)

***

Command-clicking on an `http://` link will open that link in your default browser.

Vim
---

`:1,20bd` with `20` being the highest-numbered buffer will clear all buffers.

***

`c/` will change up and until the search term.
