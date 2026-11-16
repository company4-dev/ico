# ICO
ICO allows you to generate .ico files from pre-existing images.

## Installation

```bash
composer require company4-dev/ico
```

## Usage

### Set-up the ICO
| Parameter | Type     | Default | Description
| --------- | -------- | ------- | -----------
| `$in`     | `string` | `null`  | The path to the source image file
| `$out`    | `string` | `null`  | Path to the target ICO file, if null, the file will be saved to the same location, but with a .ico extension.
| `$sizes`  | `array`  | `[]`    | An array of sizes that the source image should be rendered at in the generated ICO file. If sizes are not supplied, sizes 16px<sup>2</sup>, 24px<sup>2</sup>, 32px<sup>2</sup>, 48px<sup>2</sup>, 256px<sup>2</sup> will be used.
```php
use Company4\Ico\Ico;

$ico = new ICO(
    $path,
    [
        [16, 16],
        [32, 32],
        [48, 48],
        [64, 64],
    ]
);

$ico->save($target);
```

## With Thanks
Credit to [Chris Jean](https://github.com/chrisbliss18/php-ico) who can take credit for base of the `src/ico.php` file.
