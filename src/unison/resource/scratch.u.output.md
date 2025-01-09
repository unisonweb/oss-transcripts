# Resource

The Resource ability is used to manage resources that need to be released when they are no longer needed, for example file handles or database connections.

## Library contents list

``` ucm
@unison/resource/main> pull.without-history @unison/resource/releases/1.1.0

  Downloaded 13770 entities.

  ✅

  Successfully updated @unison/resource/main from
  @unison/resource/releases/1.1.0.

@unison/resource/main> find

  1.  examples.simpleFileRead : '{IO, Exception} ()
  2.  README : Doc
  3.  ReleaseNotes : Doc
  4.  ability Resource
  5.  Resource.allocate : '{IO, Exception} a
                          -> (a ->{IO, Exception} ())
                          ->{Resource} (ReleaseKey, a)
  6.  Resource.allocate' : '{IO, Exception} t
                           -> (t ->{IO, Exception} ())
                           ->{Resource} t
  7.  Resource.allocate'.doc : Doc
  8.  Resource.bracket : '{IO, Exception} r
                         -> (r ->{IO, Exception} ())
                         -> (r ->{IO, Exception, Resource} t)
                         ->{IO, Exception} t
  9.  Resource.bracket.doc : Doc
  10. Resource.doc : Doc
  11. Resource.register : '{IO, Exception} ()
                          ->{Resource} ReleaseKey
  12. Resource.release : ReleaseKey ->{Resource} ()
  13. type Resource.ReleaseKey
  14. Resource.ReleaseKey.doc : Doc
  15. Resource.ReleaseKey.ReleaseKey : Nat -> ReleaseKey
  16. type Resource.ReleaseMap
  17. Resource.ReleaseMap.ReleaseMap : Nat
                                       -> Nat
                                       -> Map
                                         Nat
                                         ('{IO, Exception} ())
                                       -> ReleaseMap
  18. Resource.run : '{IO, Exception, Resource} a
                     ->{IO, Exception} a
  19. Resource.run.doc : Doc
  20. Resource.scope : '{g, Resource} a -> '{g, Resource} a
  21. Resource.scope.doc : Doc
  22. Resource.scope.tests.example1 : '{IO, Exception} [Result]
  23. Resource.scope! : '{g, Resource} a ->{g, Resource} a
  24. Resource.scope!.doc : Doc
```

## Code examples

``` ucm
@unison/resource/main> edit 1-6000

  ☝️

  I added 19 definitions to the top of scratch.u

  You can edit them there, then run `update` to replace the
  definitions currently in this namespace.
```
