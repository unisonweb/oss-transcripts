# Xml

This library provides various utilities for extracting data from XML documents, and editing them.

## Library contents list

``` ucm
@unison/xml/main> pull.without-history @unison/xml/releases/2.1.1

  Downloaded 13750 entities.

  ✅

  Successfully updated @unison/xml/main from
  @unison/xml/releases/2.1.1.

@unison/xml/main> find

  1.   type Cursor
  2.   Cursor.collectAttributes : Map Text Text
                                  -> Cursor
                                  ->{Throw XMLError} ( Map
                                    Text Text,
                                    Cursor)
  3.   Cursor.collectChildren : Text
                                -> [XMLNode]
                                -> Cursor
                                ->{Throw XMLError} ( [XMLNode],
                                  Cursor)
  4.   Cursor.current : Cursor -> XMLEvent
  5.   Cursor.current.modify : (XMLEvent ->{g} XMLEvent)
                               -> Cursor
                               ->{g} Cursor
  6.   Cursor.current.set : XMLEvent -> Cursor -> Cursor
  7.   Cursor.currentList : Cursor -> [XMLEvent]
  8.   Cursor.currentList.doc : Doc
  9.   Cursor.currentStream : Cursor -> '{Stream XMLEvent} ()
  10.  Cursor.currentStream.doc : Doc
  11.  Cursor.currentStream! : Cursor ->{Stream XMLEvent} ()
  12.  Cursor.currentStream!.doc : Doc
  13.  Cursor.Cursor : '{Stream XMLEvent} ()
                       -> XMLEvent
                       -> '{Stream XMLEvent} ()
                       -> Cursor
  14.  Cursor.doc : Doc
  15.  Cursor.empty : Cursor
  16.  Cursor.empty.doc : Doc
  17.  Cursor.findEnclosingOpen : Text
                                  -> Cursor
                                  ->{Throw XMLError} ( Nat,
                                    Cursor)
  18.  Cursor.findEnclosingOpen.doc : Doc
  19.  Cursor.findMatchingClose : Text
                                  -> Cursor
                                  ->{Throw XMLError} ( Nat,
                                    Cursor)
  20.  Cursor.findMatchingClose.doc : Doc
  21.  Cursor.following : Cursor -> '{Stream XMLEvent} ()
  22.  Cursor.following.modify : ('{Stream XMLEvent} ()
                                 ->{g} '{g1, Stream XMLEvent} ())
                                 -> Cursor
                                 ->{g} Cursor
  23.  Cursor.following.set : '{g, Stream XMLEvent} ()
                              -> Cursor
                              -> Cursor
  24.  Cursor.fromStream : '{Stream XMLEvent} () -> Cursor
  25.  Cursor.fromStream.doc : Doc
  26.  Cursor.fromXML : Text -> Cursor
  27.  Cursor.fromXML.doc : Doc
  28.  Cursor.nextEvent : Cursor -> Optional Cursor
  29.  Cursor.nextEvent.doc : Doc
  30.  Cursor.nextEvent! : Cursor ->{Abort} Cursor
  31.  Cursor.nextEvent!.doc : Doc
  32.  Cursor.parseNode : Cursor
                          ->{Throw XMLError} ( XMLNode,
                            Optional Cursor)
  33.  Cursor.preceding : Cursor -> '{Stream XMLEvent} ()
  34.  Cursor.preceding.modify : ('{Stream XMLEvent} ()
                                 ->{g} '{g1, Stream XMLEvent} ())
                                 -> Cursor
                                 ->{g} Cursor
  35.  Cursor.preceding.set : '{g, Stream XMLEvent} ()
                              -> Cursor
                              -> Cursor
  36.  Cursor.prevEvent : Cursor -> Optional Cursor
  37.  Cursor.prevEvent.doc : Doc
  38.  Cursor.prevEvent! : Cursor ->{Abort} Cursor
  39.  Cursor.prevEvent!.doc : Doc
  40.  Cursor.rewindToOpen : Cursor ->{Throw XMLError} Cursor
  41.  Cursor.rewindToOpen.doc : Doc
  42.  Cursor.rewindUntil : (XMLEvent ->{g} Boolean)
                            -> Cursor
                            ->{g} Optional Cursor
  43.  Cursor.rewindUntil.doc : Doc
  44.  Cursor.rewindUntil! : (XMLEvent -> Boolean)
                             -> Cursor
                             ->{Abort} Cursor
  45.  Cursor.rewindUntil!.doc : Doc
  46.  Cursor.skipToClose : Cursor ->{Throw XMLError} Cursor
  47.  Cursor.skipToClose.doc : Doc
  48.  Cursor.skipUntil : (XMLEvent ->{g} Boolean)
                          -> Cursor
                          ->{g} Optional Cursor
  49.  Cursor.skipUntil.doc : Doc
  50.  Cursor.skipUntil! : (XMLEvent -> Boolean)
                           -> Cursor
                           ->{Abort} Cursor
  51.  Cursor.skipUntil!.doc : Doc
  52.  Cursor.up : Cursor -> Optional Cursor
  53.  Cursor.up.doc : Doc
  54.  Cursor.withNextEvent : (Cursor ->{e} ())
                              -> Cursor
                              ->{e} ()
  55.  Cursor.withNextEvent.doc : Doc
  56.  decodeEntities : Text -> Text
  57.  decodeEntities.doc : Doc
  58.  decodeEntities.tests : [Result]
  59.  encodeEntities : Text -> Text
  60.  encodeEntities.doc : Doc
  61.  eventParser.lexer.patterns.attribute : Pattern Text
  62.  eventParser.lexer.patterns.cdata : Pattern Text
  63.  eventParser.lexer.patterns.charData : Pattern Text
  64.  eventParser.lexer.patterns.comment : Pattern Text
  65.  eventParser.lexer.patterns.dtd.externalDoctype : Pattern
                                                          Text
  66.  eventParser.lexer.patterns.dtd.internalDoctypeStart : Pattern
                                                               Text
  67.  eventParser.lexer.patterns.emptyElemTag : Pattern Text
  68.  eventParser.lexer.patterns.encName : Pattern Text
  69.  eventParser.lexer.patterns.encodingDecl : Pattern Text
  70.  eventParser.lexer.patterns.eq : Pattern Text
  71.  eventParser.lexer.patterns.etag : Pattern Text
  72.  eventParser.lexer.patterns.externalID : Pattern Text
  73.  eventParser.lexer.patterns.literals.attValue : Pattern
                                                        Text
  74.  eventParser.lexer.patterns.literals.pubidChar : Class
  75.  eventParser.lexer.patterns.literals.pubidLiteral : Pattern
                                                            Text
  76.  eventParser.lexer.patterns.literals.systemLiteral : Pattern
                                                             Text
  77.  eventParser.lexer.patterns.name.doc : Doc
  78.  eventParser.lexer.patterns.nameTokens.name : Pattern Text
  79.  eventParser.lexer.patterns.nameTokens.nameChar : Class
  80.  eventParser.lexer.patterns.nameTokens.nameStartChar : Class
  81.  eventParser.lexer.patterns.processing : Pattern Text
  82.  eventParser.lexer.patterns.references.charRef : Pattern
                                                         Text
  83.  eventParser.lexer.patterns.references.entityRef : Pattern
                                                           Text
  84.  eventParser.lexer.patterns.references.peReference : Pattern
                                                             Text
  85.  eventParser.lexer.patterns.references.reference : Pattern
                                                           Text
  86.  eventParser.lexer.patterns.sdDecl : Pattern Text
  87.  eventParser.lexer.patterns.stag : Pattern Text
  88.  eventParser.lexer.patterns.versionInfo : Pattern Text
  89.  eventParser.lexer.patterns.versionNum : Pattern Text
  90.  eventParser.lexer.patterns.whiteSpace : Pattern Text
  91.  eventParser.lexer.patterns.whiteSpace.doc : Doc
  92.  eventParser.lexer.patterns.xmlChar : Class
  93.  eventParser.lexer.patterns.xmlChar.doc : Doc
  94.  eventParser.lexer.patterns.xmlDecl : Pattern Text
  95.  eventParser.parse : Text ->{Stream XMLEvent} ()
  96.  eventParser.parse.doc : Doc
  97.  examples.atomFeed : Text
  98.  examples.atomFeed.soup : Soup
  99.  README : Doc
  100. ReleaseNotes : Doc
  101. type Soup
  102. Soup.// : Soup -> Text ->{Throw XMLError} Soup
  103. Soup.//.doc : Doc
  104. Soup.ancestors : Soup ->{Each} Soup
  105. Soup.ancestors.doc : Doc
  106. Soup.appendContents : Text
                             -> Soup
                             ->{Throw XMLError} Soup
  107. Soup.appendContents.doc : Doc
  108. Soup.attribute : Text -> Soup ->{Throw XMLError} Text
  109. Soup.attribute.doc : Doc
  110. Soup.attributes : Soup ->{Throw XMLError} Map Text Text
  111. Soup.attributes.doc : Doc
  112. Soup.children : Soup ->{Each, Throw XMLError} Soup
  113. Soup.children.doc : Doc
  114. Soup.childTags : Soup ->{Each, Throw XMLError} Soup
  115. Soup.childTags.doc : Doc
  116. Soup.contents : Soup ->{Throw XMLError} [XMLNode]
  117. Soup.contents.doc : Doc
  118. Soup.currentEvent : Soup -> XMLEvent
  119. Soup.currentEvent.doc : Doc
  120. Soup.descendants : Soup ->{Each, Throw XMLError} Soup
  121. Soup.descendants.doc : Doc
  122. Soup.descendants.test : [Result]
  123. Soup.doc : Doc
  124. Soup.findFirst : Text -> Soup ->{Throw XMLError} Soup
  125. Soup.findFirst.doc : Doc
  126. Soup.fromStream : '{Stream XMLEvent} () -> Soup
  127. Soup.fromStream.doc : Doc
  128. Soup.getAttribute : Text -> Soup ->{Throw XMLError} Text
  129. Soup.getAttribute.doc : Doc
  130. Soup.getCursor : Soup ->{Abort} Cursor
  131. Soup.getCursor.doc : Doc
  132. Soup.hasAttribute : Text
                           -> Soup
                           ->{Throw XMLError} Boolean
  133. Soup.hasAttribute.doc : Doc
  134. Soup.hasAttributes : Soup ->{Throw XMLError} Boolean
  135. Soup.hasAttributes.doc : Doc
  136. Soup.insertAfter : Text -> Soup ->{Throw XMLError} Soup
  137. Soup.insertAfter.doc : Doc
  138. Soup.insertBefore : Text -> Soup ->{Throw XMLError} Soup
  139. Soup.insertBefore.doc : Doc
  140. Soup.isTag : Soup -> Boolean
  141. Soup.isTag.doc : Doc
  142. Soup.isText : Soup -> Boolean
  143. Soup.isText.doc : Doc
  144. Soup.matchName : (Text -> Boolean)
                        -> Soup
                        ->{Each, Throw XMLError} Soup
  145. Soup.matchName.doc : Doc
  146. Soup.named : Text -> Soup ->{Each, Throw XMLError} Soup
  147. Soup.named.doc : Doc
  148. Soup.next : Soup ->{Throw XMLError} Soup
  149. Soup.next.doc : Doc
  150. Soup.nextElement : Soup ->{Throw XMLError} Soup
  151. Soup.nextElement.doc : Doc
  152. Soup.nextSibling : Soup ->{Throw XMLError} Soup
  153. Soup.nextSibling.doc : Doc
  154. Soup.node : Soup ->{Throw XMLError} XMLNode
  155. Soup.node.doc : Doc
  156. Soup.parent : Soup ->{Throw XMLError} Soup
  157. Soup.parent.doc : Doc
  158. Soup.parseXML : Text -> Soup
  159. Soup.parseXML.doc : Doc
  160. Soup.previous : Soup -> Soup
  161. Soup.previous.doc : Doc
  162. Soup.previousElement : Soup ->{Throw XMLError} Soup
  163. Soup.previousElement.doc : Doc
  164. Soup.previousSibling : Soup ->{Throw XMLError} Soup
  165. Soup.previousSibling.doc : Doc
  166. Soup.remainingEvents! : Soup ->{Stream XMLEvent} ()
  167. Soup.remainingEvents!.doc : Doc
  168. Soup.remove : Soup ->{Throw XMLError} Soup
  169. Soup.remove.doc : Doc
  170. Soup.removeAttribute : Text -> Soup -> Soup
  171. Soup.removeAttribute.doc : Doc
  172. Soup.removeContents : Soup ->{Throw XMLError} Soup
  173. Soup.removeContents.doc : Doc
  174. Soup.rewindUntil : (XMLEvent -> Boolean)
                          -> Soup
                          ->{Throw XMLError} Soup
  175. Soup.rewindUntil.doc : Doc
  176. Soup.root : Soup -> Soup
  177. Soup.root.doc : Doc
  178. Soup.setAttribute : Text
                           -> Text
                           -> Soup
                           ->{Throw XMLError} Soup
  179. Soup.setAttribute.doc : Doc
  180. Soup.setAttributes : Map Text Text -> Soup -> Soup
  181. Soup.setAttributes.doc : Doc
  182. Soup.setContents : Text -> Soup ->{Throw XMLError} Soup
  183. Soup.setContents.doc : Doc
  184. Soup.setTagName : Text -> Soup ->{Throw XMLError} Soup
  185. Soup.setTagName.doc : Doc
  186. Soup.skipUntil : (XMLEvent -> Boolean)
                        -> Soup
                        ->{Throw XMLError} Soup
  187. Soup.Soup : Cursor -> Soup
  188. Soup.tagName : Soup ->{Throw XMLError} Text
  189. Soup.tagName.doc : Doc
  190. Soup.text : Soup ->{Throw XMLError} Text
  191. Soup.text.doc : Doc
  192. Soup.texts : Soup ->{Throw XMLError} [Text]
  193. Soup.texts.doc : Doc
  194. Soup.toXML : Soup ->{Throw XMLError} Text
  195. Soup.toXML.doc : Doc
  196. Soup.tracingErrors : Text
                            -> '{Each, Throw XMLError} a
                            -> Optional [a]
  197. Soup.tracingErrors.doc : Doc
  198. Soup.trimmedTexts : Soup ->{Throw XMLError} [Text]
  199. Soup.trimmedTexts.doc : Doc
  200. Soup.unwrap : Soup ->{Throw XMLError} Soup
  201. Soup.unwrap.doc : Doc
  202. Soup.withAttribute : Text
                            -> (Text -> Boolean)
                            -> Soup
                            ->{Each, Throw XMLError} Soup
  203. Soup.withAttribute.doc : Doc
  204. Soup.withXML : Text
                      -> (Soup ->{Each, Throw XMLError} a)
                      -> Either Text [a]
  205. Soup.withXML.doc : Doc
  206. Soup.wrap : Text -> Soup ->{Throw XMLError} Soup
  207. Soup.wrap.doc : Doc
  208. tests.cdataBug : [Result]
  209. tests.docs.xml1 : Text
  210. tests.entityDecoding : [Result]
  211. tests.laxAmpersand : [Result]
  212. type XMLError
  213. XMLError.doc : Doc
  214. XMLError.inContext : Text -> XMLError -> Text
  215. XMLError.inContext.doc : Doc
  216. XMLError.ParseError : Nat -> Text -> XMLError
  217. XMLError.StructureError : Text -> XMLError
  218. XMLError.toText : XMLError -> Text
  219. XMLError.toText.doc : Doc
  220. XMLError.traceErrors : Text
                              -> '{e, Throw XMLError} a
                              ->{e} Optional a
  221. XMLError.traceErrors.doc : Doc
  222. type XMLEvent
  223. XMLEvent.Attribute : Nat -> Text -> Text -> XMLEvent
  224. XMLEvent.CData : Nat -> Text -> XMLEvent
  225. XMLEvent.CloseTag : Nat -> Text -> XMLEvent
  226. XMLEvent.Comment : Nat -> Text -> XMLEvent
  227. XMLEvent.doc : Doc
  228. XMLEvent.Doctype : Nat -> Text -> XMLEvent
  229. XMLEvent.DocumentEnd : Nat -> XMLEvent
  230. XMLEvent.DocumentStart : Nat -> XMLEvent
  231. XMLEvent.Error : Nat -> Text -> XMLEvent
  232. XMLEvent.isAttribute : XMLEvent -> Boolean
  233. XMLEvent.isAttribute.doc : Doc
  234. XMLEvent.isCloseTag : XMLEvent -> Boolean
  235. XMLEvent.isCloseTag.doc : Doc
  236. XMLEvent.isCloseTagNamed : Text -> XMLEvent -> Boolean
  237. XMLEvent.isCloseTagNamed.doc : Doc
  238. XMLEvent.isDocumentEnd : XMLEvent -> Boolean
  239. XMLEvent.isDocumentStart : XMLEvent -> Boolean
  240. XMLEvent.isError : XMLEvent -> Boolean
  241. XMLEvent.isError.doc : Doc
  242. XMLEvent.isOpenTag : XMLEvent -> Boolean
  243. XMLEvent.isOpenTag.doc : Doc
  244. XMLEvent.isOpenTagNamed : Text -> XMLEvent -> Boolean
  245. XMLEvent.isOpenTagNamed.doc : Doc
  246. XMLEvent.isProcessing : XMLEvent -> Boolean
  247. XMLEvent.isProcessing.doc : Doc
  248. XMLEvent.isStructural : XMLEvent -> Boolean
  249. XMLEvent.isStructural.doc : Doc
  250. XMLEvent.isXMLNode : XMLEvent -> Boolean
  251. XMLEvent.isXMLNode.doc : Doc
  252. XMLEvent.isXMLText : XMLEvent -> Boolean
  253. XMLEvent.isXMLText.doc : Doc
  254. XMLEvent.OpenTag : Nat -> Text -> XMLEvent
  255. XMLEvent.Processing : Nat -> Text -> Text -> XMLEvent
  256. XMLEvent.Text : Nat -> Text -> XMLEvent
  257. XMLEvent.XMLDecl : Nat
                          -> Text
                          -> Text
                          -> Boolean
                          -> XMLEvent
  258. type XMLNode
  259. XMLNode.addAttribute : Text
                              -> Text
                              -> XMLNode
                              ->{Throw XMLError} XMLNode
  260. XMLNode.addAttribute.doc : Doc
  261. XMLNode.attributes : XMLNode -> Map Text Text
  262. XMLNode.attributes.doc : Doc
  263. XMLNode.children : XMLNode -> [XMLNode]
  264. XMLNode.children.doc : Doc
  265. XMLNode.doc : Doc
  266. XMLNode.elementNamed : Text -> XMLNode
  267. XMLNode.elementNamed.doc : Doc
  268. XMLNode.toXML : XMLNode -> Text
  269. XMLNode.toXML.doc : Doc
  270. XMLNode.XMLCData : Text -> XMLNode
  271. XMLNode.XMLElement : Text
                            -> Map Text Text
                            -> [XMLNode]
                            -> XMLNode
  272. XMLNode.XMLElement.addChild : XMLNode
                                     -> XMLNode
                                     ->{Throw XMLError} XMLNode
  273. XMLNode.XMLElement.addChild.doc : Doc
  274. XMLNode.XMLText : Text -> XMLNode
```

## Code examples

``` ucm
@unison/xml/main> edit 1-5000

  ☝️

  I added 255 definitions to the top of scratch.u

  You can edit them there, then run `update` to replace the
  definitions currently in this namespace.
```
