# pipedit

The script will read stdin, run the EDITOR and print edited file to stdout
which allows running a selected editor in a pipeline like in following not
particularly useful example:

    $ ln -l | pipedit vim | wc -l

## Usage

    $ pipedit EDITOR [EDITOR_OPTIONS]

vi, nano, vim, gvim and emacs should work without problems.

Other editors may work too, just make sure your editor does not fork but
blocks until you save and exit.

There are few predefined symbolic links:

    $ pipevi [VI_OPTIONS]
    $ pipevim [VIM_OPTIONS]
    $ pipegvim [VIM_OPTIONS]
    $ pipemacs [EMACS_OPTIONS]

And also few options are allowed:

    $ pipedit [OPTIONS]

  -h, --help    print this message
  --links       make symbolic links for few supported editors

When making links pipedit should be either in PATH or in the current working
directory(cwd). Links are created in the cwd.

