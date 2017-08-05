# game-2048

Just board game clone/rework

![image](https://user-images.githubusercontent.com/14539/28998478-7eafb2bc-7a2c-11e7-92fd-769074a13525.png)

## Code

```html
<game-controls title="2048"></game-controls>
<game-container>
    <game-message slot="message"></game-message>
    <grid-container id="grid" slot="grids" size="[[size]]" cells="[[cells]]"></grid-container>
    <tile-container id="tiles" slot="tiles" size="[[size]]" cells="[[cells]]"></tile-container>
</game-container>
```

```html
<div id="heading">
    <h1 id="title">[[title]]</h1>
    <div id="scores">
        <game-score id="score" score="[[gameScore]]" title="Score"></game-score>
        <game-score id="best-score" score="[[bestScore]]" title="Best Score"></game-score>
    </div>
</div>
<div id="cta">
    <p id="intro">Join the numbers and get to the <strong>2048 tile!</strong></p>
    <a id="restart">New Game</a>
</div>
```

```html
<tile-container id="tiles" slot="tiles" style="--size:4;"></tile-container>
    <tile-cell value="0" style="--column:1; --row:1;"></tile-cell>
    <tile-cell value="2" visible="" style="--column:2; --row:1;"></tile-cell>
    <tile-cell value="0" style="--column:3; --row:1;"></tile-cell>
    ...
    <tile-cell value="0" style="--column:3; --row:4;"></tile-cell>
    <tile-cell value="512" visible="" style="--column:4; --row:4;"></tile-cell>
</tile-container>
```

## Setup

Declare a board size:

```js
size: {
    type: Number,
    value: 4
},
```

Declare a board setup (cells) as a property:

```js
cells: {
    type: Array,
    value: () => {
        return [
        [0,2,0,4],
        [32,16,2,0],
        [0,64,64,128],
        [256,0,0,512]
        ];
    }
}
```

Assign `size` and `cells` to `grid` and `tiles` via one-way binding:

```html
<grid-container id="grid" slot="grids" size="[[size]]" cells="[[cells]]"></grid-container>
<tile-container id="tiles" slot="tiles" size="[[size]]" cells="[[cells]]"></tile-container>
```

## Author

@peterblazejewicz
