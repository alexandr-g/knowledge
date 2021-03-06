# Common terminal commands

## General

### return the last command

```bash
!!
```

### make file executable

```bash
chmod +x
```

### add write access to a group

```bash
chmod g+w
```

### change file owner and group

```bash
chown
```

### check folder size

```bash
du -h Gigabyte <folder_name>
```

-h "Human-readable" output. Use unit suffixes: Byte, Kilobyte, Megabyte, Gigabyte, Terabyte and Petabyte.

## Setup

### Using Alt/Cmd + Right/Left Arrow in iTerm

Go to iTerm Preferences → Profiles, select your profile, then the Keys tab. Find ⌥← and ⌥→ and set them to send escape sequence b and send escape sequence f respectively.

<img src="https://i.stack.imgur.com/HCNAe.png" />

https://apple.stackexchange.com/questions/136928/using-alt-cmd-right-left-arrow-in-iterm
