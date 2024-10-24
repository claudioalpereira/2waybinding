# 2waybinding
Two way binding with vanilla javascript

## Motivation
This example was born during a discussion about the needless use of current modern 

## Description
Two way data binding between the DOM and a javascript View Model.
This was born during a discussion about using modern frameworks on small projects.
As frameworks like Angular, React and KnockoutJS might be very useful tools on some cases, they are very often used with little or no considerations for their pros and cons.

## Databinding Model=>View
The global object _vm_ is a [Proxy](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Proxy), with implementations for the _get_, _delete_ and _refresh_ methods.
When a property is updated, these methods look for DOM elements with the _data-bind_ attribute and updates them with the new value.

Using a Proxy makes the _vm_ object to appear as a simple object to the user. This way he/she just needs to add and update properties like in any other object, without the need to use any setters/getters. 

## Databinding View=>Model
This is the easiest part. We just need to add an event listener to input DOM elements and update the _vm_ object with the new value. 

## Persistence
The _vm_ object is soted in localStorage and automatically retrieved from there at page load, making it persistent.

## Usage
We just need to add the _data-bind_ attribute to any element.
After this, updating input elements automatically updates the _vm_ object and updating the _vm_ object automatically updates all elements with that property in the _data-bind_ attribute. 

