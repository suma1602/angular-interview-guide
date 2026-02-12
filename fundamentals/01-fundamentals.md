# Angular Fundamentals

## What is Angular?

Angular is a platform and framework for building client-side applications using HTML and TypeScript. Developed by Google, Angular provides a robust architecture for building applications that are maintainable and scalable.

## Components

Components are the building blocks of Angular applications. Each component encapsulates a part of the user interface and defines its behavior. A component is defined using a TypeScript class and decorated with the `@Component` decorator. Here’s an example:

```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'app-hello-world',
  template: '<h1>Hello, World!</h1>'
})
export class HelloWorldComponent { }
```

In this example, `HelloWorldComponent` is a simple component that displays "Hello, World!" on the page.

## Modules

Angular applications are modular and are organized into modules. A module is a class annotated with the `@NgModule` decorator. It groups related components, directives, pipes, and services together. Here’s an example of a basic module:

```typescript
import { NgModule } from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';
import { HelloWorldComponent } from './hello-world.component';

@NgModule({
  declarations: [HelloWorldComponent],
  imports: [BrowserModule],
  bootstrap: [HelloWorldComponent]
})
export class AppModule { }
```

This module defines `HelloWorldComponent` as part of its declarations and bootstraps it when the application starts.

## Services

Services in Angular are used to encapsulate business logic and data. They can be injected into components or other services. The `@Injectable` decorator is used to define a service. Here is an example:

```typescript
import { Injectable } from '@angular/core';

@Injectable({ providedIn: 'root' })
export class DataService {
  getData() {
    return ['Angular', 'React', 'Vue'];
  }
}
```

In this example, `DataService` is a singleton service provided throughout the application. It has a method `getData()` which returns an array of framework names.

## Conclusion

Understanding these Angular fundamentals is crucial for building efficient and effective applications. Components, modules, and services work together to form the framework that supports the development of scalable web applications.