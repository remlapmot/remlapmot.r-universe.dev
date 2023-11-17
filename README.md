# remlapmot.r-universe.dev :rocket:
[![:name status badge](https://remlapmot.r-universe.dev/badges/:name)](https://remlapmot.r-universe.dev/)
[![:registry status badge](https://remlapmot.r-universe.dev/badges/:registry)](https://github.com/r-universe/remlapmot/actions/workflows/sync.yml)
[![:total status badge](https://remlapmot.r-universe.dev/badges/:total)](https://remlapmot.r-universe.dev/)

This is the repo specifying which R packages contribute to my <https://remlapmot.r-universe.dev/>.

The corresponding source universe repo is at <https://github.com/r-universe/remlapmot>.

## How to install binary R packages from this R-universe

To install binary R packages from my R-universe, include the relevant URL in your `repos` list as shown below (or set the `repos` option using `options(repos = c(...)))`.

### Windows and Intel Macs

For Windows and Intel Mac users the installation code to obtain a binary version of **knitexercise** is

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

### Ubuntu Jammy Jellyfish

For Ubuntu Jammy Jellyfish users running R through RStudio Desktop or RStudio Server the installation code is

```r
# Installation code for Ubuntu Jammy Jellyfish users in RStudio Desktop or Server
install.packages(
  'knitexercise',
  repos = c(
    'https://remlapmot.r-universe.dev/bin/linux/jammy/4.3/',
    'https://packagemanager.posit.co/cran/__linux__/jammy/latest',
    'https://cloud.r-project.org'
  )
)
```

For Ubuntu Jammy Jellyfish users running R in the Terminal first amend the `HTTPUserAgent` option, as described in the following blog [post](https://tshafer.com/blog/2023/07/posit-package-manager-linux), and then run the Linux installation code above. This is in order to obtain binary packages from the Posit Public Package Manager. If the `HTTPUserAgent` option is not amended it seems that source rather than binary packages are obtained for the Imports dependency packages. So for this case the full installation code is

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
    'https://remlapmot.r-universe.dev/bin/linux/jammy/4.3/',
    'https://packagemanager.posit.co/cran/__linux__/jammy/latest',
    'https://cloud.r-project.org'
  )
)
```

### WebR

WASM binaries for WebR users are available with the code

```r
install.packages('knitexercise',
  repos = c('https://remlapmot.r-universe.dev', 'https://repo.r-wasm.org'))
```
