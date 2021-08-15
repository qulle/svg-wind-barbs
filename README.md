# SVG Wind Barbs
SVG wind barbs for speeds from 0 to 190 knots. The SVG files uses the PATH element and is suitable for adding to Google Maps or OpenLayers.

## Demo sprite
![Demo sprite](demo-sprite-210815.svg?raw=true "Demo sprite")

## Knots to m/s ranges
| Knots | m/s (low) | m/s (high) | Knots | m/s (low) | m/s (high) |
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
|  **0** | ≥  0.0 | <  1.0 |  **95** | ≥ 47.5 | < 50.0 |
|  **2** | ≥  1.0 | <  2.5 | **100** | ≥ 50.0 | < 52.5 |
|  **5** | ≥  2.5 | <  5.0 | **105** | ≥ 52.5 | < 55.0 |
| **10** | ≥  5.0 | <  7.5 | **110** | ≥ 55.0 | < 57.5 |
| **15** | ≥  7.5 | < 10.0 | **115** | ≥ 57.5 | < 60.0 |
| **20** | ≥ 10.0 | < 12.5 | **120** | ≥ 60.0 | < 62.5 |
| **25** | ≥ 12.5 | < 15.0 | **125** | ≥ 62.5 | < 65.0 |
| **30** | ≥ 15.0 | < 17.5 | **130** | ≥ 65.0 | < 67.5 |
| **35** | ≥ 17.5 | < 20.0 | **135** | ≥ 67.5 | < 70.0 |
| **40** | ≥ 20.0 | < 22.5 | **140** | ≥ 70.0 | < 72.5 |
| **45** | ≥ 22.5 | < 25.0 | **145** | ≥ 72.5 | < 75.0 |
| **50** | ≥ 25.0 | < 27.5 | **150** | ≥ 75.0 | < 77.5 |
| **55** | ≥ 27.5 | < 30.0 | **155** | ≥ 77.5 | < 80.0 |
| **60** | ≥ 30.0 | < 32.5 | **160** | ≥ 80.0 | < 82.5 |
| **65** | ≥ 32.5 | < 35.0 | **165** | ≥ 82.5 | < 85.0 |
| **70** | ≥ 35.0 | < 37.5 | **170** | ≥ 85.0 | < 87.5 |
| **75** | ≥ 37.5 | < 40.0 | **175** | ≥ 87.5 | < 90.0 |
| **80** | ≥ 40.0 | < 42.5 | **180** | ≥ 90.0 | < 92.5 |
| **85** | ≥ 42.5 | < 45.0 | **185** | ≥ 92.5 | < 95.0 |
| **90** | ≥ 45.0 | < 47.5 | **190** | ≥ 95.0 | < 97.5 |

The table lists ranges for at what speeds in m/s to map to the correct SVG image in knots.

## JavaScript
There is a JavaScript file containing all SVG paths and has a function for putting together the correct SVG path from a given wind speed in m/s.
```javascript
import {getWindBarb} from 'windbarbs.js'
```

## SCSS/CSS
All the SVG files has a `style` tag embeded for portability. If you want to have a centrailsed styling you can remove the `style` tag and add a class to the `SVG` tag. Consider using a `BEM` (ish) naming convention and give each individual SVG file its own modifier if you want to give any specific styling.

```scss
.svg-wb {
    fill: #1A232D;
    stroke: #1A232D;
    stroke-width: 3;
    stroke-linecap: round;
    stroke-linejoin: round;
    stroke-miterlimit: 10;

    &--0 {

    }

    &--2 {

    }

    &--5 {

    }

    ....
}
```

Add the class attribute and give the base class `svg-wb` and the corresponding modifier `svg-wb--x`
```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 250 250" class="svg-wb svg-wb--5">
    <path class="svg-wb" d="M125,112V76 M125,89l7-7 M125,125l7-12.1h-14L125,125z"/>
</svg>
```

## SVG Sprite
All SVG files can be used either individually or via the sprite `windbarbs.sprite.svg`

```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 250 250">
    <use xlink:href="windbarbs.sprite.svg#5"></use>
</svg>
```

