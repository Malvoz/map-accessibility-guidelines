# Focus

Use a focus to enhance the experience for all users and a great practice to use. **Do not** remove the focus for any users!

The focus is a way to make your user experience similar for *many* different visitors is to provide visual focus indication for keyboard focus.

* The default focus may need to be changed if it cannot be seen *clearly* by a user. Sometimes adding a border to the CSS, including changing the color goes a long way. For example:  
```css
:focus {
	border: 2px dotted #000;
}
```
* Set the hover and focus CSS transitions equal to each other as the hover and focus should have the *same functionality* throughout an application. For example:
```css
:hover, :focus {
	/* CSS goes here */
}
```

## Outline
Do **_not_** use the following CSS in your website, as screen readers will be unable to navigate throughout your site:

```css
/* DO NOT use the following code in your CSS */
a {
	outline: 0;
}
a {
	outline:none;
}
```