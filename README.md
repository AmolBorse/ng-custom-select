# Angular Custom Dropdown

> Create customizable Angular2+ dropdown/datalist with your own styles.

## Install

```
npm install ng-custom-select
```

## Usage

Import `DropdownModule` into your module

your-module.module.ts
```
import { DropdownModule } from 'ng-custom-select';

@NgModule({
  imports: [
    ...
    DropdownModule,
  ],
```
Import `Settings` interface into your component class for providing settings configuration of your dropdown.

your-component.component.ts
```
import { Settings } from 'ng-custom-select';
...
export class YourComponent {
  settings: Settings;
}
```

Settings interface
```
interface Settings { 
    output?: string; //what you want in output, 'value' or 'index' of selected item. Field is optional and Default is 'index'
    isDatalist?: boolean; //true if you want dropdown to be act as Datalist. Field is optional and Default is false
    caretClass?: string; //CSS class for your Caret icon, it can be a sprite class or glyphicon or font icon class. This is also optional and Default icon applies in that case.
}
```


It takes three inputs and emits change event to parent component.
Inputs:
```
options: Array<any>; //Required | "Array of numbers or string, these values will be displayed as options in dropdown list";
selected: number; //Optional | "Index of element of options array that will be default selected in dropdown, Default is 0";
settings: Settings; //Optional | "Settings for the dropdown"
```

Now you can use dropdown selector in your component template as shown below

your-component.component.html
```
<ng-dropdown [selected]="selected" [options]="options" [settings]="settings" (onchange)="changeValue($event)"></ng-dropdown>
```

It emits onchange event to the parent component, So there should be an event handler in parent component class. $event omits a 'value' or 'index' depending upon settings input.
 
## License

MIT © [Uttam Pratap Choudhary](//https://github.com/uttamchoudhary)