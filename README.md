jscsscc
=======

 JS/CSS obfuscator.
 Copyright: Dmitry Ponomarev <demdxx@gmail.com> 2012
 Version: 0.0.1
 License: MIT

Example
=======

Config file: resources.ol
-------------------------

```sh
# JS section
output/min1.js
input/file1.js
input/file2.js

output/mylib.min.js
input/core.js
input/events.js
input/animate.js
...
input/form.js

# CSS section
output/styles.min.css
input/styles.css
input/ui.css
...

```

Make file: make
---------------

```sh
#!/bin/sh

target_dir="`pwd`/../www/resources/"
work_dir=`pwd`

for f in `find . -iname "*.ol"`
do
    echo $f
    exec jscsscc -L "$work_dir/$f" "$target_dir" 
done
```

Using
-----

```sh
# Process templates and resources
./templates/make
./resources/make
```

