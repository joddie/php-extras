# PHP Extras

A small collection of extra features for Emacs `php-mode`.

Currently includes:

  * `php-extras-insert-previous-variable`
  * `php-extras-eldoc-documentation-function`
  * Auto complete source for PHP functions based on
    `php-extras-eldoc-documentation-function`


## `php-extras-insert-previous-variable`

When variable names get too long or you have to juggle a lot of nested
arrays it gets cumbersome to repeat the same variables over and over
again while programming.

In example you have the code below and want to debug what value you
actually parsed to `some_function()`. You have point at `^` and now
all you have to write is repeat the variable...

    some_function($my_array['some_level'][0]['another_level'][7]);
    print_r(^);

Enter `php-extras` and you just hit <kbd>C-c C-$</kbd> and it will
insert the previous variable (including array indexes).

If you prefix the command (i.e. <kbd>C-u 3 C-c C-$</kbd>) it will
search back 3 variables and with negative prefix arguments it will
search forward.


## `php-extras-eldoc-documentation-function`

`eldoc-mode` is a nice minor mode that ships with Emacs. It will
display a function tip in the mini buffer showing the function and its
arguments for the function at point. That is if you provide a function
to look up the function definition.

`php-extras` provides such a function for looking up all the core PHP
functions.

The function `php-extras-generate-eldoc` will download the PHP manual
from [php.net](http://php.net) and extract the function definitions
(slow) and store them in a hash table on disk for you. If you
install `php-extras` as an ELPA package the hash table is already
generated for you.


## Auto complete source for PHP functions based

The PHP functions extracted for
`php-extras-eldoc-documentation-function` is also setup as a source for
[auto-complete](http://cx4a.org/software/auto-complete).

[auto-complete](http://cx4a.org/software/auto-complete) already comes
with a dictionary of PHP functions and will auto complete on them
using the `ac-source-dictionary`.

The source we provide with `php-extras` will hopefully be more up to
date.


## Installation

The easiest way to install `php-extras` is probably to install it via
the ELPA archive at
[Marmalade](http://marmalade-repo.org/packages/php-extras).

ELPA (package.el) is part of Emacs 24. For Emacs 23 see
[Marmalade](http://marmalade-repo.org) for installation instructions.

The version number of the ELPA package will have the date appended
when the package was build and hence the date the documentation got
extracted from [php.net](http://php.net).

## Development of PHP Extras

PHP Extras is developed at
[GitHub](https://github.com/arnested/php-extras).  Feature requests,
ideas, bug reports, and pull request are more than welcome!
