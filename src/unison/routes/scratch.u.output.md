# Routes

This is a high-level HTTP server library for Unison. It contains utilities for writing http route endpoints for servers types and functions that are used in most Unison programs.

## Library contents list

``` ucm
@unison/routes/main> pull.without-history @unison/routes/releases/6.2.6

  Downloaded 30218 entities.

  ✅

  Successfully updated @unison/routes/main from
  @unison/routes/releases/6.2.6.

@unison/routes/main> find

  1.   type Cookie
  2.   Cookie.cookie : Text -> Text -> Cookie
  3.   Cookie.Cookie : Text
                       -> Text
                       -> Optional OffsetDateTime
                       -> Optional time.Duration
                       -> Optional Text
                       -> Optional Path
                       -> Boolean
                       -> Boolean
                       -> Optional SameSite
                       -> Cookie
  4.   Cookie.cookie.doc : Doc
  5.   Cookie.domain : Cookie -> Optional Text
  6.   Cookie.domain.modify : (Optional Text
                              ->{g} Optional Text)
                              -> Cookie
                              ->{g} Cookie
  7.   Cookie.domain.set : Optional Text -> Cookie -> Cookie
  8.   Cookie.expires : Cookie -> Optional OffsetDateTime
  9.   Cookie.expires.modify : (Optional OffsetDateTime
                               ->{g} Optional OffsetDateTime)
                               -> Cookie
                               ->{g} Cookie
  10.  Cookie.expires.set : Optional OffsetDateTime
                            -> Cookie
                            -> Cookie
  11.  Cookie.httpOnly : Cookie -> Boolean
  12.  Cookie.httpOnly.modify : (Boolean ->{g} Boolean)
                                -> Cookie
                                ->{g} Cookie
  13.  Cookie.httpOnly.set : Boolean -> Cookie -> Cookie
  14.  Cookie.maxAge : Cookie -> Optional time.Duration
  15.  Cookie.maxAge.modify : (Optional time.Duration
                              ->{g} Optional time.Duration)
                              -> Cookie
                              ->{g} Cookie
  16.  Cookie.maxAge.set : Optional time.Duration
                           -> Cookie
                           -> Cookie
  17.  Cookie.name : Cookie -> Text
  18.  Cookie.name.modify : (Text ->{g} Text)
                            -> Cookie
                            ->{g} Cookie
  19.  Cookie.name.set : Text -> Cookie -> Cookie
  20.  Cookie.path : Cookie -> Optional Path
  21.  Cookie.path.modify : (Optional Path ->{g} Optional Path)
                            -> Cookie
                            ->{g} Cookie
  22.  Cookie.path.set : Optional Path -> Cookie -> Cookie
  23.  type Cookie.SameSite
  24.  Cookie.sameSite : Cookie -> Optional SameSite
  25.  Cookie.SameSite.Lax : SameSite
  26.  Cookie.sameSite.modify : (Optional SameSite
                                ->{g} Optional SameSite)
                                -> Cookie
                                ->{g} Cookie
  27.  Cookie.SameSite.NoneSameSite : SameSite
  28.  Cookie.sameSite.set : Optional SameSite
                             -> Cookie
                             -> Cookie
  29.  Cookie.SameSite.Strict : SameSite
  30.  Cookie.secure : Cookie -> Boolean
  31.  Cookie.secure.modify : (Boolean ->{g} Boolean)
                              -> Cookie
                              ->{g} Cookie
  32.  Cookie.secure.set : Boolean -> Cookie -> Cookie
  33.  Cookie.toText : Cookie -> Text
  34.  Cookie.toText.doc : Doc
  35.  Cookie.value : Cookie -> Text
  36.  Cookie.value.modify : (Text ->{g} Text)
                             -> Cookie
                             ->{g} Cookie
  37.  Cookie.value.set : Text -> Cookie -> Cookie
  38.  examples.hello : HttpRequest ->{Exception} HttpResponse
  39.  examples.helloRoute : '{Route} ()
  40.  examples.websockets.cloudChatServer : '{IO, Exception} URI
  41.  examples.websockets.cloudChatServer.doc : Doc
  42.  examples.websockets.cloudEchoServer : '{IO, Exception} URI
  43.  examples.websockets.cloudEchoServer.doc : Doc
  44.  examples.websockets.echoServer : '{IO, Exception} ()
  45.  type failure.BadGateway
  46.  failure.BadGateway.doc : Doc
  47.  type failure.BadRequest
  48.  failure.BadRequest.doc : Doc
  49.  failure.catchHttpErrors : '{g, Exception} a
                                 ->{g, Exception} Either
                                   HttpResponse a
  50.  failure.catchHttpErrors.doc : Doc
  51.  type failure.Conflict
  52.  failure.Conflict.doc : Doc
  53.  type failure.Forbidden
  54.  failure.Forbidden.doc : Doc
  55.  type failure.FormDataParseError
  56.  failure.FormDataParseError.doc : Doc
  57.  type failure.GatewayTimeout
  58.  failure.GatewayTimeout.doc : Doc
  59.  type failure.Gone
  60.  failure.Gone.doc : Doc
  61.  type failure.HttpVersionNotSupported
  62.  failure.HttpVersionNotSupported.doc : Doc
  63.  type failure.InsufficientStorage
  64.  failure.InsufficientStorage.doc : Doc
  65.  type failure.InternalServerError
  66.  failure.InternalServerError.doc : Doc
  67.  type failure.MethodDidntMatch
  68.  failure.methodDidntMatch : m1 -> m2 -> Failure
  69.  failure.methodDidntMatch.doc : Doc
  70.  failure.MethodDidntMatch.doc : Doc
  71.  type failure.MethodNotAllowed
  72.  failure.MethodNotAllowed.doc : Doc
  73.  type failure.NetworkAuthenticationRequired
  74.  failure.NetworkAuthenticationRequired.doc : Doc
  75.  type failure.NoRouteMatched
  76.  failure.noRouteMatched : '{Route} a
  77.  failure.NoRouteMatched.doc : Doc
  78.  failure.noRouteMatched.doc : Doc
  79.  type failure.NotAcceptable
  80.  failure.NotAcceptable.doc : Doc
  81.  type failure.NotFound
  82.  failure.NotFound.doc : Doc
  83.  type failure.NotImplemented
  84.  failure.NotImplemented.doc : Doc
  85.  type failure.PathDidntMatch
  86.  failure.pathDidntMatch : Failure
  87.  failure.PathDidntMatch.doc : Doc
  88.  failure.pathDidntMatch.doc : Doc
  89.  type failure.PayloadTooLarge
  90.  failure.PayloadTooLarge.doc : Doc
  91.  failure.pickStatus : Type -> HttpResponse.Status
  92.  failure.pickStatus.doc : Doc
  93.  failure.raiseBadGateway : Text -> a ->{Exception} b
  94.  failure.raiseBadGateway.doc : Doc
  95.  failure.raiseBadRequest : Text -> a ->{Exception} b
  96.  failure.raiseBadRequest.doc : Doc
  97.  failure.raiseConflict : Text -> a ->{Exception} b
  98.  failure.raiseConflict.doc : Doc
  99.  failure.raiseForbidden : Text -> a ->{Exception} b
  100. failure.raiseForbidden.doc : Doc
  101. failure.raiseGatewayTimeout : Text -> a ->{Exception} b
  102. failure.raiseGatewayTimeout.doc : Doc
  103. failure.raiseGone : Text -> a ->{Exception} b
  104. failure.raiseGone.doc : Doc
  105. failure.raiseHttpVersionNotSupported : Text
                                              -> a
                                              ->{Exception} b
  106. failure.raiseHttpVersionNotSupported.doc : Doc
  107. failure.raiseInsufficientStorage : Text
                                          -> a
                                          ->{Exception} b
  108. failure.raiseInsufficientStorage.doc : Doc
  109. failure.raiseInternalServerError : Text
                                          -> a
                                          ->{Exception} b
  110. failure.raiseInternalServerError.doc : Doc
  111. failure.raiseMethodNotAllowed : Text -> a ->{Exception} b
  112. failure.raiseMethodNotAllowed.doc : Doc
  113. failure.raiseNetworkAuthenticationRequired : Text
                                                    -> a
                                                    ->{Exception} b
  114. failure.raiseNetworkAuthenticationRequired.doc : Doc
  115. failure.raiseNotAcceptable : Text -> a ->{Exception} b
  116. failure.raiseNotAcceptable.doc : Doc
  117. failure.raiseNotFound : Text -> a ->{Exception} b
  118. failure.raiseNotFound.doc : Doc
  119. failure.raiseNotImplemented : Text -> a ->{Exception} b
  120. failure.raiseNotImplemented.doc : Doc
  121. failure.raisePayloadTooLarge : Text -> a ->{Exception} b
  122. failure.raisePayloadTooLarge.doc : Doc
  123. failure.raiseRequestTimeout : Text -> a ->{Exception} b
  124. failure.raiseRequestTimeout.doc : Doc
  125. failure.raiseServiceUnavailable : Text
                                         -> a
                                         ->{Exception} b
  126. failure.raiseServiceUnavailable.doc : Doc
  127. failure.raiseTooManyRequests : Text -> a ->{Exception} b
  128. failure.raiseTooManyRequests.doc : Doc
  129. failure.raiseUnauthorized : Text -> a ->{Exception} b
  130. failure.raiseUnauthorized.doc : Doc
  131. failure.raiseUnsupportedMediaType : Text
                                           -> a
                                           ->{Exception} b
  132. failure.raiseUnsupportedMediaType.doc : Doc
  133. failure.raiseUriTooLong : Text -> a ->{Exception} b
  134. failure.raiseUriTooLong.doc : Doc
  135. type failure.RequestTimeout
  136. failure.RequestTimeout.doc : Doc
  137. type failure.ServiceUnavailable
  138. failure.ServiceUnavailable.doc : Doc
  139. failure.tests.shortCircuit : [Result]
  140. type failure.TooManyRequests
  141. failure.TooManyRequests.doc : Doc
  142. type failure.Unauthorized
  143. failure.Unauthorized.doc : Doc
  144. type failure.UnsupportedMediaType
  145. failure.UnsupportedMediaType.doc : Doc
  146. failure.uriParseFailure : UriParseFailure -> Failure
  147. type failure.UriTooLong
  148. failure.UriTooLong.doc : Doc
  149. type HttpContext
  150. HttpContext.fromRequest : HttpRequest -> HttpContext
  151. HttpContext.fromRequest.doc : Doc
  152. HttpContext.HttpContext : Method
                                 -> unison_http_3_3_2.Version
                                 -> URI
                                 -> Optional
                                   (Optional (Map Text [Text]))
                                 -> Map Text [Text]
                                 -> HttpResponse.Status
                                 -> unison_http_3_3_2.Version
                                 -> Map Text [Text]
                                 -> HttpContext
  153. HttpContext.requestHeaders : HttpContext
                                    -> Map Text [Text]
  154. HttpContext.requestHeaders.modify : (Map Text [Text]
                                           ->{g} Map Text [Text])
                                           -> HttpContext
                                           ->{g} HttpContext
  155. HttpContext.requestHeaders.set : Map Text [Text]
                                        -> HttpContext
                                        -> HttpContext
  156. HttpContext.requestMethod : HttpContext -> Method
  157. HttpContext.requestMethod.modify : (Method ->{g} Method)
                                          -> HttpContext
                                          ->{g} HttpContext
  158. HttpContext.requestMethod.set : Method
                                       -> HttpContext
                                       -> HttpContext
  159. HttpContext.requestQuery : HttpContext
                                  -> Optional
                                    (Optional (Map Text [Text]))
  160. HttpContext.requestQuery.modify : (Optional
                                           (Optional
                                             (Map Text [Text]))
                                         ->{g} Optional
                                           (Optional
                                             (Map Text [Text])))
                                         -> HttpContext
                                         ->{g} HttpContext
  161. HttpContext.requestQuery.set : Optional
                                        (Optional
                                          (Map Text [Text]))
                                      -> HttpContext
                                      -> HttpContext
  162. HttpContext.requestUri : HttpContext -> URI
  163. HttpContext.requestUri.modify : (URI ->{g} URI)
                                       -> HttpContext
                                       ->{g} HttpContext
  164. HttpContext.requestUri.set : URI
                                    -> HttpContext
                                    -> HttpContext
  165. HttpContext.requestVersion : HttpContext
                                    -> unison_http_3_3_2.Version
  166. HttpContext.requestVersion.modify : (unison_http_3_3_2.Version
                                           ->{g} unison_http_3_3_2.Version)
                                           -> HttpContext
                                           ->{g} HttpContext
  167. HttpContext.requestVersion.set : unison_http_3_3_2.Version
                                        -> HttpContext
                                        -> HttpContext
  168. HttpContext.responseHeaders : HttpContext
                                     -> Map Text [Text]
  169. HttpContext.responseHeaders.modify : (Map Text [Text]
                                            ->{g} Map
                                              Text [Text])
                                            -> HttpContext
                                            ->{g} HttpContext
  170. HttpContext.responseHeaders.set : Map Text [Text]
                                         -> HttpContext
                                         -> HttpContext
  171. HttpContext.responseStatus : HttpContext
                                    -> HttpResponse.Status
  172. HttpContext.responseStatus.modify : (HttpResponse.Status
                                           ->{g} HttpResponse.Status)
                                           -> HttpContext
                                           ->{g} HttpContext
  173. HttpContext.responseStatus.set : HttpResponse.Status
                                        -> HttpContext
                                        -> HttpContext
  174. HttpContext.responseVersion : HttpContext
                                     -> unison_http_3_3_2.Version
  175. HttpContext.responseVersion.modify : (unison_http_3_3_2.Version
                                            ->{g} unison_http_3_3_2.Version)
                                            -> HttpContext
                                            ->{g} HttpContext
  176. HttpContext.responseVersion.set : unison_http_3_3_2.Version
                                         -> HttpContext
                                         -> HttpContext
  177. HttpContext.toResponse : HttpContext -> HttpResponse
  178. HttpContext.toResponse.doc : Doc
  179. ability OpenWebSocket
  180. OpenWebSocket.doc : Doc
  181. OpenWebSocket.openWebSocket : {OpenWebSocket} unison_cloud_18_0_6.websockets.WebSocket
  182. README : Doc
  183. ReleaseNotes : Doc
  184. ability Route
  185. Route.<|> : '{g, Route} a
                   -> '{g1, Route} a
                   -> '{g, g1, Route} a
  186. Route.constants.ContentType : Text
  187. Route.constants.ContentType.doc : Doc
  188. Route.contentTypes.formUrlEncoded : Text
  189. Route.contentTypes.formUrlEncoded.doc : Doc
  190. Route.contentTypes.htmlUtf8 : Text
  191. Route.contentTypes.htmlUtf8.doc : Doc
  192. Route.contentTypes.jsonUtf8 : Text
  193. Route.contentTypes.jsonUtf8.doc : Doc
  194. Route.contentTypes.multipartFormData : Text
  195. Route.contentTypes.multipartFormData.doc : Doc
  196. Route.contentTypes.octetStream : Text
  197. Route.contentTypes.octetStream.doc : Doc
  198. Route.contentTypes.plainUtf8.doc : Doc
  199. Route.contentTypes.textUtf8 : Text
  200. Route.deploy : Environment
                      -> '{Route,
                      unison_cloud_18_0_6.Config,
                      Exception,
                      unison_cloud_18_0_6.State,
                      Http,
                      Services,
                      Remote,
                      Random,
                      Log,
                      Scratch} ()
                      ->{Exception, Cloud} ServiceHash
                        HttpRequest HttpResponse
  201. Route.deploy.doc : Doc
  202. Route.deployWebSocket : Environment
                               -> '{Route,
                               unison_cloud_18_0_6.Config,
                               Exception,
                               unison_cloud_18_0_6.State,
                               Http,
                               OpenWebSocket,
                               Services,
                               Remote,
                               WebSockets,
                               Random,
                               Log,
                               Scratch} ()
                               ->{Exception, Cloud} ServiceHash
                                 HttpRequest
                                 (Either
                                   HttpResponse
                                   (unison_cloud_18_0_6.websockets.WebSocket
                                   ->{Remote, WebSockets} ()))
  203. Route.deployWebSocket.doc : Doc
  204. Route.doc : Doc
  205. Route.getHttpContext : {Route} HttpContext
  206. Route.internal.stripWebSockets : '{g, WebSockets} a
                                        ->{g, Exception} a
  207. Route.modifyContext : (HttpContext -> HttpContext)
                             ->{Route} ()
  208. Route.modifyContext.doc : Doc
  209. Route.noCapture : Method -> Parser () b ->{Route} b
  210. Route.noCapture.doc : Doc
  211. Route.or : '{g, Route} a
                  -> '{g, Route} a
                  -> '{g, Route} a
  212. Route.or.doc : Doc
  213. Route.request.body : '{Route} Bytes
  214. Route.request.body.decodeJson : '{g, Decoder} a
                                       ->{g, Route, Exception} a
  215. Route.request.body.decodeJson.doc : Doc
  216. Route.request.body.doc : Doc
  217. Route.request.bodyUtf8 : '{Route, Exception} Text
  218. Route.request.bodyUtf8.doc : Doc
  219. Route.request.cookies : '{Route} Map Text Text
  220. Route.request.cookies.doc : Doc
  221. Route.request.decodeBody : '{Decode, DecodeBits} a
                                  ->{Route} a
  222. Route.request.deleteCookie.doc : Doc
  223. Route.request.getCookie : Text ->{Route} Optional Text
  224. Route.request.getCookie.doc : Doc
  225. Route.request.getFormData : '{Route, Exception} Map
                                     Text [Text]
  226. Route.request.getFormData.doc : Doc
  227. Route.request.header : Text ->{Route} [Text]
  228. Route.request.header.doc : Doc
  229. Route.request.headers : '{Route} Map Text [Text]
  230. Route.request.headers.doc : Doc
  231. Route.request.headers.get.doc : Doc
  232. Route.request.headers.set : Map Text [Text] ->{Route} ()
  233. Route.request.headers.set.doc : Doc
  234. Route.request.method : '{Route} Method
  235. Route.request.method.set : Method ->{Route} ()
  236. Route.request.method.set.doc : Doc
  237. Route.request.path : '{Route} Path
  238. Route.request.path.doc : Doc
  239. Route.request.query : '{Route} Map Text [Text]
  240. Route.request.query.doc : Doc
  241. Route.request.query.set : Map Text [Text] ->{Route} ()
  242. Route.request.query.set.doc : Doc
  243. Route.request.queryParameter : Text ->{Route} [Text]
  244. Route.request.queryParameter.doc : Doc
  245. Route.request.uri : '{Route} URI
  246. Route.request.uri.doc : Doc
  247. Route.request.uri.set : URI ->{Route} ()
  248. Route.request.uri.set.doc : Doc
  249. Route.request.version : '{Route} unison_http_3_3_2.Version
  250. Route.request.version.doc : Doc
  251. Route.request.version.set : unison_http_3_3_2.Version
                                   ->{Route} ()
  252. Route.request.version.set.doc : Doc
  253. Route.respond.badRequest : Bytes ->{Route} ()
  254. Route.respond.badRequest.doc : Doc
  255. Route.respond.badRequest.html : Text ->{Route} ()
  256. Route.respond.badRequest.html.doc : Doc
  257. Route.respond.badRequest.json : Json ->{Route} ()
  258. Route.respond.badRequest.json.doc : Doc
  259. Route.respond.badRequest.octetStream : Bytes ->{Route} ()
  260. Route.respond.badRequest.octetStream.doc : Doc
  261. Route.respond.badRequest.text : Text ->{Route} ()
  262. Route.respond.badRequest.text.doc : Doc
  263. Route.respond.bytes : Nat -> Text -> Bytes ->{Route} ()
  264. Route.respond.bytes.doc : Doc
  265. Route.respond.forbidden : Bytes ->{Route} ()
  266. Route.respond.forbidden.doc : Doc
  267. Route.respond.forbidden.html : Text ->{Route} ()
  268. Route.respond.forbidden.html.doc : Doc
  269. Route.respond.forbidden.json : Json ->{Route} ()
  270. Route.respond.forbidden.json.doc : Doc
  271. Route.respond.forbidden.octetStream : Bytes ->{Route} ()
  272. Route.respond.forbidden.octetStream.doc : Doc
  273. Route.respond.forbidden.text : Text ->{Route} ()
  274. Route.respond.forbidden.text.doc : Doc
  275. Route.respond.notFound : Bytes ->{Route} ()
  276. Route.respond.notFound.doc : Doc
  277. Route.respond.notFound.html : Text ->{Route} ()
  278. Route.respond.notFound.html.doc : Doc
  279. Route.respond.notFound.json : Json ->{Route} ()
  280. Route.respond.notFound.json.doc : Doc
  281. Route.respond.notFound.octetStream : Bytes ->{Route} ()
  282. Route.respond.notFound.octetStream.doc : Doc
  283. Route.respond.notFound.text : Text ->{Route} ()
  284. Route.respond.notFound.text.doc : Doc
  285. Route.respond.ok : Bytes ->{Route} ()
  286. Route.respond.ok.css : Text ->{Route} ()
  287. Route.respond.ok.css.doc : Doc
  288. Route.respond.ok.doc : Doc
  289. Route.respond.ok.html : Text ->{Route} ()
  290. Route.respond.ok.html.doc : Doc
  291. Route.respond.ok.js : Text ->{Route} ()
  292. Route.respond.ok.js.doc : Doc
  293. Route.respond.ok.json : Json ->{Route} ()
  294. Route.respond.ok.json.doc : Doc
  295. Route.respond.ok.octetStream : Bytes ->{Route} ()
  296. Route.respond.ok.octetStream.doc : Doc
  297. Route.respond.ok.svg : Text ->{Route} ()
  298. Route.respond.ok.svg.doc : Doc
  299. Route.respond.ok.text : Text ->{Route} ()
  300. Route.respond.ok.text.doc : Doc
  301. Route.respond.status : HttpResponse.Status
                              -> Bytes
                              ->{Route} ()
  302. Route.respond.status.css : HttpResponse.Status
                                  -> Text
                                  ->{Route} ()
  303. Route.respond.status.doc : Doc
  304. Route.respond.status.html : HttpResponse.Status
                                   -> Text
                                   ->{Route} ()
  305. Route.respond.status.html.doc : Doc
  306. Route.respond.status.js : HttpResponse.Status
                                 -> Text
                                 ->{Route} ()
  307. Route.respond.status.json : HttpResponse.Status
                                   -> Json
                                   ->{Route} ()
  308. Route.respond.status.json.doc : Doc
  309. Route.respond.status.octetStream : HttpResponse.Status
                                          -> Bytes
                                          ->{Route} ()
  310. Route.respond.status.octetStream.doc : Doc
  311. Route.respond.status.svg : HttpResponse.Status
                                  -> Text
                                  ->{Route} ()
  312. Route.respond.status.text : HttpResponse.Status
                                   -> Text
                                   ->{Route} ()
  313. Route.respond.status.text.doc : Doc
  314. Route.respond.unauthorized : Bytes ->{Route} ()
  315. Route.respond.unauthorized.doc : Doc
  316. Route.respond.unauthorized.html : Text ->{Route} ()
  317. Route.respond.unauthorized.html.doc : Doc
  318. Route.respond.unauthorized.json : Json ->{Route} ()
  319. Route.respond.unauthorized.json.doc : Doc
  320. Route.respond.unauthorized.octetStream : Bytes
                                                ->{Route} ()
  321. Route.respond.unauthorized.octetStream.doc : Doc
  322. Route.respond.unauthorized.text : Text ->{Route} ()
  323. Route.respond.unauthorized.text.doc : Doc
  324. Route.response.appendBody : Bytes ->{Route} ()
  325. Route.response.appendJson : Json ->{Route} ()
  326. Route.response.appendJson.doc : Doc
  327. Route.response.appendText : Text ->{Route} ()
  328. Route.response.appendText.doc : Doc
  329. Route.response.deleteCookie : Cookie ->{Route} ()
  330. Route.response.headers : '{Route} Map Text [Text]
  331. Route.response.headers.add : Text -> Text ->{Route} ()
  332. Route.response.headers.add.doc : Doc
  333. Route.response.headers.doc : Doc
  334. Route.response.headers.get : Text
                                    ->{Route} Optional [Text]
  335. Route.response.headers.get.doc : Doc
  336. Route.response.headers.remove : Text ->{Route} ()
  337. Route.response.headers.remove.doc : Doc
  338. Route.response.headers.set : Map Text [Text] ->{Route} ()
  339. Route.response.headers.set.doc : Doc
  340. Route.response.setCookie : Cookie ->{Route} ()
  341. Route.response.setCookie.doc : Doc
  342. Route.response.setStatus : HttpResponse.Status
                                  ->{Route} ()
  343. Route.response.setStatus.doc : Doc
  344. Route.response.status : '{Route} HttpResponse.Status
  345. Route.response.status.doc : Doc
  346. Route.response.status.set : HttpResponse.Status
                                   ->{Route} ()
  347. Route.response.status.set.doc : Doc
  348. Route.response.version : '{Route} unison_http_3_3_2.Version
  349. Route.response.version.doc : Doc
  350. Route.response.version.set : unison_http_3_3_2.Version
                                    ->{Route} ()
  351. Route.response.version.set.doc : Doc
  352. Route.route : Method -> Parser (a ->{g} a) a ->{Route} a
  353. Route.route.doc : Doc
  354. Route.route.pair : Method
                          -> Parser (a ->{f} c ->{g} (a, c)) b
                          ->{Route} b
  355. Route.route.pair.doc : Doc
  356. Route.route.tuple2 : Method
                            -> Parser (a ->{f} c ->{g} (a, c)) b
                            ->{Route} b
  357. Route.route.tuple2.doc : Doc
  358. Route.route.tuple3 : Method
                            -> Parser
                              (a
                              ->{f} c
                              ->{g} d
                              ->{h} (a, c, d))
                              b
                            ->{Route} b
  359. Route.route.tuple3.doc : Doc
  360. Route.routes : ['{g, Route} a] -> '{g, Route} a
  361. Route.routes.doc : Doc
  362. Route.routes.test : [Result]
  363. Route.run : '{g, Route, Exception} ()
                   -> HttpRequest
                   ->{g, Exception} HttpResponse
  364. Route.run.doc : Doc
  365. Route.run.impl : '{g, Route} ()
                        -> HttpRequest
                        ->{g, Exception} HttpResponse
  366. Route.runWebSocketCloud : '{Route,
                                 unison_cloud_18_0_6.Config,
                                 Exception,
                                 unison_cloud_18_0_6.State,
                                 Http,
                                 OpenWebSocket,
                                 Services,
                                 Remote,
                                 WebSockets,
                                 Random,
                                 Log,
                                 Scratch} ()
                                 -> HttpRequest
                                 ->{unison_cloud_18_0_6.Config,
                                 Exception,
                                 unison_cloud_18_0_6.State,
                                 Http,
                                 Services,
                                 Remote,
                                 Random,
                                 Log,
                                 Scratch} Either
                                   HttpResponse
                                   (unison_cloud_18_0_6.websockets.WebSocket
                                   ->{Exception,
                                   Remote,
                                   WebSockets} ())
  367. Route.runWebSocketCloud.doc : Doc
  368. Route.runWebSocketIO : '{g,
                              Route,
                              OpenWebSocket,
                              WebSockets} ()
                              -> HttpRequest
                              ->{g, IO, Exception} Either
                                HttpResponse
                                (unison_cloud_18_0_6.websockets.WebSocket
                                ->{g, IO, Exception, WebSockets} ())
  369. Route.runWebSocketIO.doc : Doc
  370. Route.serve : '{IO, Route, Exception} ()
                     -> server.Config
                     ->{IO, Exception} '{IO, Exception} ()
  371. Route.serve.doc : Doc
  372. Route.serveSimple : '{IO, Route, Exception} ()
                           -> Nat
                           ->{IO, Exception} '{IO, Exception} ()
  373. Route.serveSimple.doc : Doc
  374. Route.serveWebSocket : '{IO,
                              Route,
                              Exception,
                              OpenWebSocket,
                              WebSockets} ()
                              -> server.Config
                              ->{IO, Exception} '{IO, Exception} ()
  375. Route.setHttpContext : HttpContext ->{Route} ()
  376. Route.skip : Failure ->{Route} x
  377. Route.streaming : '{g, Route} ()
                         -> '{g, Stream Bytes} ()
                         -> HttpRequest
                         ->{g, Exception} ( HttpResponse,
                           '{g, Stream Bytes} ())
  378. Route.streaming.doc : Doc
  379. Route.streaming.impl : '{g, Route} ()
                              -> '{g, Stream Bytes} ()
                              -> HttpContext
                              ->{g, Exception} ( HttpContext,
                                '{g, Stream Bytes} ())
  380. Route.streaming.impl.doc : Doc
  381. Route.streamingAndWebSocketCloud : '{Route,
                                          unison_cloud_18_0_6.Config,
                                          Exception,
                                          unison_cloud_18_0_6.State,
                                          Http,
                                          OpenWebSocket,
                                          Services,
                                          Remote,
                                          WebSockets,
                                          Random,
                                          Log,
                                          Scratch} ()
                                          -> '{Remote,
                                          Stream Bytes} ()
                                          -> HttpRequest
                                          ->{unison_cloud_18_0_6.Config,
                                          Exception,
                                          unison_cloud_18_0_6.State,
                                          Http,
                                          Services,
                                          Remote,
                                          Random,
                                          Log,
                                          Scratch} Either
                                            ( HttpResponse,
                                              '{Remote,
                                            Stream Bytes} ())
                                            (unison_cloud_18_0_6.websockets.WebSocket
                                            ->{Exception,
                                            Remote,
                                            WebSockets} ())
  382. Route.streamingAndWebSocketCloud.doc : Doc
  383. Route.streamingAndWebSocketIO : '{g,
                                       IO,
                                       Route,
                                       Exception,
                                       OpenWebSocket,
                                       WebSockets} ()
                                       -> '{g, IO, Stream Bytes} ()
                                       -> HttpRequest
                                       ->{g, IO, Exception} Either
                                         ( HttpResponse,
                                           '{g,
                                         IO,
                                         Stream Bytes} ())
                                         (unison_cloud_18_0_6.websockets.WebSocket
                                         ->{g,
                                         IO,
                                         Exception,
                                         WebSockets} ())
  384. Route.streamingAndWebSocketIO.impl : '{g,
                                            IO,
                                            Route,
                                            Exception,
                                            OpenWebSocket,
                                            WebSockets} ()
                                            -> '{g,
                                            IO,
                                            Stream Bytes} ()
                                            -> HttpContext
                                            ->{g, IO, Exception} Either
                                              ( HttpContext,
                                                '{g,
                                              IO,
                                              Stream Bytes} ())
                                              (unison_cloud_18_0_6.websockets.WebSocket
                                              ->{g,
                                              IO,
                                              Exception} ())
  385. Route.streamingAndWebSocketRemote : '{Route,
                                           Exception,
                                           OpenWebSocket,
                                           Remote,
                                           WebSockets} ()
                                           -> '{Remote,
                                           Stream Bytes} ()
                                           -> HttpRequest
                                           ->{Exception, Remote} Either
                                             ( HttpResponse,
                                               '{Remote,
                                             Stream Bytes} ())
                                             (unison_cloud_18_0_6.websockets.WebSocket
                                             ->{Exception,
                                             Remote,
                                             WebSockets} ())
  386. Route.streamingAndWebSocketRemote.doc : Doc
  387. Route.streamingAndWebSocketRemote.impl : '{g,
                                                Route,
                                                Exception,
                                                OpenWebSocket,
                                                Remote,
                                                WebSockets} ()
                                                -> '{Remote,
                                                Stream Bytes} ()
                                                -> HttpContext
                                                ->{g,
                                                Exception,
                                                Remote} Either
                                                  ( HttpContext,
                                                    '{Remote,
                                                  Stream Bytes} ())
                                                  (unison_cloud_18_0_6.websockets.WebSocket
                                                  ->{g,
                                                  Exception,
                                                  Remote} ())
  388. Route.symbolic.or.doc : Doc
  389. Route.test.harness : '{g, Route} ()
                            -> '{f, Http} b
                            ->{f, g, Exception} b
  390. Route.test.harness.cloud : '{IO, Exception, Cloud} s
                                  -> (s
                                  ->{Route,
                                  unison_cloud_18_0_6.Config,
                                  Exception,
                                  unison_cloud_18_0_6.State,
                                  Http,
                                  Services,
                                  Remote,
                                  Random,
                                  Log,
                                  Scratch} ())
                                  -> (s
                                  ->{unison_cloud_18_0_6.Config,
                                  Exception,
                                  unison_cloud_18_0_6.State,
                                  Http,
                                  Services,
                                  Remote,
                                  Random,
                                  Log,
                                  Scratch} b)
                                  -> (b
                                  ->{IO,
                                  Exception,
                                  Each,
                                  Random,
                                  Cloud,
                                  Label} ())
                                  ->{IO, Exception} [Result]
  391. Route.test.harness.cloud.doc : Doc
  392. Route.test.harness.cloud.simple : '{IO, Exception, Cloud} s
                                         -> (s
                                         ->{Route,
                                         unison_cloud_18_0_6.Config,
                                         Exception,
                                         unison_cloud_18_0_6.State,
                                         Http,
                                         Services,
                                         Remote,
                                         Random,
                                         Log,
                                         Scratch} ())
                                         -> (s
                                         ->{unison_cloud_18_0_6.Config,
                                         Exception,
                                         unison_cloud_18_0_6.State,
                                         Http,
                                         Services,
                                         Remote,
                                         Random,
                                         Log,
                                         Scratch} b)
                                         ->{IO, Exception} b
  393. Route.test.harness.cloud.simple.doc : Doc
  394. Route.test.harness.cloud.simple.example : '{IO} [Result]
  395. Route.test.harness.doc : Doc
  396. Route.try : '{g, Route} a ->{g, Route} Either Failure a
  397. Route.try.doc : Doc
  398. Route.tryRoute : Method
                        -> Parser (a ->{g} a) a
                        ->{Route, Throw UriParseFailure} a
  399. Route.tryRoute.doc : Doc
  400. Route.tryUri : Parser (a ->{g} a) a
                      ->{Route, Throw UriParseFailure} a
  401. Route.uri : Parser (a ->{g} a) a ->{Route} a
  402. Route.uri.doc : Doc
  403. up.base.abilities.Exception.handleFailure : (Failure
                                                   ->{e} a)
                                                   -> '{g,
                                                   Exception} a
                                                   ->{e, g} a
  404. up.base.data.Multimap.fromList : [(k, v)] -> Map k [v]
  405. up.base.data.Multimap.fromList.doc : Doc
  406. up.base.Float.fromHalfPrecision : Nat -> Float
  407. up.base.Float.fromHalfPrecision.doc : Doc
  408. up.base.Float.fromHalfPrecision.tests.largestSubnormal : [Result]
  409. up.base.Float.fromHalfPrecision.tests.maxHalf : [Result]
  410. up.base.Float.fromHalfPrecision.tests.negativeOne : [Result]
  411. up.base.Float.fromHalfPrecision.tests.negativeZero : [Result]
  412. up.base.Float.fromHalfPrecision.tests.normal : [Result]
  413. up.base.Float.fromHalfPrecision.tests.notANumber : [Result]
  414. up.base.Float.fromHalfPrecision.tests.positiveOne : [Result]
  415. up.base.Float.fromHalfPrecision.tests.positiveZero : [Result]
  416. up.base.Float.fromHalfPrecision.tests.smallestNormal : [Result]
  417. up.base.Float.fromHalfPrecision.tests.subnormal : [Result]
  418. up.base.Float.fromSinglePrecision : Nat -> Float
  419. up.base.Float.fromSinglePrecision.doc : Doc
  420. up.base.Float.fromSinglePrecision.tests.largestSubnormal : [Result]
  421. up.base.Float.fromSinglePrecision.tests.maxSingle : [Result]
  422. up.base.Float.fromSinglePrecision.tests.negativeOne : [Result]
  423. up.base.Float.fromSinglePrecision.tests.negativeZero : [Result]
  424. up.base.Float.fromSinglePrecision.tests.normal : [Result]
  425. up.base.Float.fromSinglePrecision.tests.notANumber : [Result]
  426. up.base.Float.fromSinglePrecision.tests.positiveOne : [Result]
  427. up.base.Float.fromSinglePrecision.tests.positiveZero : [Result]
  428. up.base.Float.fromSinglePrecision.tests.smallestNormal : [Result]
  429. up.base.Float.fromSinglePrecision.tests.subnormal : [Result]
  430. up.base.Float.product : [Float] -> Float
  431. up.base.Float.product.doc : Doc
  432. up.base.Float.sum : [Float] -> Float
  433. up.base.Float.sum.doc : Doc
  434. up.base.Float.toHalfPrecision : Float -> Nat
  435. up.base.Float.toHalfPrecision.doc : Doc
  436. up.base.Float.toHalfPrecision.monotonic : [Result]
  437. up.base.Float.toHalfPrecision.tests.largestSubnormal : [Result]
  438. up.base.Float.toHalfPrecision.tests.maxHalf : [Result]
  439. up.base.Float.toHalfPrecision.tests.negativeOne : [Result]
  440. up.base.Float.toHalfPrecision.tests.negativeZero : [Result]
  441. up.base.Float.toHalfPrecision.tests.normal : [Result]
  442. up.base.Float.toHalfPrecision.tests.notANumber : [Result]
  443. up.base.Float.toHalfPrecision.tests.positiveOne : [Result]
  444. up.base.Float.toHalfPrecision.tests.positiveZero : [Result]
  445. up.base.Float.toHalfPrecision.tests.smallestNormal : [Result]
  446. up.base.Float.toHalfPrecision.tests.subnormal : [Result]
  447. up.base.Float.toSinglePrecision : Float -> Nat
  448. up.base.Float.toSinglePrecision.doc : Doc
  449. up.base.Float.toSinglePrecision.monotonic : [Result]
  450. up.base.Float.toSinglePrecision.tests.largestSubnormal : [Result]
  451. up.base.Float.toSinglePrecision.tests.maxSingle : [Result]
  452. up.base.Float.toSinglePrecision.tests.negativeOne : [Result]
  453. up.base.Float.toSinglePrecision.tests.negativeZero : [Result]
  454. up.base.Float.toSinglePrecision.tests.normal : [Result]
  455. up.base.Float.toSinglePrecision.tests.notANumber : [Result]
  456. up.base.Float.toSinglePrecision.tests.positiveOne : [Result]
  457. up.base.Float.toSinglePrecision.tests.positiveZero : [Result]
  458. up.base.Float.toSinglePrecision.tests.smallestNormal : [Result]
  459. up.base.Float.toSinglePrecision.tests.subnormal : [Result]
  460. up.base.Int.product : [Int] -> Int
  461. up.base.Int.product.doc : Doc
  462. up.base.Int.sum : [Int] -> Int
  463. up.base.Int.sum.doc : Doc
  464. type up.base.time.DayOfWeek
  465. up.base.time.DayOfWeek.daysSinceSat : base.time.DayOfWeek
                                             -> Nat
  466. up.base.time.DayOfWeek.daysSinceSat.doc : Doc
  467. up.base.time.DayOfWeek.doc : Doc
  468. up.base.time.DayOfWeek.Fri : base.time.DayOfWeek
  469. up.base.time.DayOfWeek.fromName : Text
                                         -> Optional
                                           base.time.DayOfWeek
  470. up.base.time.DayOfWeek.fromName.doc : Doc
  471. up.base.time.DayOfWeek.isWeekday : base.time.DayOfWeek
                                          -> Boolean
  472. up.base.time.DayOfWeek.isWeekday.doc : Doc
  473. up.base.time.DayOfWeek.isWeekend : base.time.DayOfWeek
                                          -> Boolean
  474. up.base.time.DayOfWeek.isWeekend.doc : Doc
  475. up.base.time.DayOfWeek.Mon : base.time.DayOfWeek
  476. up.base.time.DayOfWeek.name : base.time.DayOfWeek -> Text
  477. up.base.time.DayOfWeek.name.doc : Doc
  478. up.base.time.DayOfWeek.next : base.time.DayOfWeek
                                     -> base.time.DayOfWeek
  479. up.base.time.DayOfWeek.next.doc : Doc
  480. up.base.time.DayOfWeek.number : Nat
                                       -> base.time.DayOfWeek
  481. up.base.time.DayOfWeek.number.doc : Doc
  482. up.base.time.DayOfWeek.previous : base.time.DayOfWeek
                                         -> base.time.DayOfWeek
  483. up.base.time.DayOfWeek.previous.doc : Doc
  484. up.base.time.DayOfWeek.Sat : base.time.DayOfWeek
  485. up.base.time.DayOfWeek.shortName : base.time.DayOfWeek
                                          -> Text
  486. up.base.time.DayOfWeek.shortName.doc : Doc
  487. up.base.time.DayOfWeek.Sun : base.time.DayOfWeek
  488. up.base.time.DayOfWeek.Thu : base.time.DayOfWeek
  489. up.base.time.DayOfWeek.Tue : base.time.DayOfWeek
  490. up.base.time.DayOfWeek.Wed : base.time.DayOfWeek
  491. up.base.time.LocalDate.dayOfWeek : LocalDate
                                          -> base.time.DayOfWeek
  492. up.base.time.LocalDate.dayOfWeek.doc : Doc
  493. up.base.time.LocalDateTime.dayOfWeek : LocalDateTime
                                              -> base.time.DayOfWeek
  494. up.base.time.LocalDateTime.dayOfWeek.doc : Doc
  495. up.base.time.OffsetDateTime.dayOfWeek : OffsetDateTime
                                               -> base.time.DayOfWeek
  496. up.base.time.OffsetDateTime.dayOfWeek.doc : Doc
  497. up.codec.Decode.feedPartial : Bytes
                                     -> '{g, Decode} a
                                     -> '{g, Decode} (a, Bytes)
  498. up.codec.Decode.feedPartial.doc : Doc
  499. up.codec.Decode.float16be : '{Decode} Float
  500. up.codec.Decode.float16be.doc : Doc
  501. up.codec.Decode.float16le : '{Decode} Float
  502. up.codec.Decode.float16le.doc : Doc
  503. up.codec.Decode.float32be : '{Decode} Float
  504. up.codec.Decode.float32be.doc : Doc
  505. up.codec.Decode.float32le : '{Decode} Float
  506. up.codec.Decode.float32le.doc : Doc
  507. up.codec.Decode.float64be : '{Decode} Float
  508. up.codec.Decode.float64be.doc : Doc
  509. up.codec.Decode.float64le : '{Decode} Float
  510. up.codec.Decode.float64le.doc : Doc
  511. up.codec.Decode.fromStreamPartial : '{g,
                                           Decode,
                                           DecodeBits} a
                                           -> '{g, Stream Bytes} r
                                           ->{g,
                                           Throw DecodeError} ( a,
                                             '{g, Stream Bytes} r)
  512. up.codec.Decode.fromStreamPartial.doc : Doc
  513. up.codec.DecodeError.toFailure : DecodeError -> Failure
  514. up.codec.DecodeError.toFailure.doc : Doc
```
