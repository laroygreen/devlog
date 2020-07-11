### Understanding services in Blazor better
July 11, 2020 A.M.

#### Problem

A modal component which:
+ Only allows a single instance to be displayed.
+ Is connected to the Flux store and can react to state changes.
+ Renders a defined layout specific to the calling component.

#### Solution

Refactor `BlazorModal.ModalService` to manage scoped instances of `Modal` components with `Add` and `Get` methods. I chose this approach as I started to understand better the order in which Blazor builds the render tree as well as how Javascript interop works when used in a singleton (A call gets made to a Javascript function but the function that is called can be on any of the clients). 

Having a scoped list of `Modal` instances allows passing an `Id` as a `CascadingValue` which can then retrieve a reference to the modal component via `BlazorModal.ModalService.Get`. An ElementReference cannot be cascaded directly as cascading happens before the render tree is built (ElementReference is null until after render).
