# jekyll-comments-over-github
##### Comments over github's issue system for jekyll blog

## Quick start
1. import file
 * insert `_includes/comments.html` in your `_includes` dir
 * insert `_sass/comments.scss` in your `_scss` dir

2. embed in your jekyll blog
 * insert `@import _comments` in your css file
 * insert `{% include comments.html %}` in your layouts file, where you want the see the comments
 * create an issue for every post that will be commented ([example][example_issue])
 * add `github_username` and `repository_name` in your `_config.yml`
 * add `issueID` in your post

## Examples

  _config.yml
  ```
  ...

  github_username:  gioditalia
  repository_name: gioditalia.github.io

  ...
  ```

  _layouts/default.html *(every page can be commented need only "issueID")*
  ```
  <!DOCTYPE html>
  <html>

    {% include head.html %}

    <body>

      {% include header.html %}

      <div class="page-content">
        <div class="wrapper">
          {{ content }}
        </div>
        {% include comments.html %}
      </div>

      {% include footer.html %}

    </body>

  </html>
  ```

  _post/2016-12-27-example.md
  ```
  ---
  layout: post
  title:  "Example!"
  date:   2016-12-27
  categories: jekyll news
  issueID: 10
  ---

  some text...
  ```


 [example_issue]: https://github.com/gioditalia/gioditalia.github.io/issues/1
