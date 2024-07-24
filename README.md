# Ascify

Ascify is a command-line tool for renaming files and directories by converting their names to ASCII characters. It is particularly useful for filenames containing special characters or non-Latin alphabets.

## Features

- **Convert filenames to ASCII**: Handles non-Latin alphabets and special characters.
- **Interactive mode**: Edit proposed names interactively.
- **Recursive renaming**: Rename files in subdirectories.
- **Dry-run option**: Preview changes without making any modifications.
- **Custom encoding**: Specify the encoding of original filenames.

## Usage

```
Usage: ./ascify -e <enc> [-ynhvdre]
-y, --yes              Don't ask for confirmation
-h, --help             Display this message
-n, --dry-run          Don't change names, print them instead
-v, --version          Display current version of the program
-d, --directory        Enable renaming directories
-r, --recursive        Enable renaming files in subdirectories
-e enc, --encoding=enc Set encoding of the original names. Default is UTF-8.
```

## Examples

### Basic Usage

```bash
./ascify -r
```

### Preview Changes Without Renaming

```bash
./ascify -nr
```

#### Output:

```
/home/user/ascify/test_assets/zażółcić gęślą jaźń żółwia?.pdf ->
/home/user/ascify/test_assets/zazolcic_gesla_jazn_zolwia.pdf
/home/user/ascify/test_assets/ab             c,d,e ->
/home/user/ascify/test_assets/ab_cde
/home/user/ascify/test_assets/Батогов Е. В.: Gentoo Linux. Cборник статей.pdf ->
/home/user/ascify/test_assets/Batogov_E._V.:_Gentoo_Linux._Cbornik_statei.pdf
/home/user/ascify/test_assets/test  dir/Łódź ->
/home/user/ascify/test_assets/test  dir/Lodz
/home/user/ascify/test_assets/żółć ->
/home/user/ascify/test_assets/zolc(1)
/home/user/ascify/test_assets/Яблоко ->
/home/user/ascify/test_assets/Iabloko
```

### Interactive Mode

Without the `-y` option, Ascify will prompt for confirmation before renaming each file:

```bash
./ascify -r
```

#### Output:

```
/home/user/ascify/test_assets/zażółcić gęślą jaźń żółwia?.pdf ->
/home/user/ascify/test_assets/zazolcic_gesla_jazn_zolwia.pdf [yes/no/edit]
```
