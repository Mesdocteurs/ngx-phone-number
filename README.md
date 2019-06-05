# ngx-phone-number
A simple international telephone number input. Allows you to create a phone number field with country dropdown. 

This is a fork of [ngx-international-phone-number](https://github.com/nikhiln/ngx-international-phone-number), asjusted to use smaller [libphonenumber-js](https://github.com/catamphetamine/libphonenumber-js) instead of Google's lib.

## Installation

To install this library, run:

```bash
$ npm install ngx-phone-number --save
```

## Consuming your library

Once you have installed it you can import `PhoneNumberModule` from `ngx-phone-number` in any application module. E.g.

```typescript
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';

import { AppComponent } from './app.component';

// Import your library
import { PhoneNumberModule } from 'ngx-phone-number';

@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    BrowserModule,

    // InternationalPhoneNumberModule module
    PhoneNumberModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```

Once it is imported, you can use `international-phone-number`:

```xml
<!-- app.component.html -->
<form name="sample-form" (ngSubmit)="submit()" #f="ngForm">
 <international-phone-number [(ngModel)]="model.phone_number" placeholder="Enter phone number" [maxlength]="20" [defaultCountry]="'in'" [required]="true" #phoneNumber="ngModel" name="phone_number" [allowedCountries]="['in', 'ca', 'us']"></international-phone-number>

  <div *ngIf="f.submitted && !phoneNumber.valid" class="help-block">Phone number is required and should be valid</div>
  <button type="submit">Submit</button>
</form>
```

### Attributes/Options:
       defaultCountryCode : An ISO 639-1 country code can be provided to set default country selected.
       placeholder: A placeholder text which would be displayed in input widget
       required: Indicates whether it's required or not
       allowDropdown: Indicates whether to allow selecting country from dropdown
       allowedCountries: A list of countries (iso codes) that would get display in country dropdown. E.g. [allowedCountries]="['in', 'ca', 'us']" would only show Canada, India and US. If not provided, all the countries would get displayed.


## Authors
    * Original Author: nikhiln
    * Author: diokhan 
## License

MIT
