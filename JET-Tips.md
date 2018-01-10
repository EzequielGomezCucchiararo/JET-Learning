JET
------
Data-binding
------

##### Controler:

```javascript
self.name = ko.Observable([default-value])
self.students = ko.observableArray([
    { name: 'Max', class: 'Math' },
    { name: 'Tom', class: 'English' }, 
]);
self.show = ko.Observable(true);
self.bestStundent = {
    name: 'Tim',
    class: 'Spanish'
};
```

##### HTML:
```HTML
<!-- Data binding -->
<div><input data-bind="value: name"></input></div>
<div><span data-bind="text: name"></span></div>

<!-- 2-way data binding -->
<div><span data-bind="textInput: name"></span></div>

<!-- For each -->
<div data-bind="foreach: students">
    <p data-bind="name"></p>
    <p data-bind="class"></p>
</div>

<!-- If bindind -->
<div data-bind:"if: show">Look at me</div>
<div data-bind:"if: !show">Look at me! Ey! I'm talking to you! Hey</div>

<!-- Ifnot bindind -->
<div data-bind:"ifnot: !show">Look at me</div>

<!-- with bindind -->
<p data-bind="with: bestStudent">
    Name: <span data-bind="text: name"> </span>,
    Class: <span data-bind="text: class"> </span>
    <!-- How to access de parent -->
    IS the best?: <span data-bind="text: $parent.show"> </span>
</p>

<!-- Click binding (where addStudent is a function) -->
<button data-bind="click: addStundent">Add a student</button>

```