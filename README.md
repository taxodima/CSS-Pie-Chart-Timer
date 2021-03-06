# CSS Pie Chart Timer

Create a pie chart timer/countdown using CSS and Javascript.

CSS Pie Chart Timer works fine on these browsers:
* IE 9
* Opera
* Firefox
* Chrome

The animation is done in Javascript as it's the only way to make it work properly with IE 9.

## Html

You need to use a specific html hierarchy with css classes to make it work.
* As a timer:

```html
    <div id='wrapper1'>
        <div class='pctTimer'>
            <div class='pctTrack'></div>
            <div class='pctPie'>
                <div class='pctSpinner pctSlice'></div>
                <div class='pctFiller pctSlice'></div>
            </div>
        </div>
    </div>
```
* As a countdown:

```html
    <div class='pctTimer pctCountdown'>
        <div class='pctTrack'></div>
        <div class='pctPie'>
            <div class='pctSpinner pctSlice'></div>
            <div class='pctFiller pctSlice'></div>
        </div>
    </div>
```

As you can see, the only difference between the 2 codes is the `pctCountdown` class.
The `<div class='pctTrack'></div>` block is also optional.

## CSS or LESS

There is two version available in the repo:
* a CSS file with some default values
* a LESS file with a mixin so you can easily use it in your project

## Usage

### CSS

To customize the way the timer/countdown renders, you need to include `pie_chart_timer.css`. After that, you can customize the timer by changing some css classes:
```css
#wrapper1 .pctTimer {
    font-size: 150px; /* The size (width and height) of the timer */
}

#wrapper1 .pctTrack,
#wrapper1 .pctPie .pctSlice {
    border: 0.05em solid #eee; /* size of the border (and track) and the color of the track */
    width: 0.9em;  /* 1em - (2*border-width) */
    height: 0.9em;  /* 1em - (2*border-width) */
}

#wrapper1 .pctPie .pctSlice {
    background: transparent; /* fill-color of the timer */
    border-color: #c0c0c0; /* border color of the timer */
}
```

### LESS

LESS is definitely the easiest way to use this small script. You only need to include `pie_chart_timer.mixin.less`. This will include basic css and provide you a mixin to easily set the size and style of your timer. Here is an example:

```css
#wrapper1 {
    .pie-chart-timer(200px, 10px, #c0c0c0, #eee, transparent);
}
```
The arguments are:

1. The size (width and height) of the timer
2. The size of the border (and track)
3. The color of the border [default: #c0c0c0]
4. The color of the track [default: transparent]
5. The fill-color of the timer [default: transparent]

Only the first two arguments are required.

## Example

You can see an example of the code in `example.html`. This page uses the `css` version of the code. But an example using less is also available in `styles.less`.