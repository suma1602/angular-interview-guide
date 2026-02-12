# Complete Guide to Angular Components

Angular components are the building blocks of Angular applications. They encapsulate data, HTML, and behavior, allowing for modular architecture.

## 1. Lifecycle Hooks
Lifecycle hooks are a way to tap into key events in a component's life. The main hooks are:

- **ngOnInit**: Invoked once the component is initialized.
- **ngOnChanges**: Called when any bound input properties change.
- **ngOnDestroy**: Clean-up just before the component is destroyed.

### Example:
```typescript
import { Component, OnInit, OnDestroy, Input } from '@angular/core';

@Component({
  selector: 'app-example',
  templateUrl: './example.component.html'
})
export class ExampleComponent implements OnInit, OnDestroy {
  @Input() data: string;

  ngOnInit() {
    console.log('Component initialized!');
  }

  ngOnDestroy() {
    console.log('Component will be destroyed!');
  }
}
```

## 2. Component Communication
Components can communicate in three ways:
- **Input and Output decorators**: For parent-child communication.
- **Service**: For sibling communication.
- **EventEmitter**: To emit events to parent components.

### Example:
**Child Component:**
```typescript
import { Component, Output, EventEmitter } from '@angular/core';

@Component({
  selector: 'child-component',
  template: `<button (click)="notifyParent()">Notify Parent</button>`
})
export class ChildComponent {
  @Output() notify: EventEmitter<string> = new EventEmitter();

  notifyParent() {
    this.notify.emit('Data from Child');
  }
}
```
**Parent Component:**
```html
<child-component (notify)="onNotify($event)"></child-component>
```

## 3. Styling Components
Components can be styled in three ways:
- Inline styles
- Component styles
- Global styles

### Example:
```typescript
@Component({
  selector: 'app-styled',
  templateUrl: './styled.component.html',
  styles: [':host { display: block; background: lightgray; }']
})
export class StyledComponent {}
```

## 4. Best Practices
1. **Keep components small and focused**: A component should do one thing.
2. **Use one-way data binding whenever possible**: It ensures unidirectional data flow.
3. **Leverage Angular’s built-in directives**: Like `*ngFor`, `*ngIf` for efficiency.
4. **Avoid logic in templates**: Keep templates clean by handling logic in the TypeScript code.

### Conclusion
Angular components are crucial for building scalable applications. Utilize lifecycle hooks, effective communication strategies, proper styling, and best practices to create robust Angular applications.