<p align="center">
  <a href="https://github.com/sebastianmusial/SSCSS">
    <img src="sscss.png" width="300" alt="SSCSS logo"/>
  </a>
</p>
<p align="center">
  The light Sass library for managing your sizes and dimensions across breakpoints.
</p>

<p align="center">
	<strong>@Articles:</strong><br>
  <a href="https://medium.com/@sebastianmusia/how-to-style-modern-applications-in-a-simple-way-f93e95cd6962" target="blank">How to style modern applications in a simple way?</a>
</p>

## Installation

`npm i sscss`

Create your own `_core.scss` file with imports:
```
@import 'your-own-variables-and-settings';
@import '~sscss/sscss';
```
The file should be imported in all components where you will use Sass inheritances (@extend).

## Settings

In the settings, you can use your own breakpoints in the `px` unit.<br>
The `interpolation` key (boolean) in the map is optional and allows overwriting your global settings.

Example of breakpoints:

```
$mobile: 320px;
$tablet: 768px;
$desktop: 1024px;
```

Example of required settings:
```
$sscss-font-size: (
  'small':    ($mobile: 12px,  $tablet: 14px,  $desktop: 16px,  'interpolation': true),
  'medium':   ($mobile: 14px,  $tablet: 18px),
  'big':      ($mobile: 24px),
);

$sscss-dimension: (
  'small':    ($mobile: 4px,   $tablet: 8px,   $desktop: 16px,  'interpolation': true),
  'medium':   ($mobile: 8px,   $desktop: 32px),
  'big':      ($mobile: 16px,  $tablet: 32px,  'interpolation': false),
);
```

---
In the app you can use:

* the `@extend` approach allows you avoid styles generated outside your components.
* the `.class` approach allows you to generate small global utility classes. 
* the linear interpolation or standard breakpoint behaviors.

Example of optional global settings:
```
$sscss-font-interpolation: false;
$sscss-font-as-class: false;

$sscss-dimension-interpolation: false;
$sscss-dimension-as-class: false;
```

| Variable | Description | Default |
| --- | --- | --- |
| `$sscss-font-interpolation` | Settings for linear interpolation. | `false` |
| `$sscss-font-as-class` | Settings for `.class` or `@extend` approach. | `false` |
| `$sscss-dimension-interpolation` | Settings for linear interpolation. | `false` |
| `$sscss-dimension-as-class` | Settings for `.class` or `@extend` approach. | `false` |

## Usage

<details open><summary>Fonts</summary>

Name is generated based on a `$sscss-font-size` variable.

| Extensions | Class |
| --- | --- |
| `@extend %u-font-size--{name}` | `.u-font-size--{name}` | `.%u-font-size--{name}` |
</details>

<details open><summary>Paddings</summary>

Name is generated based on a `$sscss-dimension` variable.

| Extension | Class | Description |
| --- | --- | --- |
| `@extend %u-padding--{name}` | `.u-padding--{name}` |  Padding top, right, bottom, left |
| `@extend %u-padding--top-{name}` | `.u-padding--top-{name}` |  Padding top |
| `@extend %u-padding--right-{name}` | `.u-padding--right-{name}` |  Padding right |
| `@extend %u-padding--bottom-{name}` | `.u-padding--bottom-{name}` |  Padding bottom |
| `@extend %u-padding--left-{name}` | `.u-padding--left-{name}` |  Padding left |
| `@extend %u-padding--v-{name}` | `.u-padding--v-{name}` |  Padding top, bottom (vertical) |
| `@extend %u-padding--h-{name}` | `.u-padding--h-{name}` |  Padding right, left (horizontal) |
</details>

<details open><summary>Margins</summary>

Name is generated based on a `$sscss-dimension` variable.