## Individual SVGs
### 0
```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 250 250">
    <path fill="#1A232D" d="M125,120c2.762,0,5,2.239,5,5c0,2.762-2.238,5-5,5c-2.761,0-5-2.238-5-5C120,122.239,122.239,120,125,120z"/>
    <path fill="none" stroke="#1A232D" stroke-width="2" d="M125,115c5.523,0,10,4.477,10,10c0,5.523-4.477,10-10,10 c-5.523,0-10-4.477-10-10C115,119.477,119.477,115,125,115z "/>
</svg>
```

### 2
```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 250 250">
    <style type="text/css">
        .svg-wb{fill:#1A232D;stroke:#1A232D;stroke-width:3;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:10;}
    </style>
    <path class="svg-wb" d="M125,112V76 M125,125l7-12.1h-14L125,125z"/>
</svg>
```

### 5
```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 250 250">
    <style type="text/css">
        .svg-wb{fill:#1A232D;stroke:#1A232D;stroke-width:3;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:10;}
    </style>
    <path class="svg-wb" d="M125,112V76 M125,89l7-7 M125,125l7-12.1h-14L125,125z"/>
</svg>
```

### 10
```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 250 250">
    <style type="text/css">
        .svg-wb{fill:#1A232D;stroke:#1A232D;stroke-width:3;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:10;}
    </style>
    <path class="svg-wb" d="M125,112V89 M125,89l14-14 M125,125l7-12.1h-14L125,125z"/>
</svg>
```

### 15
```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 250 250">
    <style type="text/css">
        .svg-wb{fill:#1A232D;stroke:#1A232D;stroke-width:3;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:10;}
    </style>
    <path class="svg-wb" d="M125,112V89 M125,89l14-14 M125,100l7-7 M125,125l7-12.1h-14L125,125z"/>
</svg>
```

### 20
```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 250 250">
    <style type="text/css">
        .svg-wb{fill:#1A232D;stroke:#1A232D;stroke-width:3;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:10;}
    </style>
    <path class="svg-wb" d="M125,112V89 M125,89l14-14 M125,100l14-14 M125,125l7-12.1h-14L125,125z"/>
</svg>
```

### 25
```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 250 250">
    <style type="text/css">
        .svg-wb{fill:#1A232D;stroke:#1A232D;stroke-width:3;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:10;}
    </style>
    <path class="svg-wb" d="M125,112V79 M125,79l14-14 M125,90l14-14 M125,100l7-7 M125,125l7-12.1h-14L125,125z"/>
</svg>
```

### 30
```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 250 250">
    <style type="text/css">
        .svg-wb{fill:#1A232D;stroke:#1A232D;stroke-width:3;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:10;}
    </style>
    <path class="svg-wb" d="M125,112V79 M125,79l14-14 M125,90l14-14 M125,100l14-14 M125,125l7-12.1h-14L125,125z"/>
</svg>
```

### 35
```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 250 250">
    <style type="text/css">
        .svg-wb{fill:#1A232D;stroke:#1A232D;stroke-width:3;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:10;}
    </style>
    <path class="svg-wb" d="M125,112V69 M125,69l14-14 M125,80l14-14 M125,90l14-14 M125,100l7-7 M125,125l7-12.1h-14L125,125z"/>
</svg>
```

### 40
```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 250 250">
    <style type="text/css">
        .svg-wb{fill:#1A232D;stroke:#1A232D;stroke-width:3;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:10;}
    </style>
    <path class="svg-wb" d="M125,112V69 M125,69l14-14 M125,80l14-14 M125,90l14-14 M125,100l14-14 M125,125l7-12.1h-14L125,125z"/>
</svg>
```

### 45
```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 250 250">
    <style type="text/css">
        .svg-wb{fill:#1A232D;stroke:#1A232D;stroke-width:3;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:10;}
    </style>
    <path class="svg-wb" d="M125,112V59 M125,59l14-14 M125,70l14-14 M125,80l14-14 M125,90l14-14 M125,100l7-7 M125,125l7-12.1h-14 L125,125z"/>
</svg>
```

