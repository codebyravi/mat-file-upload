# Angular Material File Upload [![Build Status](https://travis-ci.org/bjsawyer/mat-file-upload.svg?branch=master)](https://travis-ci.org/bjsawyer/mat-file-upload)

This tool is a simple & configurable file upload component for use with [Angular Material](https://material.angular.io/).

Live Demo: https://bjsawyer.github.io/mat-file-upload/

<img width="552" alt="Screen Shot 2019-04-24 at 8 40 27 PM" src="https://user-images.githubusercontent.com/8974594/56702301-472f7000-66d1-11e9-9480-1e5145ce7dde.png">

## Prerequisites

In order to use `mat-file-upload` in your app, you must have the following dependencies installed:

- [Angular](https://angular.io/)
- [Angular Material](https://material.angular.io/)
- [Material Icons](https://material.angular.io/guide/getting-started#step-6-optional-add-material-icons)

## Usage

1. Install package from npm (`npm i mat-file-upload`).
2. Add `MatFileUploadModule` to your module's imports, like so:

```typescript
@NgModule({
  declarations: [AppComponent],
  imports: [
    ...
    MatFileUploadModule,
    ...
  ],
  providers: [],
  bootstrap: [AppComponent],
})
export class AppModule {}
```

3. Add the element to your template, like so:

Basic:

<!-- prettier-ignore -->
```html
<mat-file-upload></mat-file-upload>
```

Advanced:

<!-- prettier-ignore -->
```html
<mat-file-upload
  [labelText]="'Select a file (or multiple) to upload:'"
  [allowMultipleFiles]="true"
  [showUploadButton]="true"
  (uploadClicked)="onUploadClicked($event)"
  (selectedFilesChanged)="onSelectedFilesChanged($event)">
</mat-file-upload>
```

## Options

### `@Input()` Properties

| Directive              | Type      | Description                                                                  | Default Value    |
| ---------------------- | --------- | ---------------------------------------------------------------------------- | ---------------- |
| `[allowMultipleFiles]` | `boolean` | True/false representing whether the user can select multiple files at a time | false            |
| `[labelText]`          | `string`  | The text to be displayed for the file upload label                           | "Select file(s)" |
| `[showUploadButton]`   | `boolean` | True/false representing whether the "Upload" button is shown in the DOM      | true             |

### `@Output()` Properties

| Directive                | Type                     | Description                                                                                  |
| ------------------------ | ------------------------ | -------------------------------------------------------------------------------------------- |
| `(uploadClicked)`        | `EventEmitter<FileList>` | Event handler that emits the list of selected files whenever the "Upload" button is clicked  |
| `(selectedFilesChanged)` | `EventEmitter<FileList>` | Event handler that emits the list of selected files whenever the user changes file selection |
