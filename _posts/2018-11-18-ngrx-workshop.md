---
layout: post
title: 'Ngrx'
date: 2018-09-17 08:00:00
comments: true
published: true
categories: development, angular, rxjs, ngrx
---

# Common pitfalls and solutions
I'm working on an [example Angular application](https://github.com/Zolomon/ngrx-common-pitfalls-and-solutions) that showcases some common pitfalls and solutions when using NgRx.

# Angular Connect 2018 & 2017 videos
Here's a [link](https://www.youtube.com/channel/UCzrskTiT_ObAk3xBkVxMz5g/videos?sort=dd&view=0&flow=grid) to the videos from last year's conference. There were quite a few talks this year as well as useful slots where you could meet other people. I spent my time conversing with interesting fellows, but I did see some talks. Here's a list of the ones I did see and appreciate:
* [RxJS Schedulers in Depth](https://www.youtube.com/watch?v=S1eDh7MonbI),
* [Automating UI testing](https://www.youtube.com/watch?v=3_XvaSD_0xo),
* [You might not need NgRx](https://www.youtube.com/watch?v=omnwu_etHTY).

# NgRx Workshop
I also attended a workshop on NgRx. Whats follows below is a bullet point list that summarises the important content of the workshop.


* There is a new website for NgRX, take a look at their new [guide](https://ngrx.io/guide/).

* Always pass the root state type, e.g. `ApplicationState`, in `Store<ApplicationState>` in the constructor for injection
```typescript
// src/store/root.state.ts
export interface State {
    firstName: string;
    lastName: string;
}
```
```typescript
import { ApplicationStoreState } from '../../store';
@Component({
    selector: 'app-my-comp',
    templateUrl: './my.component.html'
})
class MyComponent {
    time$: Observable<number>;

    constructor(private store: Store<ApplicationStoreState.State>) {
        this.time$ = store.pipe(select(ApplicationQuery.getTime))l
    }
}
```
* Always derive from the root state, e.g. `ApplicationState` inside a selector query:
```typescript
// src/store/root.state.ts
export interface ApplicationState {
    contacts: ContactState
}
```
```typescript
// store/contacts/contacts.query.ts
export const (state: ApplicationState) => state.contacts.list
```
* Use namespaces for queries. This creates a single point for reusable query functions which can be shared and easily tested.
```typescript
export namespace ContactsQuery {
    export const getContacts = (state: ApplicationState) => state.contacts.list
}
```

* Use utility functions as sub-reducers inside your reducers to break down complexity
```typescript
export function reducer(state: State, action: Action) {
    switch(action.type) {
        case ACTION_1:
        case ACTION_2:
            return subReducer1And2(state, action)
        case ACTION_3: 
            return subReducer3(state, action)

        case default:
            return state
    }
}
```

* Use facade pattern to hide the store in the constructor, basically behind a service 
The components only have access to the exposing functions via the facade
```typescript
export class MyComponentFacade {
    constructor(private service1: FirstService, private service2: SecondService) { }

    public getFromFirstAndSecond() {
        return this.service1.getFirstValue() + this.service2.getSecondValue();
    }
}
```

* Return the same reference to unchanged objects while inside a reducer
See page 62 in the slides, always return the same reference to items that have not changed

* Use store-freeze during development to ensure that you are not accidentally breaking the NgRx contract.

* Router state `ngrx-router-store`
[router-store](https://github.com/ngrx/platform/tree/master/modules/router-store)

* For subscriptions of RxJS observables, use `takeUntil` inside `ngOnDestroy`.
Lookup npm take until destroy.
Use `extractRouterParams`.
```typescript
class Component {
    ngUnsubscribe$ = new BehaviourSubject();

    constructor() {

    //
        someSub = this.store.pipe(
            select(thing), 
            takeUntil(this.ngUnsubscribe)
        ).subscribe(x => {
            // Get things until subscribe
        });
    }

    ngOnDestroy() {
        this.ngUnsubscribe.next();
    }
}
```
[Read more about subscriptions here.](https://blog.angularindepth.com/angular-question-rxjs-subscribe-vs-async-pipe-in-component-templates-c956c8c0c794)

* Only store state that needs to be persisted between application sessions. 

* Marble tests are useful for unit testing Observables. See this [article](https://medium.com/city-pantry/handling-errors-in-ngrx-effects-a95d918490d9) for more information.

* How do you unit test a component that uses NgRx? Mock the store behind a facade in the component, unit test the reducer and the selectors separately

* JSBin is useful for making public small examples for JavaScript. See this [link to jsbin.com](https://jsbin.com).

* Error reporting & handling:
   1. [How to handle runtime errors in your Angular application](https://itnext.io/how-to-handle-your-run-time-errors-in-your-angular-application-8d72fefbf8a4),
   2. [Handling errors in NgRx Effects](https://medium.com/city-pantry/handling-errors-in-ngrx-effects-a95d918490d9),
   3. [Global error handling with Angular and NgRx](https://medium.com/calyx/global-error-handling-with-angular-and-ngrx-d895f7df2895), 
Basically, capture errors inside @Effects, for side-effects like when you're talking to a REST endpoint, and use that to trigger a toast.

<div style="padding-bottom: 5px"></div>

* [When to unsubscribe](https://stackoverflow.com/questions/38008334/angular-rxjs-when-should-i-unsubscribe-from-subscription)

* [Switchmap bugs](https://blog.angularindepth.com/switchmap-bugs-b6de69155524)

* Ngrx multiple actions effects: 
    1. [https://vsavkin.com/](https://vsavkin.com/)
    2. [https://blog.nrwl.io/ngrx-patterns-and-techniques-f46126e2b1e5](https://blog.nrwl.io/ngrx-patterns-and-techniques-f46126e2b1e5)
<div style="padding-bottom: 5px"></div>
* Use flags in your store if you need to be notified when an action has completed.
Like `{loaded: true}`

* [How to use effects](https://blog.angularindepth.com/start-using-ngrx-effects-for-this-e0b2bd9da165)
