# Errors

## IonicSelectable is disabled or already closed

```
ERROR Error: Uncaught (in promise): IonicSelectable is disabled or already closed.
```

The error occurs when `close()` method is invoked while component is disabled or closed.  
**Note**: Ionic will only throw the error in development mode when running application with `ionic serve`.

### Solution

The error can be ignored as it will not happen in production mode. However, you can still prevent it by using `catch`

```
this.portComponent.close().catch(() => { });
```

or by checking `isEnabled` and `isOpened` fields.

```
if (this.portComponent.isEnabled && this.portComponent.isOpened) {
  this.portComponent.close();
}
```

## IonicSelectable is disabled or already opened

```
ERROR Error: Uncaught (in promise): IonicSelectable is disabled or already opened.
```

The error occurs when `open()` method is invoked while component is disabled or opened.  
**Note**: Ionic will only throw the error in development mode when running application with `ionic serve`.

### Solution

The error can be ignored as it will not happen in production mode. However, you can still prevent it by using`catch`

```
this.portComponent.open().catch(() => { });
```

or by checking `isEnabled` and `isOpened` fields.

```
if (this.portComponent.isEnabled && !this.portComponent.isOpened) {
  this.portComponent.open();
}
```

## IonicSelectable content cannot be scrolled

```
ERROR Error: Uncaught (in promise): IonicSelectable content cannot be scrolled.
```

The error occurs when `scrollToTop()` or `scrollToBottom()` method is invoked while component is not opened.  
**Note**: Ionic will only throw the error in development mode when running application with `ionic serve`.

### Solution

The error can be ignored as it will not happen in production mode. However, you can still prevent it by adding `catch`

```
this.portComponent.scrollToTop().catch(() => { });
```

or by checking `isOpened` field.

```
if (this.portComponent.isOpened) {
  this.portComponent.scrollToTop();
}
```
