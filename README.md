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

But I could live with all the `.Rmd` files being at the root of the project.

## Attempt 01 - output_dir

There is an `output_dir` option in the `render()` function of [rmarkdown](https://www.rdocumentation.org/packages/rmarkdown/versions/1.11/topics/render) but that doesn't seem to work, either. The developer of `knitr` says [he's thought a lot](https://github.com/rstudio/rmarkdown/issues/587#issuecomment-168437646) about the issue, but that it is not possible to put an output in another folder because of relative paths.

I tried it in [01_pubtest.Rmd](01_pubtest.Rmd).

## Attempt 02 - ezknitr

There is an R package [ezknitr](https://github.com/ropensci/ezknitr), but I can't get it to work. I think it is intended to work from an `.R` file and then be run from the command line. I _want_ to do my original work in RMarkdown and use the internal "knit" command.

I tried in in [02_ezknit.Rmd](02_ezknit.Rmd) but it errors and creates only a partial `.md` file and no HTML.

## Attempt 03 - Use docs for RMarkdown files

My third attempt was to store my RMarkdown files inside the `docs` folder. This works, but I would rather have the `.Rmd` files in a folder of their own or at the root level of the project, and only have the published `.html` or `.pdf` files inside of `docs`.

My example file [did publish here](https://critmcdonald.github.io/r-publishing-test/03_indocs.html).

## Attempt 04 - Better knitr metadata

This option in [04_knitropt.Rmd](04_knitropt.Rmd) seems to work. You can [see the result here](https://critmcdonald.github.io/r-publishing-test/04_knitropt.html).


## Attempt 5 - Some News Nerdery suggestions

Saving [those notes here](05_nnsuggests.Rmd).



