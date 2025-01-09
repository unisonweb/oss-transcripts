# Uri-parser

This library provides a parser to turn URIs into Unison types that are nicer to work with.

It's centered around the Parser type. See its documentation for more details.

## Library contents list

``` ucm
@unison/uri-parser/main> pull.without-history @unison/uri-parser/releases/2.1.2

  Downloaded 13577 entities.

  ✅

  Successfully updated @unison/uri-parser/main from
  @unison/uri-parser/releases/2.1.2.

@unison/uri-parser/main> find

  1.   devGuide : Doc
  2.   ability ParseQuery
  3.   ParseQuery.boolean : Text ->{ParseQuery} Optional Boolean
  4.   ParseQuery.boolean.doc : Doc
  5.   ParseQuery.custom : Text
                           -> ([Text] ->{g} a)
                           ->{g, ParseQuery} a
  6.   ParseQuery.custom.doc : Doc
  7.   ParseQuery.customSingle : Text
                                 -> Expected
                                 -> (Text ->{g} Optional a)
                                 ->{g, ParseQuery} Optional a
  8.   ParseQuery.doc : Doc
  9.   ParseQuery.float : Text ->{ParseQuery} Optional Float
  10.  ParseQuery.float.doc : Doc
  11.  ParseQuery.getParameter : Text ->{ParseQuery} [Text]
  12.  ParseQuery.int : Text ->{ParseQuery} Optional Int
  13.  ParseQuery.int.doc : Doc
  14.  ParseQuery.nat : Text ->{ParseQuery} Optional Nat
  15.  ParseQuery.nat.doc : Doc
  16.  ParseQuery.parseQuery : '{ParseQuery} a
                               -> Query
                               ->{Exception} a
  17.  ParseQuery.parseQuery.doc : Doc
  18.  ParseQuery.parseQueryString : '{ParseQuery} a
                                     -> Text
                                     ->{Exception} a
  19.  ParseQuery.parseQueryString.doc : Doc
  20.  ParseQuery.parseRawQuery : '{ParseQuery} a
                                  -> RawQuery
                                  ->{Exception} a
  21.  ParseQuery.parseRawQuery.doc : Doc
  22.  type ParseQuery.QueryParseFailure
  23.  ParseQuery.queryParseFailure : QueryParseFailure
                                      ->{ParseQuery} a
  24.  ParseQuery.QueryParseFailure.InvalidParameter : InvalidQueryParameter
                                                       -> QueryParseFailure
  25.  type ParseQuery.QueryParseFailure.InvalidParameterCause
  26.  ParseQuery.QueryParseFailure.InvalidParameterCause.doc : Doc
  27.  ParseQuery.QueryParseFailure.InvalidParameterCause.IncorrectCount : Nat
                                                                           -> InvalidParameterCause
  28.  ParseQuery.QueryParseFailure.InvalidParameterCause.Invalid : InvalidParameterCause
  29.  type ParseQuery.QueryParseFailure.InvalidQueryParameter
  30.  ParseQuery.QueryParseFailure.InvalidQueryParameter.actual : InvalidQueryParameter
                                                                   -> [Text]
  31.  ParseQuery.QueryParseFailure.InvalidQueryParameter.actual.modify : ([Text]
                                                                          ->{g} [Text])
                                                                          -> InvalidQueryParameter
                                                                          ->{g} InvalidQueryParameter
  32.  ParseQuery.QueryParseFailure.InvalidQueryParameter.actual.set : [Text]
                                                                       -> InvalidQueryParameter
                                                                       -> InvalidQueryParameter
  33.  ParseQuery.QueryParseFailure.InvalidQueryParameter.cause : InvalidQueryParameter
                                                                  -> InvalidParameterCause
  34.  ParseQuery.QueryParseFailure.InvalidQueryParameter.cause.modify : (InvalidParameterCause
                                                                         ->{g} InvalidParameterCause)
                                                                         -> InvalidQueryParameter
                                                                         ->{g} InvalidQueryParameter
  35.  ParseQuery.QueryParseFailure.InvalidQueryParameter.cause.set : InvalidParameterCause
                                                                      -> InvalidQueryParameter
                                                                      -> InvalidQueryParameter
  36.  ParseQuery.QueryParseFailure.InvalidQueryParameter.expected : InvalidQueryParameter
                                                                     -> Expected
  37.  ParseQuery.QueryParseFailure.InvalidQueryParameter.expected.modify : (Expected
                                                                            ->{g} Expected)
                                                                            -> InvalidQueryParameter
                                                                            ->{g} InvalidQueryParameter
  38.  ParseQuery.QueryParseFailure.InvalidQueryParameter.expected.set : Expected
                                                                         -> InvalidQueryParameter
                                                                         -> InvalidQueryParameter
  39.  ParseQuery.QueryParseFailure.InvalidQueryParameter.InvalidQueryParameter : Text
                                                                                  -> Expected
                                                                                  -> [Text]
                                                                                  -> InvalidParameterCause
                                                                                  -> InvalidQueryParameter
  40.  ParseQuery.QueryParseFailure.InvalidQueryParameter.key : InvalidQueryParameter
                                                                -> Text
  41.  ParseQuery.QueryParseFailure.InvalidQueryParameter.key.modify : (Text
                                                                       ->{g} Text)
                                                                       -> InvalidQueryParameter
                                                                       ->{g} InvalidQueryParameter
  42.  ParseQuery.QueryParseFailure.InvalidQueryParameter.key.set : Text
                                                                    -> InvalidQueryParameter
                                                                    -> InvalidQueryParameter
  43.  ParseQuery.QueryParseFailure.InvalidQueryParameter.toText : InvalidQueryParameter
                                                                   -> Text
  44.  ParseQuery.QueryParseFailure.MalformedQuery : Text
                                                     -> QueryParseFailure
  45.  ParseQuery.QueryParseFailure.MissingParameter : Text
                                                       -> QueryParseFailure
  46.  ParseQuery.QueryParseFailure.toText : QueryParseFailure
                                             -> Text
  47.  ParseQuery.required : (Text ->{ParseQuery} Optional b)
                             -> Text
                             ->{ParseQuery} b
  48.  ParseQuery.run : '{ParseQuery} a
                        -> Map Text [Text]
                        ->{Exception} a
  49.  ParseQuery.run.doc : Doc
  50.  ParseQuery.text : Text ->{ParseQuery} Optional Text
  51.  ParseQuery.text.doc : Doc
  52.  ParseQuery.tryRun : '{ParseQuery} a
                           -> Map Text [Text]
                           -> Either QueryParseFailure a
  53.  type Parser a b
  54.  Parser.& : Parser a (query -> b)
                  -> '{ParseQuery} query
                  -> Parser a b
  55.  Parser.&.doc : Doc
  56.  Parser./ : Parser a b -> Parser b c -> Parser a c
  57.  Parser./.doc : Doc
  58.  Parser.<|> : Parser a b -> Parser a b -> Parser a b
  59.  Parser.<|>.doc : Doc
  60.  Parser.=> : Parser a b -> a -> Parser (b -> c) c
  61.  Parser.=>.doc : Doc
  62.  Parser.custom : Text
                       -> (Text -> Optional a)
                       -> Parser (a -> b) b
  63.  Parser.custom.doc : Doc
  64.  Parser.doc : Doc
  65.  type Parser.examples.BlogRoute
  66.  Parser.examples.BlogRoute.Blog : Nat -> BlogRoute
  67.  Parser.examples.BlogRoute.Comment : Text
                                           -> Nat
                                           -> BlogRoute
  68.  Parser.examples.BlogRoute.Topic : Text -> BlogRoute
  69.  Parser.examples.BlogRoute.User : Text -> BlogRoute
  70.  type Parser.Expected
  71.  Parser.Expected.Exact : Text -> Expected
  72.  Parser.Expected.Meta : Text -> Expected
  73.  Parser.Expected.toText : Expected -> Text
  74.  Parser.float : Parser (Float -> a) a
  75.  Parser.float.doc : Doc
  76.  Parser.int : Parser (Int -> a) a
  77.  Parser.int.doc : Doc
  78.  Parser.map : a -> Parser a b -> Parser (b -> c) c
  79.  Parser.map.doc : Doc
  80.  Parser.matches : Parser (a ->{g} a) a -> URI -> Boolean
  81.  Parser.matches.doc : Doc
  82.  Parser.matchesText : Parser (a ->{g} a) a
                            -> Text
                            -> Boolean
  83.  Parser.matchesText.doc : Doc
  84.  Parser.nat : Parser (Nat -> a) a
  85.  Parser.nat.doc : Doc
  86.  Parser.noCapture : Parser () b -> Parser (b -> c) c
  87.  Parser.noCapture.doc : Doc
  88.  Parser.oneOf : [Parser a b] -> Parser a b
  89.  Parser.oneOf.doc : Doc
  90.  Parser.optional : Parser a b -> Parser a b
  91.  Parser.optional.doc : Doc
  92.  Parser.parse : Parser (a ->{g} a) a
                      -> URI
                      ->{Exception} Optional a
  93.  Parser.parse.doc : Doc
  94.  Parser.parseMaybe : Parser (a ->{g} a) a
                           -> URI
                           -> Optional a
  95.  Parser.parseMaybe.doc : Doc
  96.  Parser.ParseQuery.QueryParseFailure.doc : Doc
  97.  Parser.ParseQuery.QueryParseFailure.InvalidQueryParameter.doc : Doc
  98.  Parser.Parser : (State a
                       ->{Throw QueryParseFailure} [State b])
                       -> Parser a b
  99.  Parser.parseText : Parser (a ->{g} a) a
                          -> Text
                          ->{Exception} Optional a
  100. Parser.parseText.doc : Doc
  101. Parser.parseTextMaybe : Parser (a ->{g} a) a
                               -> Text
                               -> Optional a
  102. Parser.parseTextMaybe.doc : Doc
  103. type Parser.PathParseFailure
  104. Parser.PathParseFailure.actual : PathParseFailure
                                        -> [Text]
  105. Parser.PathParseFailure.actual.modify : ([Text]
                                               ->{g} [Text])
                                               -> PathParseFailure
                                               ->{g} PathParseFailure
  106. Parser.PathParseFailure.actual.set : [Text]
                                            -> PathParseFailure
                                            -> PathParseFailure
  107. Parser.PathParseFailure.committed : PathParseFailure
                                           -> [Text]
  108. Parser.PathParseFailure.committed.modify : ([Text]
                                                  ->{g} [Text])
                                                  -> PathParseFailure
                                                  ->{g} PathParseFailure
  109. Parser.PathParseFailure.committed.set : [Text]
                                               -> PathParseFailure
                                               -> PathParseFailure
  110. Parser.PathParseFailure.doc : Doc
  111. Parser.PathParseFailure.expected : PathParseFailure
                                          -> Expected
  112. Parser.PathParseFailure.expected.modify : (Expected
                                                 ->{g} Expected)
                                                 -> PathParseFailure
                                                 ->{g} PathParseFailure
  113. Parser.PathParseFailure.expected.set : Expected
                                              -> PathParseFailure
                                              -> PathParseFailure
  114. Parser.PathParseFailure.PathParseFailure : Expected
                                                  -> [Text]
                                                  -> [Text]
                                                  -> PathParseFailure
  115. Parser.PathParseFailure.toText : PathParseFailure -> Text
  116. Parser.PathParseFailure.toText.doc : Doc
  117. Parser.query : '{ParseQuery} query
                      -> Parser (query -> a) a
  118. Parser.query.doc : Doc
  119. Parser.required : Parser a b -> Parser a b
  120. Parser.required.doc : Doc
  121. Parser.rest : Parser ([Text] -> o) o
  122. Parser.rest.doc : Doc
  123. Parser.restAsText : Parser (Text -> c) c
  124. Parser.restAsText.doc : Doc
  125. Parser.root : Parser a a
  126. Parser.root.doc : Doc
  127. Parser.run : Parser (a ->{g} a) a
                    -> URI
                    ->{Throw QueryParseFailure} [State a]
  128. Parser.run.doc : Doc
  129. Parser.s : Text -> Parser a a
  130. Parser.s.doc : Doc
  131. type Parser.State value
  132. Parser.State.committed : State value -> Boolean
  133. Parser.State.committed.modify : (Boolean ->{g} Boolean)
                                       -> State value
                                       ->{g} State value
  134. Parser.State.committed.set : Boolean
                                    -> State value
                                    -> State value
  135. Parser.State.firstResult : [State a]
                                  -> Optional (State a)
  136. Parser.State.frag : State value -> Optional Text
  137. Parser.State.frag.modify : (Optional Text
                                  ->{g} Optional Text)
                                  -> State value
                                  ->{g} State value
  138. Parser.State.frag.set : Optional Text
                               -> State value
                               -> State value
  139. Parser.State.getFirstMatch : [State a] -> Optional a
  140. Parser.State.map : (a ->{g} b) -> State a ->{g} State b
  141. Parser.State.map.doc : Doc
  142. Parser.State.params : State value -> Map Text [Text]
  143. Parser.State.params.modify : (Map Text [Text]
                                    ->{g} Map Text [Text])
                                    -> State value
                                    ->{g} State value
  144. Parser.State.params.set : Map Text [Text]
                                 -> State value
                                 -> State value
  145. Parser.State.State : [Text]
                            -> [Text]
                            -> Map Text [Text]
                            -> Optional Text
                            -> Boolean
                            -> Either Expected value
                            -> State value
  146. Parser.State.unvisited : State value -> [Text]
  147. Parser.State.unvisited.modify : ([Text] ->{g} [Text])
                                       -> State value
                                       ->{g} State value
  148. Parser.State.unvisited.set : [Text]
                                    -> State value
                                    -> State value
  149. Parser.State.value : State value -> Either Expected value
  150. Parser.State.value.modify : (Either Expected value1
                                   ->{g} Either Expected value)
                                   -> State value1
                                   ->{g} State value
  151. Parser.State.value.set : Either Expected value
                                -> State value1
                                -> State value
  152. Parser.State.visited : State value -> [Text]
  153. Parser.State.visited.modify : ([Text] ->{g} [Text])
                                     -> State value
                                     ->{g} State value
  154. Parser.State.visited.set : [Text]
                                  -> State value
                                  -> State value
  155. Parser.text : Parser (Text -> a) a
  156. Parser.text.doc : Doc
  157. Parser.top : Parser a a
  158. Parser.top.doc : Doc
  159. Parser.tryParse : Parser (a ->{g} a) a
                         -> URI
                         -> Either UriParseFailure a
  160. Parser.tryParse.doc : Doc
  161. Parser.tryParseText : Parser (a ->{g} a) a
                             -> Text
                             -> Either UriParseFailure a
  162. Parser.tryParseText.doc : Doc
  163. type Parser.UriParseFailure
  164. Parser.UriParseFailure.BadPath : [PathParseFailure]
                                        -> UriParseFailure
  165. Parser.UriParseFailure.BadQuery : QueryParseFailure
                                         -> UriParseFailure
  166. Parser.UriParseFailure.BadUri : Text -> UriParseFailure
  167. Parser.UriParseFailure.doc : Doc
  168. type Parser.UriParseFailure.InvalidUri
  169. Parser.UriParseFailure.toText : UriParseFailure -> Text
  170. Parser.withQuery : Parser a (query -> b)
                          -> '{ParseQuery} query
                          -> Parser a b
  171. Parser.withQuery.doc : Doc
  172. README : Doc
  173. ReleaseNotes : Doc
```

## Code examples

``` ucm
@unison/uri-parser/main> edit 1-5000

  ☝️

  I added 150 definitions to the top of scratch.u

  You can edit them there, then run `update` to replace the
  definitions currently in this namespace.
```
