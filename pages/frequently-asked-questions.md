# Frequently asked questions

## Why do I get error `Can't bind to 'items' since it isn't a known property of 'ionic-selectable'`?

The error occurs when `IonicSelectableModule` isn't imported to your app or page module.

First, check that `IonicSelectableModule` is imported to your `app.module.ts` that is normally located in `src\app\app.module.ts`.

```
import { IonicSelectableModule } from 'ionic-selectable';

@NgModule({
  imports: [
    IonicSelectableModule
  ]
})
export class AppModule { }
```

Then if you use Ionic 3+ you might be as well using lazy loaded pages. Check if your pages have a module file, for example, `home.module.ts`, and if they do then import `IonicSelectableModule` to each page module too.

```
import { IonicSelectableModule } from 'ionic-selectable';
import { HomePage } from './home';

@NgModule({
  declarations: [
    HomePage
  ],
  imports: [
    IonicPageModule.forChild(HomePage),
    IonicSelectableModule
  ]
})
export class HomePageModule { }
```

## What is the best way to handle a large amount of items?

Loading time and responsiveness of the component might get rather slow, when dealing with a lot of items, e.g. a 1000 or more.
There are two ways to tackle it.

**Async search**

In this case no items are loaded and displayed initially. Items will be added while user is typing to search.  
See [demo](/ionic-selectable-docs/search-items-asynchronously).

**Infinite scroll**

This approach relies on Ionic [InfiniteScroll](https://ionicframework.com/docs/api/components/infinite-scroll/InfiniteScroll/).  
Initially only the first bunch of items is loaded and displayed, for example we can show only the first 20 items.  
Then more items is loaded bunch by bunch while user is scrolling down.  
See [demo](/ionic-selectable-docs/infinite-scroll).

**Virtual scroll**

This approach relies on Ionic [VirtualScroll](https://ionicframework.com/docs/api/components/virtual-scroll/VirtualScroll/).  
See [demo](/ionic-selectable-docs/virtual-scroll).

## Why the component does not appear and only label is visible?

Versions from [2.7.0](https://github.com/eakoriakin/ionic-selectable/releases/tag/2.7.0) to `3.*.*` require Ionic `item-content` attribute.
Version `4.*.*` doesn't need it.

```
<ionic-selectable item-content>
</ionic-selectable>
```
