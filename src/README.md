Component outputs
=================

### Introduction

Although we're able to parametrize our components using _inputs_ we'd also like to introduce some events for our components.

Let's use `@Output()` and `EventEmitter`!

### Task

1. Add another _input_ for our component: _profileName_

2. Whenever the user clicks on the profile picture, we'd like to emit an event: _profilePictureClicked_. Introduce this as _output_. The payload of this event is the value of the _profileName_ input.

Example: `@Output() profilePictureClicked = new EventEmitter<???>()`

3. Modify the already existing `onPictureClicked()` method. Emit an event using the _profilePictureClicked_ output.

Example: `this.profilePictureClicked.emit(this.profileName)`

4. On the parent components class (_AppComponent_): introduce a callback method: `profileSelected(profileName: ???): void`

5. `console.log` the received value (for now).

4. Bind the _profilePictureClicked_ output of your _profile-picture_ component to your _profileSelected_ method of the _app_ component.

### HOWTOs

#### Example:

In the _app.component.html_:
```html
<app-profile-picture
  profileName="Mike"
  (profilePictureClicked)="profileSelected($event)">
  ...
</app-profile-picture>     
```
