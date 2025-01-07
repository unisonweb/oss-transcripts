# Http

This project contains functions for working with HTTP requests and responses. It contains both HTTP client and HTTP server utilities.

## Library contents list

``` ucm
@unison/http/main> pull.without-history @unison/http/releases/3.8.0

  Downloaded 23887 entities.

  ✅

  Successfully updated @unison/http/main from
  @unison/http/releases/3.8.0.

@unison/http/main> find

  1.   type Body
  2.   Body.Body : Bytes -> Body
  3.   Body.decodeBody : msg
                         -> (msg -> Headers)
                         -> (Body -> msg -> msg)
                         ->{Decode} (msg, Headers)
  4.   Body.decodeChunkedBody : Boolean
                                ->{Decode} (Body, Headers)
  5.   Body.decodeNonChunkedBody : Headers ->{Decode} Body
  6.   Body.decompressBody : Headers -> Body -> Either Text Body
  7.   Body.empty : Body
  8.   Body.formEncoded : Query -> Body
  9.   Body.formEncoded.tests : [Result]
  10.  Body.fromText : Text -> Body
  11.  Body.fromText.doc : Doc
  12.  Body.standardContentDecoders : data.Map
                                        Text
                                        (Bytes
                                        ->{g} Either Text Bytes)
  13.  Body.toBytes : Body -> Bytes
  14.  type client.Config
  15.  client.Config.Config : Optional proxy.Config
                              -> client.Config
  16.  client.Config.default : client.Config
  17.  client.Config.proxy : client.Config
                             -> Optional proxy.Config
  18.  client.Config.proxy.modify : (Optional proxy.Config
                                    ->{g} Optional proxy.Config)
                                    -> client.Config
                                    ->{g} client.Config
  19.  client.Config.proxy.set : Optional proxy.Config
                                 -> client.Config
                                 -> client.Config
  20.  client.Config.proxyPresence : client.Config
                                     -> ProxyPresence
  21.  client.Config.withProxy : HostName
                                 -> Port
                                 -> client.Config
                                 -> client.Config
  22.  client.Config.withProxy.doc : Doc
  23.  client.examples.query : '{IO, Exception} HttpResponse
  24.  client.examples.simple : '{IO, Exception} HttpResponse
  25.  client.examples.trailingSlash : Path
  26.  type client.failure.ConnectFailure
  27.  type client.failure.InternalFailure
  28.  type client.failure.Unsupported
  29.  client.failure.unsupportedScheme : Scheme -> Failure
  30.  type client.failure.UpstreamFailure
  31.  type client.failure.WebSocketHandsakeFailure
  32.  ability client.Http
  33.  client.Http.configuredHandler : client.Config
                                       -> Request {Http} a
                                       ->{IO} a
  34.  client.Http.configuredHandler.connect : client.Config
                                               -> HttpRequest
                                               ->{IO, Exception} Either
                                                 HttpResponse
                                                 Connection
  35.  client.Http.configuredHandler.connectNoProxy : URI
                                                      ->{IO,
                                                      Exception} Connection
  36.  client.Http.configuredHandler.connectViaProxy : proxy.Config
                                                       -> HttpRequest
                                                       ->{IO,
                                                       Exception} Either
                                                         HttpResponse
                                                         Connection
  37.  client.Http.configuredHandler.connectViaProxy.impl : proxy.Config
                                                            -> Optional
                                                              ClientConfig
                                                            -> HostName
                                                            -> Port
                                                            -> Headers
                                                            ->{IO,
                                                            Exception} Either
                                                              HttpResponse
                                                              Connection
  38.  client.Http.configuredHandler.http : client.Config
                                            -> HttpRequest
                                            ->{Decode,
                                            Stream Bytes} HttpResponse
  39.  client.Http.configuredHandler.webSocket : client.Config
                                                 -> Connection
                                                 -> HttpRequest
                                                 ->{IO, Random} Either
                                                   Failure
                                                   WebSocket
  40.  client.Http.delete : URI ->{Exception, Http} HttpResponse
  41.  client.Http.doc : Doc
  42.  client.Http.get : URI ->{Exception, Http} HttpResponse
  43.  client.Http.handler : Request {Http} a ->{IO} a
  44.  client.Http.handler.doc : Doc
  45.  client.Http.patch : URI
                           -> Body
                           ->{Exception, Http} HttpResponse
  46.  client.Http.post : URI
                          -> Body
                          ->{Exception, Http} HttpResponse
  47.  client.Http.put : URI
                         -> Body
                         ->{Exception, Http} HttpResponse
  48.  client.Http.request : HttpRequest
                             ->{Exception, Http} HttpResponse
  49.  client.Http.run : '{g, Http} a ->{g, IO} a
  50.  client.Http.run.tests.testHttp : '{IO} [Result]
  51.  client.Http.run.tests.testHttps : '{IO} [Result]
  52.  client.Http.runConfigured : client.Config
                                   -> '{g, Http} a
                                   ->{g, IO} a
  53.  client.Http.runConfigured.tests.testProxyHttp : '{IO} [Result]
  54.  client.Http.runConfigured.tests.testProxyHttp.doc : Doc
  55.  client.Http.runConfigured.tests.testProxyHttps : '{IO} [Result]
  56.  client.Http.runConfigured.tests.testProxyHttps.doc : Doc
  57.  client.Http.tryDelete : URI
                               ->{Http} Either
                                 Failure HttpResponse
  58.  client.Http.tryGet : URI
                            ->{Http} Either Failure HttpResponse
  59.  client.Http.tryPatch : URI
                              -> Body
                              ->{Http} Either
                                Failure HttpResponse
  60.  client.Http.tryPost : URI
                             ->{Http} Body
                             ->{Http} Either
                               Failure HttpResponse
  61.  client.Http.tryPut : URI
                            -> Body
                            ->{Http} Either Failure HttpResponse
  62.  client.Http.tryRequest : HttpRequest
                                ->{Http} Either
                                  Failure HttpResponse
  63.  ability client.HttpWebSocket
  64.  client.HttpWebSocket.configuredHandler : client.Config
                                                -> Request
                                                  {HttpWebSocket}
                                                  a
                                                ->{IO} a
  65.  client.HttpWebSocket.handler : Request {HttpWebSocket} a
                                      ->{IO} a
  66.  client.HttpWebSocket.tryWebSocket : HttpRequest
                                           ->{HttpWebSocket} Either
                                             Failure WebSocket
  67.  client.HttpWebSocket.webSocket : HttpRequest
                                        ->{Exception,
                                        HttpWebSocket} WebSocket
  68.  type client.proxy.Config
  69.  client.proxy.Config.Config : Authority -> proxy.Config
  70.  client.proxy.Config.proxy : proxy.Config -> Authority
  71.  client.proxy.Config.proxy.modify : (Authority
                                          ->{g} Authority)
                                          -> proxy.Config
                                          ->{g} proxy.Config
  72.  client.proxy.Config.proxy.set : Authority
                                       -> proxy.Config
                                       -> proxy.Config
  73.  client.proxy.connectRequest : proxy.Config
                                     -> HttpRequest
                                     -> HttpRequest
  74.  client.proxy.connectRequest.impl : proxy.Config
                                          -> HostName
                                          -> Port
                                          -> Headers
                                          -> HttpRequest
  75.  client.proxy.connectRequest.tests.example1 : [Result]
  76.  client.proxy.defaultProxyHeaders : Headers -> Headers
  77.  client.proxy.host : proxy.Config -> HostName
  78.  client.proxy.port : proxy.Config -> Port
  79.  type client.proxy.ProxyPresence
  80.  client.proxy.ProxyPresence.NoProxy : ProxyPresence
  81.  client.proxy.ProxyPresence.Proxy : ProxyPresence
  82.  client.README : Doc
  83.  client.test.formatIOError : IOError -> Text
  84.  client.test.header_lines : [Text]
  85.  client.test.localProxyConfig : proxy.Config
  86.  client.test.redir_response_bytes : Bytes
  87.  client.test.redir_response_lines : [Text]
  88.  client.test.redir_response_text : Text
  89.  client.test.socketSlurp : Socket ->{IO, Exception} Bytes
  90.  client.test.testGet : '{IO, Exception} Text
  91.  client.test.unisonDocs : URI
  92.  client.up.base.IO.net.Connection.receiveByteStream : Connection
                                                            -> '{IO,
                                                            Exception,
                                                            Stream
                                                              Bytes} ()
  93.  type Headers
  94.  Headers.== : Headers -> Headers -> Boolean
  95.  Headers.add : Text -> Text -> Headers -> Headers
  96.  Headers.asBytes : Headers -> Bytes
  97.  Headers.asBytes.tests.multivalue : [Result]
  98.  Headers.contains : Text -> Headers -> Boolean
  99.  Headers.delete : Text -> Headers -> Headers
  100. Headers.doc : Doc
  101. Headers.empty : Headers
  102. Headers.equals : Headers -> Headers -> Boolean
  103. Headers.fromList : [(Text, Text)] -> Headers
  104. Headers.getCommaDelimitedValues : Text
                                         -> Headers
                                         -> [Text]
  105. Headers.getDateTime : Text
                             -> Headers
                             ->{Exception} [OffsetDateTime]
  106. Headers.getDateTime.doc : Doc
  107. Headers.getInstant : Text
                            -> Headers
                            ->{Exception} [Instant]
  108. Headers.getInstant.doc : Doc
  109. Headers.getValues : Text -> Headers -> [Text]
  110. Headers.Headers : data.Map Text [Text] -> Headers
  111. Headers.HttpDate.fromGMTDateTime : LocalDateTime -> Text
  112. Headers.HttpDate.fromGMTDateTime.doc : Doc
  113. Headers.HttpDate.fromInstant : Instant -> Text
  114. Headers.HttpDate.fromInstant.doc : Doc
  115. Headers.HttpDate.fromOffsetDateTime : OffsetDateTime
                                             -> Text
  116. Headers.HttpDate.fromOffsetDateTime.doc : Doc
  117. Headers.HttpDate.parse.localDate : Text
                                          ->{Abort} LocalDate
  118. Headers.HttpDate.parse.localDateTime : Text
                                              ->{Abort} LocalDateTime
  119. Headers.HttpDate.parse.localTime : Text
                                          ->{Abort} LocalTime
  120. Headers.HttpDate.parse.offsetDateTime : Text
                                               ->{Abort} OffsetDateTime
  121. Headers.HttpDate.parse.offsetDateTime.doc : Doc
  122. Headers.isChunked : Headers -> Boolean
  123. Headers.isEmpty : Headers -> Boolean
  124. Headers.orElse : Headers -> Headers -> Headers
  125. Headers.orElse.doc : Doc
  126. Headers.orElse.test : [Result]
  127. Headers.parseHeaders : Text -> Either Text Headers
  128. Headers.requireHeader : Text
                               -> Headers
                               ->{Exception} Text
  129. Headers.requireHeader.doc : Doc
  130. Headers.retainOnly : Set Text -> Headers -> Headers
  131. Headers.singleton : Text -> Text -> Headers
  132. Headers.standard.accept : Text -> Headers
  133. Headers.standard.acceptEncoding.default : Headers
  134. Headers.standard.contentLength : Body -> Headers
  135. Headers.standard.contentLength.doc : Doc
  136. Headers.standard.contentLength.get : Headers
                                            -> Optional Nat
  137. Headers.standard.host.forAuthority : Authority -> Headers
  138. Headers.standard.host.forAuthority.tests.noPort : [Result]
  139. Headers.standard.host.forAuthority.tests.withPort : [Result]
  140. Headers.standard.host.forURI : URI -> Headers
  141. Headers.standard.host.forUri : URI -> Headers
  142. Headers.standard.location.get : Headers -> Optional Path
  143. Headers.standard.location.get.tests : [Result]
  144. Headers.standard.userAgent : Text -> Headers
  145. Headers.toMap : Headers -> data.Map Text [Text]
  146. Headers.union : Headers -> Headers -> Headers
  147. Headers.union.doc : Doc
  148. Headers.union.tests.nonempty : [Result]
  149. Headers.union.tests.withEmpty : [Result]
  150. structural type Holder g
  151. Holder.Holder : ('{g} () ->{g} ()) -> Holder g
  152. type HttpRequest
  153. HttpRequest.== : HttpRequest -> HttpRequest -> Boolean
  154. HttpRequest.addHeader : Text
                               -> Text
                               -> HttpRequest
                               -> HttpRequest
  155. HttpRequest.addHeader.doc : Doc
  156. HttpRequest.body : HttpRequest -> Body
  157. HttpRequest.body.set : Body -> HttpRequest -> HttpRequest
  158. HttpRequest.decode : '{Decode} HttpRequest
  159. HttpRequest.decodeHeadersOnly.doc : Doc
  160. HttpRequest.delete : URI -> HttpRequest
  161. HttpRequest.doc : Doc
  162. HttpRequest.encode : ProxyPresence
                            -> HttpRequest
                            -> Bytes
  163. HttpRequest.encode.nonProxyRequestLine : HttpRequest
                                                -> Bytes
  164. HttpRequest.encode.proxyRequestLineText : HttpRequest
                                                 -> Text
  165. HttpRequest.encodeChunked : ProxyPresence
                                   -> HttpRequest
                                   -> '{Stream Bytes} Headers
                                   ->{Stream Bytes} ()
  166. HttpRequest.encodeChunked.doc : Doc
  167. HttpRequest.encodeChunked.tests.withoutTrailers : [Result]
  168. HttpRequest.encodeChunked.tests.withTrailers : [Result]
  169. HttpRequest.encodeNoBody : ProxyPresence
                                  -> HttpRequest
                                  -> Bytes
  170. HttpRequest.encodeNoBody.doc : Doc
  171. HttpRequest.ensureEqual : HttpRequest
                                 -> HttpRequest
                                 ->{Exception} ()
  172. HttpRequest.equals : HttpRequest
                            -> HttpRequest
                            -> Boolean
  173. HttpRequest.fromBytes : Bytes ->{Exception} HttpRequest
  174. HttpRequest.fromBytes.doc : Doc
  175. HttpRequest.fromStream : '{g, Stream Bytes} a
                                ->{g, Exception} HttpRequest
  176. HttpRequest.get : URI -> HttpRequest
  177. HttpRequest.get.doc : Doc
  178. HttpRequest.headers : HttpRequest -> Headers
  179. HttpRequest.headers.modify : (Headers ->{g} Headers)
                                    -> HttpRequest
                                    ->{g} HttpRequest
  180. HttpRequest.headers.pattern.tchar : Pattern Text
  181. HttpRequest.headers.pattern.tchar.doc : Doc
  182. HttpRequest.headers.pattern.token : Pattern Text
  183. HttpRequest.HttpRequest : Method
                                 -> Version
                                 -> URI
                                 -> Headers
                                 -> Body
                                 -> HttpRequest
  184. HttpRequest.method : HttpRequest -> Method
  185. HttpRequest.method.doc : Doc
  186. HttpRequest.patch : URI -> Body -> HttpRequest
  187. HttpRequest.pattern.method : IPattern Capture Text
  188. HttpRequest.pattern.method.connect : IPattern
                                              Capture Text
  189. HttpRequest.pattern.method.delete : IPattern Capture Text
  190. HttpRequest.pattern.method.get : IPattern Capture Text
  191. HttpRequest.pattern.method.head : IPattern Capture Text
  192. HttpRequest.pattern.method.options : IPattern
                                              Capture Text
  193. HttpRequest.pattern.method.patch : IPattern Capture Text
  194. HttpRequest.pattern.method.post : IPattern Capture Text
  195. HttpRequest.pattern.method.put : IPattern Capture Text
  196. HttpRequest.pattern.method.trace : IPattern Capture Text
  197. HttpRequest.pattern.requestLine : IPattern
                                           (And
                                             (And
                                               Capture
                                               (And
                                                 (And
                                                   (And
                                                     Capture
                                                     (And
                                                       (And
                                                         (And
                                                           Capture
                                                           Capture)
                                                         Capture)
                                                       Capture))
                                                   Capture)
                                                 Capture))
                                             Capture)
                                           Text
  198. HttpRequest.pattern.version : IPattern Capture Text
  199. HttpRequest.pattern.version.http10 : IPattern
                                              Capture Text
  200. HttpRequest.pattern.version.http11 : IPattern
                                              Capture Text
  201. HttpRequest.post : URI -> Body -> HttpRequest
  202. HttpRequest.put : URI -> Body -> HttpRequest
  203. type HttpRequest.RequestLine
  204. HttpRequest.RequestLine.RequestLine : Method
                                             -> URI
                                             -> Version
                                             -> RequestLine
  205. HttpRequest.RequestLine.requestMethod : RequestLine
                                               -> Method
  206. HttpRequest.RequestLine.requestMethod.modify : (Method
                                                      ->{g} Method)
                                                      -> RequestLine
                                                      ->{g} RequestLine
  207. HttpRequest.RequestLine.requestMethod.set : Method
                                                   -> RequestLine
                                                   -> RequestLine
  208. HttpRequest.RequestLine.requestURI : RequestLine -> URI
  209. HttpRequest.RequestLine.requestUri : RequestLine -> URI
  210. HttpRequest.RequestLine.requestURI.modify : (URI
                                                   ->{g} URI)
                                                   -> RequestLine
                                                   ->{g} RequestLine
  211. HttpRequest.RequestLine.requestUri.modify : (URI
                                                   ->{g} URI)
                                                   -> RequestLine
                                                   ->{g} RequestLine
  212. HttpRequest.RequestLine.requestURI.set : URI
                                                -> RequestLine
                                                -> RequestLine
  213. HttpRequest.RequestLine.requestUri.set : URI
                                                -> RequestLine
                                                -> RequestLine
  214. HttpRequest.RequestLine.requestVersion : RequestLine
                                                -> Version
  215. HttpRequest.RequestLine.requestVersion.modify : (Version
                                                       ->{g} Version)
                                                       -> RequestLine
                                                       ->{g} RequestLine
  216. HttpRequest.RequestLine.requestVersion.set : Version
                                                    -> RequestLine
                                                    -> RequestLine
  217. HttpRequest.requestLine.tests : [Result]
  218. HttpRequest.setHeader : Text
                               -> [Text]
                               -> HttpRequest
                               -> HttpRequest
  219. HttpRequest.setHeader.doc : Doc
  220. HttpRequest.tests.roundTrip : [Result]
  221. HttpRequest.uri : HttpRequest -> URI
  222. HttpRequest.uri.modify : (URI ->{g} URI)
                                ->{g} HttpRequest
                                ->{g} HttpRequest
  223. HttpRequest.version : HttpRequest -> Version
  224. HttpRequest.version.doc : Doc
  225. type HttpResponse
  226. HttpResponse.== : HttpResponse -> HttpResponse -> Boolean
  227. HttpResponse.addHeader : Text
                                -> Text
                                -> HttpResponse
                                -> HttpResponse
  228. HttpResponse.badRequest : HttpResponse
  229. HttpResponse.body : HttpResponse -> Body
  230. HttpResponse.body.modify : (Body ->{g} Body)
                                  ->{g} HttpResponse
                                  ->{g} HttpResponse
  231. HttpResponse.body.set : Body
                               -> HttpResponse
                               -> HttpResponse
  232. HttpResponse.bodyText : HttpResponse ->{Exception} Text
  233. HttpResponse.bodyText.doc : Doc
  234. HttpResponse.decode : Boolean ->{Decode} HttpResponse
  235. HttpResponse.doc : Doc
  236. HttpResponse.encode : HttpResponse -> Bytes
  237. HttpResponse.encodeChunked : HttpResponse
                                    -> '{Stream Bytes} Headers
                                    ->{Exception, Stream Bytes} ()
  238. HttpResponse.encodeChunked.doc : Doc
  239. HttpResponse.encodeChunked.tests.withoutTrailers : [Result]
  240. HttpResponse.encodeChunked.tests.withTrailers : [Result]
  241. HttpResponse.encodeNoBody : HttpResponse -> Bytes
  242. HttpResponse.ensureEqual : HttpResponse
                                  -> HttpResponse
                                  ->{Exception} ()
  243. HttpResponse.ensureStatus : (HttpResponse.Status
                                   -> Boolean)
                                   -> HttpResponse
                                   ->{Exception} HttpResponse
  244. HttpResponse.ensureStatus.doc : Doc
  245. HttpResponse.ensureSuccess : HttpResponse
                                    ->{Exception} HttpResponse
  246. HttpResponse.ensureSuccess.doc : Doc
  247. HttpResponse.error : HttpResponse
  248. HttpResponse.expectStatus : (HttpResponse.Status
                                   -> Boolean)
                                   -> HttpResponse
                                   ->{Exception} ()
  249. HttpResponse.expectStatus.doc : Doc
  250. HttpResponse.expectSuccess : HttpResponse
                                    ->{Exception} ()
  251. HttpResponse.fromBytes : Boolean
                                -> Bytes
                                ->{Exception} HttpResponse
  252. HttpResponse.fromBytes.doc : Doc
  253. HttpResponse.fromStream : Boolean
                                 -> '{g, Stream Bytes} a
                                 ->{g, Exception} HttpResponse
  254. HttpResponse.headers : HttpResponse -> Headers
  255. HttpResponse.HttpResponse : HttpResponse.Status
                                   -> Version
                                   -> Headers
                                   -> Body
                                   -> HttpResponse
  256. HttpResponse.isSuccess : HttpResponse -> Boolean
  257. HttpResponse.noContent : HttpResponse
  258. HttpResponse.notFound : HttpResponse
  259. HttpResponse.ok : Body -> HttpResponse
  260. HttpResponse.pattern.reason : IPattern Capture Text
  261. HttpResponse.pattern.status : IPattern Capture Text
  262. HttpResponse.pattern.statusLine : IPattern
                                           (And
                                             (And
                                               Capture Capture)
                                             Capture)
                                           Text
  263. HttpResponse.pattern.statusLine.testReasonIsOptional : [Result]
  264. HttpResponse.setBody : Body
                              -> HttpResponse
                              -> HttpResponse
  265. type HttpResponse.Status
  266. HttpResponse.status : HttpResponse -> HttpResponse.Status
  267. HttpResponse.Status.code : HttpResponse.Status -> Nat
  268. HttpResponse.Status.code.modify : (Nat ->{g} Nat)
                                         -> HttpResponse.Status
                                         ->{g} HttpResponse.Status
  269. HttpResponse.Status.code.set : Nat
                                      -> HttpResponse.Status
                                      -> HttpResponse.Status
  270. HttpResponse.Status.isFailure : HttpResponse.Status
                                       -> Boolean
  271. HttpResponse.Status.isSuccess : HttpResponse.Status
                                       -> Boolean
  272. HttpResponse.Status.reason : HttpResponse.Status -> Text
  273. HttpResponse.Status.reason.modify : (Text ->{g} Text)
                                           -> HttpResponse.Status
                                           ->{g} HttpResponse.Status
  274. HttpResponse.Status.reason.set : Text
                                        -> HttpResponse.Status
                                        -> HttpResponse.Status
  275. HttpResponse.Status.Status : Nat
                                    -> Text
                                    -> HttpResponse.Status
  276. HttpResponse.Status.toText : HttpResponse.Status -> Text
  277. type HttpResponse.Status.UnexpectedResponseStatus
  278. LICENSE : License
  279. LICENSE.doc : Doc
  280. message.encodeChunkedBody : '{g, Stream Bytes} Headers
                                   ->{g, Stream Bytes} ()
  281. message.encodeChunkedBody.doc : Doc
  282. Method.fromText : Text -> Optional Method
  283. Method.toText : Method -> Text
  284. type proxy.ProxyPresence
  285. proxy.ProxyPresence.NoProxy : ProxyPresence
  286. proxy.ProxyPresence.Proxy : ProxyPresence
  287. README : Doc
  288. ReleaseNotes : Doc
  289. server.CHANGELOG : Doc
  290. server.changelogs.v10 : Doc
  291. server.changelogs.v6 : Doc
  292. server.changelogs.v7 : Doc
  293. server.changelogs.v8 : Doc
  294. server.changelogs.v9 : Doc
  295. type server.Config
  296. server.Config.Config : Optional HostName
                              -> Port
                              -> Nat
                              -> Optional ServerConfig
                              -> server.Config
  297. server.Config.createSemaphore : server.Config ->{IO} Sem
  298. server.Config.hostName : server.Config
                                -> Optional HostName
  299. server.Config.hostName.modify : (Optional HostName
                                       ->{g} Optional HostName)
                                       -> server.Config
                                       ->{g} server.Config
  300. server.Config.hostName.set : Optional HostName
                                    -> server.Config
                                    -> server.Config
  301. server.Config.numThreads : server.Config -> Nat
  302. server.Config.numThreads.modify : (Nat ->{g} Nat)
                                         -> server.Config
                                         ->{g} server.Config
  303. server.Config.numThreads.set : Nat
                                      -> server.Config
                                      -> server.Config
  304. server.Config.port : server.Config -> Port
  305. server.Config.port.modify : (Port ->{g} Port)
                                   -> server.Config
                                   ->{g} server.Config
  306. server.Config.port.set : Port
                                -> server.Config
                                -> server.Config
  307. server.Config.serve : Routes {IO}
                             -> server.Config
                             ->{IO, Exception} '{IO, Exception} ()
  308. server.Config.serve.doc : Doc
  309. server.Config.tlsConfig : server.Config
                                 -> Optional ServerConfig
  310. server.Config.tlsConfig.modify : (Optional ServerConfig
                                        ->{g} Optional
                                          ServerConfig)
                                        -> server.Config
                                        ->{g} server.Config
  311. server.Config.tlsConfig.set : Optional ServerConfig
                                     -> server.Config
                                     -> server.Config
  312. server.example.alohaHandler : Handler IO
  313. server.example.helloHandler : Handler IO
  314. server.example.helloHandler2 : Handler IO
  315. server.example.main : '{IO, Exception} ()
  316. server.example.tracing404 : HttpRequest -> HttpResponse
  317. server.forkServer : server.Config
                           -> (HttpRequest
                           ->{IO, Exception} Either
                             HttpResponse WebSocketHandler)
                           ->{IO, Exception} '{IO, Exception} ()
  318. type server.Handler g
  319. server.Handler.doc : Doc
  320. server.Handler.Handler : (HttpRequest
                                ->{g, Exception, Abort} HttpResponse)
                                -> Handler g
  321. server.Handler.HandlerWebSocket : (HttpRequest
                                         ->{g, Exception, Abort} WebSocketHandler)
                                         -> Handler g
  322. server.Http.webSocket : HttpRequest
                               ->{Exception, HttpWebSocket} WebSocket
  323. server.internal.handleConnection : (HttpRequest
                                          ->{IO, Exception} Either
                                            HttpResponse
                                            WebSocketHandler)
                                          -> Connection
                                          ->{IO,
                                          Exception,
                                          Abort} ()
  324. server.internal.handleRequest : Connection
                                       -> HttpRequest
                                       -> (HttpRequest
                                       ->{IO, Exception} Either
                                         HttpResponse
                                         WebSocketHandler)
                                       ->{IO, Exception} ()
  325. server.internal.socketListener : server.Config
                                        -> (HttpRequest
                                        ->{IO, Exception} Either
                                          HttpResponse
                                          WebSocketHandler)
                                        -> ListeningServerSocket
                                        ->{IO} ()
  326. server.README : Doc
  327. type server.Routes g
  328. server.Routes.<<< : Routes {g} -> Handler g -> Routes {g}
  329. server.Routes.>>> : Handler g -> Routes {g} -> Routes {g}
  330. server.Routes.default : Routes g
  331. server.Routes.default404 : HttpRequest -> HttpResponse
  332. server.Routes.default500 : Failure
                                  -> HttpRequest
                                  -> HttpResponse
  333. server.Routes.doc : Doc
  334. server.Routes.get : Path -> HttpRequest -> Boolean
  335. server.Routes.path : Path -> HttpRequest -> Boolean
  336. server.Routes.post : Path -> HttpRequest -> Boolean
  337. server.Routes.Routes : [Handler g]
                              -> (HttpRequest
                              ->{g} HttpResponse)
                              -> (Failure
                              -> HttpRequest
                              ->{g} HttpResponse)
                              -> Routes g
  338. server.Routes.toFunction : Routes IO
                                  -> HttpRequest
                                  ->{IO} Either
                                    HttpResponse
                                    WebSocketHandler
  339. server.Routes.with404 : (HttpRequest ->{g} HttpResponse)
                               -> Routes {g}
                               -> Routes {g}
  340. server.Routes.with500 : (Failure
                               -> HttpRequest
                               ->{g} HttpResponse)
                               -> Routes {g}
                               -> Routes {g}
  341. server.Routes.withHeader : Text
                                  -> Text
                                  -> HttpRequest
                                  -> Boolean
  342. server.runServer : server.Config
                          -> (HttpRequest
                          ->{IO, Exception} Either
                            HttpResponse WebSocketHandler)
                          ->{IO, Exception} ()
  343. type server.State g
  344. server.State.error : State g
                            -> Failure
                            -> HttpRequest
                            ->{g} HttpResponse
  345. server.State.handlerReq.internal.webSocketKey : HttpRequest
                                                       -> Optional
                                                         Text
  346. server.State.handlerReq.internal.webSocketKey.tests : [Result]
  347. server.State.handlers : State g -> [Handler g]
  348. server.State.notFound : State g
                               -> HttpRequest
                               ->{g} HttpResponse
  349. server.State.semaphore : State g -> Sem
  350. server.State.semaphore.set : Sem
                                    -> State {g}
                                    -> State {g}
  351. server.State.State : Routes g -> Sem -> State g
  352. server.test.integration.all : ['{g,
                                     IO,
                                     Http,
                                     HttpWebSocket,
                                     Stream Result} ()]
  353. server.test.integration.baseUri : URI
  354. server.test.integration.client.get : '{IO,
                                            Http,
                                            HttpWebSocket,
                                            Stream Result} ()
  355. server.test.integration.client.handleClientException : '{IO,
                                                              Exception,
                                                              Http,
                                                              HttpWebSocket,
                                                              Stream
                                                                Result} ()
                                                              ->{IO,
                                                              Http,
                                                              HttpWebSocket,
                                                              Stream
                                                                Result} ()
  356. server.test.integration.client.handleWSClientException : '{IO,
                                                                Exception,
                                                                HttpWebSocket,
                                                                Stream
                                                                  Result} ()
                                                                ->{IO,
                                                                Http,
                                                                HttpWebSocket,
                                                                Stream
                                                                  Result} ()
  357. server.test.integration.client.manyRequests : '{IO,
                                                     Http,
                                                     HttpWebSocket,
                                                     Stream
                                                       Result} ()
  358. server.test.integration.client.post : '{IO,
                                             Http,
                                             HttpWebSocket,
                                             Stream Result} ()
  359. server.test.integration.client.statusResults : Text
                                                      -> HttpResponse.Status
                                                      ->{Stream
                                                        Result} ()
  360. server.test.integration.client.webSocket : '{IO,
                                                  Http,
                                                  HttpWebSocket,
                                                  Stream Result} ()
  361. server.test.integration.expectedGetResponse : Body
  362. server.test.integration.expectedPostResponse : Body
  363. server.test.integration.host : Text
  364. server.test.integration.main : '{IO, Exception} [Result]
  365. server.test.integration.newServer : HttpRequest
                                           -> Either
                                             HttpResponse
                                             WebSocketHandler
  366. server.test.integration.port : Text
  367. server.test.integration.server : Routes g
  368. server.test.integration.server.getHandler : Handler g
  369. server.test.integration.server.postHandler : Handler g
  370. server.test.integration.server.routes : Routes g
  371. server.test.integration.server.webSocketHandler : Handler
                                                           g
  372. server.up.base.IO.logAndIgnore : '{IO, Exception} a
                                        ->{IO} ()
  373. type server.WebSocketHandler
  374. server.WebSocketHandler.async : (Message
                                       ->{IO, Stream Message} ())
                                       -> '{IO,
                                       Exception,
                                       Stream Message} ()
                                       ->{IO, Exception} WebSocketHandler
  375. server.WebSocketHandler.async.doc : Doc
  376. server.WebSocketHandler.async.doc.example1 : '{IO,
                                                    Exception} ()
  377. server.WebSocketHandler.doc : Doc
  378. server.WebSocketHandler.sync : '{IO,
                                      Exception,
                                      Ask Message,
                                      Stream Message} ()
                                      ->{IO} WebSocketHandler
  379. server.WebSocketHandler.sync.doc : Doc
  380. server.WebSocketHandler.sync.doc.example1 : '{IO,
                                                   Exception} ()
  381. server.WebSocketHandler.WebSocketHandler : (WebSocket
                                                  -> ((Either
                                                    Failure ()
                                                  ->{IO,
                                                  Exception} ())
                                                  ->{IO,
                                                  Exception} ())
                                                  ->{IO,
                                                  Exception} ())
                                                  -> WebSocketHandler
  382. tests.checkHttpRequestRoundTrip : HttpRequest
                                         ->{Exception, Each} ()
  383. tests.checkHttpRequestRoundTrip.doc : Doc
  384. tests.chunkedWithoutTrailers : [Result]
  385. tests.chunkedWithTrailers : [Result]
  386. tests.chunkedWithTrailersAreActuallyOptional : [Result]
  387. tests.exampleRequest : Bytes
  388. tests.exampleResponse : Bytes
  389. tests.testChunkedRequestRoundTrip : [Result]
  390. tests.testChunkedRequestRoundTripNoTrailers : [Result]
  391. tests.testChunkedRequestRoundTripWithTrailers : [Result]
  392. tests.testChunkedResponseRoundTrip : [Result]
  393. tests.testFromStream : [Result]
  394. tests.testHttpRequestRoundTrip : [Result]
  395. tests.testHttpResponseRoundTrip : [Result]
  396. tests.testParseRequest : [Result]
  397. tests.testParseResponse : [Result]
  398. tests.testRequestLine : [Result]
  399. tests.testStatusLine : [Result]
  400. up.base.Bytes.encodeNat8 : Nat -> Bytes
  401. up.base.data.Map.filterKeys : (k ->{g2} Boolean)
                                     -> data.Map k v
                                     ->{g2} data.Map k v
  402. up.base.test.ensureEqualBy : (a -> a -> Boolean)
                                    -> a
                                    -> a
                                    ->{Exception} ()
  403. util.slurpByteStream : '{Stream Bytes} r -> Bytes
  404. type Version
  405. Version.fromText : Text -> Either Text Version
  406. Version.http10 : Version
  407. Version.http11 : Version
  408. Version.http20 : Version
  409. Version.major : Version -> Nat
  410. Version.major.modify : (Nat ->{g} Nat)
                              -> Version
                              ->{g} Version
  411. Version.major.set : Nat -> Version -> Version
  412. Version.minor : Version -> Nat
  413. Version.minor.modify : (Nat ->{g} Nat)
                              -> Version
                              ->{g} Version
  414. Version.minor.set : Nat -> Version -> Version
  415. Version.toText : Version -> Text
  416. Version.Version : Nat -> Nat -> Version
  417. type websockets.Endpoint
  418. websockets.Endpoint.Client : Endpoint
  419. websockets.Endpoint.isClient : Endpoint -> Boolean
  420. websockets.Endpoint.Server : Endpoint
  421. type websockets.errors.WebSocketClosed
  422. websockets.example : '{IO, Exception} ()
  423. type websockets.Frame
  424. websockets.Frame.Binary : Boolean -> Bytes -> Frame
  425. websockets.Frame.Close : Optional (Nat, Text) -> Frame
  426. websockets.Frame.Continuation : Boolean -> Bytes -> Frame
  427. websockets.Frame.decoder : '{Decode,
                                  DecodeBits,
                                  Throw DecodeError} Frame
  428. websockets.Frame.decoder.decodeCloseReason : Bytes
                                                    ->{Throw
                                                      DecodeError} Optional
                                                      ( Nat,
                                                        Text)
  429. websockets.Frame.decoder.maskOrUnmask : Bytes
                                               -> Bytes
                                               -> Bytes
  430. websockets.Frame.decoder.tests.fragmentedContinuation : [Result]
  431. websockets.Frame.decoder.tests.fragmentedTextUnmasked : [Result]
  432. websockets.Frame.decoder.tests.ping : [Result]
  433. websockets.Frame.decoder.tests.pong : [Result]
  434. websockets.Frame.decoder.tests.singleTextMasked : [Result]
  435. websockets.Frame.decoder.tests.singleTextUnmasked : [Result]
  436. websockets.Frame.encoder : Optional Bytes
                                  -> Frame
                                  -> Bytes
  437. websockets.Frame.encoder.tests.fragmentedContinuation : [Result]
  438. websockets.Frame.encoder.tests.fragmentedTextUnasked : [Result]
  439. websockets.Frame.encoder.tests.ping : [Result]
  440. websockets.Frame.encoder.tests.pong : [Result]
  441. websockets.Frame.encoder.tests.singleTextMasked : [Result]
  442. websockets.Frame.encoder.tests.singleTextUnmasked : [Result]
  443. websockets.Frame.Ping : Bytes -> Frame
  444. websockets.Frame.Pong : Bytes -> Frame
  445. websockets.Frame.Text : Boolean -> Text -> Frame
  446. websockets.handshake : HttpRequest
                              -> Connection
                              ->{IO, Exception} ()
  447. websockets.handshake.doc : Doc
  448. websockets.internal.readFrame : Connection
                                       ->{IO, Exception} Frame
  449. type websockets.Message
  450. websockets.Message.binary : Bytes -> Message
  451. websockets.Message.binary.doc : Doc
  452. websockets.Message.BinaryMessage : Bytes -> Message
  453. websockets.Message.doc : Doc
  454. websockets.Message.text : Text -> Message
  455. websockets.Message.text.doc : Doc
  456. websockets.Message.TextMessage : Text -> Message
  457. websockets.Message.toFrames : Nat
                                     -> Message
                                     ->{Stream Frame} ()
  458. websockets.metadata.authors.alvaroc1 : Author
  459. websockets.metadata.authors.alvaroc1.guid : GUID
  460. websockets.metadata.copyrightHolders.alvaroc1 : CopyrightHolder
  461. websockets.metadata.licenses.alvaroc12023 : License
  462. websockets.protocol.receive : '{Abort,
                                     Decode,
                                     DecodeBits,
                                     Throw DecodeError,
                                     Stream Bytes} Message
  463. websockets.README : Doc
  464. websockets.upgradeResponse : HttpRequest
                                    ->{Exception} HttpResponse
  465. websockets.util.createAcceptString : Text
                                            ->{Exception} Text
  466. websockets.util.createAcceptString.tests.ex1 : [Result]
  467. websockets.util.handshakeRequestDecoder : '{Exception,
                                                 Decode} HttpRequest
  468. websockets.util.magicKeyString : Text
  469. type websockets.WebSocket
  470. websockets.WebSocket.close : WebSocket
                                    ->{IO, Exception} ()
  471. websockets.WebSocket.closer : WebSocket
                                     -> '{IO, Exception} ()
  472. websockets.WebSocket.closer.modify : ('{IO, Exception} ()
                                            ->{g} '{IO,
                                            Exception} ())
                                            -> WebSocket
                                            ->{g} WebSocket
  473. websockets.WebSocket.closer.set : '{IO, Exception} ()
                                         -> WebSocket
                                         -> WebSocket
  474. websockets.WebSocket.doc : Doc
  475. websockets.WebSocket.receive : WebSocket
                                      ->{IO, Exception} Message
  476. websockets.WebSocket.receiver : WebSocket
                                       -> '{IO, Exception} Message
  477. websockets.WebSocket.receiver.modify : ('{IO, Exception} Message
                                              ->{g} '{IO,
                                              Exception} Message)
                                              -> WebSocket
                                              ->{g} WebSocket
  478. websockets.WebSocket.receiver.set : '{IO, Exception} Message
                                           -> WebSocket
                                           -> WebSocket
  479. websockets.WebSocket.send : WebSocket
                                   -> Message
                                   ->{IO, Exception} ()
  480. websockets.WebSocket.send.modify : ((Message
                                          ->{IO, Exception} ())
                                          ->{g} Message
                                          ->{IO, Exception} ())
                                          -> WebSocket
                                          ->{g} WebSocket
  481. websockets.WebSocket.send.set : (Message
                                       ->{IO, Exception} ())
                                       -> WebSocket
                                       -> WebSocket
  482. websockets.WebSocket.threadSafeWebSocket : Connection
                                                  -> Endpoint
                                                  -> Nat
                                                  -> Bytes
                                                  ->{IO} WebSocket
  483. websockets.WebSocket.threadSafeWebSocket.doc : Doc
  484. websockets.WebSocket.WebSocket : (Message
                                        ->{IO, Exception} ())
                                        -> '{IO, Exception} Message
                                        -> '{IO, Exception} ()
                                        -> WebSocket
```
