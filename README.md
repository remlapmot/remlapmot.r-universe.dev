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

### Ubuntu Linux Noble Numbat using R-release (version 4.5.#)

#### Ubuntu Noble Numbat x86_64 using R through RStudio Desktop or RStudio Server

For Ubuntu Noble Numbat users running R through RStudio Desktop or RStudio Server the installation code is

```r
# Installation code for Ubuntu Jammy Jellyfish users in RStudio Desktop or Server
install.packages(
  'knitexercise',
  repos = c(
    'https://remlapmot.r-universe.dev/bin/linux-x86_64/noble/4.5/',
    'https://p3m.dev/cran/__linux__/noble/latest',
    'https://cloud.r-project.org'
  )
)
```

#### Ubuntu Noble Numbat x86_64 using R in a shell

For Ubuntu Noble Numbat users running R in a shell first amend the `HTTPUserAgent` option, as described in the following blog [post](https://tshafer.com/blog/2023/07/posit-package-manager-linux), and then run the Linux installation code above. This is in order to obtain binary packages from the Posit Public Package Manager. If the `HTTPUserAgent` option is not amended it seems that source rather than binary packages are obtained for the Imports dependency packages. So for this case the full installation code is

```r
# Installation code for Ubuntu Jammy Jellyfish users running R in the Terminal
options(HTTPUserAgent = sprintf(
  "R/%s R (%s)",
  getRversion(),
  paste(getRversion(),
        R.version["platform"],
        R.version["arch"],
        R.version["os"])
))

install.packages(
  'knitexercise',
  repos = c(
    'https://remlapmot.r-universe.dev/bin/linux/noble-x86_64/4.5/',
    'https://p3m.dev/cran/__linux__/noble/latest',
    'https://cloud.r-project.org'
  )
)
```

#### Ubuntu Noble Numbat ARM

For Ubuntu Noble Numbat on ARM please use

```r
install.packages(
  'knitexercise',
  repos = c(
    'https://remlapmot.r-universe.dev/bin/linux/noble-aarch64/4.5/',
    'https://cloud.r-project.org'
  )
)
```

### WebR

WASM binaries for [WebR](https://docs.r-wasm.org/webr/latest/) users are available with the code

```r
install.packages('knitexercise',
  repos = c('https://remlapmot.r-universe.dev', 'https://repo.r-wasm.org'))
```
