# Grouping items
## Demo
  * [Grouping items](https://stackblitz.com/edit/ionic-selectable-grouping?file=app/pages/home/home.html)

## Example

View:

    <ion-item>
      <ion-label>Port</ion-label>
      <ionic-selectable
        [(ngModel)]="port"
        itemValueField="id"
        itemTextField="name"
        groupValueField="country.id"
        groupTextField="country.name"
        [items]="ports">
        <ng-template ionicSelectableGroupTemplate let-group="group">
          {{group.text}}
        </ng-template>
      </ionic-selectable>
    </ion-item>
