<!--
theme: gaia
paginate: true
headingDivider: 2
backgroundColor: white
-->

# Capstone Class Slides

This repository converts [Marp](https://marp.app) formatted markdown slides into html and pdf with [Github actions](https://github.com/actions).

Converted slides are also available as web pages through [Github pages](https://pages.github.com).

## Directory and Branch Structures

- There are two branches: `main` and `gh-pages`
- Branch `main` contains [Marp formatted markdown slides](https://marpit.marp.app/directives)
- A push on `main` branch rebuilds all slides (`*.md`) at root level
- Actions are defined in `.github/workflows/`
- Branch `gh-pages` is created automatically
- Converted slides are in `output` directory

## Example

Converted slides from `getting-started.md` are in `gh-pages` branch:

```
.
├── output
│   └── getting-started.html
│   └── getting-started.pdf
└── getting-started.md
```

URLs for converted slides are
```
https://ucsb-ds-capstone-2021.github.io/slides/output/getting-started.html
https://ucsb-ds-capstone-2021.github.io/slides/output/getting-started.pdf
```

## Working on slides locally

Easiest way is to use [marp-cli docker image](https://hub.docker.com/r/marpteam/marp-cli/).

- Clone this repository and run `marp-cli` in server mode:  
    ```bash
    git clone https://github.com/ucsb-ds-capstone-2021/slides.git
    cd slides
    docker run --rm --init \
        -v $PWD:/home/marp/app -e LANG=$LANG \
        -p 8080:8080 -p 37717:37717 marpteam/marp-cli -s .        
    ```
- Open [`http://localhost:8080`](http://localhost:8080) in your browser.


