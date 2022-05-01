# AdaUI (WIP)

AdaUI is a modern way to declare multi-threaded user interfaces for any platform.

It uses the [Observer pattern paradigm](https://en.wikipedia.org/wiki/Observer_pattern),and [State pattern](https://en.wikipedia.org/wiki/State_pattern), 
and all the Ada language OO and tasking features.


## Features

 * **Views** supports a declarative approach of its content, and are not driven by outside clients or programs
 * Each View owns his data structure representing the **state** of that view 
 * The view changes it’s appearance or the data displayed through a change in data of the **state** object
 * Updating data in the **State** object will trigger the update of the **View**
 * The **Business Model Unit** - or main program - only communicates with the View through the **state** object
 * **Multiple clients** (Business Model Units) may access the **State** object in a **multi-threaded way** in order to address/update the **same View** object
 * The **State** object may adapt/transform some of the incoming data into user-formated data, as for dates, physical units, ... ready to be displayed by the **View** 


## Design paradigm

Inspired by the state-management software design pattern as promoted by Apple for his new [SwiftUI framework](https://developer.apple.com/tutorials/swiftui).

This is the end of former MVC or MVVM design pattern!

Read this inspiring article [How MVVM devs get MVVM wrong in SwiftUI: From view model to state](https://swift2931.medium.com/how-mvvm-devs-get-mvvm-wrong-in-swiftui-a937a4268483) 


## Implementation Notes

 * **Views** are first-class _task objects_ 
 * **State** data is accessible through a _protected object_ 
 * **State Data definition** is declared in a specific unit
 * Updating data in the **State** object will call the registered _callback procedure_ linked to the *update entry* in the **View** _task object_
 * In order to communicate with a _protected object_, The **Business Model Unit** - or main program - has to be a _task object_.

 