### 50
```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 250 250">
    <style type="text/css">
        .svg-wb{fill:#1A232D;stroke:#1A232D;stroke-width:3;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:10;}
    </style>
    <path class="svg-wb" d="M125,112V76 M125,76h14l-14,14V76z M125,125l7-12.1h-14L125,125z"/>
</svg>
```

### 55
```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 250 250">
    <style type="text/css">
        .svg-wb{fill:#1A232D;stroke:#1A232D;stroke-width:3;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:10;}
    </style>
    <path class="svg-wb" d="M125,112V76 M125,76h14l-14,14V76z M125,100l7-7 M125,125l7-12.1h-14L125,125z"/>
</svg>
```

### 60
```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 250 250">
    <style type="text/css">
        .svg-wb{fill:#1A232D;stroke:#1A232D;stroke-width:3;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:10;}
    </style>
    <path class="svg-wb" d="M125,112V76 M125,76h14l-14,14V76z M125,100l14-14 M125,125l7-12.1h-14L125,125z"/>
</svg>
```

### 65
```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 250 250">
    <style type="text/css">
        .svg-wb{fill:#1A232D;stroke:#1A232D;stroke-width:3;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:10;}
    </style>
    <path class="svg-wb" d="M125,112V66 M125,66h14l-14,14V66z M125,90l14-14 M125,100l7-7 M125,125l7-12.1h-14L125,125z"/>
</svg>
```

### 70
```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 250 250">
    <style type="text/css">
        .svg-wb{fill:#1A232D;stroke:#1A232D;stroke-width:3;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:10;}
    </style>
    <path class="svg-wb" d="M125,112V66 M125,66h14l-14,14V66z M125,90l14-14 M125,100l14-14 M125,125l7-12.1h-14L125,125z"/>
</svg>
```

### 75
```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 250 250">
    <style type="text/css">
        .svg-wb{fill:#1A232D;stroke:#1A232D;stroke-width:3;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:10;}
    </style>
    <path class="svg-wb" d="M125,112V56 M125,56h14l-14,14V56z M125,80l14-14 M125,90l14-14 M125,100l7-7 M125,125l7-12.1h-14L125,125z"/>
</svg>
```

### 80
```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 250 250">
    <style type="text/css">
        .svg-wb{fill:#1A232D;stroke:#1A232D;stroke-width:3;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:10;}
    </style>
    <path class="svg-wb" d="M125,112V56 M125,56h14l-14,14V56z M125,80l14-14 M125,90l14-14 M125,100l14-14 M125,125l7-12.1h-14L125,125z"/>
</svg>
```

### 85
```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 250 250">
    <style type="text/css">
        .svg-wb{fill:#1A232D;stroke:#1A232D;stroke-width:3;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:10;}
    </style>
    <path class="svg-wb" d="M125,112V46 M125,46h14l-14,14V46z M125,70l14-14 M125,80l14-14 M125,90l14-14 M125,100l7-7 M125,125l7-12.1 h-14L125,125z"/>
</svg>
```

### 90
```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 250 250">
    <style type="text/css">
        .svg-wb{fill:#1A232D;stroke:#1A232D;stroke-width:3;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:10;}
    </style>
    <path class="svg-wb" d="M125,112V46 M125,46h14l-14,14V46z M125,70l14-14 M125,80l14-14 M125,90l14-14 M125,100l14-14 M125,125l7-12.1 h-14L125,125z"/>
</svg>
```

### 95
```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 250 250">
    <style type="text/css">
        .svg-wb{fill:#1A232D;stroke:#1A232D;stroke-width:3;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:10;}
    </style>
    <path class="svg-wb" d="M125,112V36 M125,36h14l-14,14V36z M125,60l14-14 M125,70l14-14 M125,80l14-14 M125,90l14-14 M125,100l7-7 M125,125l7-12.1h-14L125,125z"/>
</svg>
```

### 100
```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 250 250">
    <style type="text/css">
        .svg-wb{fill:#1A232D;stroke:#1A232D;stroke-width:3;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:10;}
    </style>
    <path class="svg-wb" d="M125,112V62 M125,62h14l-14,14V62z M125,76h14l-14,14V76z M125,125l7-12.1h-14L125,125z"/>
</svg>
```