| Extension | Class | Description |
| --- | --- | --- |
| `@extend %u-margin--{name}` | `.u-margin--{name}` | Margin top, right, bottom, left |
| `@extend %u-margin--top-{name}` | `.u-margin--top-{name}` | Margin top |
| `@extend %u-margin--right-{name}` | `.u-margin--right-{name}` | Margin right |
| `@extend %u-margin--bottom-{name}` | `.u-margin--bottom-{name}` | Margin bottom |
| `@extend %u-margin--left-{name}` | `.u-margin--left-{name}` | Margin left |
| `@extend %u-margin--v-{name}` | `.u-margin--v-{name}` | Margin top, bottom (vertical) |
| `@extend %u-margin--h-{name}` | `.u-margin--h-{name}` | Margin right, left (horizontal) |
| `@extend %u--margin--{name}` | `.u--margin--{name}` | Negative value of margin top, right, bottom, left |
| `@extend %u--margin--top-{name}` | `.u--margin--top-{name}` | Negative value of margin top |
| `@extend %u--margin--right-{name}` | `.u--margin--right-{name}` | Negative value of margin right |
| `@extend %u--margin--bottom-{name}` | `.u--margin--bottom-{name}` | Negative value of margin bottom |
| `@extend %u--margin--left-{name}` | `.u--margin--left-{name}` | Negative value of margin left |
| `@extend %u--margin--v-{name}` | `.u--margin--v-{name}` | Negative value of margin top, bottom (vertical) |
| `@extend %u--margin--h-{name}` | `.u--margin--h-{name}` | Negative value of margin right, left (horizontal) |
</details>

<details open><summary>Positions</summary>

Name is generated based on a `$sscss-dimension` variable.

| Extension | Class | Description |
| --- | --- | --- |
| `@extend %u-position--{name}` | `.u-position--{name}` | Position top, right, bottom, left |
| `@extend %u-position--top-{name}` | `.u-position--top-{name}` | Position top |
| `@extend %u-position--right-{name}` | `.u-position--right-{name}` | Position right |
| `@extend %u-position--bottom-{name}` | `.u-position--bottom-{name}` | Position bottom |
| `@extend %u-position--left-{name}` | `.u-position--left-{name}` | Position left |
| `@extend %u-position--v-{name}` | `.u-position--v-{name}` | Position top, bottom (vertical) |
| `@extend %u-position--h-{name}` | `.u-position--h-{name}` | Position right, left (horizontal) |
| `@extend %u--position--{name}` | `.u--position--{name}` | Negative value of position top, right, bottom, left |
| `@extend %u--position--top-{name}` | `.u--position--top-{name}` | Negative value of position top |
| `@extend %u--position--right-{name}` | `.u--position--right-{name}` | Negative value of position right |
| `@extend %u--position--bottom-{name}` | `.u--position--bottom-{name}` | Negative value of position bottom |
| `@extend %u--position--left-{name}` | `.u--position--left-{name}` | Negative value of position left |
| `@extend %u--position--v-{name}` | `.u--position--v-{name}` | Negative value of position top, bottom (vertical) |
| `@extend %u--position--h-{name}` | `.u--position--h-{name}` | Negative value of position right, left (horizontal) |
</details>

## Author

