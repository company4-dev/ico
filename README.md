# PHP ICO
Incremental Backups allows you to reduce the storage taken up by backups by only saving incremental changes. (Full database backups are always captured).

Incremental Backups supports Laravel so your backups can be stored in a sensible location.

On an initial run, the Incrementor will create a full backup. From then on it'll create a full database backup and any files that have been saved since the previous run.

Run another full backup then the incrementor will start with changed from that backup.

Want to just backup the database? Chain in `->database_only()` before `->run()` as explained below. This won't effect any future backups.

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
use Company4\ICO;

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
