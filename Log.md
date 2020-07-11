### Understanding services in Blazor better

**Problem**: Each client should have one global modal component which:
+ Only allows a single instance to be displayed.
+ Is connected to the Flux store and can react to state changes.
+ Renders a defined layout specific to the calling component.
