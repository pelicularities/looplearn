[What is Unity doing under the hood???](https://forum.unity.com/threads/how-are-monobehavior-methods-get-implemented-inside.1152383/)

From Unity Game Development Cookbook, 2.2 Using Callbacks:
> In addition to these common methods, there are other methods that can be called depending on the circumstances. For example, if a script implements the `OnDestroy` method and the object is destroyed, the `OnDestroy` method will be called. Some methods will be called only if there’s a component of a specific type attached to the same game object. For example, if a script implements the method `OnBecameVisible` _and_ it has a `Renderer` component attached (such as a `SpriteRenderer` or `MeshRenderer`), the `OnBecameVisible` method will be called when the object comes into view of a camera.

> These methods aren’t overridden from any parent class. Unity examines the class, registers the fact that the class implements the method, and calls it directly.

> As a result, it doesn’t really matter if the methods are `public` or `private`; Unity will call them anyway. **As a matter of coding convention, many developers make the methods `private` to prevent other classes from calling them, since only the engine should be doing this.** (emphasis mine)

Lifecycle
- Awake
- Start
- Update
- LateUpdate
- OnDestroy