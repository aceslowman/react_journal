# JSX

JSX is a syntax extension to JavaScript. It is a preprocessor that allows JavaScript to use XML syntax, which greatly improves the readability of your code within React.

This allows you to write things that look and feel much more like html.

There are some immediate differences when writing with JSX and React, such as when creating html elements, where you would typically use the word "class", you now use "className". If you need to use a JavaScript expression within your JSX, you want to put curly braces around the expression.

## JSX and Injections

Never blindly trust user input. An injection attack is when a user inputs harmful information, that for example, might delete or alter database information. With that said, user input that is rendered by React via JSX is automatically escaped, preventing injection attacks automatically.
