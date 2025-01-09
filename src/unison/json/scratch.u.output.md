# Json

A Json library with nice error reporting. It supports parsing, encoding, and decoding arbitrary Unison types into Json.

## Library contents list

``` ucm
@unison/json/main> pull.without-history @unison/json/releases/1.2.3

  Downloaded 14505 entities.

  ✅

  Successfully updated @unison/json/main from
  @unison/json/releases/1.2.3.

@unison/json/main> find

  1.   type core.Json
  2.   core.Json.array : [Json] -> Json
  3.   core.Json.Array : [Json] -> Json
  4.   core.Json.boolean : Boolean -> Json
  5.   core.Json.Boolean : Boolean -> Json
  6.   core.Json.catchFromText : Text -> Either Failure Json
  7.   core.Json.catchUnconsText : Text
                                   -> Either
                                     Failure (Json, Text)
  8.   core.Json.doc : Doc
  9.   core.Json.float : Float -> Json
  10.  core.Json.fromText : Text ->{Exception} Json
  11.  core.Json.fromText.tests.emptyArray : [Result]
  12.  core.Json.fromText.tests.emptyObject : [Result]
  13.  core.Json.int : Int -> Json
  14.  core.Json.nat : Nat -> Json
  15.  core.Json.null : Json
  16.  core.Json.Null : Json
  17.  core.Json.Number.Unparsed : Text -> Json
  18.  core.Json.object : [(Text, Json)] -> Json
  19.  core.Json.Object : [(Text, Json)] -> Json
  20.  core.Json.object.add : Text -> Json -> Json -> Json
  21.  core.Json.object.add.doc : Doc
  22.  core.Json.object.addBoolean : Text
                                     -> Boolean
                                     -> Json
                                     -> Json
  23.  core.Json.object.addBoolean.doc : Doc
  24.  core.Json.object.addFloat : Text -> Float -> Json -> Json
  25.  core.Json.object.addFloat.doc : Doc
  26.  core.Json.object.addInt : Text -> Int -> Json -> Json
  27.  core.Json.object.addInt.doc : Doc
  28.  core.Json.object.addList : Text -> [Json] -> Json -> Json
  29.  core.Json.object.addList.doc : Doc
  30.  core.Json.object.addMap : Text
                                 -> Map Text Json
                                 -> Json
                                 -> Json
  31.  core.Json.object.addMap.doc : Doc
  32.  core.Json.object.addNat : Text -> Nat -> Json -> Json
  33.  core.Json.object.addNat.doc : Doc
  34.  core.Json.object.addOptional : Text
                                      -> Optional Json
                                      -> Json
                                      -> Json
  35.  core.Json.object.addOptional.doc : Doc
  36.  core.Json.object.addOptionalBoolean : Text
                                             -> Optional Boolean
                                             -> Json
                                             -> Json
  37.  core.Json.object.addOptionalBoolean.doc : Doc
  38.  core.Json.object.addOptionalFloat : Text
                                           -> Optional Float
                                           -> Json
                                           -> Json
  39.  core.Json.object.addOptionalFloat.doc : Doc
  40.  core.Json.object.addOptionalInt : Text
                                         -> Optional Int
                                         -> Json
                                         -> Json
  41.  core.Json.object.addOptionalInt.doc : Doc
  42.  core.Json.object.addOptionalList : Text
                                          -> Optional [Json]
                                          -> Json
                                          -> Json
  43.  core.Json.object.addOptionalList.doc : Doc
  44.  core.Json.object.addOptionalMap : Text
                                         -> Optional
                                           (Map Text Json)
                                         -> Json
                                         -> Json
  45.  core.Json.object.addOptionalMap.doc : Doc
  46.  core.Json.object.addOptionalNat : Text
                                         -> Optional Nat
                                         -> Json
                                         -> Json
  47.  core.Json.object.addOptionalNat.doc : Doc
  48.  core.Json.object.addOptionalText : Text
                                          -> Optional Text
                                          -> Json
                                          -> Json
  49.  core.Json.object.addOptionalText.doc : Doc
  50.  core.Json.object.addText : Text -> Text -> Json -> Json
  51.  core.Json.object.addText.doc : Doc
  52.  core.Json.object.empty : Json
  53.  core.Json.object.empty.doc : Doc
  54.  type core.Json.ParseError
  55.  core.Json.ParseError : Text -> a -> Failure
  56.  core.Json.ParseError.doc : Doc
  57.  core.Json.ParseError.message : Json.ParseError -> Text
  58.  core.Json.ParseError.message.doc : Doc
  59.  core.Json.ParseError.ParseError : Text
                                         -> Nat
                                         -> Text
                                         -> Json.ParseError
  60.  core.Json.ParseError.position : Json.ParseError -> Nat
  61.  core.Json.ParseError.position.doc : Doc
  62.  core.Json.ParseError.raiseFailure : Json.ParseError
                                           ->{Exception} r
  63.  core.Json.ParseError.remainder : Json.ParseError -> Text
  64.  core.Json.ParseError.remainder.doc : Doc
  65.  core.Json.ParseError.toText : Json.ParseError -> Text
  66.  core.Json.ParseError.toText.doc : Doc
  67.  core.Json.tests.controlChars : [Result]
  68.  core.Json.tests.parsing : [Result]
  69.  core.Json.tests.roundtripTextEsc1 : [Result]
  70.  core.Json.tests.unicodeHex : [Result]
  71.  core.Json.text : Text -> Json
  72.  core.Json.Text : Text -> Json
  73.  core.Json.toText : Json -> Text
  74.  core.Json.toText.doc : Doc
  75.  core.Json.tryFromText : Text
                               -> Either Json.ParseError Json
  76.  core.Json.tryUnconsText : Text
                                 -> Either
                                   Json.ParseError (Json, Text)
  77.  core.Json.unconsText : Text ->{Exception} (Json, Text)
  78.  core.Json.unconsTextOrThrow : Text
                                     ->{Throw Json.ParseError} ( Json,
                                       Text)
  79.  core.Json.util.dropLeadingWhitespace : Text -> Text
  80.  core.Json.util.hexCharToNat : Char -> Nat
  81.  core.Json.util.hexCodepoint : Text -> Char
  82.  core.Json.util.parseTextLiteral : Text
                                         -> Optional
                                           (Text, Text)
  83.  core.ReleaseNotes : Doc
  84.  core.util.Text.controlCharToHex : Nat -> Text
  85.  core.util.Text.literalForm : Text -> Text
  86.  core.util.Text.literalForm.doc : Doc
  87.  core.util.Text.toHexChar : Nat -> Text
  88.  ability Decoder
  89.  Decoder.<|> : '{g, Decoder} v
                     -> '{g2, Decoder} v
                     -> '{g, g2, Decoder} v
  90.  Decoder.array : '{g, Decoder} a -> '{g, Decoder} [a]
  91.  Decoder.array.at : Nat
                          -> '{g, Decoder} a
                          -> '{g, Decoder} a
  92.  Decoder.array.at! : Nat
                           -> '{g, Decoder} a
                           ->{g, Decoder} a
  93.  Decoder.array.at!.doc : Doc
  94.  Decoder.array.doc : Doc
  95.  Decoder.array.offset : Nat
                              -> '{g, Decoder} t
                              -> '{g, Decoder} t
  96.  Decoder.array.offset.doc : Doc
  97.  Decoder.array.offset! : Nat
                               -> '{g, Decoder} a
                               ->{g, Decoder} a
  98.  Decoder.array.offset!.doc : Doc
  99.  Decoder.array.sum : Nat
                           -> '{g, Decoder} a
                           -> Nat
                           -> (a ->{g2, Decoder} b)
                           -> '{g, g2, Decoder} b
  100. Decoder.array! : '{g, Decoder} t ->{g, Decoder} [t]
  101. Decoder.array!.doc : Doc
  102. Decoder.array2 : '{g, Decoder} a
                        -> '{g2, Decoder} b
                        -> '{g, g2, Decoder} (a, b)
  103. Decoder.array3 : '{g, Decoder} a
                        -> '{g2, Decoder} b
                        -> '{g3, Decoder} c
                        -> '{g, g2, g3, Decoder} (a, b, c)
  104. Decoder.array4 : '{g, Decoder} a
                        -> '{g2, Decoder} b
                        -> '{g3, Decoder} c
                        -> '{g4, Decoder} d
                        -> '{g, g2, g3, g4, Decoder} ( a,
                          b,
                          c,
                          d)
  105. Decoder.array5 : '{g, Decoder} a
                        -> '{g2, Decoder} b
                        -> '{g3, Decoder} c
                        -> '{g4, Decoder} d
                        -> '{g5, Decoder} e
                        -> '{g, g2, g3, g4, g5, Decoder} ( a,
                          b,
                          c,
                          d,
                          e)
  106. Decoder.array6 : '{g, Decoder} a
                        -> '{g2, Decoder} b
                        -> '{g3, Decoder} c
                        -> '{g4, Decoder} d
                        -> '{g5, Decoder} e
                        -> '{g6, Decoder} f
                        -> '{g, g2, g3, g4, g5, g6, Decoder} ( a,
                          b,
                          c,
                          d,
                          e,
                          f)
  107. Decoder.boolean : '{Decoder} Boolean
  108. type Decoder.DecodingFailure
  109. Decoder.DecodingFailure.DecodingFailure : Text
                                                 -> [PathElement]
                                                 -> Json
                                                 -> Any
                                                 -> DecodingFailure
  110. Decoder.DecodingFailure.doc : Doc
  111. Decoder.DecodingFailure.ParseFailure : Json.ParseError
                                              -> DecodingFailure
  112. Decoder.DecodingFailure.raiseFailure : DecodingFailure
                                              ->{Exception} r
  113. Decoder.DecodingFailure.toBaseFailure : DecodingFailure
                                               -> Failure
  114. Decoder.DecodingFailure.toBaseFailure.doc : Doc
  115. Decoder.DecodingFailure.toText : DecodingFailure -> Text
  116. Decoder.DecodingFailure.toText.doc : Doc
  117. Decoder.DecodingFailure.UnexpectedTrailingText : Text
                                                        -> Any
                                                        -> DecodingFailure
  118. Decoder.doc : Doc
  119. Decoder.either : '{g, Decoder} l
                        -> '{g2, Decoder} r
                        -> '{g, g2, Decoder} Either l r
  120. Decoder.either.doc : Doc
  121. Decoder.emptyArray : '{Decoder} ()
  122. Decoder.emptyArray.doc : Doc
  123. Decoder.emptyObject : '{Decoder} ()
  124. Decoder.emptyObject.doc : Doc
  125. Decoder.fail : Text ->{Decoder} x
  126. Decoder.fail.doc : Doc
  127. Decoder.failDebug : Text -> a ->{Decoder} x
  128. Decoder.failDebug.doc : Doc
  129. Decoder.failWith : DecodingFailure ->{Decoder} x
  130. Decoder.float : '{Decoder} Float
  131. Decoder.focus : PathElement
                       -> Json
                       -> '{g, Decoder} a
                       ->{g, Decoder} a
  132. Decoder.int : '{Decoder} Int
  133. Decoder.nat : '{Decoder} Nat
  134. Decoder.null : '{Decoder} ()
  135. Decoder.number.unparsed : '{Decoder} Text
  136. Decoder.object : '{g, Decoder} v
                        -> '{g, Decoder} Map Text v
  137. Decoder.object.at : Text
                           -> '{g, Decoder} a
                           -> '{g, Decoder} a
  138. Decoder.object.at! : Text
                            -> '{g, Decoder} a
                            ->{g, Decoder} a
  139. Decoder.object.at!.doc : Doc
  140. Decoder.object.doc : Doc
  141. Decoder.object.optionalAt : Text
                                   -> '{g, Decoder} a
                                   -> '{g, Decoder} Optional a
  142. Decoder.object.optionalAt.doc : Doc
  143. Decoder.object.optionalAt.tests.absent : [Result]
  144. Decoder.object.optionalAt.tests.present : [Result]
  145. Decoder.object.optionalAt! : Text
                                    -> '{g, Decoder} a
                                    ->{g, Decoder} Optional a
  146. Decoder.object.optionalAt!.doc : Doc
  147. Decoder.object.sum : Text
                            -> '{g, Decoder} a
                            -> (a ->{g2, Decoder} b)
                            -> '{g, g2, Decoder} b
  148. Decoder.object.sum.doc : Doc
  149. Decoder.object.sum.nested : Text
                                   -> '{g, Decoder} a
                                   -> Text
                                   -> (a ->{g2, Decoder} b)
                                   -> '{g, g2, Decoder} b
  150. Decoder.object! : '{g, Decoder} t
                         ->{g, Decoder} Map Text t
  151. Decoder.object!.doc : Doc
  152. Decoder.optional : '{g, Decoder} a
                          -> '{g, Decoder} Optional a
  153. Decoder.optional.doc : Doc
  154. Decoder.optional! : '{g, Decoder} a
                           ->{g, Decoder} Optional a
  155. Decoder.optional!.doc : Doc
  156. Decoder.or : '{g, Decoder} v
                    -> '{g2, Decoder} v
                    -> '{g, g2, Decoder} v
  157. Decoder.orNull : '{g, Decoder} a
                        -> '{g, Decoder} Optional a
  158. Decoder.orNull.doc : Doc
  159. Decoder.path : '{Decoder} [PathElement]
  160. Decoder.path! : {Decoder} [PathElement]
  161. type Decoder.PathElement
  162. Decoder.PathElement.ArrayIndex : Nat -> PathElement
  163. Decoder.PathElement.Label : Text -> PathElement
  164. Decoder.PathElement.ObjectKey : Text -> PathElement
  165. Decoder.reraise : Either DecodingFailure b
                         ->{Exception} b
  166. Decoder.run : '{g, Decoder} t -> Text ->{g, Exception} t
  167. Decoder.run.doc : Doc
  168. Decoder.run.parsed : '{g, Decoder} t
                            -> Json
                            ->{g, Exception} t
  169. Decoder.scope : Text
                       -> '{g, Decoder} a
                       -> '{g, Decoder} a
  170. Decoder.scope.doc : Doc
  171. Decoder.tests.ex1 : [Result]
  172. Decoder.tests.ex2 : [Result]
  173. Decoder.tests.ex3 : [Result]
  174. Decoder.tests.ex4 : [Result]
  175. Decoder.tests.ex5 : [Result]
  176. Decoder.tests.ex6 : [Result]
  177. Decoder.text : '{Decoder} Text
  178. Decoder.try : '{g, Decoder} v
                     -> '{g, Decoder} Either DecodingFailure v
  179. Decoder.tryRun : '{g, Decoder} a
                        -> Text
                        ->{g} Either DecodingFailure a
  180. Decoder.tryRun.doc : Doc
  181. Decoder.tryRun.noTrailing : '{g, Decoder} t
                                   -> Text
                                   ->{g} Either
                                     DecodingFailure t
  182. Decoder.tryRun.noTrailing.doc : Doc
  183. Decoder.tryRun.parsed : '{g, Decoder} a
                               -> Json
                               ->{g} Either DecodingFailure a
  184. Decoder.value : '{Decoder} Json
  185. Decoder.value! : {Decoder} Json
  186. Readme : Doc
  187. ReleaseNotes : Doc
```

## Code examples

``` ucm
@unison/json/main> edit 1-6000

  ☝️

  I added 171 definitions to the top of scratch.u

  You can edit them there, then run `update` to replace the
  definitions currently in this namespace.
```
