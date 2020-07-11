### Understanding services in Blazor better
July 11, 2020 A.M.

#### Problem

A modal component which:
+ Only allows a single instance to be displayed.
+ Is connected to the Flux store and can react to state changes.
+ Renders a defined layout specific to the calling component.

#### Solution

Refactor `BlazorModal.ModalService` to manage scoped instances of `Modal` components with `Add` and `Get` methods.
