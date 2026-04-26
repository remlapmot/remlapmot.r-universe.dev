# remlapmot.r-universe.dev :rocket:

[![:name status badge](https://remlapmot.r-universe.dev/badges/:name)](https://remlapmot.r-universe.dev/)
[![:registry status badge](https://remlapmot.r-universe.dev/badges/:registry)](https://github.com/r-universe/remlapmot/actions/workflows/sync.yml)
[![:total status badge](https://remlapmot.r-universe.dev/badges/:total)](https://remlapmot.r-universe.dev/)

This is the repo specifying which R packages contribute to my <https://remlapmot.r-universe.dev/>.

The corresponding source universe repo is at <https://github.com/r-universe/remlapmot>.

## How to install binary R packages from this R-universe

To install binary R packages from my R-universe, include the relevant URL in your `repos` list as shown below (or set the `repos` option using `options(repos = c(...))` which you could do in your *.Rprofile* file).

### Windows and Macs

For Windows and Mac users (for both Intel Macs and Apple Silicon [aka M series] Macs) the installation code to obtain a binary version of **knitexercise** is

```r
# Installation code for Windows and Intel Mac users
install.packages(
  'knitexercise',
  repos = c(
    'https://remlapmot.r-universe.dev',
    'https://cloud.r-project.org'
  )
)
```

### Ubuntu Linux Noble Numbat

Copying from the [official documentation about Linux binary packages](https://docs.r-universe.dev/install/binaries.html#binaries-linux)

```r
linux_binary_repo <- function(universe){
  sprintf('https://%s.r-universe.dev/bin/linux/noble-%s/%s/', 
    universe,
    R.version$arch, 
    substr(getRversion(), 1, 3))
}

# For example: enable ropensci and cran repositories 
options(repos = linux_binary_repo(c('ropensci', 'cran')))

# Then install say knitexercise with
install.packages("knitexercise")
```

If you prefer to obtain your CRAN binary packages from the Public Posit Package Manager see the setup page on the website. You will need a repos entry along the lines of

```r
arch <- R.version["arch"]
rv <- substr(getRversion(), 1, 3)
options(repos = c(
  CRAN = sprintf("https://packagemanager.posit.co/cran/latest/bin/linux/noble-%s/%s", arch, rv),
  runiverse = sprintf("https://remlapmot.r-universe.dev/bin/linux/noble-%s/%s/", arch, rv)
))

# Then install say knitexercise with
install.packages("knitexercise")
```

As `ubuntu:latest` changes you would need to change the codename `noble` within this. For example, r-universe will likely swap to Resolute Raccoon (`resolute`) soon.

### WebR

WASM binaries for [WebR](https://docs.r-wasm.org/webr/latest/) users are available with the code

```r
install.packages('knitexercise',
  repos = c('https://remlapmot.r-universe.dev', 'https://repo.r-wasm.org'))
```
