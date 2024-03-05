# Lei Xiong's personal webpage

This is the personal website of Lei Xiong, which can be visualized at [https://jsxlei.github.io/](https://jsxlei.github.io/).

### Installation

Assuming you have [Ruby](https://www.ruby-lang.org/en/downloads/) and [Bundler](https://bundler.io/) installed on your system (*hint: for ease of managing ruby gems, consider using [rbenv](https://github.com/rbenv/rbenv)*), first fork the theme from `github.com:alshedivat/al-folio` to `github.com:<your-username>/<your-repo-name>` and do the following:

```bash
$ git clone git@github.com:<your-username>/<your-repo-name>.git
$ cd <your-repo-name>
$ bundle install
$ bundle exec jekyll serve
```

Note: Use sudo if you encounter issues when you run bundle install  
Now, feel free to customize the theme however you like (don't forget to change the name!).
After you are done, you can deploy it to [GitHub Pages](https://pages.github.com/) by running the deploy script:


```bash
$ ./bin/deploy
```
Note: make sure to commit all your changes on the `src` branch before deploying!

## Modification
after modified some files in the src repo at the local, upload the updates to the remote repo.

    git add *
    git commit -m “”
    git push origin src
    ./bin/deploy 

## Preview

```
 bundle exec jekyll serve
```


#### Theming
Six beautiful theme colors have been selected to choose from.
The default is purple, but quickly change it by editing the `_sass/base.scss` file in line 40.
The color variable are listed there, as well.

