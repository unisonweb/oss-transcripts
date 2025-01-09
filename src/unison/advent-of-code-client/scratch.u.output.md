# Advent-of-code-client

This library provides a client for the Advent of Code HTTP API. It supports downloading user-specific input and submitting answers for each problem.

## Library contents list

``` ucm
@unison/advent-of-code-client/main> pull.without-history @unison/advent-of-code-client/releases/1.4.2

  Downloaded 29222 entities.

  ✅

  Successfully updated @unison/advent-of-code-client/main from
  @unison/advent-of-code-client/releases/1.4.2.

@unison/advent-of-code-client/main> find

  1.  ability AdventOfCode
  2.  AdventOfCode.defaultHandler : '{g,
                                    IO,
                                    AdventOfCode,
                                    Exception,
                                    Log Text} r
                                    ->{g, IO, Exception} r
  3.  type AdventOfCode.defaultHandler.Config
  4.  AdventOfCode.defaultHandler.Config.apiBaseUri : defaultHandler.Config
                                                      -> URI
  5.  AdventOfCode.defaultHandler.Config.apiBaseUri.modify : (URI
                                                             ->{g} URI)
                                                             -> defaultHandler.Config
                                                             ->{g} defaultHandler.Config
  6.  AdventOfCode.defaultHandler.Config.apiBaseUri.set : URI
                                                          -> defaultHandler.Config
                                                          -> defaultHandler.Config
  7.  AdventOfCode.defaultHandler.Config.apiToken : defaultHandler.Config
                                                    -> Token
  8.  AdventOfCode.defaultHandler.Config.apiToken.modify : (Token
                                                           ->{g} Token)
                                                           -> defaultHandler.Config
                                                           ->{g} defaultHandler.Config
  9.  AdventOfCode.defaultHandler.Config.apiToken.set : Token
                                                        -> defaultHandler.Config
                                                        -> defaultHandler.Config
  10. AdventOfCode.defaultHandler.Config.cacheDir : defaultHandler.Config
                                                    -> Optional
                                                      FilePath
  11. AdventOfCode.defaultHandler.Config.cacheDir.modify : (Optional
                                                             FilePath
                                                           ->{g} Optional
                                                             FilePath)
                                                           -> defaultHandler.Config
                                                           ->{g} defaultHandler.Config
  12. AdventOfCode.defaultHandler.Config.cacheDir.set : Optional
                                                          FilePath
                                                        -> defaultHandler.Config
                                                        -> defaultHandler.Config
  13. AdventOfCode.defaultHandler.Config.Config : URI
                                                  -> Token
                                                  -> Optional
                                                    FilePath
                                                  -> Optional
                                                    LogLevel
                                                  -> defaultHandler.Config
  14. AdventOfCode.defaultHandler.Config.default : '{IO,
                                                   Exception} defaultHandler.Config
  15. AdventOfCode.defaultHandler.Config.defaultApiBaseUri : URI
  16. AdventOfCode.defaultHandler.Config.defaultCacheDir : '{IO,
                                                           Exception} FilePath
  17. AdventOfCode.defaultHandler.Config.defaultToken : '{IO,
                                                        Exception} Token
  18. AdventOfCode.defaultHandler.Config.defaultToken.doc : Doc
  19. AdventOfCode.defaultHandler.Config.doc : Doc
  20. AdventOfCode.defaultHandler.Config.logLevel : defaultHandler.Config
                                                    -> Optional
                                                      LogLevel
  21. AdventOfCode.defaultHandler.Config.logLevel.modify : (Optional
                                                             LogLevel
                                                           ->{g} Optional
                                                             LogLevel)
                                                           -> defaultHandler.Config
                                                           ->{g} defaultHandler.Config
  22. AdventOfCode.defaultHandler.Config.logLevel.set : Optional
                                                          LogLevel
                                                        -> defaultHandler.Config
                                                        -> defaultHandler.Config
  23. AdventOfCode.defaultHandler.configured : defaultHandler.Config
                                               -> '{g,
                                               IO,
                                               AdventOfCode,
                                               Exception,
                                               Log Text} r
                                               ->{g,
                                               IO,
                                               Exception} r
  24. AdventOfCode.defaultHandler.defaultLogger.impl : Request
                                                         {Log
                                                           Text}
                                                         r
                                                       ->{IO,
                                                       Exception} r
  25. AdventOfCode.defaultHandler.toHttp : URI
                                           -> Optional FilePath
                                           -> Token
                                           -> '{g, AdventOfCode} r
                                           ->{g,
                                           IO,
                                           Exception,
                                           Http,
                                           Log Text} r
  26. AdventOfCode.doc : Doc
  27. AdventOfCode.input : Year -> Day ->{AdventOfCode} Text
  28. AdventOfCode.solveAndSubmit : Year
                                    -> Day
                                    -> Part
                                    -> (Text ->{g} Text)
                                    ->{g,
                                    AdventOfCode,
                                    Log Text} ()
  29. AdventOfCode.solveAndSubmit.doc : Doc
  30. AdventOfCode.solveAndSubmit.impl : Year
                                         -> Day
                                         -> Part
                                         -> (Text ->{g} Text)
                                         ->{g, AdventOfCode} SubmissionResult
  31. AdventOfCode.solveAndSubmit.impl.doc : Doc
  32. AdventOfCode.submit : Year
                            -> Day
                            -> Part
                            -> Text
                            ->{AdventOfCode} SubmissionResult
  33. api.addRequestDefaults : Token
                               -> HttpRequest
                               -> HttpRequest
  34. api.cacheSuccessfulRequest : FilePath
                                   -> HttpRequest
                                   ->{IO,
                                   Exception,
                                   Http,
                                   Log Text} HttpResponse
  35. api.cacheSuccessfulRequest.doc : Doc
  36. api.dayPath : Year -> Day -> Path
  37. api.expectSuccess : HttpResponse ->{Exception} ()
  38. type api.failure.SubmissionError
  39. type api.failure.UnexpectedResponseStatus
  40. api.getInput : URI -> Year -> Day ->{Exception, Http} Text
  41. api.http.cacheSuccess : FilePath
                              -> '{g, Http} r
                              ->{g,
                              IO,
                              Exception,
                              Http,
                              Log Text} r
  42. api.submitAnswer : URI
                         -> Year
                         -> Day
                         -> Part
                         -> Text
                         ->{Exception, Http} SubmissionResult
  43. type api.Token
  44. api.Token.doc : Doc
  45. api.Token.Token : Text -> Token
  46. api.Token.toText : Token -> Text
  47. api.Token.toText.modify : (Text ->{g} Text)
                                -> Token
                                ->{g} Token
  48. api.Token.toText.set : Text -> Token -> Token
  49. api.withApiDefaults : Token -> '{g, Http} r ->{g, Http} r
  50. type Day
  51. Day.Day : Nat -> Day
  52. type Day.Part
  53. Day.Part.doc : Doc
  54. Day.Part.Part : Nat -> Part
  55. Day.Part.toNat : Part -> Nat
  56. Day.Part.toNat.modify : (Nat ->{g} Nat) -> Part ->{g} Part
  57. Day.Part.toNat.set : Nat -> Part -> Part
  58. Day.Part.toText : Part -> Text
  59. Day.toNat : Day -> Nat
  60. Day.toNat.modify : (Nat ->{g} Nat) -> Day ->{g} Day
  61. Day.toNat.set : Nat -> Day -> Day
  62. Day.toText : Day -> Text
  63. docs.beKind : Doc
  64. docs.configuration : Doc
  65. docs.example : '{IO, Exception} ()
  66. docs.example.doc : Doc
  67. docs.gettingToken : Doc
  68. README : Doc
  69. ReleaseNotes : Doc
  70. type SubmissionResult
  71. SubmissionResult.Correct : SubmissionResult
  72. SubmissionResult.Incorrect : SubmissionResult
  73. up.logging.Log.toStream : '{g, Log a} r
                                -> '{g, Stream (LogLevel, a)} r
  74. up.logging.Log.toStream! : '{g, Log a} r
                                 ->{g, Stream (LogLevel, a)} r
  75. up.logging.Log.withLogLevel! : Optional LogLevel
                                     -> '{g, Log a} r
                                     ->{g, Log a} r
  76. up.logging.Log.withLogLevel!.doc : Doc
```

## Code examples

``` ucm
@unison/advent-of-code-client/main> edit 1-5000

  ☝️

  I added 68 definitions to the top of scratch.u

  You can edit them there, then run `update` to replace the
  definitions currently in this namespace.
```
