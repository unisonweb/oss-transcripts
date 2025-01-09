# json-core

A minimal library with just a Json syntax tree and functions to and from text.

## Library contents list

``` ucm
@unison/json-core/main> pull.without-history @unison/json-core/releases/1.0.3

  Downloaded 12882 entities.

  ✅

  Successfully updated @unison/json-core/main from
  @unison/json-core/releases/1.0.3.

@unison/json-core/main> find

  1.  type Json
  2.  Json.array : [Json] -> Json
  3.  Json.Array : [Json] -> Json
  4.  Json.boolean : Boolean -> Json
  5.  Json.Boolean : Boolean -> Json
  6.  Json.catchFromText : Text -> Either Failure Json
  7.  Json.catchUnconsText : Text -> Either Failure (Json, Text)
  8.  Json.doc : Doc
  9.  Json.float : Float -> Json
  10. Json.fromText : Text ->{Exception} Json
  11. Json.fromText.tests.emptyArray : [Result]
  12. Json.fromText.tests.emptyObject : [Result]
  13. Json.int : Int -> Json
  14. Json.nat : Nat -> Json
  15. Json.null : Json
  16. Json.Null : Json
  17. Json.Number.Unparsed : Text -> Json
  18. Json.object : [(Text, Json)] -> Json
  19. Json.Object : [(Text, Json)] -> Json
  20. type Json.ParseError
  21. Json.ParseError : Text -> a -> Failure
  22. Json.ParseError.doc : Doc
  23. Json.ParseError.message : ParseError -> Text
  24. Json.ParseError.message.doc : Doc
  25. Json.ParseError.ParseError : Text
                                   -> Nat
                                   -> Text
                                   -> ParseError
  26. Json.ParseError.position : ParseError -> Nat
  27. Json.ParseError.position.doc : Doc
  28. Json.ParseError.raiseFailure : ParseError ->{Exception} r
  29. Json.ParseError.remainder : ParseError -> Text
  30. Json.ParseError.remainder.doc : Doc
  31. Json.ParseError.toText : ParseError -> Text
  32. Json.ParseError.toText.doc : Doc
  33. Json.tests.controlChars : [Result]
  34. Json.tests.parsing : [Result]
  35. Json.tests.roundtripTextEsc1 : [Result]
  36. Json.tests.unicodeHex : [Result]
  37. Json.text : Text -> Json
  38. Json.Text : Text -> Json
  39. Json.toText : Json -> Text
  40. Json.toText.doc : Doc
  41. Json.tryFromText : Text -> Either ParseError Json
  42. Json.tryUnconsText : Text
                           -> Either ParseError (Json, Text)
  43. Json.unconsText : Text ->{Exception} (Json, Text)
  44. Json.unconsTextOrThrow : Text
                               ->{Throw ParseError} (Json, Text)
  45. Json.util.dropLeadingWhitespace : Text -> Text
  46. Json.util.hexCharToNat : Char -> Nat
  47. Json.util.hexCodepoint : Text -> Char
  48. Json.util.parseTextLiteral : Text -> Optional (Text, Text)
  49. Readme : Doc
  50. ReleaseNotes : Doc
  51. util.Text.controlCharToHex : Nat -> Text
  52. util.Text.literalForm : Text -> Text
  53. util.Text.literalForm.doc : Doc
  54. util.Text.toHexChar : Nat -> Text
```

## Code examples

``` ucm
@unison/json-core/main> edit 1-6000

  ☝️

  I added 47 definitions to the top of scratch.u

  You can edit them there, then run `update` to replace the
  definitions currently in this namespace.
```
