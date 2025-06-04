# EventSignal

TypeScript event emitter for a single event type, designed for this pattern:

```ts
events: {
    click: new EventSignal<MouseEvent>()
}


let eventListener = events.click.addListener(() => {...})

// events dispatching
events.click.dispatch(new MouseEvent());

// we can remove event listeners with
eventListener.remove()
```

Supports event priority:
```ts
addListener(listener, priority: number = 0)
```

It's designed to work well with native events including stopPropagation handling