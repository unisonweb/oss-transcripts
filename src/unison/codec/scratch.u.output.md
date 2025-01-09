# Codec

This is a library for writing compositional binary codecs that can serialize and/or deserialize Unison values to and from binary formats. Functions are provided for writing and reading values to and from
Bytes, network sockets, and files.

## Library contents list

``` ucm
@unison/codec/main> pull.without-history @unison/codec/releases/1.8.5

  Downloaded 14629 entities.

  ✅

  Successfully updated @unison/codec/main from
  @unison/codec/releases/1.8.5.

@unison/codec/main> find

  1.   ability Decode
  2.   Decode.alsoBytes : '{g, Decode} a
                          ->{g, Decode} (Bytes, a)
  3.   Decode.alsoBytes.doc : Doc
  4.   Decode.ascii : '{Decode} Text
  5.   Decode.ascii.doc : Doc
  6.   Decode.ascii.test : [Result]
  7.   Decode.asciiChar : '{Decode} Char
  8.   Decode.asciiChar.doc : Doc
  9.   Decode.asciiChar.test : [Result]
  10.  Decode.asciiNullTerminated : '{Decode} Text
  11.  Decode.asciiNullTerminated.doc : Doc
  12.  Decode.asciiNullTerminated.test : [Result]
  13.  Decode.atEof : '{g} r -> '{g, Decode} r
  14.  Decode.atEof.doc : Doc
  15.  Decode.bits : Bytes ->{DecodeBits} ()
  16.  Decode.bits.doc : Doc
  17.  Decode.bitsFromBytes : Nat ->{Decode, DecodeBits} ()
  18.  Decode.bitsFromBytes.doc : Doc
  19.  Decode.boolean : '{Decode} Boolean
  20.  Decode.boolean.doc : Doc
  21.  Decode.byte : '{Decode} Nat
  22.  Decode.byte.doc : Doc
  23.  Decode.bytesRead : {Decode} Nat
  24.  Decode.bytesRead.doc : Doc
  25.  Decode.char : Char ->{Decode} Char
  26.  Decode.char.doc : Doc
  27.  Decode.charIn : Class ->{Decode} Char
  28.  Decode.charIn.doc : Doc
  29.  Decode.compressed.zlib : '{g, Decode} t ->{g, Decode} t
  30.  Decode.compressed.zlib.doc : Doc
  31.  Decode.compressed.zlib.roundtrip : [Result]
  32.  Decode.consumeUntil : Bytes ->{Decode} Bytes
  33.  Decode.consumeUntil.doc : Doc
  34.  Decode.decodePartial : '{g, Decode} a
                              ->{g, Decode} (a, Bytes)
  35.  Decode.decodePartial.doc : Doc
  36.  Decode.decodePartial.tests : [Result]
  37.  Decode.doc : Doc
  38.  type Decode.doc.Book
  39.  Decode.doc.Book.author : Book -> Text
  40.  Decode.doc.Book.author.modify : (Text ->{g} Text)
                                       -> Book
                                       ->{g} Book
  41.  Decode.doc.Book.author.set : Text -> Book -> Book
  42.  Decode.doc.Book.Book : Text
                              -> Text
                              -> Int
                              -> Nat
                              -> Text
                              -> Bytes
                              -> Book
  43.  Decode.doc.Book.coverImage : Book -> Bytes
  44.  Decode.doc.Book.coverImage.modify : (Bytes ->{g} Bytes)
                                           -> Book
                                           ->{g} Book
  45.  Decode.doc.Book.coverImage.set : Bytes -> Book -> Book
  46.  Decode.doc.Book.isbn : Book -> Text
  47.  Decode.doc.Book.isbn.modify : (Text ->{g} Text)
                                     -> Book
                                     ->{g} Book
  48.  Decode.doc.Book.isbn.set : Text -> Book -> Book
  49.  Decode.doc.Book.pages : Book -> Nat
  50.  Decode.doc.Book.pages.modify : (Nat ->{g} Nat)
                                      -> Book
                                      ->{g} Book
  51.  Decode.doc.Book.pages.set : Nat -> Book -> Book
  52.  Decode.doc.Book.title : Book -> Text
  53.  Decode.doc.Book.title.modify : (Text ->{g} Text)
                                      -> Book
                                      ->{g} Book
  54.  Decode.doc.Book.title.set : Text -> Book -> Book
  55.  Decode.doc.Book.year : Book -> Int
  56.  Decode.doc.Book.year.modify : (Int ->{g} Int)
                                     -> Book
                                     ->{g} Book
  57.  Decode.doc.Book.year.set : Int -> Book -> Book
  58.  Decode.doc.decodeBook : '{Decode} Book
  59.  Decode.either : '{g, Decode} a
                       -> '{g, Decode} b
                       ->{g, Decode} Either a b
  60.  Decode.either.doc : Doc
  61.  Decode.eof : '{Decode} ()
  62.  Decode.eof.doc : Doc
  63.  Decode.fail : [Text] ->{Decode} a
  64.  Decode.fail.doc : Doc
  65.  Decode.failOnThrow : '{g, Decode, Throw DecodeError} a
                            ->{g, Decode} a
  66.  Decode.failOnThrow.doc : Doc
  67.  Decode.failWith : Text ->{Decode} a
  68.  Decode.failWith.doc : Doc
  69.  Decode.feed : Bytes -> '{g, Decode} a -> '{g, Decode} a
  70.  Decode.feed.doc : Doc
  71.  Decode.feed.tests.checkBytesRead : [Result]
  72.  Decode.feed.tests.feedThreeBytes : [Result]
  73.  Decode.feedPartial : Bytes
                            -> '{g, Decode} a
                            -> '{g, Decode} (a, Bytes)
  74.  Decode.feedPartial.doc : Doc
  75.  Decode.fixedAscii : Nat ->{Decode} Text
  76.  Decode.fixedAscii.deprecated : Nat
                                      ->{Decode,
                                      Throw DecodeError} Text
  77.  Decode.fixedAscii.doc : Doc
  78.  Decode.fixedSizeOrFail : Nat
                                -> '{g, Decode} a
                                ->{g, Decode} a
  79.  Decode.fixedSizeOrFail.doc : Doc
  80.  Decode.fixedSizeOrFail.impl : (Nat -> r ->{g} r)
                                     -> Nat
                                     -> '{g, Decode} r
                                     ->{g, Decode} r
  81.  Decode.fixedSizeOrFail.tests.success : [Result]
  82.  Decode.fixedSizeOrFail.tests.tooFewBytes : [Result]
  83.  Decode.fixedSizeOrFail.tests.tooManyBytes : [Result]
  84.  Decode.fixedUtf8 : Nat ->{Decode} Text
  85.  Decode.fixedUtf8.deprecated : Nat
                                     ->{Decode,
                                     Throw DecodeError} Text
  86.  Decode.fixedUtf8.doc : Doc
  87.  Decode.fromBytes : Bytes
                          -> '{g, Decode, DecodeBits} a
                          ->{g, Throw DecodeError} a
  88.  Decode.fromBytes.doc : Doc
  89.  Decode.fromConnection : Connection
                               -> '{g, Decode, DecodeBits} a
                               ->{g, IO, Exception} a
  90.  Decode.fromConnection.doc : Doc
  91.  Decode.fromHandle : Handle
                           -> '{g, Decode, DecodeBits} a
                           ->{g, IO, Exception} a
  92.  Decode.fromHandle.doc : Doc
  93.  Decode.fromSocket : Nat
                           -> Socket
                           -> '{g, Decode, DecodeBits} a
                           ->{g, IO, Exception} a
  94.  Decode.fromSocket.doc : Doc
  95.  Decode.fromStream : '{g, Decode, DecodeBits} a
                           -> '{g, Stream Bytes} r
                           ->{g, Throw DecodeError} a
  96.  Decode.fromStream.doc : Doc
  97.  Decode.fromStream.tests : [Result]
  98.  Decode.fromStreamPartial : '{g, Decode, DecodeBits} a
                                  -> '{g, Stream Bytes} r
                                  ->{g, Throw DecodeError} ( a,
                                    '{g, Stream Bytes} r)
  99.  Decode.fromStreamPartial.doc : Doc
  100. Decode.fromStreamPartial.tests : [Result]
  101. Decode.handleFailure : (Bytes -> [Text] ->{g, Decode} a)
                              -> '{g, Decode} a
                              ->{g, Decode} a
  102. Decode.indentLabels : Text
                             -> '{g, Decode} a
                             ->{g, Decode} a
  103. Decode.int16be : '{Decode} Int
  104. Decode.int16be.doc : Doc
  105. Decode.int16le : '{Decode} Int
  106. Decode.int16le.doc : Doc
  107. Decode.int32be : '{Decode} Int
  108. Decode.int32be.doc : Doc
  109. Decode.int32le : '{Decode} Int
  110. Decode.int32le.doc : Doc
  111. Decode.int64be : '{Decode} Int
  112. Decode.int64be.doc : Doc
  113. Decode.int64le : '{Decode} Int
  114. Decode.int64le.doc : Doc
  115. Decode.isDone : '{g, Decode} a ->{g, Decode} Boolean
  116. Decode.isDone.doc : Doc
  117. Decode.isEOF : '{Decode} Boolean
  118. Decode.isEOF.doc : Doc
  119. Decode.label : Text -> '{g, Decode} a ->{g, Decode} a
  120. Decode.label.doc : Doc
  121. Decode.labels : [Text] -> '{g, Decode} a ->{g, Decode} a
  122. Decode.labels.doc : Doc
  123. Decode.list : Nat -> '{g, Decode} a ->{g, Decode} [a]
  124. Decode.list.doc : Doc
  125. Decode.literalBytes : Bytes ->{Decode} Bytes
  126. Decode.literalBytes.doc : Doc
  127. Decode.lookAhead : '{g, Decode} a ->{g, Decode} a
  128. Decode.lookAhead.doc : Doc
  129. Decode.lookAhead.test.ex1 : [Result]
  130. Decode.lookAheadMaybe : '{g, Decode} Optional a
                               ->{g, Decode} Optional a
  131. Decode.lookAheadMaybe.doc : Doc
  132. Decode.many : '{g, Decode} a ->{g, Decode} [a]
  133. Decode.many.doc : Doc
  134. Decode.manyUntil : '{g, Decode} a
                          -> '{g, Decode} b
                          ->{g, Decode} [a]
  135. Decode.manyUntil.doc : Doc
  136. Decode.modifyLabels : ([Text] -> [Text])
                             -> '{g, Decode} a
                             ->{g, Decode} a
  137. Decode.moreBytes : {Decode} (Optional Bytes)
  138. Decode.moreBytes.doc : Doc
  139. Decode.nat16be : '{Decode} Nat
  140. Decode.nat16be.doc : Doc
  141. Decode.nat16le : '{Decode} Nat
  142. Decode.nat16le.doc : Doc
  143. Decode.nat32be : '{Decode} Nat
  144. Decode.nat32be.doc : Doc
  145. Decode.nat32le : '{Decode} Nat
  146. Decode.nat32le.doc : Doc
  147. Decode.nat64be : '{Decode} Nat
  148. Decode.nat64be.doc : Doc
  149. Decode.nat64le : '{Decode} Nat
  150. Decode.nat64le.doc : Doc
  151. Decode.nextBytes : Nat ->{Decode} Bytes
  152. Decode.nextBytes.doc : Doc
  153. Decode.nextBytes.tests : [Result]
  154. Decode.nullTerminated : '{g, Decode} a ->{g, Decode} a
  155. Decode.nullTerminated.doc : Doc
  156. Decode.nullTerminatedList : '{g, Decode} a
                                   ->{g, Decode} [a]
  157. Decode.nullTerminatedList.doc : Doc
  158. Decode.nullTerminatedMap : '{g, Decode} k
                                  -> '{h, Decode} v
                                  ->{g, h, Decode} Map k v
  159. Decode.nullTerminatedMap.doc : Doc
  160. Decode.optional : '{g} o ->{g, Decode} Optional o
  161. Decode.optional.doc : Doc
  162. Decode.or : '{g, Decode} a
                   -> '{g, Decode} a
                   ->{g, Decode} a
  163. Decode.or.doc : Doc
  164. Decode.pair : '{g, Decode} a
                     -> '{h, Decode} b
                     ->{g, h, Decode} (a, b)
  165. Decode.pair.doc : Doc
  166. Decode.patternCaptures : '{Decode} Text
                                -> Pattern Text
                                ->{Decode} [Text]
  167. Decode.patternCaptures.doc : Doc
  168. Decode.peek : '{Decode} Optional Nat
  169. Decode.peek.doc : Doc
  170. Decode.peekChar : '{Decode} Optional Char
  171. Decode.peekChar.doc : Doc
  172. Decode.peekN : Nat ->{Decode} Bytes
  173. Decode.peekN.doc : Doc
  174. Decode.remainder : '{Decode} Bytes
  175. Decode.remainder.doc : Doc
  176. Decode.remit : Bytes ->{Decode} ()
  177. Decode.remit.doc : Doc
  178. Decode.remit.tests.remitStreaming : [Result]
  179. Decode.remit.tests.remitUsingBytes : [Result]
  180. Decode.remit.tests.testRemit : '{Decode} ([Nat], [Nat])
  181. Decode.runDecode : '{g, Decode, DecodeBits} a
                          -> Bytes
                          ->{g, Throw DecodeError} a
  182. Decode.runDecode.doc : Doc
  183. Decode.sepBy : '{g, Decode} a
                      -> '{g, Decode} b
                      ->{g, Decode} [a]
  184. Decode.sepBy.doc : Doc
  185. Decode.sepBy1 : '{g, Decode} a
                       -> '{g, Decode} b
                       ->{g, Decode} List.Nonempty a
  186. Decode.sepBy1.doc : Doc
  187. Decode.skip : Nat ->{Decode} ()
  188. Decode.skip.doc : Doc
  189. Decode.skipMany : '{g, Decode} a ->{g, Decode} ()
  190. Decode.skipMany.doc : Doc
  191. Decode.skipMany1 : '{g, Decode} a ->{g, Decode} ()
  192. Decode.skipMany1.doc : Doc
  193. Decode.skipUntil : Bytes ->{Decode} ()
  194. Decode.skipUntil.doc : Doc
  195. Decode.some : '{g, Decode} a
                     ->{g, Decode} List.Nonempty a
  196. Decode.some.doc : Doc
  197. Decode.someDigits : '{Decode} Nat
  198. Decode.someDigits.doc : Doc
  199. Decode.someDigits.tests.digits : [Result]
  200. Decode.someDigits.tests.empty : [Result]
  201. Decode.terminate : '{g, Decode} a ->{g, Decode} a
  202. Decode.terminate.doc : Doc
  203. Decode.tests.checkDecodeResult : '{g, Decode, DecodeBits} r
                                        -> r
                                        -> Bytes
                                        -> Bytes
                                        ->{g,
                                        Exception,
                                        Each,
                                        Random} ()
  204. Decode.tests.checkDecodeResult.doc : Doc
  205. Decode.tests.checkDecodeResultBy : (r
                                          ->{h1} r
                                          ->{h} Boolean)
                                          -> '{g,
                                          Decode,
                                          DecodeBits} r
                                          -> r
                                          -> Bytes
                                          -> Bytes
                                          ->{g,
                                          Exception,
                                          Each,
                                          Random} ()
  206. Decode.tests.checkDecodeResultBy.doc : Doc
  207. Decode.text : Text ->{Decode} Text
  208. Decode.text.doc : Doc
  209. Decode.tracingOr : '{g, Decode} a
                          -> '{g, Decode} a
                          ->{g, Decode} a
  210. Decode.try : '{g, Decode} a ->{g, Decode} a
  211. Decode.try.doc : Doc
  212. Decode.trySilently : '{g, Decode} a ->{g, Decode} a
  213. Decode.trySilently.doc : Doc
  214. Decode.unexpectedEof : '{Decode} a
  215. Decode.universal : '{IO, Decode} a
  216. Decode.universal.doc : Doc
  217. Decode.until : Bytes -> '{g, Decode} a ->{g, Decode} a
  218. Decode.until.doc : Doc
  219. Decode.until.tests : [Result]
  220. Decode.utf8 : '{Decode} Text
  221. Decode.utf8.doc : Doc
  222. Decode.utf8NullTerminated : '{Decode} Text
  223. Decode.utf8NullTerminated.doc : Doc
  224. Decode.value : '{Decode} Value
  225. Decode.value.doc : Doc
  226. Decode.variableSizeBytes : '{g, Decode} Nat
                                  -> '{g, Decode} a
                                  ->{g, Decode} a
  227. Decode.variableSizeBytes.doc : Doc
  228. ability DecodeBits
  229. type DecodeBits.Alignment
  230. DecodeBits.Alignment.AlignLeft : Alignment
  231. DecodeBits.Alignment.AlignRight : Alignment
  232. DecodeBits.Alignment.doc : Doc
  233. DecodeBits.bit : '{DecodeBits} Boolean
  234. DecodeBits.bit.doc : Doc
  235. DecodeBits.currentOffset : '{DecodeBits} Nat
  236. DecodeBits.currentOffset.doc : Doc
  237. type DecodeBits.DecoderState
  238. DecodeBits.DecoderState.bitOffset : DecoderState -> Nat
  239. DecodeBits.DecoderState.bitOffset.doc : Doc
  240. DecodeBits.DecoderState.DecoderState : Bytes
                                              -> Nat
                                              -> DecoderState
  241. DecodeBits.DecoderState.doc : Doc
  242. DecodeBits.DecoderState.input : DecoderState -> Bytes
  243. DecodeBits.DecoderState.input.doc : Doc
  244. DecodeBits.doc : Doc
  245. DecodeBits.examples.decodeIpHeader : '{Decode,
                                            DecodeBits,
                                            Throw DecodeError} IpHeader
  246. type DecodeBits.examples.IpAddress
  247. DecodeBits.examples.IpAddress.IpAddress : Nat
                                                 -> IpAddress
  248. type DecodeBits.examples.IpHeader
  249. DecodeBits.examples.IpHeader.destinationAddress : IpHeader
                                                         -> IpV4Address
  250. DecodeBits.examples.IpHeader.destinationAddress.modify : (IpV4Address
                                                                ->{g} IpV4Address)
                                                                -> IpHeader
                                                                ->{g} IpHeader
  251. DecodeBits.examples.IpHeader.destinationAddress.set : IpV4Address
                                                             -> IpHeader
                                                             -> IpHeader
  252. DecodeBits.examples.IpHeader.fragmentOffset : IpHeader
                                                     -> Nat
  253. DecodeBits.examples.IpHeader.fragmentOffset.modify : (Nat
                                                            ->{g} Nat)
                                                            -> IpHeader
                                                            ->{g} IpHeader
  254. DecodeBits.examples.IpHeader.fragmentOffset.set : Nat
                                                         -> IpHeader
                                                         -> IpHeader
  255. DecodeBits.examples.IpHeader.identification : IpHeader
                                                     -> Nat
  256. DecodeBits.examples.IpHeader.identification.modify : (Nat
                                                            ->{g} Nat)
                                                            -> IpHeader
                                                            ->{g} IpHeader
  257. DecodeBits.examples.IpHeader.identification.set : Nat
                                                         -> IpHeader
                                                         -> IpHeader
  258. DecodeBits.examples.IpHeader.internetHeaderLength : IpHeader
                                                           -> Nat
  259. DecodeBits.examples.IpHeader.internetHeaderLength.modify : (Nat
                                                                  ->{g} Nat)
                                                                  -> IpHeader
                                                                  ->{g} IpHeader
  260. DecodeBits.examples.IpHeader.internetHeaderLength.set : Nat
                                                               -> IpHeader
                                                               -> IpHeader
  261. DecodeBits.examples.IpHeader.IpHeader : Nat
                                               -> Nat
                                               -> TypeOfService
                                               -> Nat
                                               -> Nat
                                               -> Boolean
                                               -> Boolean
                                               -> Nat
                                               -> Duration
                                               -> Nat
                                               -> IpV4Address
                                               -> IpV4Address
                                               -> Bytes
                                               -> IpHeader
  262. DecodeBits.examples.IpHeader.lastFragment : IpHeader
                                                   -> Boolean
  263. DecodeBits.examples.IpHeader.lastFragment.modify : (Boolean
                                                          ->{g} Boolean)
                                                          -> IpHeader
                                                          ->{g} IpHeader
  264. DecodeBits.examples.IpHeader.lastFragment.set : Boolean
                                                       -> IpHeader
                                                       -> IpHeader
  265. DecodeBits.examples.IpHeader.mayBeFragment : IpHeader
                                                    -> Boolean
  266. DecodeBits.examples.IpHeader.mayBeFragment.modify : (Boolean
                                                           ->{g} Boolean)
                                                           -> IpHeader
                                                           ->{g} IpHeader
  267. DecodeBits.examples.IpHeader.mayBeFragment.set : Boolean
                                                        -> IpHeader
                                                        -> IpHeader
  268. DecodeBits.examples.IpHeader.options : IpHeader -> Bytes
  269. DecodeBits.examples.IpHeader.options.modify : (Bytes
                                                     ->{g} Bytes)
                                                     -> IpHeader
                                                     ->{g} IpHeader
  270. DecodeBits.examples.IpHeader.options.set : Bytes
                                                  -> IpHeader
                                                  -> IpHeader
  271. DecodeBits.examples.IpHeader.protocol : IpHeader -> Nat
  272. DecodeBits.examples.IpHeader.protocol.modify : (Nat
                                                      ->{g} Nat)
                                                      -> IpHeader
                                                      ->{g} IpHeader
  273. DecodeBits.examples.IpHeader.protocol.set : Nat
                                                   -> IpHeader
                                                   -> IpHeader
  274. DecodeBits.examples.IpHeader.sourceAddress : IpHeader
                                                    -> IpV4Address
  275. DecodeBits.examples.IpHeader.sourceAddress.modify : (IpV4Address
                                                           ->{g} IpV4Address)
                                                           -> IpHeader
                                                           ->{g} IpHeader
  276. DecodeBits.examples.IpHeader.sourceAddress.set : IpV4Address
                                                        -> IpHeader
                                                        -> IpHeader
  277. DecodeBits.examples.IpHeader.timeToLive : IpHeader
                                                 -> Duration
  278. DecodeBits.examples.IpHeader.timeToLive.modify : (Duration
                                                        ->{g} Duration)
                                                        -> IpHeader
                                                        ->{g} IpHeader
  279. DecodeBits.examples.IpHeader.timeToLive.set : Duration
                                                     -> IpHeader
                                                     -> IpHeader
  280. DecodeBits.examples.IpHeader.totalLength : IpHeader
                                                  -> Nat
  281. DecodeBits.examples.IpHeader.totalLength.modify : (Nat
                                                         ->{g} Nat)
                                                         -> IpHeader
                                                         ->{g} IpHeader
  282. DecodeBits.examples.IpHeader.totalLength.set : Nat
                                                      -> IpHeader
                                                      -> IpHeader
  283. DecodeBits.examples.IpHeader.typeOfService : IpHeader
                                                    -> TypeOfService
  284. DecodeBits.examples.IpHeader.typeOfService.modify : (TypeOfService
                                                           ->{g} TypeOfService)
                                                           -> IpHeader
                                                           ->{g} IpHeader
  285. DecodeBits.examples.IpHeader.typeOfService.set : TypeOfService
                                                        -> IpHeader
                                                        -> IpHeader
  286. DecodeBits.examples.IpHeader.version : IpHeader -> Nat
  287. DecodeBits.examples.IpHeader.version.modify : (Nat
                                                     ->{g} Nat)
                                                     -> IpHeader
                                                     ->{g} IpHeader
  288. DecodeBits.examples.IpHeader.version.set : Nat
                                                  -> IpHeader
                                                  -> IpHeader
  289. type DecodeBits.examples.IpV4Address
  290. DecodeBits.examples.IpV4Address.IpV4Address : Nat
                                                     -> Nat
                                                     -> Nat
                                                     -> Nat
                                                     -> IpV4Address
  291. DecodeBits.examples.rawIpHeader : Bytes
  292. type DecodeBits.examples.TypeOfService
  293. DecodeBits.examples.TypeOfService.DecodeBits.examples.TypeOfService : Nat
                                                                             -> Boolean
                                                                             -> Boolean
                                                                             -> Boolean
                                                                             -> TypeOfService
  294. DecodeBits.examples.TypeOfService.highReliability : TypeOfService
                                                           -> Boolean
  295. DecodeBits.examples.TypeOfService.highReliability.modify : (Boolean
                                                                  ->{g} Boolean)
                                                                  -> TypeOfService
                                                                  ->{g} TypeOfService
  296. DecodeBits.examples.TypeOfService.highReliability.set : Boolean
                                                               -> TypeOfService
                                                               -> TypeOfService
  297. DecodeBits.examples.TypeOfService.highThroughput : TypeOfService
                                                          -> Boolean
  298. DecodeBits.examples.TypeOfService.highThroughput.modify : (Boolean
                                                                 ->{g} Boolean)
                                                                 -> TypeOfService
                                                                 ->{g} TypeOfService
  299. DecodeBits.examples.TypeOfService.highThroughput.set : Boolean
                                                              -> TypeOfService
                                                              -> TypeOfService
  300. DecodeBits.examples.TypeOfService.lowDelay : TypeOfService
                                                    -> Boolean
  301. DecodeBits.examples.TypeOfService.lowDelay.modify : (Boolean
                                                           ->{g} Boolean)
                                                           -> TypeOfService
                                                           ->{g} TypeOfService
  302. DecodeBits.examples.TypeOfService.lowDelay.set : Boolean
                                                        -> TypeOfService
                                                        -> TypeOfService
  303. DecodeBits.examples.TypeOfService.precedence : TypeOfService
                                                      -> Nat
  304. DecodeBits.examples.TypeOfService.precedence.modify : (Nat
                                                             ->{g} Nat)
                                                             -> TypeOfService
                                                             ->{g} TypeOfService
  305. DecodeBits.examples.TypeOfService.precedence.set : Nat
                                                          -> TypeOfService
                                                          -> TypeOfService
  306. DecodeBits.fail : [Text] ->{DecodeBits} a
  307. DecodeBits.feed : Bytes ->{DecodeBits} ()
  308. DecodeBits.feed.doc : Doc
  309. DecodeBits.fromEmpty : '{g, DecodeBits} a
                              ->{g, Throw DecodeError} a
  310. DecodeBits.fromEmpty.doc : Doc
  311. DecodeBits.getBits : Alignment
                            -> Nat
                            ->{DecodeBits} Bytes
  312. DecodeBits.getBits.doc : Doc
  313. DecodeBits.getDecoderState : {DecodeBits} DecoderState
  314. DecodeBits.getInt : Nat ->{DecodeBits} Int
  315. DecodeBits.getInt.doc : Doc
  316. DecodeBits.isEmpty : '{DecodeBits} Boolean
  317. DecodeBits.isEmpty.doc : Doc
  318. DecodeBits.nextByte : '{DecodeBits} ()
  319. DecodeBits.nextByte.doc : Doc
  320. DecodeBits.remaining : '{DecodeBits} Nat
  321. DecodeBits.remaining.doc : Doc
  322. DecodeBits.run : Bytes
                        -> '{g, DecodeBits} a
                        ->{g, Throw DecodeError} a
  323. DecodeBits.run.doc : Doc
  324. DecodeBits.setDecoderState : DecoderState
                                    ->{DecodeBits} ()
  325. DecodeBits.skip : Nat ->{DecodeBits} ()
  326. DecodeBits.skip.doc : Doc
  327. DecodeBits.wordN : Nat ->{DecodeBits} Nat
  328. DecodeBits.wordN.doc : Doc
  329. type DecodeError
  330. DecodeError.DecodeError : [Text]
                                 -> Position
                                 -> Bytes
                                 -> DecodeError
  331. DecodeError.frame : DecodeError -> Bytes
  332. DecodeError.frame.modify : (Bytes ->{g} Bytes)
                                  -> DecodeError
                                  ->{g} DecodeError
  333. DecodeError.frame.set : Bytes
                               -> DecodeError
                               -> DecodeError
  334. DecodeError.position : DecodeError -> Position
  335. DecodeError.position.modify : (Position ->{g} Position)
                                     -> DecodeError
                                     ->{g} DecodeError
  336. DecodeError.position.set : Position
                                  -> DecodeError
                                  -> DecodeError
  337. DecodeError.toFailure : DecodeError -> Failure
  338. DecodeError.toFailure.doc : Doc
  339. DecodeError.trace : DecodeError -> [Text]
  340. DecodeError.trace.modify : ([Text] ->{g} [Text])
                                  -> DecodeError
                                  ->{g} DecodeError
  341. DecodeError.trace.set : [Text]
                               -> DecodeError
                               -> DecodeError
  342. encode.ascii : Text ->{Stream Bytes} ()
  343. encode.asciiChar : Char ->{Stream Bytes} ()
  344. encode.asciiChar.doc : Doc
  345. encode.byte : Nat ->{Stream Bytes} ()
  346. encode.byte.doc : Doc
  347. encode.compressed.zlib : (a ->{g, Stream Bytes} ())
                                -> a
                                ->{g, Stream Bytes} ()
  348. encode.compressed.zlib.doc : Doc
  349. encode.int16be : Int ->{Stream Bytes} ()
  350. encode.int16be.doc : Doc
  351. encode.int16le : Int ->{Stream Bytes} ()
  352. encode.int16le.doc : Doc
  353. encode.int32be : Int ->{Stream Bytes} ()
  354. encode.int32be.doc : Doc
  355. encode.int32le : Int ->{Stream Bytes} ()
  356. encode.int32le.doc : Doc
  357. encode.int64be : Int ->{Stream Bytes} ()
  358. encode.int64be.doc : Doc
  359. encode.int64le : Int ->{Stream Bytes} ()
  360. encode.int64le.doc : Doc
  361. encode.list : (a ->{g, Stream Bytes} ())
                     -> [a]
                     ->{g, Stream Bytes} ()
  362. encode.nat16be : Nat ->{Stream Bytes} ()
  363. encode.nat16be.doc : Doc
  364. encode.nat16le : Nat ->{Stream Bytes} ()
  365. encode.nat16le.doc : Doc
  366. encode.nat32be : Nat ->{Stream Bytes} ()
  367. encode.nat32be.doc : Doc
  368. encode.nat32le : Nat ->{Stream Bytes} ()
  369. encode.nat32le.doc : Doc
  370. encode.nat64be : Nat ->{Stream Bytes} ()
  371. encode.nat64be.doc : Doc
  372. encode.nat64le : Nat ->{Stream Bytes} ()
  373. encode.nat64le.doc : Doc
  374. encode.nullTerminatedString : Text ->{Stream Bytes} ()
  375. encode.nullTerminatedString.doc : Doc
  376. encode.replicated : Nat
                           -> '{g, Stream Bytes} a
                           ->{g, Stream Bytes} [a]
  377. encode.toBytes : '{g, Stream Bytes} () ->{g} Bytes
  378. encode.toBytes.doc : Doc
  379. encode.toConnection : Connection
                             -> '{g, EncodeBits, Stream Bytes} a
                             ->{g, IO, Exception} a
  380. encode.toConnection.doc : Doc
  381. encode.toSocket : Socket
                         -> '{g, EncodeBits, Stream Bytes} a
                         ->{g, IO, Exception} a
  382. encode.toSocket.doc : Doc
  383. encode.universal : a ->{Stream Bytes} ()
  384. encode.universal.doc : Doc
  385. encode.utf8 : Text ->{Stream Bytes} ()
  386. encode.utf8.doc : Doc
  387. encode.value : Value ->{Stream Bytes} ()
  388. encode.value.doc : Doc
  389. encode.variableSizeBytes : (Nat ->{g, Stream Bytes} ())
                                  -> (a ->{g, Stream Bytes} ())
                                  -> a
                                  ->{g, Stream Bytes} ()
  390. encode.variableSizeBytes.doc : Doc
  391. ability EncodeBits
  392. EncodeBits.encode : '{f, EncodeBits} a
                           -> (a ->{g} EncoderState ->{h} b)
                           ->{f, g, h} b
  393. EncodeBits.encode.doc : Doc
  394. type EncodeBits.EncoderState
  395. EncodeBits.EncoderState.currentBit : EncoderState -> Nat
  396. EncodeBits.EncoderState.currentBit.doc : Doc
  397. EncodeBits.EncoderState.currentWord : EncoderState -> Nat
  398. EncodeBits.EncoderState.currentWord.doc : Doc
  399. EncodeBits.EncoderState.encodedBytes : EncoderState
                                              -> Bytes
  400. EncodeBits.EncoderState.encodedBytes.doc : Doc
  401. EncodeBits.EncoderState.EncoderState : Bytes
                                              -> Nat
                                              -> Nat
                                              -> EncoderState
  402. EncodeBits.examples.checksum : Bytes -> Nat
  403. EncodeBits.examples.checksum.doc : Doc
  404. EncodeBits.examples.encodeIpHeader : IpHeader
                                            ->{Stream Bytes} ()
  405. EncodeBits.examples.ipHeader : IpHeader
  406. EncodeBits.getEncoderState : {EncodeBits} EncoderState
  407. EncodeBits.putBit : Boolean ->{EncodeBits} ()
  408. EncodeBits.putBits : Nat -> Bytes ->{EncodeBits} ()
  409. EncodeBits.putBits.doc : Doc
  410. EncodeBits.putWordN : Nat -> Nat ->{EncodeBits} ()
  411. EncodeBits.putWordN.doc : Doc
  412. EncodeBits.setEncoderState : EncoderState
                                    ->{EncodeBits} ()
  413. EncodeBits.toBytes : '{g, EncodeBits} () ->{g} Bytes
  414. EncodeBits.toBytes.doc : Doc
  415. EncodeBits.toStream : '{g, EncodeBits} a
                             ->{g, Stream Bytes} a
  416. EncodeBits.toStream.doc : Doc
  417. type EncodeError
  418. EncodeError.EncodeError : Text -> EncodeError
  419. type Position
  420. Position.Position : Nat -> Position
  421. README : Doc
  422. README.encodeBook : Book ->{Stream Bytes} ()
  423. ReleaseNotes : Doc
  424. up.base.test.ensureFailure : '{g, Exception} t
                                    ->{g, Exception} ()
  425. up.base.test.ensureThrows : '{g, Throw e} t
                                   ->{g, Exception} ()
  426. up.Char.toUtf8 : Char -> Bytes
  427. withConnection : Connection
                        -> '{g,
                        EncodeBits,
                        Decode,
                        DecodeBits,
                        Stream Bytes} r
                        ->{g, IO, Exception} r
  428. withConnection.doc : Doc
  429. withSocket : Nat
                    -> Socket
                    -> '{g,
                    EncodeBits,
                    Decode,
                    DecodeBits,
                    Stream Bytes} r
                    ->{g, IO, Exception} r
  430. withSocket.doc : Doc
```

## Code examples

``` ucm
@unison/codec/main> edit 1-5000

  ☝️

  I added 407 definitions to the top of scratch.u

  You can edit them there, then run `update` to replace the
  definitions currently in this namespace.
```
