c
=

> "There isn't much that's special about C. That's one of the reasons why it's fast."

I love C for it's raw speed, (although it does have its drawbacks). We
should all write more C.

With this shell script, you can compile and execute a C "scripts" in
one go!

Here's a simple example:
```c
#include <stdio.h>

int main(void) {
    printf("Hello World!\n");
    return 0;
}
```

Run it by typing:
```bash
$ c hello.c
Hello World!
```

Or, call it from the shebang!
```c
#!/usr/bin/c
#include <stdio.h>

int main(void) {
    printf("Hello World!\n");
    return 0;
}
```
```bash
$ chmod +x hello.c
$ ./hello.c
Hello World!
```

## Hooked? Here's how to install:
For all users:
```bash
$ git clone https://github.com/ryanmjacobs/c
$ sudo cp ./c/c /usr/bin/c
```
Just for a local user:
```bash
$ git clone https://github.com/ryanmjacobs/c
$ mkdir -p ~/.bin
$ cp ./c/c ~/.bin/c
$ echo 'PATH=$PATH:$HOME/.bin' >> ~/.bashrc
```

## Okay, how do I use it?
### Multiple Files - CLI
Anything you want passed to the compiler, put in quotes as the first argument.
Whether they're flags (`-Wall`, `-O2`, etc.) or file names (`file.c`,
`main.c`, etc.).

```bash
$ c "main.c other.c" arg1 arg2
$ c "main.c other.c -Wall -lncurses" arg1 arg2
```
### Single File - CLI
With only one file, omit the quotes:
```bash
$ c hello.c
$ c main.c arg1 arg2
```

## Shebang!
After adding a shebang, just set the file to executable and it's ready to run.
```bash
$ chmod +x file.c
$ ./file.c
```

### Single File - Shebang
Add this to the top of your C file:
```c
#!/usr/bin/c
```

### Multiple Files - Shebang
Just tack on any extra flags, options, or files you want passed to the compiler.
Then be sure to add the terminating `--` characters.
```c
#!/usr/bin/c file1.c file2.c -lncurses -lm --
```

## The End
Thanks for browsing this project. If you have any problems, questions, or
ideas just submit an issue and/or pull request. I hope you enjoy using it as
much as I did making it!

## License
MIT. See [LICENSE](https://raw.githubusercontent.com/ryanmjacobs/c/master/LICENSE).
