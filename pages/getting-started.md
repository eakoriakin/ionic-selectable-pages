# Getting started

Take a few steps to get started with Ionic Selectable.

## 1. Install the package

```
// Ionic 4.
npm install ionic-selectable@4 --save

// Ionic 3.
npm install ionic-selectable@3 --save
```

Once you have installed the package you can either jump right to a [source code example with a live demo](/basic-usage) or follow the steps below to configure Ionic Selectable module.

## 2. Import the module

Import `IonicSelectableModule` to your `app.module.ts` that is normally located in `src\app\app.module.ts`.

```
import { IonicSelectableModule } from 'ionic-selectable';

@NgModule({
  imports: [IonicSelectableModule]
})
export class AppModule { }
```

**Note:** Additionally, if you use Ionic 3+ you might be as well using lazy loaded pages. Check if your pages have a module file, for example, `home.module.ts`, and if they do then import `IonicSelectableModule` to each page module too.

```
import { IonicSelectableModule } from 'ionic-selectable';
import { HomePage } from './home';

@NgModule({
  declarations: [HomePage],
  imports: [IonicPageModule.forChild(HomePage), IonicSelectableModule]
})
export class HomePageModule { }

```

## 3. Add the component to template

```
<ion-item>
  <ion-label>Port</ion-label>
  <ionic-selectable
    item-content // Required for Ionic 3 only.
    [(ngModel)]="port"
    [items]="ports"
    [itemValueField]="'id'"
    [itemTextField]="'name'"
    [canSearch]="true"
    (onChange)="portChange($event)">
  </ionic-selectable>
</ion-item>
```

## 4. Configure the component

```
import { IonicSelectableComponent } from 'ionic-selectable';

class Port {
  public id: number;
  public name: string;
}

@Component()
export class HomePage {
  public ports: Port[];
  public port: Port;

  public constructor() {
    this.ports = [
      { id: 1, name: 'Tokai' },
      { id: 2, name: 'Vladivostok' },
      { id: 3, name: 'Navlakhi' }
    ];
  }

  public portChange(event: {
    component: IonicSelectableComponent,
    value: any
  }) {
    console.log('port:', event.value);
  }
}
```

## 5. Check out the docs

Take your time to go though the common [use cases](/basic-usage), features ([grouping](/grouping-items), [editing](/editing-adding-editing-and-deleting-items), [templates](/add-item-template), [forms](/form-control)) and API ([fields](/add-button-text-field), [methods](/add-item-method), [events](/on-add-item-event)) to see what Ionic Selectable is capable of.
