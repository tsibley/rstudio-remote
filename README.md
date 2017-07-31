# RStudio remote

Run code in your RStudio session from your terminal or favorite editor.

RStudio's integration of code, data, and results is amazing, but having to use
its editor stinks.  Flipping back and forth between your favorite editor and
RStudio to repeatedly source the file also stinks and breaks the flow of
piecemeal execution of code chunks.

The program `rstudio-console` will connect to a running RStudio session on your
computer and feed it console input.  RStudio will echo the input and show the
output, just as if you'd typed it into the RStudio console directly.

When used interactively at a terminal, `rstudio-console` is a very basic REPL.

When piped input from another command or a file, `rstudio-console` sends the R code
to RStudio and exits.  This makes it easy to pipe highlighted code from your
favorite editor, such as Vim, to your RStudio session.

Currently `rstudio-console` is written in bash and requires a couple standard
external commands like `curl` and `lsof` and a couple not-as-standard commands
like [`jq`](https://stedolan.github.io/jq/) and `steal-envs` (provided in this
repo).  While it works pretty well, it's a proof-of-concept and could be
further refined, either in shell or in any other language.  It's based on
watching RStudio itself interact with its backend session but might benefit
from actually reading the RStudio backend's source code or documentation.