### 105
```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 250 250">
    <style type="text/css">
        .svg-wb{fill:#1A232D;stroke:#1A232D;stroke-width:3;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:10;}
    </style>
    <path class="svg-wb" d="M125,112V62 M125,62h14l-14,14V62z M125,76h14l-14,14V76z M125,100l7-7 M125,125l7-12.1h-14L125,125z"/>
</svg>
```

### 110
```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 250 250">
    <style type="text/css">
        .svg-wb{fill:#1A232D;stroke:#1A232D;stroke-width:3;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:10;}
    </style>
    <path class="svg-wb" d="M125,112V62 M125,62h14l-14,14V62z M125,76h14l-14,14V76z M125,100l14-14 M125,125l7-12.1h-14L125,125z"/>
</svg>
```

### 115
```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 250 250">
    <style type="text/css">
        .svg-wb{fill:#1A232D;stroke:#1A232D;stroke-width:3;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:10;}
    </style>
    <path class="svg-wb" d="M125,112V52 M125,52h14l-14,14V52z M125,66h14l-14,14V66z M125,90l14-14 M125,100l7-7 M125,125l7-12.1h-14 L125,125z"/>
</svg>
```

### 120
```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 250 250">
    <style type="text/css">
        .svg-wb{fill:#1A232D;stroke:#1A232D;stroke-width:3;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:10;}
    </style>
    <path class="svg-wb" d="M125,112V52 M125,52h14l-14,14V52z M125,66h14l-14,14V66z M125,90l14-14 M125,100l14-14 M125,125l7-12.1h-14 L125,125z"/>
</svg>
```

### 125
```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 250 250">
    <style type="text/css">
        .svg-wb{fill:#1A232D;stroke:#1A232D;stroke-width:3;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:10;}
    </style>
    <path class="svg-wb" d="M125,112V42 M125,42h14l-14,14V42z M125,56h14l-14,14V56z M125,80l14-14 M125,90l14-14 M125,100l7-7 M125,125 l7-12.1h-14L125,125z"/>
</svg>
```

### 130
```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 250 250">
    <style type="text/css">
        .svg-wb{fill:#1A232D;stroke:#1A232D;stroke-width:3;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:10;}
    </style>
    <path class="svg-wb" d="M125,112V42 M125,42h14l-14,14V42z M125,56h14l-14,14V56z M125,80l14-14 M125,90l14-14 M125,100l14-14 M125,125 l7-12.1h-14L125,125z"/>
</svg>
```

### 135
```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 250 250">
    <style type="text/css">
        .svg-wb{fill:#1A232D;stroke:#1A232D;stroke-width:3;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:10;}
    </style>
    <path class="svg-wb" d="M125,112V32 M125,32h14l-14,14V32z M125,46h14l-14,14V46z M125,70l14-14 M125,80l14-14 M125,90l14-14 M125,100 l7-7 M125,125l7-12.1h-14L125,125z"/>
</svg>
```

### 140
```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 250 250">
    <style type="text/css">
        .svg-wb{fill:#1A232D;stroke:#1A232D;stroke-width:3;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:10;}
    </style>
    <path class="svg-wb" d="M125,112V32 M125,32h14l-14,14V32z M125,46h14l-14,14V46z M125,70l14-14 M125,80l14-14 M125,90l14-14 M125,100 l14-14 M125,125l7-12.1h-14L125,125z"/>
</svg>
```

### 145
```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 250 250">
    <style type="text/css">
        .svg-wb{fill:#1A232D;stroke:#1A232D;stroke-width:3;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:10;}
    </style>
    <path class="svg-wb" d="M125,112V22 M125,22h14l-14,14V22z M125,36h14l-14,14V36z M125,60l14-14 M125,70l14-14 M125,80l14-14 M125,90 l14-14 M125,100l7-7 M125,125l7-12.1h-14L125,125z"/>
</svg>
```

