# AdaUI

AdaUI is a modern way to declare multi-threaded user interfaces for any platform.

It uses the [Observer pattern paradigm](https://en.wikipedia.org/wiki/Observer_pattern)


## Features

 * **Views** supports a declarative approach of its content, and are not driven by outside clients or programs
 * Each View owns his data structure representing the **state** of that view 
 * The view changes it’s appearance or the data displayed through a change in data of the **state** object
 * Updating data in the **State** object will trigger the update of the **View**
 * The **Business Model Unit** - or main program - only communicates with the View through the **state** object
 * **Multiple clients** (Business Model Units) may access the **State** object in a **multi-threaded way** in order to address/update the **same View** object

## Design paradigm

Inspired by the View-Model software design pattern as found and proted by [Apple’s SwiftUI](https://developer.apple.com/tutorials/swiftui).


This is the end of former MVC design pattern!


## Implementation Notes

 * **Views** are first-class _task objects_ 
 * **State** data is accessible through a _protected object_ 
 * **State Data definition** is declared in a specific unit
 * Updating data in the **State** object will call the registered _callback procedure_ linked to the *update entry* in the **View** _task object_
 * In order to communicate with a _protected object_, The **Business Model Unit** - or main program - has to be a _task object_.

 
