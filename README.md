tdraw
---
Inspired by [Explaining Code using ASCII Art](https://blog.regehr.org/archives/1653).<br/>
Supports box / line drawing, text input and eraser.
wfn's fork from [aca/tdraw](https://github.com/aca/tdraw)

![tdraw](./tdraw.gif)

#### Install
```
go get -u github.com/aca/tdraw
```
or download from https://github.com/aca/tdraw/releases

#### Usage
1. Pipe output to file, easy way:
```
tdraw > draw.txt
```

2. Explicitly ask it to save to file (overwrites existing one), optionally with parameter resolved:
```
Usage of ./tdraw:
  -filename string
    	output filename (optional params for it: datetime) (default "drawing_{{.datetime}}.txt")
  -output-to-file
    	on exit, save output to text file (disabled by default)
```

Filename is optional and it's convenient to leave it out:
```
% ./tdraw -output-to-file
  [program runs, user presses ctrl+c at some point]
Output file: drawing_2025-03-23_130808.txt
```

This was added for more flexibility in the feature, e.g. would be nice to
 - read in txt file
 - keep track of shapes as entities
 - save entity list (separate file optionally), re-arrange shapes to fit new shapes
   - overall would be great to have small subset of draw.io functionality but with dynamic context-aware shape management

#### Modes

```
// tdraw has 4 modes.
ESC: Box(+Undirected line, default)
l: Directed line
t: Text
e: Erase

CTRL-C/CTRL-D: exit

// It might not work if terminal emulator consumes right click(iterm2)
MouseR: Eraser 
```