<table border="0">
  <tr>
    <td>
      <a href="https://github.com/sebastianmusial" style="color: white">
        <img src="https://github.com/sebastianmusial.png?s=150" width="150"/>
      </a>
    </td>
    <td>
      <p><strong>Sebastian Musiał</strong></p>
      <p><img src="data:image/svg+xml;base64,PD94bWwgdmVyc2lvbj0iMS4wIiA/PjwhRE9DVFlQRSBzdmcgIFBVQkxJQyAnLS8vVzNDLy9EVEQgU1ZHIDEuMS8vRU4nICAnaHR0cDovL3d3dy53My5vcmcvR3JhcGhpY3MvU1ZHLzEuMS9EVEQvc3ZnMTEuZHRkJz48c3ZnIGVuYWJsZS1iYWNrZ3JvdW5kPSJuZXcgMCAwIDQ4IDQ4IiBoZWlnaHQ9IjQ4cHgiIHZlcnNpb249IjEuMSIgdmlld0JveD0iMCAwIDQ4IDQ4IiB3aWR0aD0iNDhweCIgeG1sOnNwYWNlPSJwcmVzZXJ2ZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIiB4bWxuczp4bGluaz0iaHR0cDovL3d3dy53My5vcmcvMTk5OS94bGluayI+PGcgaWQ9IkV4cGFuZGVkIj48Zz48Zz48cGF0aCBkPSJNNDQsNDBINGMtMi4yMDYsMC00LTEuNzk0LTQtNFYxMmMwLTIuMjA2LDEuNzk0LTQsNC00aDQwYzIuMjA2LDAsNCwxLjc5NCw0LDR2MjRDNDgsMzguMjA2LDQ2LjIwNiw0MCw0NCw0MHogTTQsMTAgICAgIGMtMS4xMDMsMC0yLDAuODk3LTIsMnYyNGMwLDEuMTAzLDAuODk3LDIsMiwyaDQwYzEuMTAzLDAsMi0wLjg5NywyLTJWMTJjMC0xLjEwMy0wLjg5Ny0yLTItMkg0eiIvPjwvZz48Zz48cGF0aCBkPSJNMjQsMjkuMTkxTDYuNDU3LDE3Ljg0Yy0wLjQ2NC0wLjMwMS0wLjU5Ny0wLjkxOS0wLjI5Ny0xLjM4M3MwLjkxOS0wLjU5NiwxLjM4My0wLjI5N0wyNCwyNi44MDlMNDAuNDU3LDE2LjE2ICAgICBjMC40NjQtMC4yOTksMS4wODMtMC4xNjcsMS4zODMsMC4yOTdzMC4xNjcsMS4wODItMC4yOTcsMS4zODNMMjQsMjkuMTkxeiIvPjwvZz48Zz48cGF0aCBkPSJNNi4wMDEsMzRjLTAuMzIzLDAtMC42NDEtMC4xNTYtMC44MzMtMC40NDVjLTAuMzA3LTAuNDYtMC4xODMtMS4wOCwwLjI3Ny0xLjM4N2w5LTZjMC40Ni0wLjMwNywxLjA4MS0wLjE4MywxLjM4NywwLjI3NyAgICAgYzAuMzA3LDAuNDYsMC4xODMsMS4wOC0wLjI3NywxLjM4N2wtOSw2QzYuMzg0LDMzLjk0NSw2LjE5MSwzNCw2LjAwMSwzNHoiLz48L2c+PGc+PHBhdGggZD0iTTQxLjk5OSwzNGMtMC4xOSwwLTAuMzgzLTAuMDU1LTAuNTU0LTAuMTY4bC05LTZjLTAuNDYtMC4zMDctMC41ODQtMC45MjctMC4yNzctMS4zODcgICAgIGMwLjMwNi0wLjQ2LDAuOTI2LTAuNTg0LDEuMzg3LTAuMjc3bDksNmMwLjQ2LDAuMzA3LDAuNTg0LDAuOTI3LDAuMjc3LDEuMzg3QzQyLjY0LDMzLjg0NCw0Mi4zMjIsMzQsNDEuOTk5LDM0eiIvPjwvZz48L2c+PC9nPjwvc3ZnPg==" style="width: 18px; height: 18px; vertical-align: middle; margin: 0 5px 5px 0"> <a href="mailto:kontakt@sebastianmusial.pl">kontakt@sebastianmusial.pl</a></p>
      <p><img src="data:image/svg+xml;base64,PD94bWwgdmVyc2lvbj0iMS4wIiA/PjwhRE9DVFlQRSBzdmcgIFBVQkxJQyAnLS8vVzNDLy9EVEQgU1ZHIDEuMS8vRU4nICAnaHR0cDovL3d3dy53My5vcmcvR3JhcGhpY3MvU1ZHLzEuMS9EVEQvc3ZnMTEuZHRkJz48c3ZnIGhlaWdodD0iNTEycHgiIGlkPSLlvaLnirZfMl8xXyIgc3R5bGU9ImVuYWJsZS1iYWNrZ3JvdW5kOm5ldyAwIDAgNTEyIDUxMjsiIHZlcnNpb249IjEuMSIgdmlld0JveD0iMCAwIDUxMiA1MTIiIHdpZHRoPSI1MTJweCIgeG1sOnNwYWNlPSJwcmVzZXJ2ZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIiB4bWxuczp4bGluaz0iaHR0cDovL3d3dy53My5vcmcvMTk5OS94bGluayI+PGcgaWQ9IuW9oueKtl8yIj48Zz48cGF0aCBkPSJNNDg1Ljk4LDExMy4xNDFjLTE2LjkyMyw3LjUwNi0zNS4xMDksMTIuNTc4LTU0LjE5NywxNC44NTggICAgYzE5LjQ4LTExLjY3OSwzNC40NDUtMzAuMTcxLDQxLjQ5LTUyLjIwOGMtMTguMjM0LDEwLjgxNC0zOC40MywxOC42NjgtNTkuOTI1LDIyLjg5OWMtMTcuMjEzLTE4LjM0MS00MS43MzgtMjkuNzk5LTY4Ljg4LTI5Ljc5OSAgICBjLTUyLjExNCwwLTk0LjM2OCw0Mi4yNS05NC4zNjgsOTQuMzY0YzAsNy4zOTYsMC44MzQsMTQuNTk4LDIuNDQ0LDIxLjUwNWMtNzguNDI3LTMuOTM2LTE0Ny45NjItNDEuNTA0LTE5NC41MDQtOTguNTk3ICAgIGMtOC4xMjMsMTMuOTM3LTEyLjc3NywzMC4xNDYtMTIuNzc3LDQ3LjQ0MWMwLDMyLjczOSwxNi42NTksNjEuNjIzLDQxLjk4LDc4LjU0NmMtMTUuNDY5LTAuNDkxLTMwLjAyLTQuNzM1LTQyLjc0Mi0xMS44MDQgICAgYy0wLjAwOSwwLjM5NS0wLjAwOSwwLjc4OC0wLjAwOSwxLjE4OGMwLDQ1LjcyMSwzMi41MjksODMuODU5LDc1LjY5OCw5Mi41MzFjLTcuOTE4LDIuMTU2LTE2LjI1NSwzLjMxMS0yNC44NjEsMy4zMTEgICAgYy02LjA4MSwwLTExLjk5Mi0wLjU5My0xNy43NTUtMS42OTNjMTIuMDA5LDM3LjQ4OCw0Ni44NTgsNjQuNzczLDg4LjE1Myw2NS41MzNjLTMyLjI5NiwyNS4zMTItNzIuOTg1LDQwLjM5Ni0xMTcuMTk4LDQwLjM5NiAgICBjLTcuNjE3LDAtMTUuMTI4LTAuNDQ2LTIyLjUxMS0xLjMyYzQxLjc2MiwyNi43NzUsOTEuMzY1LDQyLjQsMTQ0LjY1NSw0Mi40YzE3My41NzQsMCwyNjguNDkzLTE0My43OTQsMjY4LjQ5My0yNjguNDk2ICAgIGMwLTQuMDkxLTAuMDkyLTguMTYtMC4yNzMtMTIuMjA4QzQ1Ny4zMzIsMTQ4LjY4NCw0NzMuMzMsMTMyLjA2NCw0ODUuOTgsMTEzLjE0MXoiIHN0eWxlPSJmaWxsLXJ1bGU6ZXZlbm9kZDtjbGlwLXJ1bGU6ZXZlbm9kZDtmaWxsOiMyQ0E3RTA7Ii8+PC9nPjwvZz48L3N2Zz4=" style="width: 18px; height: 18px; vertical-align: middle; margin: 0 5px 5px 0"> <a href="https://twitter.com/SebaMusial">@sebamusial</a></p>
    </td>
  </tr>
</table>
