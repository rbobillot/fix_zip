# fix_zip

## What's going on ?

Our spies might have stolen crucial secret files from our enemies.

- [secret.zip](./misc/secret.zip) (a **PASSWORD PROTECTED zip file**)

Our data analyst team came to the conclusion that
the essential secret information can be found within the [secret.zip](./misc/secret.zip)

But the file is protected by a password, and we don't know much about it:

- is it a password, a passphrase ?
- what characters compose the pass ? alpha, num, symbols ?
- what's the pass length ?

Also, our spies have found and stolen 3 pass files:

- [pass-1.zip](./misc/pass-1.zip) (a **zip file** containing a `.txt` file)
- [pass-2.zip](./misc/pass-2.zip) (a **zip file** containing a `.txt` file)
- [pass-3.zip](./misc/pass-3.zip) (a **CORRUPTED zip** file)

They led our analysts to the conclusion
that each `pass-{N}.txt` file's content,
are the **1st**, **2nd** and **3rd** part of the password protecting the [secret.zip](./misc/secret.zip)

Unfortunately the [pass-3.zip](./misc/pass-3.zip) looks corrupted,
impossible to extract the `pass-3.txt` file from it.

Our security experts have a few theories about this corruption,
they think this was corrupted on purpose.

A few techniques might have been used to cipher it, but the experts tend to think
that a single-byte xor cipher might have been used here.

If only there was a way to check the integrity of a zip file...
Some data in it that never changes, and that can be brute-forced ?

## Your mission

Decipher the [pass-3.zip](./misc/pass-3.zip), and extract the data from [secret.zip](./misc/secret.zip)

To help you on your task here are some crucial resources:

- [Official ZIP documentation](https://www.x-ways.net/winhex/kb/ff/ZIP.txt)
- [About the XOR cipher](https://en.wikipedia.org/wiki/XOR_cipher)
- Some useful Unix commands: `zip`, `unzip`, `zipdetails`, `xxd`

## Development

Use your Gleam knowledge to:

- read data from file
- update it
- rewrite the file (or write to another file, if you prefer)

```sh
gleam run   # Run the project
gleam test  # Run the tests
```
