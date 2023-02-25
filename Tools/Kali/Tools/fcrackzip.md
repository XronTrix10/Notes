# ⚙️ fcrackzip

## Description

fcrackzip is a fast password cracker partly written in assembler. It is able to crack password protected zip files with brute force or dictionary based attacks, optionally testing with unzip its results. It can also crack cpmask’ed images.

## Installation
```
sudo apt install fcrackzip
```

## Usage Example

```
fcrackzip -v -u -D -p /usr/share/wordlists/rockyou.txt ~/save.zip
```

- -v for verbosity
- -u for unzipping
- -D for dictionary attack
- -p for preferring dictionary file