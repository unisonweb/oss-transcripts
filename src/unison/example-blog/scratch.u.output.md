# Example-blog

An example blog using @unison/blog-engine.

## Library contents list

``` ucm
@unison/example-blog/main> pull.without-history @unison/example-blog/main

  Downloaded 37905 entities.

  ✅

  Successfully updated @unison/example-blog/main from
  @unison/example-blog/main.

@unison/example-blog/main> find

  1.  authors.alice : BlogAuthor
  2.  authors.bob : BlogAuthor
  3.  blog : '{Exception, Cloud} Blog
  4.  blog.build : '{IO, Exception} ()
  5.  blog.buildDeploy : '{IO, Exception} URI
  6.  blog.deploy : '{IO, Exception} URI
  7.  posts.blogWithUnison : Doc
  8.  posts.elementsOfProgramming : Doc
  9.  posts.unisonDocExample : Doc
  10. README : Doc
```

## Code examples

``` ucm
@unison/example-blog/main> edit 1-5000

  ☝️

  I added 10 definitions to the top of scratch.u

  You can edit them there, then run `update` to replace the
  definitions currently in this namespace.
```

