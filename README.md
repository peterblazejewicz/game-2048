# game-2048

Just board game clone/rework

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
