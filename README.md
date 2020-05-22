# @mesdocteurs/ngx-phone-number
A simple international telephone number input. Allows you to create a phone number field with country dropdown. 

This is a fork of [ngx-phone-number](https://github.com/diokhan/ngx-phone-number).
## Installation

To install this library, run:

```bash
$ npm install @mesdocteurs/ngx-phone-number --save
```

## Consuming your library

Once you have installed it you can import `PhoneNumberModule` from `@mesdocteurs/ngx-phone-number` in any application module. E.g.

```typescript
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';

import { AppComponent } from './app.component';

// Import your library
import { PhoneNumberModule } from '@mesdocteurs/ngx-phone-number';

@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    BrowserModule,

    // PhoneNumberModule module
    PhoneNumberModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```

Once it is imported, you can use `phone-number`:

```xml
<!-- app.component.html -->
<form name="sample-form" (ngSubmit)="submit()" #f="ngForm">
 <phone-number [(ngModel)]="model.phone_number" placeholder="Enter phone number" [maxlength]="20" [defaultCountry]="'in'" [required]="true" #phoneNumber="ngModel" name="phone_number" [allowedCountries]="['in', 'ca', 'us']"></phone-number>

  <div *ngIf="f.submitted && !phoneNumber.valid" class="help-block">Phone number is required and should be valid</div>
  <button type="submit">Submit</button>
</form>
```

### Attributes/Options:
       defaultCountryCode : An ISO 639-1 country code can be provided to set default country selected.
       placeholder: A placeholder text which would be displayed in input widget
       required: Indicates whether it's required or not
       disabled: Indicates whether it's disabled or not
       allowDropdown: Indicates whether to allow selecting country from dropdown
       allowedCountries: A list of countries (iso codes) that would get display in country dropdown. E.g. [allowedCountries]="['in', 'ca', 'us']" would only show Canada, India and US. If not provided, all the countries would get displayed.


## Authors
    * Original Author: nikhiln
    * Author: diokhan 
    * Author: Lucas Martinez
## License

MIT