### 150
```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 250 250">
    <style type="text/css">
        .svg-wb{fill:#1A232D;stroke:#1A232D;stroke-width:3;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:10;}
    </style>
    <path class="svg-wb" d="M125,112V48 M125,48h14l-14,14V48z M125,62h14l-14,14V62z M125,76h14l-14,14V76z M125,125l7-12.1h-14L125,125z"/>
</svg>
```

### 155
```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 250 250">
    <style type="text/css">
        .svg-wb{fill:#1A232D;stroke:#1A232D;stroke-width:3;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:10;}
    </style>
    <path class="svg-wb" d="M125,112V48 M125,48h14l-14,14V48z M125,62h14l-14,14V62z M125,76h14l-14,14V76z M125,100l7-7 M125,125l7-12.1 h-14L125,125z"/>
</svg>
```

### 160
```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 250 250">
    <style type="text/css">
        .svg-wb{fill:#1A232D;stroke:#1A232D;stroke-width:3;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:10;}
    </style>
    <path class="svg-wb" d="M125,112V48 M125,48h14l-14,14V48z M125,62h14l-14,14V62z M125,76h14l-14,14V76z M125,100l14-14 M125,125 l7-12.1h-14L125,125z"/>
</svg>
```

### 165
```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 250 250">
    <style type="text/css">
        .svg-wb{fill:#1A232D;stroke:#1A232D;stroke-width:3;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:10;}
    </style>
    <path class="svg-wb" d="M125,112V38 M125,38h14l-14,14V38z M125,52h14l-14,14V52z M125,66h14l-14,14V66z M125,90l14-14 M125,100l7-7 M125,125l7-12.1h-14L125,125z"/>
</svg>
```

### 170
```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 250 250">
    <style type="text/css">
        .svg-wb{fill:#1A232D;stroke:#1A232D;stroke-width:3;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:10;}
    </style>
    <path class="svg-wb" d="M125,112V38 M125,38h14l-14,14V38z M125,52h14l-14,14V52z M125,66h14l-14,14V66z M125,90l14-14 M125,100l14-14 M125,125l7-12.1h-14L125,125z"/>
</svg>
```

### 175
```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 250 250">
    <style type="text/css">
        .svg-wb{fill:#1A232D;stroke:#1A232D;stroke-width:3;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:10;}
    </style>
    <path class="svg-wb" d="M125,112V28 M125,28h14l-14,14V28z M125,42h14l-14,14V42z M125,56h14l-14,14V56z M125,80l14-14 M125,90l14-14 M125,100l7-7 M125,125l7-12.1h-14L125,125z"/>
</svg>
```

### 180
```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 250 250">
    <style type="text/css">
        .svg-wb{fill:#1A232D;stroke:#1A232D;stroke-width:3;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:10;}
    </style>
    <path class="svg-wb" d="M125,112V28 M125,28h14l-14,14V28z M125,42h14l-14,14V42z M125,56h14l-14,14V56z M125,80l14-14 M125,90l14-14 M125,100l14-14 M125,125l7-12.1h-14L125,125z"/>
</svg>
```

### 185
```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 250 250">
    <style type="text/css">
        .svg-wb{fill:#1A232D;stroke:#1A232D;stroke-width:3;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:10;}
    </style>
    <path class="svg-wb" d="M125,112V18 M125,18h14l-14,14V18z M125,32h14l-14,14V32z M125,46h14l-14,14V46z M125,70l14-14 M125,80l14-14 M125,90l14-14 M125,100l7-7 M125,125l7-12.1h-14L125,125z"/>
</svg>
```

### 190
```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 250 250">
    <style type="text/css">
        .svg-wb{fill:#1A232D;stroke:#1A232D;stroke-width:3;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:10;}
    </style>
    <path class="svg-wb" d="M125,112V18 M125,18h14l-14,14V18z M125,32h14l-14,14V32z M125,46h14l-14,14V46z M125,70l14-14 M125,80l14-14 M125,90l14-14 M125,100l14-14 M125,125l7-12.1h-14L125,125z"/>
</svg>
```

## Author
[Qulle](https://github.com/qulle/)
