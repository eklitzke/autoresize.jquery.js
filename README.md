This contains a few changes from the jQuery autoresize plugin from
[James Padolsey](http://james.padolsey.com/javascript/jquery-plugin-autoresize/);
these changes are based off of version 1.04 of his plugin. The changes are:

* There was a bug where if a text field started out larger than the maximum
  textarea size, it would never get resized. So, for instance, if you had passed
  in `limit` as 1000 (the default), but you initialized the textarea with 1200px
  worth of text, the textarea would stay tiny (instead of resizing to 1000px).
* In James' version, the resizing doesn't happen until there's activity in the
  textarea (e.g. on a keypress), so if you wanted to immediately resize the
  textarea you had to send a keypress event to the textarea object. I though
  this was weird, so there's now a `resizeImmediately` parameter you can pass in
  to toggle whether or not the textarea should immediately be resized; this
  parameter defaults to `true`.
* There's a small optimization that can cause less Javascript to execute in the
  resize callback when typing in very large textareas (larger than the `limit`).
