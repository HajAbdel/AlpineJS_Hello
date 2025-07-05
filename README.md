# AlpineJS_Hello
Hello Alpine JS

## add this to <head>

```html
<script src="//unpkg.com/alpinejs" defer></script>
```

## x-data

- define a private var

```html
<div x-data="{ count: 0 }">
  <button @click="count++">+</button>
  <span x-text="count"></span>
</div>
```

## x-text : 

- Replace inner text with value

```html
<span x-text="message"></span>
```

## x-if

- Conditionally render (not just show/hide)
- Only adds the element to the DOM if loggedIn is true.
- Different from x-show, which hides it with CSS.

```html
<template x-if="loggedIn">
  <p>Welcome back!</p>
</template>
```

## x-for

- Loop through a list

```html
<ul x-data="{ items: ['One', 'Two', 'Three'] }">
  <li x-for="item in items" x-text="item"></li>
</ul>
```

## x-show

- Show/hide elements (via display CSS)
- Only shows the <div> when open == true.

```html
<div x-data="{ open: false }">
  <button @click="open = !open">Toggle</button>
  <div x-show="open">This is visible when open is true</div>
</div>
```

## x-transition

- Add simple animations : smooth transition when showing/hiding.

```html
<div x-show="open" x-transition>
  Fades in/out with animation
</div>
```

## Handle events

- @click : when click

```html
<button @click="count++">Click me</button>
```

## x-model

- Auto sync input with var

```html
<div x-data="{ name: '' }">
  <input x-model="name">
  <p>Hello <span x-text="name"></span></p>
</div>
```

## x-effect

- Run code whenever a variable changes
- Alpine listen to all vars used in x-effect & executes code automatically when count changes.

```html
<div x-data="{ count: 0, doubled: 0 }" x-effect="doubled = count * 2">
  <button @click="count++">+</button>
  <p>Count: <span x-text="count"></span></p>
  <p>Doubled: <span x-text="doubled"></span></p>
</div>

```

## x-init 

- Runs code once when the component is initialized.

```html
<div x-data="{ message: '' }" x-init="message = 'Hello from Alpine!'">
  <p x-text="message"></p>
</div>
```
