# Publishing tests with RMarkdown

My desiire is to publish/knit HTML from RMarkdown into a `docs` folder so I can host it with Github Pages.

I would prefer to host the RMarkdown file itself in a folder of it's own, like `analysis/` using a directory structure like this:

```bash
.project_root
-- README.md
-- analysis
   |-- analysis_file.Rmd
-- docs
   |-- analysis_file.html
-- data
   |-- datafile.csv
```

## output_dir

There is an `output_dir` option in the `render()` function of [rmarkdown](https://www.rdocumentation.org/packages/rmarkdown/versions/1.11/topics/render) but that doesn't seem to work, either. The developer of `knitr` says [he's thought a lot](https://github.com/rstudio/rmarkdown/issues/587#issuecomment-168437646) about the issue, but that it is not possible to put an output in another folder because of relative paths.

I tried it in [01_pubtest.Rmd](01_pubtest.Rmd).


## ezknitr

There is an R package [ezknitr](https://github.com/ropensci/ezknitr), but I can't get it to work. I think it is intended to work from an `.R` file and then be run from the command line. I _want_ to do my original work in RMarkdown and use the internal "knit" command.

I tried in in `02_ezknit` but it errors and creates only a partial `.md` file and no HTML.

## use docs for RMarkdown files

My last attempt is to store my RMarkdown files inside the `docs` folder. This works, but I would rather have the `.Rmd` files in a folder of their own, and only have the published `.html` or `.pdf` files inside of `docs`.

Theoretically, my example file [would be published here](https://critmcdonald.github.io/r-publishing-test/03_indocs.html).
