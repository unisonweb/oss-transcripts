# Cloud

This is the official Unison Cloud client library. It contains functions for deploying Unison Cloud services, running distributed programs, and interacting with the Unison Cloud API.

## Library contents list

``` ucm
@unison/cloud/main> pull.without-history @unison/cloud/releases/20.1.0

  Downloaded 28193 entities.

  ✅

  Successfully updated @unison/cloud/main from
  @unison/cloud/releases/20.1.0.

@unison/cloud/main> find

  1.    type AccessToken
  2.    AccessToken.AccessToken : Text -> AccessToken
  3.    AccessToken.doc : Doc
  4.    type Blob.ETag
  5.    Blob.ETag.doc : Doc
  6.    Blob.ETag.ETag : Text -> ETag
  7.    type Blob.Key
  8.    Blob.Key.doc : Doc
  9.    Blob.Key.Key : Text -> Key
  10.   Blob.Key.toText : Key -> Text
  11.   type Blob.Metadata
  12.   Blob.Metadata.byteCount : Metadata -> Nat
  13.   Blob.Metadata.doc : Doc
  14.   Blob.Metadata.etag : Metadata -> ETag
  15.   Blob.Metadata.key : Metadata -> Key
  16.   Blob.Metadata.lastModified : Metadata -> Instant
  17.   Blob.Metadata.Metadata : Key
                                 -> ETag
                                 -> Nat
                                 -> Instant
                                 -> Metadata
  18.   ability Blobs
  19.   Blobs.bytes.create : Database
                             -> Key
                             -> Bytes
                             ->{Exception, Blobs} ETag
  20.   Blobs.bytes.create.doc : Doc
  21.   Blobs.bytes.createStreaming : Database
                                      -> Key
                                      -> '{Remote, Stream Bytes} ()
                                      ->{Exception, Blobs} ETag
  22.   Blobs.bytes.delete : Database
                             -> Key
                             ->{Exception, Blobs} ()
  23.   Blobs.bytes.delete.doc : Doc
  24.   Blobs.bytes.list : Database
                           -> Optional Nat
                           -> Text
                           -> Optional PageToken
                           ->{Exception, Blobs} PrefixListResults
  25.   Blobs.bytes.list.doc : Doc
  26.   Blobs.bytes.prefixQuery : Database
                                  -> Optional Nat
                                  -> Text
                                  -> Optional PageToken
                                  ->{Exception, Blobs} PrefixQueryResults
  27.   Blobs.bytes.prefixQuery.doc : Doc
  28.   Blobs.bytes.read : Database
                           -> Key
                           ->{Exception, Blobs} Optional
                             (Bytes, Metadata)
  29.   Blobs.bytes.read.doc : Doc
  30.   Blobs.bytes.readMetadata : Database
                                   -> Key
                                   ->{Exception, Blobs} Optional
                                     Metadata
  31.   Blobs.bytes.readMetadata.doc : Doc
  32.   Blobs.bytes.readRange : Database
                                -> Key
                                -> Nat
                                -> Nat
                                ->{Exception, Blobs} Optional
                                  (Bytes, ETag)
  33.   Blobs.bytes.tryCreate : Database
                                -> Key
                                -> Bytes
                                ->{Blobs} Either Failure ETag
  34.   Blobs.bytes.tryCreateStreaming : Database
                                         -> Key
                                         -> '{Remote,
                                         Stream Bytes} ()
                                         ->{Blobs} Either
                                           Failure ETag
  35.   Blobs.bytes.tryDelete : Database
                                -> Key
                                ->{Blobs} Either Failure ()
  36.   Blobs.bytes.tryList : Database
                              -> Optional Nat
                              -> Text
                              -> Optional PageToken
                              ->{Blobs} Either
                                Failure PrefixListResults
  37.   Blobs.bytes.tryList.doc : Doc
  38.   Blobs.bytes.tryList.impl : Database
                                   -> Optional Nat
                                   -> Text
                                   -> Text
                                   -> Optional PageToken
                                   ->{Blobs} Either
                                     Failure PrefixListResults
  39.   Blobs.bytes.tryPrefixQuery : Database
                                     -> Optional Nat
                                     -> Text
                                     -> Optional PageToken
                                     ->{Blobs} Either
                                       Failure
                                       PrefixQueryResults
  40.   Blobs.bytes.tryRead : Database
                              -> Key
                              ->{Blobs} Either
                                Failure
                                (Optional (Bytes, Metadata))
  41.   Blobs.bytes.tryReadMetadata : Database
                                      -> Key
                                      ->{Blobs} Either
                                        Failure
                                        (Optional Metadata)
  42.   Blobs.bytes.tryReadRange : Database
                                   -> Key
                                   -> Nat
                                   -> Nat
                                   ->{Blobs} Either
                                     Failure
                                     (Optional (Bytes, ETag))
  43.   Blobs.bytes.tryWrite : Database
                               -> Key
                               -> Bytes
                               ->{Blobs} Either Failure ETag
  44.   Blobs.bytes.tryWriteStreaming : Database
                                        -> Key
                                        -> '{Remote,
                                        Stream Bytes} ()
                                        ->{Blobs} Either
                                          Failure ETag
  45.   Blobs.bytes.write : Database
                            -> Key
                            -> Bytes
                            ->{Exception, Blobs} ETag
  46.   Blobs.bytes.write.doc : Doc
  47.   Blobs.bytes.writeStreaming : Database
                                     -> Key
                                     -> '{Remote, Stream Bytes} ()
                                     ->{Exception, Blobs} ETag
  48.   Blobs.doc : Doc
  49.   type Blobs.PageToken
  50.   Blobs.PageToken.doc : Doc
  51.   Blobs.PageToken.PageToken : Text -> PageToken
  52.   Blobs.PageToken.toText : PageToken -> Text
  53.   type Blobs.PrefixListResult
  54.   Blobs.PrefixListResult.BlobResult : Metadata
                                            -> PrefixListResult
  55.   Blobs.PrefixListResult.PrefixResult : Text
                                              -> PrefixListResult
  56.   type Blobs.PrefixListResults
  57.   Blobs.PrefixListResults.nextPageToken : PrefixListResults
                                                -> Optional
                                                  PageToken
  58.   Blobs.PrefixListResults.PrefixListResults : Optional
                                                      PageToken
                                                    -> [PrefixListResult]
                                                    -> PrefixListResults
  59.   Blobs.PrefixListResults.results : PrefixListResults
                                          -> [PrefixListResult]
  60.   Blobs.PrefixQueryResult.blobs : PrefixQueryResults
                                        -> [Metadata]
  61.   Blobs.PrefixQueryResult.nextPageToken : PrefixQueryResults
                                                -> Optional
                                                  PageToken
  62.   type Blobs.PrefixQueryResults
  63.   Blobs.PrefixQueryResults.PrefixQueryResults : Optional
                                                        PageToken
                                                      -> [Metadata]
                                                      -> PrefixQueryResults
  64.   Blobs.typed.create : Database
                             -> Key
                             -> a
                             ->{Exception, Blobs} ETag
  65.   Blobs.typed.create.doc : Doc
  66.   Blobs.typed.delete : Database
                             -> Key
                             ->{Exception, Blobs} ()
  67.   Blobs.typed.delete.doc : Doc
  68.   Blobs.typed.list : Database
                           -> Optional Nat
                           -> Text
                           -> Optional PageToken
                           ->{Exception, Blobs} PrefixListResults
  69.   Blobs.typed.list.doc : Doc
  70.   Blobs.typed.prefixQuery : Database
                                  -> Optional Nat
                                  -> Text
                                  -> Optional PageToken
                                  ->{Exception, Blobs} PrefixQueryResults
  71.   Blobs.typed.prefixQuery.doc : Doc
  72.   Blobs.typed.read : Database
                           -> Key
                           ->{Exception, Blobs} Optional
                             (a, Metadata)
  73.   Blobs.typed.read.doc : Doc
  74.   Blobs.typed.readMetadata : Database
                                   -> Key
                                   ->{Exception, Blobs} Optional
                                     Metadata
  75.   Blobs.typed.readMetadata.doc : Doc
  76.   Blobs.typed.tryCreate : Database
                                -> Key
                                -> a
                                ->{Blobs} Either Failure ETag
  77.   Blobs.typed.tryDelete : Database
                                -> Key
                                ->{Blobs} Either Failure ()
  78.   Blobs.typed.tryList : Database
                              -> Optional Nat
                              -> Text
                              -> Optional PageToken
                              ->{Blobs} Either
                                Failure PrefixListResults
  79.   Blobs.typed.tryList.doc : Doc
  80.   Blobs.typed.tryList.impl : Database
                                   -> Optional Nat
                                   -> Text
                                   -> Text
                                   -> Optional PageToken
                                   ->{Blobs} Either
                                     Failure PrefixListResults
  81.   Blobs.typed.tryPrefixQuery : Database
                                     -> Optional Nat
                                     -> Text
                                     -> Optional PageToken
                                     ->{Blobs} Either
                                       Failure
                                       PrefixQueryResults
  82.   Blobs.typed.tryRead : Database
                              -> Key
                              ->{Blobs} Either
                                Failure (Optional (a, Metadata))
  83.   Blobs.typed.tryReadMetadata : Database
                                      -> Key
                                      ->{Blobs} Either
                                        Failure
                                        (Optional Metadata)
  84.   Blobs.typed.tryWrite : Database
                               -> Key
                               -> a
                               ->{Blobs} Either Failure ETag
  85.   Blobs.typed.write : Database
                            -> Key
                            -> a
                            ->{Exception, Blobs} ETag
  86.   Blobs.typed.write.doc : Doc
  87.   ability Cloud
  88.   type Cloud.ClientConfig
  89.   Cloud.ClientConfig.authority : Cloud.ClientConfig
                                       -> Authority
  90.   Cloud.ClientConfig.authority.doc : Doc
  91.   Cloud.ClientConfig.ClientConfig : HostName
                                          -> Port
                                          -> Port
                                          -> AccessToken
                                          -> Optional
                                            Tls.ClientConfig
                                          -> client.Config
                                          -> Cloud.ClientConfig
  92.   Cloud.ClientConfig.default : '{IO, Exception} Cloud.ClientConfig
  93.   Cloud.ClientConfig.default.doc : Doc
  94.   Cloud.ClientConfig.defaultHttp.doc : Doc
  95.   Cloud.ClientConfig.defaults.defaultTlsConfig : HostName
                                                       -> Tls.ClientConfig
  96.   Cloud.ClientConfig.defaults.defaultTlsConfig.doc : Doc
  97.   Cloud.ClientConfig.defaults.defaultUnisonCloudHost : '{IO,
                                                             Exception} HostName
  98.   Cloud.ClientConfig.defaults.defaultUnisonCloudHost.doc : Doc
  99.   Cloud.ClientConfig.defaults.defaultUnisonCloudHttpPort : Optional
                                                                   Tls.ClientConfig
                                                                 ->{IO,
                                                                 Exception} Port
  100.  Cloud.ClientConfig.defaults.defaultUnisonCloudHttpPort.doc : Doc
  101.  Cloud.ClientConfig.defaults.defaultUnisonCloudPort : Optional
                                                               Tls.ClientConfig
                                                             ->{IO} Port
  102.  Cloud.ClientConfig.defaults.defaultUnisonCloudPort.doc : Doc
  103.  Cloud.ClientConfig.doc : Doc
  104.  Cloud.ClientConfig.host : Cloud.ClientConfig -> HostName
  105.  Cloud.ClientConfig.host.doc : Doc
  106.  Cloud.ClientConfig.host.modify : (HostName
                                         ->{g} HostName)
                                         -> Cloud.ClientConfig
                                         ->{g} Cloud.ClientConfig
  107.  Cloud.ClientConfig.host.modify.doc : Doc
  108.  Cloud.ClientConfig.host.set : HostName
                                      -> Cloud.ClientConfig
                                      -> Cloud.ClientConfig
  109.  Cloud.ClientConfig.host.set.doc : Doc
  110.  Cloud.ClientConfig.httpConfig : Cloud.ClientConfig
                                        -> client.Config
  111.  Cloud.ClientConfig.httpConfig.doc : Doc
  112.  Cloud.ClientConfig.httpConfig.modify : (client.Config
                                               ->{g} client.Config)
                                               -> Cloud.ClientConfig
                                               ->{g} Cloud.ClientConfig
  113.  Cloud.ClientConfig.httpConfig.modify.doc : Doc
  114.  Cloud.ClientConfig.httpConfig.set : client.Config
                                            -> Cloud.ClientConfig
                                            -> Cloud.ClientConfig
  115.  Cloud.ClientConfig.httpConfig.set.doc : Doc
  116.  Cloud.ClientConfig.httpPort : Cloud.ClientConfig -> Port
  117.  Cloud.ClientConfig.httpPort.doc : Doc
  118.  Cloud.ClientConfig.httpPort.modify : (Port ->{g} Port)
                                             -> Cloud.ClientConfig
                                             ->{g} Cloud.ClientConfig
  119.  Cloud.ClientConfig.httpPort.modify.doc : Doc
  120.  Cloud.ClientConfig.httpPort.set : Port
                                          -> Cloud.ClientConfig
                                          -> Cloud.ClientConfig
  121.  Cloud.ClientConfig.httpPort.set.doc : Doc
  122.  Cloud.ClientConfig.httpUri : Cloud.ClientConfig
                                     -> Path
                                     -> RawQuery
                                     -> URI
  123.  Cloud.ClientConfig.httpUri.doc : Doc
  124.  Cloud.ClientConfig.tcpPort : Cloud.ClientConfig -> Port
  125.  Cloud.ClientConfig.tcpPort.doc : Doc
  126.  Cloud.ClientConfig.tcpPort.modify : (Port ->{g} Port)
                                            -> Cloud.ClientConfig
                                            ->{g} Cloud.ClientConfig
  127.  Cloud.ClientConfig.tcpPort.modify.doc : Doc
  128.  Cloud.ClientConfig.tcpPort.set : Port
                                         -> Cloud.ClientConfig
                                         -> Cloud.ClientConfig
  129.  Cloud.ClientConfig.tcpPort.set.doc : Doc
  130.  Cloud.ClientConfig.tlsConfig : Cloud.ClientConfig
                                       -> Optional
                                         Tls.ClientConfig
  131.  Cloud.ClientConfig.tlsConfig.doc : Doc
  132.  Cloud.ClientConfig.tlsConfig.modify : (Optional
                                                Tls.ClientConfig
                                              ->{g} Optional
                                                Tls.ClientConfig)
                                              -> Cloud.ClientConfig
                                              ->{g} Cloud.ClientConfig
  133.  Cloud.ClientConfig.tlsConfig.modify.doc : Doc
  134.  Cloud.ClientConfig.tlsConfig.set : Optional
                                             Tls.ClientConfig
                                           -> Cloud.ClientConfig
                                           -> Cloud.ClientConfig
  135.  Cloud.ClientConfig.tlsConfig.set.doc : Doc
  136.  Cloud.ClientConfig.token : Cloud.ClientConfig
                                   -> AccessToken
  137.  Cloud.ClientConfig.token.doc : Doc
  138.  Cloud.ClientConfig.token.modify : (AccessToken
                                          ->{g} AccessToken)
                                          -> Cloud.ClientConfig
                                          ->{g} Cloud.ClientConfig
  139.  Cloud.ClientConfig.token.modify.doc : Doc
  140.  Cloud.ClientConfig.token.set : AccessToken
                                       -> Cloud.ClientConfig
                                       -> Cloud.ClientConfig
  141.  Cloud.ClientConfig.token.set.doc : Doc
  142.  Cloud.Daemon.assign : Daemon
                              -> DaemonHash
                              ->{Exception, Cloud} ()
  143.  Cloud.Daemon.assign.impl : Daemon
                                   -> DaemonHash
                                   ->{Cloud} Either Failure ()
  144.  Cloud.Daemon.create.impl : Text
                                   ->{Cloud} Either
                                     Failure Daemon
  145.  Cloud.Daemon.delete : Daemon ->{Exception, Cloud} ()
  146.  Cloud.Daemon.delete.impl : Daemon
                                   ->{Cloud} Either Failure ()
  147.  Cloud.Daemon.deploy : Daemon
                              -> Environment
                              -> '{Environment.Config,
                              Exception,
                              Http,
                              Blobs,
                              Services,
                              Storage,
                              Remote,
                              websockets.HttpWebSocket,
                              WebSockets,
                              Random,
                              Log,
                              Scratch} ()
                              ->{Exception, Cloud} DaemonHash
  148.  Cloud.Daemon.deploy.doc : Doc
  149.  Cloud.Daemon.logs.tail.console : Daemon
                                         ->{IO,
                                         Exception,
                                         Cloud} Void
  150.  Cloud.Daemon.named : Text ->{Exception, Cloud} Daemon
  151.  Cloud.Daemon.unassign : Daemon ->{Exception, Cloud} ()
  152.  Cloud.Daemon.unassign.impl : Daemon
                                     ->{Cloud} Either Failure ()
  153.  Cloud.DaemonHash.create : Environment
                                  -> '{Environment.Config,
                                  Exception,
                                  Http,
                                  Blobs,
                                  Services,
                                  Storage,
                                  Remote,
                                  websockets.HttpWebSocket,
                                  WebSockets,
                                  Random,
                                  Log,
                                  Scratch} ()
                                  ->{Exception, Cloud} DaemonHash
  154.  Cloud.DaemonHash.create.impl : Environment
                                       -> '{Remote} ()
                                       ->{Cloud} Either
                                         Failure DaemonHash
  155.  Cloud.DaemonHash.create.remote : Environment
                                         -> '{Remote} ()
                                         ->{Exception, Cloud} DaemonHash
  156.  Cloud.DaemonHash.delete : DaemonHash
                                  ->{Exception, Cloud} ()
  157.  Cloud.DaemonHash.delete.impl : DaemonHash
                                       ->{Cloud} Either
                                         Failure ()
  158.  Cloud.DaemonHash.logs.tail.console : DaemonHash
                                             ->{IO,
                                             Exception,
                                             Cloud} Void
  159.  Cloud.Database.assign.impl : Database
                                     -> Environment
                                     ->{Cloud} Either Failure ()
  160.  Cloud.Database.create.impl : Text
                                     ->{Cloud} Either
                                       Failure Database
  161.  Cloud.Database.delete.impl : Database
                                     ->{Cloud} Either Failure ()
  162.  Cloud.Database.unassign.impl : Database
                                       -> Environment
                                       ->{Cloud} Either
                                         Failure ()
  163.  Cloud.deploy : Environment
                       -> (a
                       ->{Environment.Config,
                       Exception,
                       Http,
                       Blobs,
                       Services,
                       Storage,
                       Remote,
                       Random,
                       Log,
                       Scratch} b)
                       ->{Exception, Cloud} ServiceHash a b
  164.  Cloud.deploy.doc : Doc
  165.  Cloud.deploy.doc.example : '{IO, Exception, Cloud} ServiceHash
                                     Text Bytes
  166.  Cloud.deploy.impl : Environment
                            -> (a ->{Remote} b)
                            ->{Cloud} Either
                              Failure (ServiceHash a b)
  167.  Cloud.deploy.remote : Environment
                              -> (a ->{Remote} b)
                              ->{Exception, Cloud} ServiceHash
                                a b
  168.  Cloud.deploy.remote.doc : Doc
  169.  Cloud.deployHttp : Environment
                           -> (HttpRequest
                           ->{Environment.Config,
                           Exception,
                           Http,
                           Blobs,
                           Services,
                           Storage,
                           Remote,
                           Random,
                           Log,
                           Scratch} HttpResponse)
                           ->{Exception, Cloud} ServiceHash
                             HttpRequest HttpResponse
  170.  Cloud.deployHttp.doc : Doc
  171.  Cloud.deployHttp.doc.example : '{IO, Exception, Cloud} ServiceHash
                                         HttpRequest
                                         HttpResponse
  172.  Cloud.deployHttp.remote : Environment
                                  -> (HttpRequest
                                  ->{Remote} HttpResponse)
                                  ->{Exception, Cloud} ServiceHash
                                    HttpRequest HttpResponse
  173.  Cloud.deployHttp.remote.doc : Doc
  174.  Cloud.deployHttpWebSocket : Environment
                                    -> (HttpRequest
                                    ->{Environment.Config,
                                    Exception,
                                    Http,
                                    Blobs,
                                    Services,
                                    Storage,
                                    Remote,
                                    Random,
                                    Log,
                                    Scratch} Either
                                      HttpResponse
                                      (websockets.WebSocket
                                      ->{Exception,
                                      Remote,
                                      WebSockets} ()))
                                    ->{Exception, Cloud} ServiceHash
                                      HttpRequest
                                      (Either
                                        HttpResponse
                                        (websockets.WebSocket
                                        ->{Remote, WebSockets} ()))
  175.  Cloud.deployHttpWebSocket.doc : Doc
  176.  Cloud.deployHttpWebSocket.remote : Environment
                                           -> (HttpRequest
                                           ->{Remote} Either
                                             HttpResponse
                                             (websockets.WebSocket
                                             ->{Exception,
                                             Remote,
                                             WebSockets} ()))
                                           ->{Exception, Cloud} ServiceHash
                                             HttpRequest
                                             (Either
                                               HttpResponse
                                               (websockets.WebSocket
                                               ->{Remote,
                                               WebSockets} ()))
  177.  Cloud.deployHttpWebSocket.remote.doc : Doc
  178.  Cloud.deployWebSocket : Environment
                                -> (websockets.WebSocket
                                ->{Exception,
                                Remote,
                                WebSockets} ())
                                ->{Exception, Cloud} ServiceHash
                                  HttpRequest
                                  (Either
                                    HttpResponse
                                    (websockets.WebSocket
                                    ->{Remote, WebSockets} ()))
  179.  Cloud.deployWebSocket.doc : Doc
  180.  Cloud.doc : Doc
  181.  Cloud.domains.createDomainMapping : HostName
                                            -> Text
                                            ->{IO, Exception} ()
  182.  Cloud.domains.createDomainMapping.doc : Doc
  183.  Cloud.domains.createDomainMapping.withConfig : Cloud.ClientConfig
                                                       -> HostName
                                                       -> Text
                                                       ->{IO,
                                                       Exception} ()
  184.  Cloud.domains.createDomainMapping.withConfig.doc : Doc
  185.  Cloud.domains.deleteDomainMapping : HostName
                                            ->{IO, Exception} ()
  186.  Cloud.domains.deleteDomainMapping.doc : Doc
  187.  Cloud.domains.deleteDomainMapping.withConfig : Cloud.ClientConfig
                                                       -> HostName
                                                       ->{IO,
                                                       Exception} ()
  188.  Cloud.domains.deleteDomainMapping.withConfig.doc : Doc
  189.  Cloud.domains.doc : Doc
  190.  Cloud.domains.example : '{IO, Exception} ()
  191.  Cloud.domains.getDomainMapping : HostName
                                         ->{IO, Exception} Text
  192.  Cloud.domains.getDomainMapping.doc : Doc
  193.  Cloud.domains.getDomainMapping.withConfig : Cloud.ClientConfig
                                                    -> HostName
                                                    ->{IO,
                                                    Exception} Text
  194.  Cloud.domains.getDomainMapping.withConfig.doc : Doc
  195.  Cloud.domains.listDomainMappings : '{IO, Exception} [( HostName,
                                             Text)]
  196.  Cloud.domains.listDomainMappings.doc : Doc
  197.  Cloud.domains.listDomainMappings.withConfig : Cloud.ClientConfig
                                                      ->{IO,
                                                      Exception} [( HostName,
                                                        Text)]
  198.  Cloud.domains.listDomainMappings.withConfig.doc : Doc
  199.  Cloud.Environment.create.impl : Text
                                        ->{Cloud} Either
                                          Failure Environment
  200.  Cloud.Environment.delete.impl : Environment
                                        ->{Cloud} Either
                                          Failure ()
  201.  Cloud.Environment.deleteValue.impl : Environment
                                             -> Text
                                             ->{Cloud} Either
                                               Failure ()
  202.  Cloud.Environment.list.impl : {Cloud} (Either
                                        Failure [Environment])
  203.  Cloud.Environment.setValue.impl : Environment
                                          -> Text
                                          -> Text
                                          ->{Cloud} Either
                                            Failure ()
  204.  Cloud.exposeHttp : ServiceHash HttpRequest HttpResponse
                           ->{Exception, Cloud} URI
  205.  Cloud.exposeHttp.doc : Doc
  206.  Cloud.exposeHttp.doc.example : '{IO, Exception, Cloud} URI
  207.  Cloud.exposeHttp.doc.example.handleRequest : HttpRequest
                                                     ->{Environment.Config,
                                                     Exception} HttpResponse
  208.  Cloud.exposeHttp.impl : ServiceHash
                                  HttpRequest HttpResponse
                                ->{Cloud} Either Failure URI
  209.  Cloud.exposeHttpWebSocket : ServiceHash
                                      HttpRequest
                                      (Either
                                        HttpResponse
                                        (websockets.WebSocket
                                        ->{Remote, WebSockets} ()))
                                    ->{Exception, Cloud} URI
  210.  Cloud.exposeHttpWebSocket.doc : Doc
  211.  Cloud.exposeHttpWebSocket.impl : ServiceHash
                                           HttpRequest
                                           (Either
                                             HttpResponse
                                             (websockets.WebSocket
                                             ->{Remote,
                                             WebSockets} ()))
                                         ->{Cloud} Either
                                           Failure URI
  212.  Cloud.logs : QueryOptions ->{Exception, Cloud} [Json]
  213.  type Cloud.logs.Direction
  214.  Cloud.logs.Direction.Backward : Direction
  215.  Cloud.logs.Direction.doc : Doc
  216.  Cloud.logs.Direction.Forward : Direction
  217.  Cloud.logs.Direction.toText : Direction -> Text
  218.  Cloud.logs.Direction.toText.doc : Doc
  219.  Cloud.logs.doc : Doc
  220.  Cloud.logs.impl : QueryOptions
                          ->{Cloud} Either Failure [Json]
  221.  Cloud.logs.internal.pageLogs : QueryOptions
                                       -> (QueryOptions
                                       ->{g, IO} [Json])
                                       ->{g,
                                       IO,
                                       Exception,
                                       Stream Json} Void
  222.  type Cloud.logs.QueryOptions
  223.  Cloud.logs.QueryOptions.default : QueryOptions
  224.  Cloud.logs.QueryOptions.default.doc : Doc
  225.  Cloud.logs.QueryOptions.direction : QueryOptions
                                            -> Optional
                                              Direction
  226.  Cloud.logs.QueryOptions.direction.doc : Doc
  227.  Cloud.logs.QueryOptions.direction.modify : (Optional
                                                     Direction
                                                   ->{g} Optional
                                                     Direction)
                                                   -> QueryOptions
                                                   ->{g} QueryOptions
  228.  Cloud.logs.QueryOptions.direction.set : Optional
                                                  Direction
                                                -> QueryOptions
                                                -> QueryOptions
  229.  Cloud.logs.QueryOptions.doc : Doc
  230.  Cloud.logs.QueryOptions.end : QueryOptions
                                      -> Optional Instant
  231.  Cloud.logs.QueryOptions.end.doc : Doc
  232.  Cloud.logs.QueryOptions.end.modify : (Optional Instant
                                             ->{g} Optional
                                               Instant)
                                             -> QueryOptions
                                             ->{g} QueryOptions
  233.  Cloud.logs.QueryOptions.end.set : Optional Instant
                                          -> QueryOptions
                                          -> QueryOptions
  234.  Cloud.logs.QueryOptions.limit : QueryOptions
                                        -> Optional Nat
  235.  Cloud.logs.QueryOptions.limit.doc : Doc
  236.  Cloud.logs.QueryOptions.limit.modify : (Optional Nat
                                               ->{g} Optional
                                                 Nat)
                                               -> QueryOptions
                                               ->{g} QueryOptions
  237.  Cloud.logs.QueryOptions.limit.set : Optional Nat
                                            -> QueryOptions
                                            -> QueryOptions
  238.  Cloud.logs.QueryOptions.QueryOptions : Optional Text
                                               -> Optional Nat
                                               -> Optional
                                                 Instant
                                               -> Optional
                                                 Instant
                                               -> Optional
                                                 Direction
                                               -> QueryOptions
  239.  Cloud.logs.QueryOptions.search : QueryOptions
                                         -> Optional Text
  240.  Cloud.logs.QueryOptions.search.doc : Doc
  241.  Cloud.logs.QueryOptions.search.modify : (Optional Text
                                                ->{g} Optional
                                                  Text)
                                                -> QueryOptions
                                                ->{g} QueryOptions
  242.  Cloud.logs.QueryOptions.search.set : Optional Text
                                             -> QueryOptions
                                             -> QueryOptions
  243.  Cloud.logs.QueryOptions.start : QueryOptions
                                        -> Optional Instant
  244.  Cloud.logs.QueryOptions.start.doc : Doc
  245.  Cloud.logs.QueryOptions.start.modify : (Optional Instant
                                               ->{g} Optional
                                                 Instant)
                                               -> QueryOptions
                                               ->{g} QueryOptions
  246.  Cloud.logs.QueryOptions.start.set : Optional Instant
                                            -> QueryOptions
                                            -> QueryOptions
  247.  Cloud.logs.service : ServiceHash a b
                             -> QueryOptions
                             ->{IO, Exception} [Json]
  248.  Cloud.logs.service.doc : Doc
  249.  Cloud.logs.service.tail : ServiceHash a b
                                  ->{IO, Exception, Stream Json} Void
  250.  Cloud.logs.service.tail.console : ServiceHash a b
                                          ->{IO, Exception} Void
  251.  Cloud.logs.service.tail.console.doc : Doc
  252.  Cloud.logs.service.tail.doc : Doc
  253.  Cloud.logs.service.tail.withConfig : Cloud.ClientConfig
                                             -> ServiceHash a b
                                             ->{IO,
                                             Exception,
                                             Stream Json} Void
  254.  Cloud.logs.service.tail.withConfig.doc : Doc
  255.  Cloud.logs.service.withConfig : Cloud.ClientConfig
                                        -> ServiceHash a b
                                        -> QueryOptions
                                        ->{IO, Exception} [Json]
  256.  Cloud.logs.service.withConfig.doc : Doc
  257.  Cloud.logs.spec : Doc
  258.  Cloud.logs.tail : QueryOptions
                          ->{IO, Exception, Stream Json} Void
  259.  Cloud.logs.tail.console : ServiceHash a b
                                  ->{IO, Exception} Void
  260.  Cloud.logs.tail.console.doc : Doc
  261.  Cloud.logs.tail.doc : Doc
  262.  Cloud.logs.tail.withConfig : Cloud.ClientConfig
                                     -> QueryOptions
                                     ->{IO,
                                     Exception,
                                     Stream Json} Void
  263.  Cloud.logs.tail.withConfig.doc : Doc
  264.  Cloud.main : '{IO, Exception, Cloud} a
                     -> '{IO, Exception} a
  265.  Cloud.main.doc : Doc
  266.  Cloud.main.example.myMain : '{IO, Exception} ServiceHash
                                      HttpRequest HttpResponse
  267.  Cloud.main.local : '{IO, Exception, Cloud} t
                           -> '{IO, Exception} t
  268.  Cloud.main.local.doc : Doc
  269.  Cloud.main.local.serve : '{IO, Exception, Cloud} a
                                 -> '{IO, Exception} a
  270.  Cloud.main.local.serve.doc : Doc
  271.  Cloud.run : '{g, Cloud} a ->{g, IO, Exception} a
  272.  Cloud.run.doc : Doc
  273.  Cloud.run.local : '{IO, Exception, Cloud} a
                          ->{IO, Exception} a
  274.  Cloud.run.local.doc : Doc
  275.  Cloud.run.local.doc.configuration : Doc
  276.  Cloud.run.local.impl : LocalCloudConfig
                               -> Interrupt
                               -> '{IO, Exception, Cloud} a
                               ->{IO, Exception, Random} a
  277.  type Cloud.run.local.LocalCloudConfig
  278.  Cloud.run.local.LocalCloudConfig.default : '{IO} LocalCloudConfig
  279.  Cloud.run.local.LocalCloudConfig.httpHost : LocalCloudConfig
                                                    -> Optional
                                                      HostName
  280.  Cloud.run.local.LocalCloudConfig.httpHost.modify : (Optional
                                                             HostName
                                                           ->{g} Optional
                                                             HostName)
                                                           -> LocalCloudConfig
                                                           ->{g} LocalCloudConfig
  281.  Cloud.run.local.LocalCloudConfig.httpHost.set : Optional
                                                          HostName
                                                        -> LocalCloudConfig
                                                        -> LocalCloudConfig
  282.  Cloud.run.local.LocalCloudConfig.httpPort : LocalCloudConfig
                                                    -> Port
  283.  Cloud.run.local.LocalCloudConfig.httpPort.modify : (Port
                                                           ->{g} Port)
                                                           -> LocalCloudConfig
                                                           ->{g} LocalCloudConfig
  284.  Cloud.run.local.LocalCloudConfig.httpPort.set : Port
                                                        -> LocalCloudConfig
                                                        -> LocalCloudConfig
  285.  Cloud.run.local.LocalCloudConfig.LocalCloudConfig : Boolean
                                                            -> Optional
                                                              HostName
                                                            -> Port
                                                            -> LocalCloudConfig
  286.  Cloud.run.local.LocalCloudConfig.printBanners : LocalCloudConfig
                                                        -> Boolean
  287.  Cloud.run.local.LocalCloudConfig.printBanners.modify : (Boolean
                                                               ->{g} Boolean)
                                                               -> LocalCloudConfig
                                                               ->{g} LocalCloudConfig
  288.  Cloud.run.local.LocalCloudConfig.printBanners.set : Boolean
                                                            -> LocalCloudConfig
                                                            -> LocalCloudConfig
  289.  Cloud.run.local.serve : '{IO, Exception, Cloud} a
                                ->{IO, Exception} a
  290.  Cloud.run.local.serve.doc : Doc
  291.  Cloud.run.withConfig : Cloud.ClientConfig
                               -> '{g, Cloud} a
                               ->{g, IO} a
  292.  Cloud.run.withConfig.doc : Doc
  293.  Cloud.ServiceName.assign.impl : ServiceName a b
                                        -> ServiceHash a b
                                        ->{Cloud} Either
                                          Failure URI
  294.  Cloud.ServiceName.create.impl : Text
                                        ->{Cloud} Either
                                          Failure
                                          (ServiceName a b)
  295.  Cloud.ServiceName.delete.impl : ServiceName a b
                                        ->{Cloud} Either
                                          Failure ()
  296.  Cloud.ServiceName.unassign.impl : ServiceName a b
                                          ->{Cloud} Either
                                            Failure ()
  297.  Cloud.submit : Environment
                       -> '{Environment.Config,
                       Exception,
                       Http,
                       Blobs,
                       Services,
                       Storage,
                       Remote,
                       websockets.HttpWebSocket,
                       WebSockets,
                       Random,
                       Log,
                       Scratch} a
                       ->{Exception, Cloud} a
  298.  Cloud.submit.doc : Doc
  299.  Cloud.submit.impl : Environment
                            -> '{Remote} a
                            ->{Cloud} Either Failure a
  300.  Cloud.submit.remote : Environment
                              -> '{Remote} a
                              ->{Exception, Cloud} a
  301.  Cloud.submit.remote.doc : Doc
  302.  Cloud.undeploy : ServiceHash a b ->{Exception, Cloud} ()
  303.  Cloud.undeploy.doc : Doc
  304.  Cloud.undeploy.impl : ServiceHash a b
                              ->{Cloud} Either Failure ()
  305.  Cloud.unexposeHttp : ServiceHash
                               HttpRequest HttpResponse
                             ->{Exception, Cloud} ()
  306.  Cloud.unexposeHttp.doc : Doc
  307.  Cloud.unexposeHttp.impl : ServiceHash
                                    HttpRequest HttpResponse
                                  ->{Cloud} Either Failure ()
  308.  Cloud.unexposeHttpWebSocket.impl : ServiceHash
                                             HttpRequest
                                             (Either
                                               HttpResponse
                                               (websockets.WebSocket
                                               ->{Remote,
                                               WebSockets} ()))
                                           ->{Cloud} Either
                                             Failure ()
  309.  type Daemon
  310.  Daemon.Daemon : Daemon.Id -> Text -> Daemon
  311.  type Daemon.Id
  312.  Daemon.id : Daemon -> Daemon.Id
  313.  Daemon.Id.Id : Text -> Daemon.Id
  314.  Daemon.Id.toText : Daemon.Id -> Text
  315.  Daemon.name : Daemon -> Text
  316.  type DaemonHash
  317.  DaemonHash.DaemonHash : Text -> DaemonHash
  318.  DaemonHash.toText : DaemonHash -> Text
  319.  type Database
  320.  Database.assign : Database
                          -> Environment
                          ->{Exception, Cloud} ()
  321.  Database.assign.doc : Doc
  322.  Database.Database : Database.Id -> Text -> Database
  323.  Database.default : '{Exception, Cloud} Database
  324.  Database.default.doc : Doc
  325.  Database.delete : Database ->{Exception, Cloud} ()
  326.  Database.delete.doc : Doc
  327.  Database.doc : Doc
  328.  type Database.Id
  329.  Database.id : Database -> Database.Id
  330.  Database.Id.Database.Id.Id : Text -> Database.Id
  331.  Database.id.doc : Doc
  332.  Database.Id.doc : Doc
  333.  Database.Id.fromJson : '{Decoder} Database.Id
  334.  Database.Id.fromJson.doc : Doc
  335.  Database.Id.toText : Database.Id -> Text
  336.  Database.Id.toText.doc : Doc
  337.  Database.list : '{IO, Exception} [DatabaseInfo]
  338.  Database.list.doc : Doc
  339.  Database.list.withConfig : Cloud.ClientConfig
                                   ->{IO, Exception} [DatabaseInfo]
  340.  Database.list.withConfig.doc : Doc
  341.  Database.name : Database -> Text
  342.  Database.name.doc : Doc
  343.  Database.named : Text ->{Exception, Cloud} Database
  344.  Database.named.doc : Doc
  345.  Database.toText : Database -> Text
  346.  Database.toText.doc : Doc
  347.  Database.unassign : Database
                            -> Environment
                            ->{Exception, Cloud} ()
  348.  Database.unassign.doc : Doc
  349.  type DatabaseInfo
  350.  DatabaseInfo.DatabaseInfo : Database.Id
                                    -> Text
                                    -> [Environment.Id]
                                    -> DatabaseInfo
  351.  DatabaseInfo.doc : Doc
  352.  DatabaseInfo.environments : DatabaseInfo
                                    -> [Environment.Id]
  353.  DatabaseInfo.environments.doc : Doc
  354.  DatabaseInfo.environments.modify : ([Environment.Id]
                                           ->{g} [Environment.Id])
                                           -> DatabaseInfo
                                           ->{g} DatabaseInfo
  355.  DatabaseInfo.environments.set : [Environment.Id]
                                        -> DatabaseInfo
                                        -> DatabaseInfo
  356.  DatabaseInfo.fromJson : '{Decoder} DatabaseInfo
  357.  DatabaseInfo.fromJson.doc : Doc
  358.  DatabaseInfo.id : DatabaseInfo -> Database.Id
  359.  DatabaseInfo.id.doc : Doc
  360.  DatabaseInfo.id.modify : (Database.Id ->{g} Database.Id)
                                 -> DatabaseInfo
                                 ->{g} DatabaseInfo
  361.  DatabaseInfo.id.set : Database.Id
                              -> DatabaseInfo
                              -> DatabaseInfo
  362.  DatabaseInfo.name : DatabaseInfo -> Text
  363.  DatabaseInfo.name.doc : Doc
  364.  DatabaseInfo.name.modify : (Text ->{g} Text)
                                   -> DatabaseInfo
                                   ->{g} DatabaseInfo
  365.  DatabaseInfo.name.set : Text
                                -> DatabaseInfo
                                -> DatabaseInfo
  366.  type DeploymentInfo
  367.  DeploymentInfo.deployedAt : DeploymentInfo -> Instant
  368.  DeploymentInfo.deployedAt.doc : Doc
  369.  DeploymentInfo.deployedAt.modify : (Instant
                                           ->{g} Instant)
                                           -> DeploymentInfo
                                           ->{g} DeploymentInfo
  370.  DeploymentInfo.deployedAt.set : Instant
                                        -> DeploymentInfo
                                        -> DeploymentInfo
  371.  DeploymentInfo.deployedBy : DeploymentInfo -> UserInfo
  372.  DeploymentInfo.deployedBy.doc : Doc
  373.  DeploymentInfo.deployedBy.modify : (UserInfo
                                           ->{g} UserInfo)
                                           -> DeploymentInfo
                                           ->{g} DeploymentInfo
  374.  DeploymentInfo.deployedBy.set : UserInfo
                                        -> DeploymentInfo
                                        -> DeploymentInfo
  375.  DeploymentInfo.DeploymentInfo : ServiceHash.Untyped
                                        -> Instant
                                        -> Optional Instant
                                        -> UserInfo
                                        -> Optional Instant
                                        -> Optional Instant
                                        -> DeploymentInfo
  376.  DeploymentInfo.doc : Doc
  377.  DeploymentInfo.exposedAt : DeploymentInfo
                                   -> Optional Instant
  378.  DeploymentInfo.exposedAt.doc : Doc
  379.  DeploymentInfo.exposedAt.modify : (Optional Instant
                                          ->{g} Optional Instant)
                                          -> DeploymentInfo
                                          ->{g} DeploymentInfo
  380.  DeploymentInfo.exposedAt.set : Optional Instant
                                       -> DeploymentInfo
                                       -> DeploymentInfo
  381.  DeploymentInfo.fromJson : '{Decoder} DeploymentInfo
  382.  DeploymentInfo.fromJson.doc : Doc
  383.  DeploymentInfo.hash : DeploymentInfo
                              -> ServiceHash.Untyped
  384.  DeploymentInfo.hash.doc : Doc
  385.  DeploymentInfo.hash.modify : (ServiceHash.Untyped
                                     ->{g} ServiceHash.Untyped)
                                     -> DeploymentInfo
                                     ->{g} DeploymentInfo
  386.  DeploymentInfo.hash.set : ServiceHash.Untyped
                                  -> DeploymentInfo
                                  -> DeploymentInfo
  387.  DeploymentInfo.undeployedAt : DeploymentInfo
                                      -> Optional Instant
  388.  DeploymentInfo.undeployedAt.modify : (Optional Instant
                                             ->{g} Optional
                                               Instant)
                                             -> DeploymentInfo
                                             ->{g} DeploymentInfo
  389.  DeploymentInfo.undeployedAt.set : Optional Instant
                                          -> DeploymentInfo
                                          -> DeploymentInfo
  390.  DeploymentInfo.unexposedAt : DeploymentInfo
                                     -> Optional Instant
  391.  DeploymentInfo.unexposedAt.modify : (Optional Instant
                                            ->{g} Optional
                                              Instant)
                                            -> DeploymentInfo
                                            ->{g} DeploymentInfo
  392.  DeploymentInfo.unexposedAt.set : Optional Instant
                                         -> DeploymentInfo
                                         -> DeploymentInfo
  393.  structural type durable.Cell a
  394.  durable.Cell.Cell : Database
                            -> a
                            -> Table () a
                            -> Cell a
  395.  durable.Cell.database : Cell a -> Database
  396.  durable.Cell.database.doc : Doc
  397.  durable.Cell.delete : Cell a ->{Remote} ()
  398.  durable.Cell.delete.doc : Doc
  399.  durable.Cell.delete.tx : Cell a ->{Transaction} ()
  400.  durable.Cell.delete.tx.doc : Doc
  401.  durable.Cell.doc : Doc
  402.  durable.Cell.docs.modificationFunctions : Doc
  403.  durable.Cell.getModify : Cell a
                                 -> (a
                                 ->{Transaction, Exception} a)
                                 ->{Remote} a
  404.  durable.Cell.getModify.doc : Doc
  405.  durable.Cell.modify : Cell a
                              -> (a
                              ->{Transaction, Exception} (a, b))
                              ->{Remote} b
  406.  durable.Cell.modify.doc : Doc
  407.  durable.Cell.modify.tx : Cell a
                                 -> (a
                                 ->{g, Transaction} (a, b))
                                 ->{g, Transaction} b
  408.  durable.Cell.modify.tx.doc : Doc
  409.  durable.Cell.modifyGet : Cell a
                                 -> (a
                                 ->{Transaction, Exception} a)
                                 ->{Remote} a
  410.  durable.Cell.modifyGet.doc : Doc
  411.  durable.Cell.modifyGet.tx : Cell a
                                    -> (a ->{g} a)
                                    ->{g,
                                    Transaction,
                                    Exception} a
  412.  durable.Cell.modifyGet.tx.doc : Doc
  413.  durable.Cell.modify_ : Cell a
                               -> (a
                               ->{Transaction, Exception} a)
                               ->{Remote} ()
  414.  durable.Cell.modify_.doc : Doc
  415.  durable.Cell.named : Database -> Text -> a -> Cell a
  416.  durable.Cell.nested : Database -> parent -> a -> Cell a
  417.  durable.Cell.read : Cell a ->{Remote} a
  418.  durable.Cell.read.tx : Cell a ->{Transaction} a
  419.  durable.Cell.reset : Cell a
                             -> a
                             ->{Exception, Storage} ()
  420.  durable.Cell.write : Cell a -> a ->{Remote} ()
  421.  durable.Cell.write.tx : Cell a -> a ->{Transaction} ()
  422.  durable.docs.fragments.wip : Doc
  423.  durable.docs.stability.draft : Doc
  424.  durable.docs.stability.final : Doc
  425.  durable.docs.stability.new : Doc
  426.  type durable.GinIndex input key id data
  427.  durable.GinIndex.doc : Doc
  428.  durable.GinIndex.insert : GinIndex input key id data
                                  -> input
                                  -> id
                                  -> data
                                  ->{Remote} ()
  429.  durable.GinIndex.internal.GinIndex : Database
                                             -> (id
                                             -> id
                                             -> Ordering)
                                             -> (input -> [key])
                                             -> OrderedTable
                                               key
                                               (OrderedTable
                                                 id data)
                                             -> GinIndex
                                               input key id data
  430.  durable.GinIndex.internal.test.all : '{IO} [Result]
  431.  durable.GinIndex.internal.test.correctness : '{IO,
                                                     Exception} ()
  432.  durable.GinIndex.internal.test.performance : '{IO,
                                                     Exception} ()
  433.  durable.GinIndex.internal.test.printGinIndex : GinIndex
                                                         input
                                                         key
                                                         id
                                                         data
                                                       ->{Remote} [( key,
                                                         [( id,
                                                         data)])]
  434.  durable.GinIndex.named : Database
                                 -> Text
                                 -> (id -> id -> Ordering)
                                 -> (input -> [key])
                                 -> GinIndex input key id data
  435.  type durable.GinIndex.Query key
  436.  durable.GinIndex.query : GinIndex input key id data
                                 -> GinIndex.Query key
                                 ->{Remote} '{Remote,
                                 Orderator (id, '{Remote} data)} ()
  437.  durable.GinIndex.Query.And : GinIndex.Query key
                                     -> GinIndex.Query key
                                     -> GinIndex.Query key
  438.  durable.GinIndex.Query.Exact : key -> GinIndex.Query key
  439.  durable.GinIndex.Query.Minus : GinIndex.Query key
                                       -> GinIndex.Query key
                                       -> GinIndex.Query key
  440.  durable.GinIndex.Query.Or : GinIndex.Query key
                                    -> GinIndex.Query key
                                    -> GinIndex.Query key
  441.  type durable.Immutable
  442.  durable.Immutable.database : Immutable -> Database
  443.  durable.Immutable.decrement.tx : Immutable
                                         -> Hashed a
                                         ->{Transaction} ()
  444.  durable.Immutable.doc : Doc
  445.  durable.Immutable.hashOf : Immutable -> a -> Hash
  446.  durable.Immutable.Immutable : Database
                                      -> Table Hash (Any, Nat)
                                      -> Immutable
  447.  durable.Immutable.increment.tx : Immutable
                                         -> a
                                         ->{Transaction} Hashed
                                           a
  448.  durable.Immutable.named : Database -> Text -> Immutable
  449.  durable.Immutable.nested : Database -> a -> Immutable
  450.  durable.Immutable.read : Immutable
                                 -> Hashed a
                                 ->{Remote} a
  451.  durable.Immutable.read.cached : Immutable
                                        -> Hashed a
                                        ->{Exception,
                                        Storage,
                                        Scratch} a
  452.  durable.Immutable.read.cached.doc : Doc
  453.  durable.Immutable.read.doc : Doc
  454.  durable.Immutable.read.state : Immutable
                                       -> Hashed a
                                       ->{Exception, Storage} a
  455.  durable.Immutable.read.tx : Immutable
                                    -> Hashed a
                                    ->{Transaction, Exception} a
  456.  durable.Immutable.table : Immutable
                                  -> Table Hash (Any, Nat)
  457.  durable.Immutable.tryRead.tx : Immutable
                                       -> Hashed a
                                       ->{Transaction} Optional
                                         a
  458.  type durable.Knn m v a
  459.  durable.Knn.add : Knn m v a
                          -> (v, a)
                          ->{Exception, Storage} ()
  460.  durable.Knn.add.tx : Knn m v a
                             -> (v, a)
                             ->{Transaction, Exception} ()
  461.  durable.Knn.arity : Knn m v a -> Nat
  462.  durable.Knn.database : Knn m v a -> Database
  463.  durable.Knn.doc : Doc
  464.  structural type durable.Knn.internal.Kit m v a
  465.  durable.Knn.internal.Kit.Kit : Nat
                                       -> Cell
                                         ( [(m, Kit m v a)],
                                           [(v, a)],
                                           [(v, a)])
                                       -> Kit m v a
  466.  durable.Knn.kit : Knn m v a -> Kit m v a
  467.  durable.Knn.Knn : Database
                          -> (v -> m)
                          -> (m -> v -> m)
                          -> (m -> v -> Float)
                          -> Kit m v a
                          -> Knn m v a
  468.  durable.Knn.lookup : Knn m v a
                             -> Nat
                             -> v
                             ->{Remote} [(Float, (v, a))]
  469.  durable.Knn.metric.combine : Knn m v a -> m -> v -> m
  470.  durable.Knn.metric.distance : Knn m v a
                                      -> m
                                      -> v
                                      -> Float
  471.  durable.Knn.metric.inject : Knn m v a -> v -> m
  472.  durable.Knn.named : Database
                            -> Text
                            -> Nat
                            -> (v -> m)
                            -> (m -> v -> m)
                            -> (m -> v -> Float)
                            -> Knn m v a
  473.  durable.Knn.nested : Database
                             -> parent
                             -> Nat
                             -> (v -> m)
                             -> (m -> v -> m)
                             -> (m -> v -> Float)
                             -> Knn m v a
  474.  type durable.Knn.SampleWords txt
  475.  durable.Knn.SampleWords.add : txt
                                      -> SampleWords txt
                                      -> SampleWords txt
  476.  durable.Knn.SampleWords.add.doc : Doc
  477.  durable.Knn.SampleWords.bound : SampleWords txt -> Nat
  478.  durable.Knn.SampleWords.bound.doc : Doc
  479.  durable.Knn.SampleWords.compressedSize : SampleWords txt
                                                 -> Nat
  480.  durable.Knn.SampleWords.distance : SampleWords txt
                                           -> SampleWords txt
                                           -> Float
  481.  durable.Knn.SampleWords.distance.doc : Doc
  482.  durable.Knn.SampleWords.doc : Doc
  483.  durable.Knn.SampleWords.empty : Nat -> SampleWords txt
  484.  durable.Knn.SampleWords.fromTokens : Nat
                                             -> [txt]
                                             -> SampleWords txt
  485.  durable.Knn.SampleWords.fromTokens.doc : Doc
  486.  durable.Knn.SampleWords.fromWords : Nat
                                            -> Text
                                            -> SampleWords Text
  487.  durable.Knn.SampleWords.fromWords.alphanumeric : Nat
                                                         -> Text
                                                         -> SampleWords
                                                           Text
  488.  durable.Knn.SampleWords.fromWords.alphanumeric.doc : Doc
  489.  durable.Knn.SampleWords.fromWords.doc : Doc
  490.  durable.Knn.SampleWords.merge : SampleWords txt
                                        -> SampleWords txt
                                        -> SampleWords txt
  491.  durable.Knn.SampleWords.merge.doc : Doc
  492.  durable.Knn.SampleWords.mergeUntrimmed : SampleWords txt
                                                 -> SampleWords
                                                   txt
                                                 -> SampleWords
                                                   txt
  493.  durable.Knn.SampleWords.mergeUntrimmed.doc : Doc
  494.  durable.Knn.SampleWords.SampleWords : Nat
                                              -> [txt]
                                              -> SampleWords txt
  495.  durable.Knn.SampleWords.trim : SampleWords txt
                                       -> SampleWords txt
  496.  durable.Knn.SampleWords.trim.doc : Doc
  497.  durable.LICENSE : License
  498.  type durable.LinearLog a
  499.  durable.LinearLog.add.tx : LinearLog a
                                   -> a
                                   ->{Transaction} ()
  500.  durable.LinearLog.at.tx : LinearLog a
                                  -> Nat
                                  ->{Transaction, Exception} a
  501.  durable.LinearLog.delete.tx : LinearLog a
                                      -> Nat
                                      ->{Transaction} ()
  502.  durable.LinearLog.doc : Doc
  503.  durable.LinearLog.LinearLog : Cell Nat
                                      -> Table Nat a
                                      -> LinearLog a
  504.  durable.LinearLog.named : Database
                                  -> Text
                                  -> LinearLog a
  505.  durable.LinearLog.nested : Database
                                   -> parent
                                   -> LinearLog v
  506.  durable.LinearLog.size.tx : LinearLog a
                                    ->{Transaction} Nat
  507.  type durable.OrderedTable k v
  508.  durable.OrderedTable.database : OrderedTable k v
                                        -> Database
  509.  durable.OrderedTable.database.doc : Doc
  510.  durable.OrderedTable.delete : OrderedTable k v
                                      -> k
                                      ->{Remote} ()
  511.  durable.OrderedTable.delete.doc : Doc
  512.  durable.OrderedTable.delete.tx : OrderedTable k v
                                         -> k
                                         ->{Transaction} ()
  513.  durable.OrderedTable.delete.tx.doc : Doc
  514.  durable.OrderedTable.doc : Doc
  515.  durable.OrderedTable.doc.addUser : OrderedTable
                                             Text UserInfo
                                           -> OrderedTable
                                             URI Nat
                                           -> UserInfo
                                           ->{Transaction,
                                           Random} ()
  516.  durable.OrderedTable.doc.getUsersByAvatar : OrderedTable
                                                      ( URI,
                                                        Text)
                                                      UserInfo
                                                    -> URI
                                                    -> '{Remote,
                                                    Stream
                                                      UserInfo} ()
  517.  durable.OrderedTable.from : OrderedTable k v
                                    -> k
                                    -> '{Remote, Stream (k, v)} ()
  518.  durable.OrderedTable.from.doc : Doc
  519.  durable.OrderedTable.from.keys : OrderedTable k v
                                         -> k
                                         -> '{Remote, Stream k} ()
  520.  durable.OrderedTable.from.keys.chunked : OrderedTable
                                                   k v
                                                 -> k
                                                 -> '{Remote,
                                                 Stream [k]} ()
  521.  durable.OrderedTable.from.keys.chunked.doc : Doc
  522.  durable.OrderedTable.from.keys.chunked.tx : OrderedTable
                                                      k v
                                                    -> k
                                                    -> '{Transaction,
                                                    Stream [k]} ()
  523.  durable.OrderedTable.from.keys.chunked.tx.doc : Doc
  524.  durable.OrderedTable.from.keys.doc : Doc
  525.  durable.OrderedTable.from.keys.tx : OrderedTable k v
                                            -> k
                                            -> '{Transaction,
                                            Stream k} ()
  526.  durable.OrderedTable.from.keys.tx.doc : Doc
  527.  durable.OrderedTable.from.prefix : OrderedTable k v
                                           -> (prefix
                                           ->{g} k
                                           -> Ordering)
                                           -> prefix
                                           ->{g} '{Remote,
                                           Stream (k, v)} ()
  528.  durable.OrderedTable.from.prefix.doc : Doc
  529.  durable.OrderedTable.from.prefix.keys : OrderedTable k v
                                                -> (prefix
                                                ->{g} k
                                                -> Ordering)
                                                -> prefix
                                                ->{g} '{Remote,
                                                Stream k} ()
  530.  durable.OrderedTable.from.prefix.keys.chunked : OrderedTable
                                                          k v
                                                        -> (prefix
                                                        ->{g} k
                                                        -> Ordering)
                                                        -> prefix
                                                        ->{g} '{Remote,
                                                        Stream
                                                          [k]} ()
  531.  durable.OrderedTable.from.prefix.keys.chunked.doc : Doc
  532.  durable.OrderedTable.from.prefix.keys.chunked.tx : OrderedTable
                                                             k v
                                                           -> (prefix
                                                           ->{g} k
                                                           -> Ordering)
                                                           -> prefix
                                                           ->{g} '{Transaction,
                                                           Stream
                                                             [k]} ()
  533.  durable.OrderedTable.from.prefix.keys.chunked.tx.doc : Doc
  534.  durable.OrderedTable.from.prefix.keys.doc : Doc
  535.  durable.OrderedTable.from.prefix.keys.tx : OrderedTable
                                                     k v
                                                   -> (prefix
                                                   ->{g} k
                                                   -> Ordering)
                                                   -> prefix
                                                   ->{g} '{Transaction,
                                                   Stream k} ()
  536.  durable.OrderedTable.from.prefix.keys.tx.doc : Doc
  537.  durable.OrderedTable.from.prefix.tx : OrderedTable k v
                                              -> (prefix
                                              ->{g} k
                                              -> Ordering)
                                              -> prefix
                                              ->{g} '{Transaction,
                                              Exception,
                                              Batch,
                                              Stream (k, v)} ()
  538.  durable.OrderedTable.from.prefix.tx.doc : Doc
  539.  durable.OrderedTable.from.tx : OrderedTable k v
                                       -> k
                                       -> '{Transaction,
                                       Exception,
                                       Batch,
                                       Stream (k, v)} ()
  540.  durable.OrderedTable.from.tx.doc : Doc
  541.  durable.OrderedTable.internal.BTree : Database
                                              -> (k
                                              -> k
                                              -> Ordering)
                                              -> Nat
                                              -> Table
                                                internal.Id
                                                (Node k)
                                              -> Table k v
                                              -> OrderedTable
                                                k v
  542.  durable.OrderedTable.internal.bulkFetchValues : OrderedTable
                                                          k v
                                                        -> '{Remote,
                                                        Stream
                                                          [k]} ()
                                                        -> '{Remote,
                                                        Stream
                                                          (k, v)} ()
  543.  durable.OrderedTable.internal.bulkFetchValues.tx : OrderedTable
                                                             k v
                                                           -> '{g,
                                                           Stream
                                                             [k]} ()
                                                           -> '{g,
                                                           Batch,
                                                           Stream
                                                             ( k,
                                                               v)} ()
  544.  durable.OrderedTable.internal.childAt : OrderedTable k v
                                                -> Nat
                                                -> Node k
                                                ->{Transaction} Node
                                                  k
  545.  durable.OrderedTable.internal.fetch : OrderedTable k v
                                              -> internal.Id
                                              ->{Transaction} Node
                                                k
  546.  durable.OrderedTable.internal.findKeySlot : OrderedTable
                                                      k v
                                                    -> k
                                                    -> Node k
                                                    -> Nat
  547.  durable.OrderedTable.internal.findLeaf : OrderedTable
                                                   k v
                                                 -> k
                                                 ->{Transaction} [Node
                                                   k]
  548.  type durable.OrderedTable.internal.Id
  549.  durable.OrderedTable.internal.Id.Id : Bytes
                                              -> internal.Id
  550.  durable.OrderedTable.internal.Id.Root : internal.Id
  551.  durable.OrderedTable.internal.index : OrderedTable k v
                                              -> Table
                                                internal.Id
                                                (Node k)
  552.  durable.OrderedTable.internal.newId : '{Random} internal.Id
  553.  type durable.OrderedTable.internal.Node k
  554.  durable.OrderedTable.internal.Node.doc : Doc
  555.  durable.OrderedTable.internal.Node.id : Node k
                                                -> internal.Id
  556.  durable.OrderedTable.internal.Node.id.modify : (internal.Id
                                                       ->{g} internal.Id)
                                                       -> Node k
                                                       ->{g} Node
                                                         k
  557.  durable.OrderedTable.internal.Node.id.set : internal.Id
                                                    -> Node k
                                                    -> Node k
  558.  durable.OrderedTable.internal.Node.isLeaf : Node k
                                                    -> Boolean
  559.  durable.OrderedTable.internal.Node.isLeaf.modify : (Boolean
                                                           ->{g} Boolean)
                                                           -> Node
                                                             k
                                                           ->{g} Node
                                                             k
  560.  durable.OrderedTable.internal.Node.isLeaf.set : Boolean
                                                        -> Node
                                                          k
                                                        -> Node
                                                          k
  561.  durable.OrderedTable.internal.Node.keys : Node k -> [k]
  562.  durable.OrderedTable.internal.Node.keys.modify : ([k1]
                                                         ->{g} [k])
                                                         -> Node
                                                           k1
                                                         ->{g} Node
                                                           k
  563.  durable.OrderedTable.internal.Node.keys.set : [k]
                                                      -> Node k1
                                                      -> Node k
  564.  durable.OrderedTable.internal.Node.Node : internal.Id
                                                  -> [k]
                                                  -> [internal.Id]
                                                  -> Boolean
                                                  -> Node k
  565.  durable.OrderedTable.internal.Node.pointers : Node k
                                                      -> [internal.Id]
  566.  durable.OrderedTable.internal.Node.pointers.modify : ([internal.Id]
                                                             ->{g} [internal.Id])
                                                             -> Node
                                                               k
                                                             ->{g} Node
                                                               k
  567.  durable.OrderedTable.internal.Node.pointers.set : [internal.Id]
                                                          -> Node
                                                            k
                                                          -> Node
                                                            k
  568.  durable.OrderedTable.internal.ordering : OrderedTable
                                                   k v
                                                 -> k
                                                 -> k
                                                 -> Ordering
  569.  durable.OrderedTable.internal.test.bugmin : '{IO,
                                                    Exception} ()
  570.  durable.OrderedTable.internal.test.correctness : '{IO,
                                                         Exception} [( Text,
                                                           [( Text,
                                                           Either
                                                           Failure
                                                           ())])]
  571.  ability durable.OrderedTable.internal.test.MapGeneration
  572.  durable.OrderedTable.internal.test.MapGeneration.durable.BTree.internal.test.MapGeneration.delete : Nat
                                                                                                            ->{MapGeneration} ()
  573.  durable.OrderedTable.internal.test.MapGeneration.durable.BTree.internal.test.MapGeneration.insert : Nat
                                                                                                            -> Bytes
                                                                                                            ->{MapGeneration} ()
  574.  durable.OrderedTable.internal.test.MapGeneration.generate : [Nat]
                                                                    ->{Random} '{MapGeneration} ()
  575.  durable.OrderedTable.internal.test.MapGeneration.log : '{MapGeneration} a
                                                               ->{IO,
                                                               Exception} ()
  576.  durable.OrderedTable.internal.test.MapGeneration.toBTree : Nat
                                                                   -> '{MapGeneration} a
                                                                   ->{Exception,
                                                                   Storage,
                                                                   Random} OrderedTable
                                                                     Nat
                                                                     Bytes
  577.  durable.OrderedTable.internal.test.MapGeneration.toImmutableMap : '{MapGeneration} a
                                                                          -> data.Map
                                                                            Nat
                                                                            Bytes
  578.  durable.OrderedTable.internal.test.perfmin : '{IO,
                                                     Exception} ()
  579.  durable.OrderedTable.internal.test.performance : '{IO,
                                                         Exception} ()
  580.  durable.OrderedTable.internal.test.prefixQueries : '{IO,
                                                           Exception} ()
  581.  durable.OrderedTable.internal.test.readViaSearch : OrderedTable
                                                             k v
                                                           -> k
                                                           ->{Transaction} Optional
                                                             v
  582.  durable.OrderedTable.internal.test.runner : Text
                                                    -> Nat
                                                    -> '{g,
                                                    Storage,
                                                    Random} a
                                                    ->{g,
                                                    IO,
                                                    Exception} a
  583.  type durable.OrderedTable.internal.test.Sample
  584.  durable.OrderedTable.internal.test.Sample.deletes : Sample
                                                            -> Nat
  585.  durable.OrderedTable.internal.test.Sample.deletes.modify : (Nat
                                                                   ->{g} Nat)
                                                                   -> Sample
                                                                   ->{g} Sample
  586.  durable.OrderedTable.internal.test.Sample.deletes.set : Nat
                                                                -> Sample
                                                                -> Sample
  587.  durable.OrderedTable.internal.test.Sample.empty : Sample
  588.  durable.OrderedTable.internal.test.Sample.keys : Sample
                                                         -> Nat
  589.  durable.OrderedTable.internal.test.Sample.keys.modify : (Nat
                                                                ->{g} Nat)
                                                                -> Sample
                                                                ->{g} Sample
  590.  durable.OrderedTable.internal.test.Sample.keys.set : Nat
                                                             -> Sample
                                                             -> Sample
  591.  type durable.OrderedTable.internal.test.Sample.Percentiles
  592.  durable.OrderedTable.internal.test.Sample.Percentiles.empty : Percentiles
  593.  durable.OrderedTable.internal.test.Sample.Percentiles.max : Percentiles
                                                                    -> Sample
  594.  durable.OrderedTable.internal.test.Sample.Percentiles.max.modify : (Sample
                                                                           ->{g} Sample)
                                                                           -> Percentiles
                                                                           ->{g} Percentiles
  595.  durable.OrderedTable.internal.test.Sample.Percentiles.max.set : Sample
                                                                        -> Percentiles
                                                                        -> Percentiles
  596.  durable.OrderedTable.internal.test.Sample.Percentiles.min : Percentiles
                                                                    -> Sample
  597.  durable.OrderedTable.internal.test.Sample.Percentiles.min.modify : (Sample
                                                                           ->{g} Sample)
                                                                           -> Percentiles
                                                                           ->{g} Percentiles
  598.  durable.OrderedTable.internal.test.Sample.Percentiles.min.set : Sample
                                                                        -> Percentiles
                                                                        -> Percentiles
  599.  durable.OrderedTable.internal.test.Sample.Percentiles.p50 : Percentiles
                                                                    -> Sample
  600.  durable.OrderedTable.internal.test.Sample.Percentiles.p50.modify : (Sample
                                                                           ->{g} Sample)
                                                                           -> Percentiles
                                                                           ->{g} Percentiles
  601.  durable.OrderedTable.internal.test.Sample.Percentiles.p50.set : Sample
                                                                        -> Percentiles
                                                                        -> Percentiles
  602.  durable.OrderedTable.internal.test.Sample.Percentiles.p95 : Percentiles
                                                                    -> Sample
  603.  durable.OrderedTable.internal.test.Sample.Percentiles.p95.modify : (Sample
                                                                           ->{g} Sample)
                                                                           -> Percentiles
                                                                           ->{g} Percentiles
  604.  durable.OrderedTable.internal.test.Sample.Percentiles.p95.set : Sample
                                                                        -> Percentiles
                                                                        -> Percentiles
  605.  durable.OrderedTable.internal.test.Sample.Percentiles.p99 : Percentiles
                                                                    -> Sample
  606.  durable.OrderedTable.internal.test.Sample.Percentiles.p99.modify : (Sample
                                                                           ->{g} Sample)
                                                                           -> Percentiles
                                                                           ->{g} Percentiles
  607.  durable.OrderedTable.internal.test.Sample.Percentiles.p99.set : Sample
                                                                        -> Percentiles
                                                                        -> Percentiles
  608.  durable.OrderedTable.internal.test.Sample.Percentiles.percentiles : [Sample]
                                                                            ->{Exception} Percentiles
  609.  durable.OrderedTable.internal.test.Sample.Percentiles.Percentiles : Nat
                                                                            -> Sample
                                                                            -> Sample
                                                                            -> Sample
                                                                            -> Sample
                                                                            -> Sample
                                                                            -> Percentiles
  610.  durable.OrderedTable.internal.test.Sample.Percentiles.render : Text
                                                                       -> Percentiles
                                                                       -> Text
  611.  durable.OrderedTable.internal.test.Sample.Percentiles.sampleSize : Percentiles
                                                                           -> Nat
  612.  durable.OrderedTable.internal.test.Sample.Percentiles.sampleSize.modify : (Nat
                                                                                  ->{g} Nat)
                                                                                  -> Percentiles
                                                                                  ->{g} Percentiles
  613.  durable.OrderedTable.internal.test.Sample.Percentiles.sampleSize.set : Nat
                                                                               -> Percentiles
                                                                               -> Percentiles
  614.  durable.OrderedTable.internal.test.Sample.reads : Sample
                                                          -> Nat
  615.  durable.OrderedTable.internal.test.Sample.reads.modify : (Nat
                                                                 ->{g} Nat)
                                                                 -> Sample
                                                                 ->{g} Sample
  616.  durable.OrderedTable.internal.test.Sample.reads.set : Nat
                                                              -> Sample
                                                              -> Sample
  617.  durable.OrderedTable.internal.test.Sample.sample : '{g,
                                                           Transaction} a
                                                           ->{g,
                                                           Transaction} ( a,
                                                             Sample)
  618.  durable.OrderedTable.internal.test.Sample.Sample : Nat
                                                           -> Nat
                                                           -> Nat
                                                           -> Nat
                                                           -> Nat
                                                           -> Sample
  619.  durable.OrderedTable.internal.test.Sample.storageReads : Sample
                                                                 -> Nat
  620.  durable.OrderedTable.internal.test.Sample.storageReads.modify : (Nat
                                                                        ->{g} Nat)
                                                                        -> Sample
                                                                        ->{g} Sample
  621.  durable.OrderedTable.internal.test.Sample.storageReads.set : Nat
                                                                     -> Sample
                                                                     -> Sample
  622.  durable.OrderedTable.internal.test.Sample.writes : Sample
                                                           -> Nat
  623.  durable.OrderedTable.internal.test.Sample.writes.modify : (Nat
                                                                  ->{g} Nat)
                                                                  -> Sample
                                                                  ->{g} Sample
  624.  durable.OrderedTable.internal.test.Sample.writes.set : Nat
                                                               -> Sample
                                                               -> Sample
  625.  durable.OrderedTable.internal.test.testMap : Nat
                                                     -> OrderedTable
                                                       k v
  626.  durable.OrderedTable.internal.values : OrderedTable k v
                                               -> Table k v
  627.  durable.OrderedTable.max : OrderedTable k v
                                   ->{Remote} Optional (k, v)
  628.  durable.OrderedTable.max.doc : Doc
  629.  durable.OrderedTable.max.tx : OrderedTable k v
                                      ->{Transaction, Exception} Optional
                                        (k, v)
  630.  durable.OrderedTable.max.tx.doc : Doc
  631.  durable.OrderedTable.maxFanout : OrderedTable k v -> Nat
  632.  durable.OrderedTable.maxFanout.doc : Doc
  633.  durable.OrderedTable.maxFanout.modify : (Nat ->{g} Nat)
                                                -> OrderedTable
                                                  k v
                                                ->{g} OrderedTable
                                                  k v
  634.  durable.OrderedTable.maxFanout.set : Nat
                                             -> OrderedTable k v
                                             -> OrderedTable k v
  635.  durable.OrderedTable.maxKey : OrderedTable k v
                                      ->{Remote} Optional k
  636.  durable.OrderedTable.maxKey.doc : Doc
  637.  durable.OrderedTable.maxKey.tx : OrderedTable k v
                                         ->{Transaction} Optional
                                           k
  638.  durable.OrderedTable.maxKey.tx.doc : Doc
  639.  durable.OrderedTable.min : OrderedTable k v
                                   ->{Remote} Optional (k, v)
  640.  durable.OrderedTable.min.doc : Doc
  641.  durable.OrderedTable.min.tx : OrderedTable k v
                                      ->{Transaction, Exception} Optional
                                        (k, v)
  642.  durable.OrderedTable.min.tx.doc : Doc
  643.  durable.OrderedTable.minKey : OrderedTable k v
                                      ->{Remote} Optional k
  644.  durable.OrderedTable.minKey.doc : Doc
  645.  durable.OrderedTable.minKey.tx : OrderedTable k v
                                         ->{Transaction} Optional
                                           k
  646.  durable.OrderedTable.minKey.tx.doc : Doc
  647.  durable.OrderedTable.named : Database
                                     -> Text
                                     -> (k -> k -> Ordering)
                                     -> OrderedTable k v
  648.  durable.OrderedTable.named.doc : Doc
  649.  durable.OrderedTable.nested : Database
                                      -> parent
                                      -> (k -> k -> Ordering)
                                      -> OrderedTable k v
  650.  durable.OrderedTable.nested.doc : Doc
  651.  durable.OrderedTable.prefixOrdering : k1
                                              -> (k1, k2)
                                              -> Ordering
  652.  durable.OrderedTable.prefixOrdering.doc : Doc
  653.  durable.OrderedTable.rangeClosed : OrderedTable k v
                                           -> k
                                           -> k
                                           -> '{Remote,
                                           Stream (k, v)} ()
  654.  durable.OrderedTable.rangeClosed.doc : Doc
  655.  durable.OrderedTable.rangeClosed.keys : OrderedTable k v
                                                -> k
                                                -> k
                                                -> '{Remote,
                                                Stream k} ()
  656.  durable.OrderedTable.rangeClosed.keys.chunked : OrderedTable
                                                          k v
                                                        -> k
                                                        -> k
                                                        -> '{Remote,
                                                        Stream
                                                          [k]} ()
  657.  durable.OrderedTable.rangeClosed.keys.chunked.doc : Doc
  658.  durable.OrderedTable.rangeClosed.keys.chunked.tx : OrderedTable
                                                             k v
                                                           -> k
                                                           -> k
                                                           -> '{Transaction,
                                                           Stream
                                                             [k]} ()
  659.  durable.OrderedTable.rangeClosed.keys.chunked.tx.doc : Doc
  660.  durable.OrderedTable.rangeClosed.keys.doc : Doc
  661.  durable.OrderedTable.rangeClosed.keys.tx : OrderedTable
                                                     k v
                                                   -> k
                                                   -> k
                                                   -> '{Transaction,
                                                   Stream k} ()
  662.  durable.OrderedTable.rangeClosed.keys.tx.doc : Doc
  663.  durable.OrderedTable.rangeClosed.prefix : OrderedTable
                                                    k v
                                                  -> (prefix
                                                  -> k
                                                  -> Ordering)
                                                  -> prefix
                                                  -> prefix
                                                  -> '{Remote,
                                                  Stream (k, v)} ()
  664.  durable.OrderedTable.rangeClosed.prefix.doc : Doc
  665.  durable.OrderedTable.rangeClosed.prefix.keys : OrderedTable
                                                         k v
                                                       -> (prefix
                                                       -> k
                                                       -> Ordering)
                                                       -> prefix
                                                       -> prefix
                                                       -> '{Remote,
                                                       Stream k} ()
  666.  durable.OrderedTable.rangeClosed.prefix.keys.chunked : OrderedTable
                                                                 k
                                                                 v
                                                               -> (prefix
                                                               -> k
                                                               -> Ordering)
                                                               -> prefix
                                                               -> prefix
                                                               -> '{Remote,
                                                               Stream
                                                                 [k]} ()
  667.  durable.OrderedTable.rangeClosed.prefix.keys.chunked.doc : Doc
  668.  durable.OrderedTable.rangeClosed.prefix.keys.chunked.tx : OrderedTable
                                                                    k
                                                                    v
                                                                  -> (prefix
                                                                  -> k
                                                                  -> Ordering)
                                                                  -> prefix
                                                                  -> prefix
                                                                  -> '{Transaction,
                                                                  Stream
                                                                    [k]} ()
  669.  durable.OrderedTable.rangeClosed.prefix.keys.chunked.tx.doc : Doc
  670.  durable.OrderedTable.rangeClosed.prefix.keys.doc : Doc
  671.  durable.OrderedTable.rangeClosed.prefix.keys.tx : OrderedTable
                                                            k v
                                                          -> (prefix
                                                          -> k
                                                          -> Ordering)
                                                          -> prefix
                                                          -> prefix
                                                          -> '{Transaction,
                                                          Stream
                                                            k} ()
  672.  durable.OrderedTable.rangeClosed.prefix.keys.tx.doc : Doc
  673.  durable.OrderedTable.rangeClosed.prefix.tx : OrderedTable
                                                       k v
                                                     -> (prefix
                                                     -> k
                                                     -> Ordering)
                                                     -> prefix
                                                     -> prefix
                                                     -> '{Transaction,
                                                     Batch,
                                                     Stream
                                                       (k, v)} ()
  674.  durable.OrderedTable.rangeClosed.prefix.tx.doc : Doc
  675.  durable.OrderedTable.rangeClosed.tx : OrderedTable k v
                                              -> k
                                              -> k
                                              -> '{Transaction,
                                              Batch,
                                              Stream (k, v)} ()
  676.  durable.OrderedTable.rangeClosed.tx.doc : Doc
  677.  durable.OrderedTable.read : OrderedTable k v
                                    -> k
                                    ->{Remote} v
  678.  durable.OrderedTable.read.doc : Doc
  679.  durable.OrderedTable.read.tx : OrderedTable k v
                                       -> k
                                       ->{Transaction,
                                       Exception} v
  680.  durable.OrderedTable.read.tx.doc : Doc
  681.  durable.OrderedTable.search : OrderedTable k v
                                      -> (k -> Ordering)
                                      -> '{Remote,
                                      Stream (k, v)} ()
  682.  durable.OrderedTable.search.keys : OrderedTable k v
                                           -> (k -> Ordering)
                                           -> '{Remote,
                                           Stream k} ()
  683.  durable.OrderedTable.search.keys.chunked : OrderedTable
                                                     k v
                                                   -> (k
                                                   -> Ordering)
                                                   -> '{Remote,
                                                   Stream [k]} ()
  684.  durable.OrderedTable.search.keys.chunked.tx : OrderedTable
                                                        k v
                                                      -> (k
                                                      -> Ordering)
                                                      -> '{Transaction,
                                                      Stream [k]} ()
  685.  durable.OrderedTable.search.keys.tx : OrderedTable k v
                                              -> (k -> Ordering)
                                              -> '{Transaction,
                                              Stream k} ()
  686.  durable.OrderedTable.search.tx : OrderedTable k v
                                         -> (k -> Ordering)
                                         -> '{Transaction,
                                         Batch,
                                         Stream (k, v)} ()
  687.  durable.OrderedTable.toOrderator : OrderedTable k v
                                           -> '{Remote,
                                           Orderator
                                             (k, '{Remote} v)} ()
  688.  durable.OrderedTable.toOrderator.keys : OrderedTable k v
                                                -> '{Remote,
                                                Orderator k} ()
  689.  durable.OrderedTable.toOrderator.keys.doc : Doc
  690.  durable.OrderedTable.toOrderator.keys.tx : OrderedTable
                                                     k v
                                                   -> '{Transaction,
                                                   Orderator k} ()
  691.  durable.OrderedTable.toOrderator.keys.tx.doc : Doc
  692.  durable.OrderedTable.toOrderator.tx : OrderedTable k v
                                              -> '{Transaction,
                                              Orderator
                                                ( k,
                                                  '{Transaction,
                                                Exception} v)} ()
  693.  durable.OrderedTable.toStream : OrderedTable k v
                                        -> '{Remote,
                                        Stream (k, v)} ()
  694.  durable.OrderedTable.toStream.keys : OrderedTable k v
                                             -> '{Remote,
                                             Stream k} ()
  695.  durable.OrderedTable.toStream.keys.chunked : OrderedTable
                                                       k v
                                                     -> '{Remote,
                                                     Stream [k]} ()
  696.  durable.OrderedTable.toStream.keys.chunked.tx : OrderedTable
                                                          k v
                                                        -> '{Transaction,
                                                        Stream
                                                          [k]} ()
  697.  durable.OrderedTable.toStream.keys.tx : OrderedTable k v
                                                -> '{Transaction,
                                                Stream k} ()
  698.  durable.OrderedTable.toStream.tx : OrderedTable k v
                                           -> '{Transaction,
                                           Batch,
                                           Stream (k, v)} ()
  699.  durable.OrderedTable.tryRead : OrderedTable k v
                                       -> k
                                       ->{Remote} Optional v
  700.  durable.OrderedTable.tryRead.tx : OrderedTable k v
                                          -> k
                                          ->{Transaction} Optional
                                            v
  701.  durable.OrderedTable.write : OrderedTable k v
                                     -> k
                                     -> v
                                     ->{Remote} ()
  702.  durable.OrderedTable.write.tx : OrderedTable k v
                                        -> k
                                        -> v
                                        ->{Transaction, Random} ()
  703.  durable.README : Doc
  704.  durable.up.Bytes.toBase16.text : Bytes -> Text
  705.  durable.up.Bytes.toBase16.text.doc : Doc
  706.  durable.up.Bytes.toBase16.text.test : [Result]
  707.  durable.up.Bytes.toBase32Hex.text : Bytes -> Text
  708.  durable.up.Bytes.toBase32Hex.text.doc : Doc
  709.  durable.up.Float.argMax : (a -> Float)
                                  -> [a]
                                  ->{Exception} a
  710.  durable.up.Float.argMin : (a ->{g} Float)
                                  -> [a]
                                  ->{g, Exception} a
  711.  durable.up.Float.argMin.indexed : (a -> Float)
                                          -> [a]
                                          ->{Exception} (a, Nat)
  712.  durable.up.Float.argMin.indexed.doc : Doc
  713.  durable.up.Float.maxIndex : (a -> Float)
                                    -> [a]
                                    ->{Exception} Nat
  714.  durable.up.Float.minBy : (a ->{g} Float)
                                 -> [a]
                                 ->{g} Float
  715.  durable.up.Float.selectMax : (a -> Float)
                                     -> [a]
                                     ->{Exception} (a, [a])
  716.  durable.up.Float.tryArgMin : (a ->{g} Float)
                                     -> [a]
                                     ->{g} Optional a
  717.  durable.up.Map.toStream : data.Map k b
                                  -> '{Stream (k, b)} ()
  718.  durable.up.Map.toStream.doc : Doc
  719.  durable.up.Map.toStream.tests : [Result]
  720.  durable.up.Stream.distinctAdjacentBy : (i ->{g1} o)
                                               -> '{g} t
                                               -> '{g,
                                               g1,
                                               Stream i} t
  721.  durable.up.Stream.distinctBy : (i ->{g1} o)
                                       -> '{g} t
                                       -> '{g1, g, Stream i} t
  722.  durable.up.Stream.distinctBy.doc : Doc
  723.  durable.up.Stream.distinctBy.tests : [Result]
  724.  durable.up.Stream.toSet! : '{g, Stream a} r ->{g} Set a
  725.  durable.util.nestedTable : fn -> parent -> Table k v
  726.  durable.util.normalizedGzipDistance : x -> y -> Float
  727.  durable.util.normalizedGzipDistance.doc : Doc
  728.  durable.util.normalizedGzipDistance.examples.ex1 : Text
  729.  durable.util.normalizedGzipDistance.examples.ex2 : Text
  730.  durable.util.normalizedGzipDistance.examples.ex3 : Text
  731.  durable.util.normalizedGzipDistanceBytes : Bytes
                                                   -> Bytes
                                                   -> Float
  732.  durable.util.normalizedGzipDistanceBytes.doc : Doc
  733.  durable.util.normalizedGzipDistanceText : Text
                                                  -> Text
                                                  -> Float
  734.  durable.util.normalizedGzipDistanceText.doc : Doc
  735.  durable.util.randomName : '{Random} Text
  736.  durable.util.Text.paragraphs : Text -> [Text]
  737.  durable.util.Text.words : Text -> [Text]
  738.  durable.util.Text.words.alphanumeric : Text -> [Text]
  739.  type Environment
  740.  ability Environment.Config
  741.  Environment.Config.doc : Doc
  742.  Environment.Config.expect : Text
                                    ->{Environment.Config,
                                    Exception} Text
  743.  Environment.Config.expect.doc : Doc
  744.  type Environment.Config.failure.MissingKey
  745.  Environment.Config.failure.MissingKey.doc : Doc
  746.  Environment.Config.lookup : Text
                                    ->{Environment.Config} Optional
                                      Text
  747.  Environment.Config.lookup.doc : Doc
  748.  Environment.default : '{Exception, Cloud} Environment
  749.  Environment.default.doc : Doc
  750.  Environment.delete : Environment ->{Exception, Cloud} ()
  751.  Environment.delete.doc : Doc
  752.  Environment.deleteValue : Environment
                                  -> Text
                                  ->{Exception, Cloud} ()
  753.  Environment.deleteValue.doc : Doc
  754.  Environment.doc : Doc
  755.  Environment.Environment : Environment.Id
                                  -> Text
                                  -> Environment
  756.  type Environment.Id
  757.  Environment.id : Environment -> Environment.Id
  758.  Environment.id.doc : Doc
  759.  Environment.Id.Environment.Id.Id : Text
                                           -> Environment.Id
  760.  Environment.Id.fromJson : '{Decoder} Environment.Id
  761.  Environment.Id.toText : Environment.Id -> Text
  762.  Environment.list : '{Exception, Cloud} [Environment]
  763.  Environment.name : Environment -> Text
  764.  Environment.name.doc : Doc
  765.  Environment.named : Text
                            ->{Exception, Cloud} Environment
  766.  Environment.named.doc : Doc
  767.  Environment.named.validateName : Text ->{Exception} ()
  768.  Environment.setValue : Environment
                               -> Text
                               -> Text
                               ->{Exception, Cloud} ()
  769.  Environment.setValue.doc : Doc
  770.  Environment.toText : Environment -> Text
  771.  type errors.Conflict
  772.  type errors.CredentialsError
  773.  type errors.ProtocolError
  774.  type errors.SerializationError
  775.  type errors.UnknownDaemon
  776.  errors.UnknownDaemon.unknownDaemonHash : DaemonHash
                                                 -> Failure
  777.  type errors.UnknownService
  778.  errors.UnknownService.unknownServiceHash : ServiceHash
                                                     a b
                                                   -> Failure
  779.  type errors.UnknownTerm
  780.  type errors.UnknownWebSocket
  781.  examples.calculate7 : '{Remote} Nat
  782.  examples.deployLoggingService : '{Exception, Cloud} ServiceHash
                                          HttpRequest
                                          HttpResponse
  783.  examples.fetchMyServiceLogs : '{IO, Exception} [Json]
  784.  examples.httpServices : '{IO, Exception} Text
  785.  examples.interactive : '{IO, Exception} ()
  786.  examples.loggingService : HttpRequest
                                  ->{Remote, Log} HttpResponse
  787.  examples.main : '{IO, Exception} ()
  788.  examples.myEnvironment : Environment
  789.  examples.myServiceHash : ServiceHash
                                   HttpRequest HttpResponse
  790.  examples.namedHttpServices : '{IO, Exception} [Text]
  791.  examples.runBoth : '{Remote} (Nat, Nat)
  792.  examples.runBothLogged : '{Remote} (Nat, Nat)
  793.  examples.serviceCallAndConfig : '{IO, Exception} ( Optional
                                          Text,
                                          Optional Text,
                                          Optional Text)
  794.  examples.simpleBatch.main : '{IO, Exception} Nat
  795.  examples.simpleHttp.main : '{IO, Exception} ServiceHash
                                     HttpRequest HttpResponse
  796.  examples.simpleHttpNamed.main : '{IO, Exception} URI
  797.  examples.simpleLogHttp.main : '{IO, Exception} ServiceHash
                                        HttpRequest HttpResponse
  798.  examples.simpleStateful : Database
                                  -> Table URI Nat
                                  -> HttpRequest
                                  ->{Exception, Storage, Log} HttpResponse
  799.  examples.simpleStatefulHttp.main : '{IO, Exception} ServiceHash
                                             HttpRequest
                                             HttpResponse
  800.  examples.uploadFile : Environment
                              -> Database
                              -> Table Text Bytes
                              -> FilePath
                              -> Text
                              ->{IO, Exception, Cloud} ()
  801.  examples.uploadFile.doc : Doc
  802.  examples.webSocketCleanup.handler : websockets.WebSocket
                                            ->{Exception,
                                            Remote,
                                            WebSockets} ()
  803.  examples.webSocketEcho.deploy : '{IO, Exception} URI
  804.  internal.cloud.runThunk : AccessToken
                                  -> (QueryOptions
                                  ->{IO, Exception} [Json])
                                  -> Environment
                                  -> Connection
                                  -> '{Http, Remote, Scratch} a
                                  ->{IO, Exception} a
  805.  type internal.CloudRequest
  806.  internal.CloudRequest.ForkRequest : AccessToken
                                            -> Text
                                            -> Thunk
                                            -> CloudRequest
  807.  internal.CloudRequest.send : Connection
                                     -> CloudRequest
                                     ->{IO, Exception} ()
  808.  internal.CloudRequest.TermReply : [(Link.Term, Bytes)]
                                          -> CloudRequest
  809.  type internal.CloudResponse
  810.  internal.CloudResponse.decode : '{IO, Exception, Decode} CloudResponse
  811.  internal.CloudResponse.FailureReply : Text
                                              -> CloudResponse
  812.  internal.CloudResponse.FailureReply.decode : Bytes
                                                     ->{Exception} CloudResponse
  813.  internal.CloudResponse.JobStarted : JobId
                                            -> CloudResponse
  814.  internal.CloudResponse.JobStarted.decode : Bytes
                                                   -> CloudResponse
  815.  internal.CloudResponse.TaskResult : Either Failure Bytes
                                            -> CloudResponse
  816.  internal.CloudResponse.TaskResult.decode : Bytes
                                                   ->{IO,
                                                   Exception} CloudResponse
  817.  internal.CloudResponse.TermRequest : [Link.Term]
                                             -> CloudResponse
  818.  internal.CloudResponse.TermRequest.decode : Bytes
                                                    ->{IO,
                                                    Exception} CloudResponse
  819.  internal.connect : Cloud.ClientConfig
                           ->{IO, Exception} Connection
  820.  internal.credentials.accessTokenFromCredentialsFile : HostName
                                                              ->{IO,
                                                              Exception} AccessToken
  821.  internal.credentials.addAuthHeader : AccessToken
                                             -> HttpRequest
                                             -> HttpRequest
  822.  internal.decodeResult : Bytes ->{IO, Exception} a
  823.  internal.docs.blobListExample : Doc
  824.  internal.docs.blobNamespaces : Doc
  825.  internal.docs.blobPrefixQueryExample : Doc
  826.  internal.expectApiSuccess : Text
                                    -> HttpResponse
                                    ->{Exception} ()
  827.  internal.json.Decoder.customDomainDetails : '{Decoder} ( HostName,
                                                      Text)
  828.  internal.json.Decoder.uriStripTrailingSlash : '{Decoder} URI
  829.  internal.location.tags.default : [Text]
  830.  internal.services.serialization.encodeService : (a
                                                        ->{Remote} b)
                                                        ->{IO,
                                                        Exception,
                                                        Stream
                                                          Bytes} ()
  831.  internal.services.serialization.encodeService.doc : Doc
  832.  internal.tests.cloud.all : Remote.Duration
                                   ->{IO, Exception, Cloud} [( Text,
                                     '{IO,
                                   Exception,
                                   Cloud,
                                   Random} ())]
  833.  internal.tests.cloud.basicState : Remote.Duration
                                          ->{Exception,
                                          Cloud,
                                          Random} ()
  834.  internal.tests.cloud.blobs.crud : Remote.Duration
                                          ->{Exception,
                                          Cloud,
                                          Random} ()
  835.  internal.tests.cloud.daemons.crud : Environment
                                            ->{Exception,
                                            Cloud,
                                            Random} ()
  836.  internal.tests.cloud.database.crud : Remote.Duration
                                             ->{Exception,
                                             Cloud,
                                             Random} ()
  837.  internal.tests.cloud.deploy.crud : Remote.Duration
                                           -> Environment
                                           ->{Exception,
                                           Cloud,
                                           Random} ()
  838.  internal.tests.cloud.deployAndCall : Environment
                                             ->{Exception,
                                             Cloud,
                                             Random} ()
  839.  internal.tests.cloud.deployWS.crud : Environment
                                             ->{Exception,
                                             Cloud,
                                             Random} ()
  840.  internal.tests.cloud.durableConstructorsHashCheck : '{IO,
                                                            Exception} [Result]
  841.  internal.tests.cloud.environment.crud : Remote.Duration
                                                ->{Exception,
                                                Cloud,
                                                Random} ()
  842.  internal.tests.cloud.exposeAndCall : Remote.Duration
                                             -> Environment
                                             ->{Exception,
                                             Cloud,
                                             Random} ()
  843.  internal.tests.cloud.premium : Environment
                                       -> [( Text,
                                         '{IO,
                                       Exception,
                                       Cloud,
                                       Random} ())]
  844.  internal.tests.cloud.runAll : '{IO, Exception} [Result]
  845.  internal.tests.cloud.runAllLocally : '{IO, Exception} [Result]
  846.  internal.tests.cloud.runStandard : Remote.Duration
                                           ->{IO, Exception} [Result]
  847.  internal.tests.cloud.runTestSuite : [( Text,
                                              '{IO,
                                            Exception,
                                            Cloud,
                                            Random} ())]
                                            ->{IO, Exception} [Result]
  848.  internal.tests.cloud.scratchOps : Environment
                                          ->{Exception, Cloud} ()
  849.  internal.tests.cloud.serviceName.assignViaId : Environment
                                                       ->{Exception,
                                                       Cloud,
                                                       Random} ()
  850.  internal.tests.cloud.serviceName.crud : Remote.Duration
                                                -> Environment
                                                ->{Exception,
                                                Cloud,
                                                Random} ()
  851.  internal.tests.cloud.standard : Remote.Duration
                                        -> Environment
                                        ->{IO, Exception} [( Text,
                                          '{IO,
                                        Exception,
                                        Cloud,
                                        Random} ())]
  852.  internal.tests.cloud.stateViaService : Remote.Duration
                                               ->{Exception,
                                               Cloud,
                                               Random} ()
  853.  internal.tests.cloud.submit : Environment
                                      ->{Exception, Cloud} ()
  854.  type internal.Thunk
  855.  internal.Thunk.create : '{Http, Remote, Scratch} a
                                -> Thunk
  856.  internal.Thunk.Thunk : Bytes -> Thunk
  857.  internal.up.base.reflection.Link.Term.isBuiltin : Link.Term
                                                          -> Boolean
  858.  internal.up.base.reflection.Link.Term.isBuiltin.doc : Doc
  859.  internal.up.base.Set.isEmpty : Set k -> Boolean
  860.  internal.up.base.Value.dependenciesRecursive : reflection.Value
                                                       ->{IO,
                                                       Exception} data.Map
                                                         Link.Term
                                                         Code
  861.  internal.up.base.Value.dependenciesRecursive.doc : Doc
  862.  internal.up.FilePath./ : FilePath -> Text -> FilePath
  863.  internal.up.http.Headers.setHeader : Text
                                             -> Text
                                             -> Headers
                                             -> Headers
  864.  internal.up.http.Headers.setHeader.doc : Doc
  865.  internal.up.http.HttpRequest.addParam.doc : Doc
  866.  internal.up.http.URI./ : URI -> Text -> URI
  867.  internal.up.http.Uri./ : URI -> Text -> URI
  868.  internal.up.http.URI.slash.doc : Doc
  869.  internal.XDG.dataDirectory : '{IO, Exception} FilePath
  870.  type internal.XDG.MissingEnvVar
  871.  type JobId
  872.  JobId.doc : Doc
  873.  JobId.JobId : Text -> JobId
  874.  JobId.toText : JobId -> Text
  875.  JobId.toText.doc : Doc
  876.  LICENSE : License
  877.  ability Log
  878.  Log.atLevel.lazyJson : Level
                               -> 'Text
                               -> 'Json
                               ->{Log} ()
  879.  Log.customLevel : Text
                          -> Text
                          -> [(Text, Text)]
                          ->{Log} ()
  880.  Log.customLevel.json : Text -> Text -> Json ->{Log} ()
  881.  Log.customLevel.lazy : Text
                               -> 'Text
                               -> '[(Text, Text)]
                               ->{Log} ()
  882.  Log.customLevel.lazyJson : Text
                                   -> 'Text
                                   -> 'Json
                                   ->{Log} ()
  883.  Log.debug : Text -> [(Text, Text)] ->{Log} ()
  884.  Log.debug.doc : Doc
  885.  Log.debug.json : Text -> Json ->{Log} ()
  886.  Log.debug.json.doc : Doc
  887.  Log.debug.lazyJson : 'Text -> 'Json ->{Log} ()
  888.  Log.debug.lazyJson.doc : Doc
  889.  Log.debugLazyJson : 'Json ->{Log} ()
  890.  Log.doc : Doc
  891.  Log.error : Text -> [(Text, Text)] ->{Log} ()
  892.  Log.error.doc : Doc
  893.  Log.error.json : Text -> Json ->{Log} ()
  894.  Log.error.json.doc : Doc
  895.  Log.error.lazyJson : 'Text -> 'Json ->{Log} ()
  896.  Log.error.lazyJson.doc : Doc
  897.  Log.ignore : '{g, Log} r ->{g} r
  898.  Log.ignore.doc : Doc
  899.  Log.info : Text -> [(Text, Text)] ->{Log} ()
  900.  Log.info.doc : Doc
  901.  Log.info.json : Text -> Json ->{Log} ()
  902.  Log.info.json.doc : Doc
  903.  Log.info.lazyJson : 'Text -> 'Json ->{Log} ()
  904.  Log.info.lazyJson.doc : Doc
  905.  Log.json : Json ->{Log} ()
  906.  Log.lazyJson : 'Json ->{Log} ()
  907.  type Log.Level
  908.  Log.Level.Custom : Text -> Level
  909.  Log.Level.Debug : Level
  910.  Log.Level.Error : Level
  911.  Log.Level.Info : Level
  912.  Log.Level.toJson : Level -> (Text, Json)
  913.  Log.Level.Warn : Level
  914.  Log.printToHandle : Handle
                            -> '{g, Log} r
                            ->{g, IO, Exception} r
  915.  Log.printToHandle.doc : Doc
  916.  Log.printToStdOut : '{g, Log} r ->{g, IO, Exception} r
  917.  Log.printToStdOut.doc : Doc
  918.  Log.stripDebug : '{g, Log} r ->{g, Log} r
  919.  Log.stripDebug.doc : Doc
  920.  Log.warn : Text -> [(Text, Text)] ->{Log} ()
  921.  Log.warn.doc : Doc
  922.  Log.warn.json : Text -> Json ->{Log} ()
  923.  Log.warn.json.doc : Doc
  924.  Log.warn.lazyJson : 'Text -> 'Json ->{Log} ()
  925.  Log.warn.lazyJson.doc : Doc
  926.  pool : '{Remote} Location
                 {Blobs,
                 Environment.Config,
                 Http,
                 websockets.HttpWebSocket,
                 Log,
                 Scratch,
                 Services,
                 Storage,
                 WebSockets}
  927.  pool.doc : Doc
  928.  pool.far : '{Remote} Location
                     {Blobs,
                     Environment.Config,
                     Http,
                     websockets.HttpWebSocket,
                     Log,
                     Scratch,
                     Services,
                     Storage,
                     WebSockets}
  929.  pool.far.doc : Doc
  930.  pool.near : '{Remote} Location
                      {Blobs,
                      Environment.Config,
                      Http,
                      websockets.HttpWebSocket,
                      Log,
                      Scratch,
                      Services,
                      Storage,
                      WebSockets}
  931.  pool.near.doc : Doc
  932.  pool.toRemote : '{Environment.Config,
                        Exception,
                        Http,
                        Blobs,
                        Services,
                        Storage,
                        Remote,
                        websockets.HttpWebSocket,
                        WebSockets,
                        Random,
                        Log,
                        Scratch} a
                        ->{Remote} a
  933.  pool.toRemote.cached : '{Environment.Config,
                               Exception,
                               Http,
                               Blobs,
                               Services,
                               Storage,
                               Remote,
                               websockets.HttpWebSocket,
                               WebSockets,
                               Log,
                               Scratch} a
                               ->{Remote} a
  934.  pool.toRemote.cached.doc : Doc
  935.  pool.toRemote.cachedFor : time.Duration
                                  -> '{Environment.Config,
                                  Exception,
                                  Http,
                                  Blobs,
                                  Services,
                                  Storage,
                                  Remote,
                                  websockets.HttpWebSocket,
                                  WebSockets,
                                  Log,
                                  Scratch} a
                                  ->{Remote} a
  936.  pool.toRemote.cachedFor.doc : Doc
  937.  pool.toRemote.cachedFor.example : '{IO, Exception} ( Text,
                                            Text,
                                            Text,
                                            Boolean,
                                            Boolean)
  938.  pool.toRemote.cachedFor.tests : [Result]
  939.  pool.toRemote.doc : Doc
  940.  pool.wrap : (a
                    ->{Environment.Config,
                    Exception,
                    Http,
                    Blobs,
                    Services,
                    Storage,
                    Remote,
                    websockets.HttpWebSocket,
                    WebSockets,
                    Random,
                    Log,
                    Scratch} b)
                    -> a
                    ->{Remote} b
  941.  pool.wrap.doc : Doc
  942.  README : Doc
  943.  ReleaseNotes : Doc
  944.  ability Remote
  945.  Remote.addFinalizer : (Outcome ->{Remote} ())
                              ->{Remote} ()
  946.  Remote.allowCancel! : {Remote} ()
  947.  Remote.assuming : (Location {} -> Location g)
                          -> '{g, Remote} a
                          ->{Remote} a
  948.  Remote.assuming.doc : Doc
  949.  Remote.at : Location g
                    -> '{g, Exception, Remote} t
                    ->{Remote} t
  950.  Remote.await : Task a ->{Remote} a
  951.  Remote.await.doc : Doc
  952.  Remote.awaitRetain : Task a ->{Remote} a
  953.  Remote.awaitRetain.doc : Doc
  954.  Remote.both : '{Remote} a
                      -> '{Remote} b
                      ->{Remote} (a, b)
  955.  Remote.both.doc : Doc
  956.  Remote.cancel : Task a ->{Remote} ()
  957.  Remote.cancel.doc : Doc
  958.  Remote.catchOnly : Type
                           -> '{g, Exception, Remote} t
                           ->{g, Exception, Remote} Either
                             Failure t
  959.  Remote.detach : Location g
                        -> '{g, Exception, Remote} t
                        ->{Remote} Thread
  960.  Remote.detachAt : Location g
                          -> '{g, Exception, Remote} t
                          ->{Remote} Thread
  961.  Remote.detachAt_ : Location g
                           -> '{g, Exception, Remote} t
                           ->{Remote} ()
  962.  Remote.detach_ : Location g
                         -> '{g, Exception, Remote} t
                         ->{Remote} ()
  963.  Remote.doc : Doc
  964.  Remote.docs.examples.ex1 : Location {g, Stream Text}
                                   ->{Remote} Nat
  965.  Remote.docs.examples.taskTrees : Either Failure Nat
  966.  Remote.docs.run : '{Exception, Remote, Scratch} a
                          -> Either Failure a
  967.  Remote.docs.run.doc : Doc
  968.  Remote.docs.run.tests.test1 : [Result]
  969.  Remote.docs.run.tests.test2 : [Result]
  970.  Remote.docs.run.tests.test3 : [Result]
  971.  type Remote.Duration
  972.  Remote.Duration.* : Nat
                            -> Remote.Duration
                            -> Remote.Duration
  973.  Remote.Duration.+ : Remote.Duration
                            -> Remote.Duration
                            -> Remote.Duration
  974.  Remote.Duration.Duration : Nat -> Remote.Duration
  975.  Remote.Duration.hours : Nat -> Remote.Duration
  976.  Remote.Duration.micros : Nat -> Remote.Duration
  977.  Remote.Duration.millis : Nat -> Remote.Duration
  978.  Remote.Duration.minutes : Nat -> Remote.Duration
  979.  Remote.Duration.seconds : Nat -> Remote.Duration
  980.  Remote.Duration.toBaseDuration : Remote.Duration
                                         -> time.Duration
  981.  Remote.Duration.toMicros : Remote.Duration -> Nat
  982.  Remote.Duration.zero : Remote.Duration
  983.  Remote.eval : Location g
                      -> '{g, Exception, Remote} t
                      ->{Remote} t
  984.  Remote.eval.doc : Doc
  985.  Remote.fail : Failure ->{Remote} x
  986.  type Remote.failure.Cancelled
  987.  Remote.failure.cancelled : Failure
  988.  type Remote.failure.DeserializationError
  989.  Remote.failure.deserializationError : Text -> Failure
  990.  type Remote.failure.FailedToLoadTerms
  991.  Remote.failure.failedToLoadTerms : [Link.Term]
                                           -> Failure
  992.  type Remote.failure.NoAvailableLocations
  993.  Remote.failure.NoAvailableLocations.doc : Doc
  994.  type Remote.failure.PromiseDeleted
  995.  Remote.failure.promiseDeleted : Promise.Id -> Failure
  996.  type Remote.failure.RestrictedOperation
  997.  Remote.failure.RestrictedOperation.doc : Doc
  998.  type Remote.failure.Timeout
  999.  Remote.failure.timeout : reason -> Failure
  1000. type Remote.failure.UnknownHash
  1001. Remote.failure.unknownHash : Text -> h -> Failure
  1002. Remote.failure.UnknownHash.doc : Doc
  1003. Remote.failure.unknownHash.doc : Doc
  1004. type Remote.failure.UnknownLocation
  1005. Remote.failure.UnknownLocation.doc : Doc
  1006. type Remote.failure.UnknownPromise
  1007. Remote.failure.unknownPromise : Promise.Id -> Failure
  1008. type Remote.failure.UnknownRef
  1009. Remote.failure.unknownRef : Ref.Id -> Failure
  1010. type Remote.failure.UnknownTask
  1011. Remote.failure.unknownTask : UID -> Failure
  1012. type Remote.failure.ValueTooLarge
  1013. Remote.failure.ValueTooLarge.doc : Doc
  1014. Remote.far : Location g
                     -> Location g2
                     ->{Remote} Location g
  1015. Remote.finalizer : '{Remote} () ->{Remote} ()
  1016. Remote.finalizerError : '{Remote} () ->{Remote} ()
  1017. Remote.fork : Location g
                      -> '{g, Exception, Remote} t
                      ->{Remote} Task t
  1018. Remote.fork.doc : Doc
  1019. Remote.forkAt : Location g
                        -> '{g, Exception, Remote} t
                        ->{Remote} Task t
  1020. Remote.forkAt.doc : Doc
  1021. Remote.forkBracketUsefulNotes.doc : Doc
  1022. Remote.gatherSuccessful : Location g
                                  -> (a ->{g, Remote} b)
                                  -> [a]
                                  ->{Remote} [b]
  1023. Remote.here! : {Remote} (Location {})
  1024. Remote.isComplete : Task a ->{Remote} Boolean
  1025. Remote.isHere : Location g ->{Remote} Boolean
  1026. Remote.isHere.doc : Doc
  1027. Remote.isIncomplete : Task a ->{Remote} Boolean
  1028. Remote.link : Task a1 -> Task a ->{Remote} ()
  1029. Remote.link.doc : Doc
  1030. Remote.localize : Location g
                          ->{Remote} Optional
                            ('{g, Exception, Remote} a
                            ->{Remote} a)
  1031. Remote.localize.doc : Doc
  1032. type Remote.Location g
  1033. Remote.Location.doc : Doc
  1034. Remote.Location.Far : Location.Id
                              -> Location.Id
                              -> Location.Id
                              -> [Text]
                              -> Location g
  1035. type Remote.Location.Id
  1036. Remote.Location.Id.LocationId : UID -> Location.Id
  1037. Remote.Location.Id.toText : Location.Id -> Text
  1038. Remote.Location.Location : Location.Id
                                   -> [Text]
                                   -> Location g
  1039. Remote.Location.locationId : Location g -> Location.Id
  1040. Remote.Location.Near : Location.Id
                               -> Location.Id
                               -> Location.Id
                               -> [Text]
                               -> Location g
  1041. Remote.Location.tags : Location g -> [Text]
  1042. Remote.Location.tags.add : Text
                                   -> Location g
                                   -> Location g
  1043. Remote.Location.unsafe.cast : Location g -> Location g2
  1044. Remote.Location.unsafe.cast.doc : Doc
  1045. Remote.near : Location g
                      -> Location g2
                      ->{Remote} Location g
  1046. type Remote.Outcome
  1047. Remote.Outcome.Cancelled : Outcome
  1048. Remote.Outcome.Completed : Outcome
  1049. Remote.Outcome.Failed : Failure -> Outcome
  1050. Remote.own : Task a ->{Remote} ()
  1051. Remote.parMap : (a ->{Remote} t) -> [a] ->{Remote} [t]
  1052. Remote.parMap.doc : Doc
  1053. Remote.parMap.impl : Nat
                             -> Boolean
                             -> (a ->{Remote} b)
                             -> [a]
                             ->{Remote} [b]
  1054. Remote.ping : Remote.Duration
                      -> Location g
                      ->{Remote} Boolean
  1055. type Remote.Promise a
  1056. Remote.Promise.delete : Remote.Promise a ->{Remote} ()
  1057. Remote.Promise.empty : '{Remote} Remote.Promise a
  1058. Remote.Promise.empty.detached! : {Remote} (Remote.Promise
                                           a)
  1059. type Remote.Promise.Id
  1060. Remote.Promise.id : Remote.Promise a -> Promise.Id
  1061. Remote.Promise.Id.Id : UID -> Promise.Id
  1062. Remote.Promise.Promise : Promise.Id
                                 -> Location.Id
                                 -> Remote.Promise a
  1063. Remote.Promise.read : Remote.Promise a ->{Remote} a
  1064. Remote.Promise.readNow : Remote.Promise a
                                 ->{Remote} Optional a
  1065. Remote.Promise.tryDelete : Remote.Promise a
                                   ->{Remote} Either Failure ()
  1066. Remote.Promise.tryRead : Remote.Promise a
                                 ->{Remote} Either Failure a
  1067. Remote.Promise.tryReadNow : Remote.Promise a
                                    ->{Remote} Either
                                      Failure (Optional a)
  1068. Remote.Promise.tryWrite : Remote.Promise a
                                  -> a
                                  ->{Remote} Either
                                    Failure Boolean
  1069. Remote.Promise.write : Remote.Promise a
                               -> a
                               ->{Remote} Boolean
  1070. Remote.Promise.write_ : Remote.Promise a
                                -> a
                                ->{Remote} ()
  1071. Remote.race : '{Remote} a
                      -> '{Remote} b
                      ->{Remote} Either a b
  1072. Remote.race.doc : Doc
  1073. Remote.raceMap : (a ->{Remote} b)
                         -> List.Nonempty a
                         ->{Remote} b
  1074. Remote.raceMap.doc : Doc
  1075. Remote.randomBytes : Nat ->{Remote} Bytes
  1076. Remote.randomly : '{g, Random} t ->{g, Remote} t
  1077. Remote.randomly.doc : Doc
  1078. type Remote.Ref a
  1079. Remote.Ref.cas : Remote.Ref a
                         -> Ref.Ticket a
                         -> a
                         ->{Remote} Boolean
  1080. Remote.Ref.delete : Remote.Ref a ->{Remote} ()
  1081. Remote.Ref.getThenUpdate : Remote.Ref a
                                   -> (a -> a)
                                   ->{Remote} a
  1082. type Remote.Ref.Id
  1083. Remote.Ref.id : Remote.Ref a -> Ref.Id
  1084. Remote.Ref.Id.Id : UID -> Ref.Id
  1085. Remote.Ref.locationId : Remote.Ref a -> Location.Id
  1086. Remote.Ref.modify : Remote.Ref a
                            -> (a -> (a, b))
                            ->{Remote} b
  1087. Remote.Ref.new : a ->{Remote} Remote.Ref a
  1088. Remote.Ref.new.detached : a ->{Remote} Remote.Ref a
  1089. Remote.Ref.read : Remote.Ref a ->{Remote} a
  1090. Remote.Ref.readForCas : Remote.Ref a
                                ->{Remote} (Ref.Ticket a, a)
  1091. Remote.Ref.Ref : Ref.Id -> Location.Id -> Remote.Ref a
  1092. type Remote.Ref.Ticket a
  1093. Remote.Ref.Ticket.Ticket : Nat -> Ref.Ticket a
  1094. Remote.Ref.tryCas : Remote.Ref a
                            -> Ref.Ticket a
                            -> a
                            ->{Remote} Either Failure Boolean
  1095. Remote.Ref.tryDelete : Remote.Ref a
                               ->{Remote} Either Failure ()
  1096. Remote.Ref.tryReadForCas : Remote.Ref a
                                   ->{Remote} Either
                                     Failure (Ref.Ticket a, a)
  1097. Remote.Ref.tryWrite : Remote.Ref a
                              -> a
                              ->{Remote} Either Failure ()
  1098. Remote.Ref.update : Remote.Ref a
                            -> (a -> a)
                            ->{Remote} ()
  1099. Remote.Ref.updateThenGet : Remote.Ref a
                                   -> (a -> a)
                                   ->{Remote} a
  1100. Remote.Ref.write : Remote.Ref a -> a ->{Remote} ()
  1101. Remote.region! : {Remote} (Location {})
  1102. Remote.reraise : Either Failure b ->{Remote} b
  1103. Remote.reraise! : '{g, Exception, Remote} a
                          ->{g, Remote} a
  1104. Remote.rng : '{Remote} RNG
  1105. Remote.rng.doc : Doc
  1106. type Remote.run.Interrupt
  1107. Remote.run.Interrupt.checkInterrupt : Interrupt
                                              ->{IO} Boolean
  1108. Remote.run.Interrupt.Interrupt : concurrent.Promise ()
                                         -> concurrent.Promise
                                           ()
                                         -> Interrupt
  1109. Remote.run.Interrupt.interruptAndAwaitFinalization : Interrupt
                                                             ->{IO} ()
  1110. Remote.run.Interrupt.interruptibly : Interrupt
                                             -> '{IO, Exception} t
                                             ->{IO,
                                             Exception,
                                             Abort} t
  1111. Remote.run.Interrupt.signalFinalization : Interrupt
                                                  ->{IO} ()
  1112. Remote.run.pure : (∀ g x. '{g} x ->{Scope s} x)
                          -> '{Remote} a
                          ->{Random, Scope s} Either Failure a
  1113. type Remote.run.pure.ThreadState s
  1114. Remote.run.pure.ThreadState.completed : ThreadState s
                                                -> Remote.Promise
                                                  (Optional
                                                    (Either
                                                      Failure
                                                      Any))
  1115. Remote.run.pure.ThreadState.completed.modify : (Remote.Promise
                                                         (Optional
                                                           (Either
                                                             Failure
                                                             Any))
                                                       ->{g} Remote.Promise
                                                         (Optional
                                                           (Either
                                                             Failure
                                                             Any)))
                                                       -> ThreadState
                                                         s
                                                       ->{g} ThreadState
                                                         s
  1116. Remote.run.pure.ThreadState.completed.set : Remote.Promise
                                                      (Optional
                                                        (Either
                                                          Failure
                                                          Any))
                                                    -> ThreadState
                                                      s
                                                    -> ThreadState
                                                      s
  1117. Remote.run.pure.ThreadState.finalizers : ThreadState s
                                                 -> [Outcome
                                                 ->{Remote,
                                                 Scope s} ()]
  1118. Remote.run.pure.ThreadState.finalizers.modify : ([Outcome
                                                        ->{Remote,
                                                        Scope s} ()]
                                                        ->{g} [Outcome
                                                        ->{Remote,
                                                        Scope s} ()])
                                                        -> ThreadState
                                                          s
                                                        ->{g} ThreadState
                                                          s
  1119. Remote.run.pure.ThreadState.finalizers.set : [Outcome
                                                     ->{Remote,
                                                     Scope s} ()]
                                                     -> ThreadState
                                                       s
                                                     -> ThreadState
                                                       s
  1120. Remote.run.pure.ThreadState.status : ThreadState s
                                             -> ThreadStatus s
  1121. Remote.run.pure.ThreadState.status.modify : (ThreadStatus
                                                      s
                                                    ->{g} ThreadStatus
                                                      s)
                                                    -> ThreadState
                                                      s
                                                    ->{g} ThreadState
                                                      s
  1122. Remote.run.pure.ThreadState.status.set : ThreadStatus s
                                                 -> ThreadState
                                                   s
                                                 -> ThreadState
                                                   s
  1123. Remote.run.pure.ThreadState.ThreadState : ThreadStatus s
                                                  -> Remote.Promise
                                                    (Optional
                                                      (Either
                                                        Failure
                                                        Any))
                                                  -> [Outcome
                                                  ->{Remote,
                                                  Scope s} ()]
                                                  -> ThreadState
                                                    s
  1124. type Remote.run.pure.ThreadStatus s
  1125. Remote.run.pure.ThreadStatus.Blocking : '{Scope s} ()
                                                -> ThreadStatus
                                                  s
  1126. Remote.run.pure.ThreadStatus.CancellationRequested : ThreadStatus
                                                               s
  1127. Remote.run.pure.ThreadStatus.Running : ThreadStatus s
  1128. Remote.run.pure.ThreadStatus.Scoped : Thread.Id
                                              -> ThreadStatus s
  1129. Remote.run.threaded : (∀ g x.
                                ctx
                                -> Interrupt
                                -> '{g} x
                                ->{IO, Exception, Abort, Remote} x)
                              ->{IO, Random} (∀ a.
                                ctx
                                -> Interrupt
                                -> '{Remote} a
                                ->{IO, Exception} a)
  1130. Remote.run.threaded.doc : Doc
  1131. Remote.scope : '{Remote} a ->{Remote} a
  1132. Remote.sleep : Remote.Duration ->{Remote} ()
  1133. Remote.sleep.doc : Doc
  1134. Remote.sleepMicroseconds : Nat ->{Remote} ()
  1135. type Remote.Task a
  1136. Remote.Task.doc : Doc
  1137. Remote.Task.promise : Task a
                              -> Remote.Promise
                                (Either Failure a)
  1138. Remote.Task.pure : a ->{Remote} Task a
  1139. Remote.Task.pure.doc : Doc
  1140. Remote.Task.resultLocation : Task a -> Location {}
  1141. Remote.Task.Task : Thread
                           -> Remote.Promise (Either Failure a)
                           -> Task a
  1142. Remote.Task.thread : Task a -> Thread
  1143. Remote.Task.workLocation : Task a -> Location {}
  1144. Remote.test.assertions.allowCancel : Exists
                                               assertions.Test
  1145. Remote.test.assertions.assertUnknownPromiseFailure : Either
                                                               Failure
                                                               a
                                                             ->{Exception} ()
  1146. Remote.test.assertions.awaitAwaitsFinalization : Exists
                                                           assertions.Test
  1147. Remote.test.assertions.basicCancellation : Exists
                                                     assertions.Test
  1148. Remote.test.assertions.basicProgram : Exists
                                                assertions.Test
  1149. Remote.test.assertions.bugInFork : Exists
                                             assertions.Test
  1150. Remote.test.assertions.bugInTryScope : Exists
                                                 assertions.Test
  1151. Remote.test.assertions.cancelAfterAwait : Exists
                                                    assertions.Test
  1152. Remote.test.assertions.cancelAwait : Exists
                                               assertions.Test
  1153. Remote.test.assertions.cancelAwaitsFinalization : Exists
                                                            assertions.Test
  1154. Remote.test.assertions.childrenGetCanceled : Exists
                                                       assertions.Test
  1155. Remote.test.assertions.forkAndAwait : Exists
                                                assertions.Test
  1156. Remote.test.assertions.forkFinalizersRuntimeException : Exists
                                                                  assertions.Test
  1157. Remote.test.assertions.forkHereIsHere : Exists
                                                  assertions.Test
  1158. Remote.test.assertions.idAllocationInFinalizers : Exists
                                                            assertions.Test
  1159. Remote.test.assertions.impure : '{IO, Exception} [Exists
                                          assertions.Test]
  1160. Remote.test.assertions.nowIsReasonable : Instant
                                                 -> Exists
                                                   assertions.Test
  1161. Remote.test.assertions.pure : [Exists assertions.Test]
  1162. Remote.test.assertions.pure.doc : Doc
  1163. Remote.test.assertions.randomBytesAreReasonable : Exists
                                                            assertions.Test
  1164. Remote.test.assertions.refDeleteNonexistent : Exists
                                                        assertions.Test
  1165. Remote.test.assertions.remoteCancellation : Exists
                                                      assertions.Test
  1166. Remote.test.assertions.run : (∀ r.
                                       '{Remote} r
                                       ->{g, Exception} r)
                                     -> [Exists assertions.Test]
                                     ->{g} [Result]
  1167. Remote.test.assertions.runAllLocally : '{IO, Exception} [Result]
  1168. Remote.test.assertions.runAllPure : [Result]
  1169. Remote.test.assertions.scopeFinalizersRuntimeException : Exists
                                                                   assertions.Test
  1170. Remote.test.assertions.scopePropagatesInterruption : Exists
                                                               assertions.Test
  1171. Remote.test.assertions.scopeRunsSyncFinalization : Exists
                                                             assertions.Test
  1172. type Remote.test.assertions.Test a
  1173. Remote.test.assertions.Test.Test : Text
                                           -> '{Remote} a
                                           -> (Either Failure a
                                           ->{Exception} ())
                                           -> assertions.Test a
  1174. Remote.test.longRunningTask : '{Remote} Task ()
  1175. Remote.test.neverEndingTask : '{Remote} Task Void
  1176. Remote.test.real.allowCancel : '{Remote} ()
  1177. Remote.test.real.cancelAfterAwait : '{Remote} ()
  1178. Remote.test.real.cancelAwait : '{Remote} ()
  1179. Remote.test.real.cancelAwaitsFinalizers : '{Remote} ()
  1180. Remote.test.real.cancelNotification : '{Remote} Either
                                                Failure ()
  1181. Remote.test.real.closedScope : '{Remote} Either
                                         Failure Text
  1182. Remote.test.real.delayedForkAwait : '{Remote} Text
  1183. Remote.test.real.detachAt : '{Remote} ()
  1184. Remote.test.real.detachedScope : '{Remote} ()
  1185. Remote.test.real.idAllocationFinalizers : '{Remote} ()
  1186. Remote.test.real.immediateForkAwait : '{Remote} Text
  1187. Remote.test.real.promiseRead : '{Remote} Text
  1188. Remote.test.real.refConcurrency : '{Remote} Nat
  1189. Remote.test.real.refReadWrite : '{Remote} Nat
  1190. Remote.test.real.scopedCancelAndOwn : '{Remote} Text
  1191. Remote.test.real.scopedCancelNotification : '{Remote} Either
                                                      Failure ()
  1192. Remote.test.real.sharedStateMultipleInterpreters : '{IO,
                                                           Exception} Nat
  1193. Remote.test.real.taskBug : '{Remote} Either Failure t
  1194. Remote.test.real.taskCancel : '{Remote} Text
  1195. Remote.test.run : '{Remote} a ->{IO, Exception} a
  1196. Remote.test.runLabeled : Text
                                 -> '{g, Exception} ()
                                 ->{g} Result
  1197. Remote.test.runLabeled.doc : Doc
  1198. Remote.test.simulate : Nat
                               -> '{Remote} a
                               -> ([Text], Either Failure a)
  1199. Remote.test.simulated.allowCancel : '{Remote} ()
  1200. Remote.test.simulated.allowCancelAfterScope : '{Remote} ()
  1201. Remote.test.simulated.cancelPreSleep : '{Remote} ()
  1202. Remote.test.simulated.cancelPromiseRead : '{Remote} ()
  1203. Remote.test.simulated.cancelSleep : '{Remote} ()
  1204. Remote.test.simulated.cancelSleepAfterForkScope : '{Remote} ()
  1205. Remote.test.simulated.cancelSleepAfterScope : '{Remote} ()
  1206. Remote.test.simulated.failShortCircuits : '{Remote} ()
  1207. Remote.test.simulated.nestedScopes : '{Remote} ()
  1208. Remote.test.simulated.promiseReadDelete : '{Remote} Either
                                                    Failure a
  1209. Remote.test.simulated.promiseRendezVous : '{Remote} Text
  1210. Remote.test.simulated.runtimeRunsDetachedThreads : '{Remote} Nat
  1211. Remote.test.simulated.scopeCancellation : '{Remote} ()
  1212. Remote.test.simulated.scopeCompletion : '{Remote} ()
  1213. Remote.test.simulated.simpleFork : '{Remote} Nat
  1214. Remote.test.simulated.uncancelableAfterScope : '{Remote} ()
  1215. Remote.test.sleepForever : '{Remote} Void
  1216. ability Remote.test.TestLog
  1217. Remote.test.TestLog.log : Text ->{TestLog} ()
  1218. Remote.test.testPool : Location {TestLog, Scratch}
  1219. type Remote.Thread
  1220. Remote.Thread.cancel : Thread ->{Remote} ()
  1221. type Remote.Thread.Id
  1222. Remote.Thread.id : Thread -> Thread.Id
  1223. Remote.Thread.Id.Id : UID -> Thread.Id
  1224. Remote.Thread.Thread : Thread.Id
                               -> Location.Id
                               -> Thread
  1225. Remote.time.monotonic! : {Remote} time.Duration
  1226. Remote.time.monotonic!.doc : Doc
  1227. Remote.time.now! : {Remote} Instant
  1228. Remote.time.now!.doc : Doc
  1229. Remote.timeout : Remote.Duration
                         -> '{Remote} a
                         ->{Remote} a
  1230. Remote.timeout.doc : Doc
  1231. Remote.try : '{g, Exception, Remote} a
                     ->{g, Remote} Either Failure a
  1232. Remote.tryAwait : Task a ->{Remote} Either Failure a
  1233. Remote.tryCancel : Thread ->{Remote} Either Failure ()
  1234. Remote.tryDetachAt : Location g
                             -> '{g, Exception, Remote} a
                             ->{Remote} Either Failure Thread
  1235. Remote.tryFar : Location g
                        -> Location g2
                        ->{Remote} Either Failure (Location g)
  1236. Remote.tryNear : Location g
                         -> Location g2
                         ->{Remote} Either Failure (Location g)
  1237. Remote.tryOr : a -> '{g, Remote} a ->{g, Remote} a
  1238. Remote.tryScope : '{Remote} a
                          ->{Remote} Either Failure a
  1239. type Remote.UID
  1240. Remote.UID.fromNat : Nat -> UID
  1241. Remote.UID.random : '{Random} UID
  1242. Remote.UID.UID : Bytes -> UID
  1243. structural type Remote.Value a
  1244. Remote.Value.at : Location g -> a -> Remote.Value a
  1245. Remote.Value.at.doc : Doc
  1246. Remote.Value.cache : Task x
                             -> Remote.Value a
                             ->{Remote} Remote.Value a
  1247. Remote.Value.cache.doc : Doc
  1248. Remote.Value.delay : '{Remote} a -> Remote.Value a
  1249. Remote.Value.delay.doc : Doc
  1250. Remote.Value.delayAt : Location {g}
                               -> '{g, Exception, Remote} t
                               -> Remote.Value t
  1251. Remote.Value.delayAt.doc : Doc
  1252. Remote.Value.doc : Doc
  1253. Remote.Value.flatMap : (i
                               ->{Exception, Remote} Remote.Value
                                 a)
                               -> Remote.Value i
                               -> Remote.Value a
  1254. Remote.Value.flatMap.doc : Doc
  1255. Remote.Value.forkMemoAt : Location {Scratch, g}
                                  -> '{g,
                                  Exception,
                                  Remote,
                                  Scratch} r
                                  ->{Remote} Remote.Value r
  1256. Remote.Value.forkMemoAt.doc : Doc
  1257. Remote.Value.fromTask : Task a -> Remote.Value a
  1258. Remote.Value.fromTask.doc : Doc
  1259. Remote.Value.fromTaskOnce : Task a -> Remote.Value a
  1260. Remote.Value.fromTaskOnce.doc : Doc
  1261. Remote.Value.get : Remote.Value a ->{Remote} a
  1262. Remote.Value.get.doc : Doc
  1263. Remote.Value.join : Remote.Value (Remote.Value a)
                            -> Remote.Value a
  1264. Remote.Value.map : (i ->{Exception, Remote} o)
                           -> Remote.Value i
                           -> Remote.Value o
  1265. Remote.Value.map.doc : Doc
  1266. Remote.Value.memo : Location {g, Scratch}
                            -> Remote.Value a
                            -> Remote.Value a
  1267. Remote.Value.memo.impl.memoHash : a -> Hash
  1268. type Remote.Value.memo.impl.MemoTagged a
  1269. Remote.Value.memo.impl.MemoTagged.MemoTagged : a
                                                       -> MemoTagged
                                                         a
  1270. Remote.Value.memo.impl.saveHash : a -> Hash
  1271. type Remote.Value.memo.impl.SaveTagged a
  1272. Remote.Value.memo.impl.SaveTagged.SaveTagged : a
                                                       -> SaveTagged
                                                         a
  1273. Remote.Value.memo' : Location {Scratch, g}
                             -> '{Remote} a
                             -> Remote.Value a
  1274. Remote.Value.memoAt : Location {Scratch, g}
                              -> '{g,
                              Exception,
                              Remote,
                              Scratch} r
                              -> Remote.Value r
  1275. Remote.Value.memoAt.doc : Doc
  1276. Remote.Value.pure : a -> Remote.Value a
  1277. Remote.Value.pure.doc : Doc
  1278. Remote.Value.toRAM : Remote.Value a
                             ->{Remote} Remote.Value a
  1279. Remote.Value.Value : (∀ r. (a ->{Remote} r) ->{Remote} r)
                             -> Remote.Value a
  1280. ability Scratch
  1281. Scratch.assume : Location g -> Location {g, Scratch}
  1282. Scratch.exists : Hashed a ->{Scratch} Boolean
  1283. type Scratch.Hashed a
  1284. type Scratch.Hashed.Hash
  1285. Scratch.Hashed.Hash.Hash : Bytes -> Hash
  1286. Scratch.Hashed.Hashed : Hash -> Hashed a
  1287. Scratch.Hashed.toBytes : Hashed a -> Bytes
  1288. Scratch.Hashed.toBytes.doc : Doc
  1289. Scratch.hashKey : k a ->{Scratch} Hashed a
  1290. Scratch.local.handler : '{IO} (∀ g a.
                                  ctx
                                  -> '{g, Scratch} a
                                  ->{g, IO} a)
  1291. Scratch.location.tag : Text
  1292. Scratch.lookup : k a ->{Scratch} Optional a
  1293. Scratch.lookupHashed : Hashed a ->{Scratch} Optional a
  1294. Scratch.RAM : '{g, Scratch} a ->{g} a
  1295. Scratch.RAM.handler : Request {Scratch} a -> a
  1296. Scratch.replicateFrom : '{Remote} Location {Scratch, g}
                                -> Nat
                                -> a
                                ->{Remote} Remote.Value a
  1297. Scratch.replicateFrom.doc : Doc
  1298. Scratch.restore! : Hashed a ->{Abort, Scratch} a
  1299. Scratch.restoreOr : a -> Hashed a ->{Scratch} a
  1300. Scratch.save : a ->{Scratch} Hashed a
  1301. Scratch.saveHashed : Hashed a -> a ->{Scratch} ()
  1302. Scratch.saveKeyed : k a -> a ->{Scratch} Hashed a
  1303. Scratch.touch : Hashed a ->{Scratch} ()
  1304. type ServiceAssignment
  1305. ServiceAssignment.assignedAt : ServiceAssignment
                                       -> Instant
  1306. ServiceAssignment.assignedAt.modify : (Instant
                                              ->{g} Instant)
                                              -> ServiceAssignment
                                              ->{g} ServiceAssignment
  1307. ServiceAssignment.assignedAt.set : Instant
                                           -> ServiceAssignment
                                           -> ServiceAssignment
  1308. ServiceAssignment.assignedBy : ServiceAssignment
                                       -> UserInfo
  1309. ServiceAssignment.assignedBy.modify : (UserInfo
                                              ->{g} UserInfo)
                                              -> ServiceAssignment
                                              ->{g} ServiceAssignment
  1310. ServiceAssignment.assignedBy.set : UserInfo
                                           -> ServiceAssignment
                                           -> ServiceAssignment
  1311. ServiceAssignment.deployedAt : ServiceAssignment
                                       -> Instant
  1312. ServiceAssignment.deployedAt.modify : (Instant
                                              ->{g} Instant)
                                              -> ServiceAssignment
                                              ->{g} ServiceAssignment
  1313. ServiceAssignment.deployedAt.set : Instant
                                           -> ServiceAssignment
                                           -> ServiceAssignment
  1314. ServiceAssignment.deployedBy : ServiceAssignment
                                       -> UserInfo
  1315. ServiceAssignment.deployedBy.modify : (UserInfo
                                              ->{g} UserInfo)
                                              -> ServiceAssignment
                                              ->{g} ServiceAssignment
  1316. ServiceAssignment.deployedBy.set : UserInfo
                                           -> ServiceAssignment
                                           -> ServiceAssignment
  1317. ServiceAssignment.doc : Doc
  1318. ServiceAssignment.exposedAt : ServiceAssignment
                                      -> Optional Instant
  1319. ServiceAssignment.exposedAt.modify : (Optional Instant
                                             ->{g} Optional
                                               Instant)
                                             -> ServiceAssignment
                                             ->{g} ServiceAssignment
  1320. ServiceAssignment.exposedAt.set : Optional Instant
                                          -> ServiceAssignment
                                          -> ServiceAssignment
  1321. ServiceAssignment.fromJson : '{Decoder} ServiceAssignment
  1322. ServiceAssignment.fromJson.doc : Doc
  1323. ServiceAssignment.hash : ServiceAssignment
                                 -> ServiceHash.Untyped
  1324. ServiceAssignment.hash.modify : (ServiceHash.Untyped
                                        ->{g} ServiceHash.Untyped)
                                        -> ServiceAssignment
                                        ->{g} ServiceAssignment
  1325. ServiceAssignment.hash.set : ServiceHash.Untyped
                                     -> ServiceAssignment
                                     -> ServiceAssignment
  1326. ServiceAssignment.historyAt : ServiceAssignment
                                      -> Optional Instant
  1327. ServiceAssignment.historyAt.modify : (Optional Instant
                                             ->{g} Optional
                                               Instant)
                                             -> ServiceAssignment
                                             ->{g} ServiceAssignment
  1328. ServiceAssignment.historyAt.set : Optional Instant
                                          -> ServiceAssignment
                                          -> ServiceAssignment
  1329. ServiceAssignment.ServiceAssignment : ServiceHash.Untyped
                                              -> UserInfo
                                              -> Instant
                                              -> Optional
                                                Instant
                                              -> Optional
                                                Instant
                                              -> Optional
                                                Instant
                                              -> [Text]
                                              -> UserInfo
                                              -> Instant
                                              -> Optional
                                                Instant
                                              -> ServiceAssignment
  1330. ServiceAssignment.tags : ServiceAssignment -> [Text]
  1331. ServiceAssignment.tags.modify : ([Text] ->{g} [Text])
                                        -> ServiceAssignment
                                        ->{g} ServiceAssignment
  1332. ServiceAssignment.tags.set : [Text]
                                     -> ServiceAssignment
                                     -> ServiceAssignment
  1333. ServiceAssignment.undeployedAt : ServiceAssignment
                                         -> Optional Instant
  1334. ServiceAssignment.undeployedAt.modify : (Optional
                                                  Instant
                                                ->{g} Optional
                                                  Instant)
                                                -> ServiceAssignment
                                                ->{g} ServiceAssignment
  1335. ServiceAssignment.undeployedAt.set : Optional Instant
                                             -> ServiceAssignment
                                             -> ServiceAssignment
  1336. ServiceAssignment.unexposedAt : ServiceAssignment
                                        -> Optional Instant
  1337. ServiceAssignment.unexposedAt.modify : (Optional Instant
                                               ->{g} Optional
                                                 Instant)
                                               -> ServiceAssignment
                                               ->{g} ServiceAssignment
  1338. ServiceAssignment.unexposedAt.set : Optional Instant
                                            -> ServiceAssignment
                                            -> ServiceAssignment
  1339. type ServiceHash a b
  1340. ServiceHash.allTags : '{IO, Exception} [Text]
  1341. ServiceHash.allTags.doc : Doc
  1342. ServiceHash.allTags.withConfig : Cloud.ClientConfig
                                         ->{IO, Exception} [Text]
  1343. ServiceHash.allTags.withConfig.doc : Doc
  1344. ServiceHash.byTag : Text
                            ->{IO, Exception} [DeploymentInfo]
  1345. ServiceHash.byTag.doc : Doc
  1346. ServiceHash.byTag.withConfig : Cloud.ClientConfig
                                       -> Text
                                       ->{IO, Exception} [DeploymentInfo]
  1347. ServiceHash.byTag.withConfig.doc : Doc
  1348. ServiceHash.doc : Doc
  1349. ServiceHash.fromJson : '{Decoder} ServiceHash.Untyped
  1350. ServiceHash.list : '{IO, Exception} [DeploymentInfo]
  1351. ServiceHash.list.doc : Doc
  1352. ServiceHash.list.withConfig : Cloud.ClientConfig
                                      ->{IO, Exception} [DeploymentInfo]
  1353. ServiceHash.list.withConfig.doc : Doc
  1354. ServiceHash.ServiceHash : Text -> ServiceHash a b
  1355. ServiceHash.tag : Text
                          -> ServiceHash.Untyped
                          ->{IO, Exception} ()
  1356. ServiceHash.tag.doc : Doc
  1357. ServiceHash.tag.withConfig : Cloud.ClientConfig
                                     -> Text
                                     -> ServiceHash.Untyped
                                     ->{IO, Exception} ()
  1358. ServiceHash.tag.withConfig.doc : Doc
  1359. ServiceHash.tags : ServiceHash.Untyped
                           ->{IO, Exception} [Text]
  1360. ServiceHash.tags.doc : Doc
  1361. ServiceHash.tags.withConfig : Cloud.ClientConfig
                                      -> ServiceHash.Untyped
                                      ->{IO, Exception} [Text]
  1362. ServiceHash.tags.withConfig.doc : Doc
  1363. ServiceHash.toText : ServiceHash a b -> Text
  1364. ServiceHash.untag : Text
                            -> ServiceHash.Untyped
                            ->{IO, Exception} ()
  1365. ServiceHash.untag.doc : Doc
  1366. ServiceHash.untag.withConfig : Cloud.ClientConfig
                                       -> Text
                                       -> ServiceHash.Untyped
                                       ->{IO, Exception} ()
  1367. ServiceHash.untag.withConfig.doc : Doc
  1368. ServiceHash.untagged : '{IO, Exception} [DeploymentInfo]
  1369. ServiceHash.untagged.doc : Doc
  1370. ServiceHash.untagged.withConfig : Cloud.ClientConfig
                                          ->{IO, Exception} [DeploymentInfo]
  1371. ServiceHash.untagged.withConfig.doc : Doc
  1372. type ServiceHash.Untyped
  1373. ServiceHash.Untyped.Untyped : Text
                                      -> ServiceHash.Untyped
  1374. type ServiceName a b
  1375. ServiceName.allTags : '{IO, Exception} [Text]
  1376. ServiceName.allTags.doc : Doc
  1377. ServiceName.allTags.withConfig : Cloud.ClientConfig
                                         ->{IO, Exception} [Text]
  1378. ServiceName.allTags.withConfig.doc : Doc
  1379. ServiceName.assign : ServiceName a b
                             -> ServiceHash a b
                             ->{Exception, Cloud} URI
  1380. ServiceName.byTag : Text
                            ->{IO, Exception} [ServiceNameInfo]
  1381. ServiceName.byTag.doc : Doc
  1382. ServiceName.byTag.withConfig : Cloud.ClientConfig
                                       -> Text
                                       ->{IO, Exception} [ServiceNameInfo]
  1383. ServiceName.byTag.withConfig.doc : Doc
  1384. ServiceName.delete : ServiceName a b
                             ->{Exception, Cloud} ()
  1385. ServiceName.doc : Doc
  1386. ServiceName.fromJson : '{Decoder} ServiceName.Untyped
  1387. ServiceName.history : ServiceName.Id
                              ->{IO, Exception} [ServiceAssignment]
  1388. ServiceName.history.doc : Doc
  1389. ServiceName.history.withConfig : Cloud.ClientConfig
                                         -> ServiceName.Id
                                         ->{IO, Exception} [ServiceAssignment]
  1390. ServiceName.history.withConfig.doc : Doc
  1391. type ServiceName.Id
  1392. ServiceName.id : ServiceName a b -> ServiceName.Id
  1393. ServiceName.Id.Id : Text -> ServiceName.Id
  1394. ServiceName.Id.toText : ServiceName.Id -> Text
  1395. ServiceName.list : '{IO, Exception} [ServiceNameInfo]
  1396. ServiceName.list.withConfig : Cloud.ClientConfig
                                      ->{IO, Exception} [ServiceNameInfo]
  1397. ServiceName.list.withConfig.doc : Doc
  1398. ServiceName.name : ServiceName a b -> Text
  1399. ServiceName.named : Text
                            ->{Exception, Cloud} ServiceName a b
  1400. ServiceName.ServiceName : ServiceName.Id
                                  -> Text
                                  -> ServiceName a b
  1401. ServiceName.tag : Text
                          -> ServiceName.Id
                          ->{IO, Exception} ()
  1402. ServiceName.tag.doc : Doc
  1403. ServiceName.tag.withConfig : Cloud.ClientConfig
                                     -> Text
                                     -> ServiceName.Id
                                     ->{IO, Exception} ()
  1404. ServiceName.tag.withConfig.doc : Doc
  1405. ServiceName.tags : ServiceName.Id
                           ->{IO, Exception} [Text]
  1406. ServiceName.tags.doc : Doc
  1407. ServiceName.tags.withConfig : Cloud.ClientConfig
                                      -> ServiceName.Id
                                      ->{IO, Exception} [Text]
  1408. ServiceName.tags.withConfig.doc : Doc
  1409. ServiceName.toText : ServiceName a b -> Text
  1410. ServiceName.unassign : ServiceName a b
                               ->{Exception, Cloud} ()
  1411. ServiceName.untag : Text
                            -> ServiceName.Id
                            ->{IO, Exception} ()
  1412. ServiceName.untag.doc : Doc
  1413. ServiceName.untag.withConfig : Cloud.ClientConfig
                                       -> Text
                                       -> ServiceName.Id
                                       ->{IO, Exception} ()
  1414. ServiceName.untag.withConfig.doc : Doc
  1415. ServiceName.untagged : '{IO, Exception} [ServiceNameInfo]
  1416. ServiceName.untagged.doc : Doc
  1417. ServiceName.untagged.withConfig : Cloud.ClientConfig
                                          ->{IO, Exception} [ServiceNameInfo]
  1418. ServiceName.untagged.withConfig.doc : Doc
  1419. type ServiceName.Untyped
  1420. ServiceName.Untyped.Untyped : ServiceName.Id
                                      -> Text
                                      -> ServiceName.Untyped
  1421. type ServiceNameInfo
  1422. ServiceNameInfo.currentDeployment : ServiceNameInfo
                                            -> Optional
                                              DeploymentInfo
  1423. ServiceNameInfo.currentDeployment.modify : (Optional
                                                     DeploymentInfo
                                                   ->{g} Optional
                                                     DeploymentInfo)
                                                   -> ServiceNameInfo
                                                   ->{g} ServiceNameInfo
  1424. ServiceNameInfo.currentDeployment.set : Optional
                                                  DeploymentInfo
                                                -> ServiceNameInfo
                                                -> ServiceNameInfo
  1425. ServiceNameInfo.fromJson : '{Decoder} ServiceNameInfo
  1426. ServiceNameInfo.owner : ServiceNameInfo -> UserInfo
  1427. ServiceNameInfo.owner.modify : (UserInfo ->{g} UserInfo)
                                       -> ServiceNameInfo
                                       ->{g} ServiceNameInfo
  1428. ServiceNameInfo.owner.set : UserInfo
                                    -> ServiceNameInfo
                                    -> ServiceNameInfo
  1429. ServiceNameInfo.service : ServiceNameInfo
                                  -> ServiceName.Untyped
  1430. ServiceNameInfo.service.modify : (ServiceName.Untyped
                                         ->{g} ServiceName.Untyped)
                                         -> ServiceNameInfo
                                         ->{g} ServiceNameInfo
  1431. ServiceNameInfo.service.set : ServiceName.Untyped
                                      -> ServiceNameInfo
                                      -> ServiceNameInfo
  1432. ServiceNameInfo.ServiceNameInfo : ServiceName.Untyped
                                          -> Optional
                                            DeploymentInfo
                                          -> UserInfo
                                          -> ServiceNameInfo
  1433. ability Services
  1434. Services.basePath : Headers -> Path
  1435. Services.basePath.doc : Doc
  1436. Services.call : ServiceHash a b
                        -> a
                        ->{Services, Remote} b
  1437. Services.callName : ServiceName a b
                            -> a
                            ->{Services, Remote} b
  1438. Services.doc : Doc
  1439. Services.resolve : ServiceName a b
                           ->{Services, Remote} ServiceHash a b
  1440. Services.tryCall : ServiceHash a b
                           -> a
                           ->{Services} Either Failure b
  1441. Services.tryCallByName : ServiceName a b
                                 -> a
                                 ->{Services} Either Failure b
  1442. Services.tryResolve : ServiceName a b
                              ->{Services} Either
                                Failure (ServiceHash a b)
  1443. ability Storage
  1444. ability Storage.Batch
  1445. Storage.Batch.awaitRead : Read v ->{Exception, Batch} v
  1446. Storage.Batch.doc : Doc
  1447. Storage.Batch.doc.examples.batchAwaitIdempotent : Doc
  1448. Storage.Batch.doc.examples.batchFailure : Doc
  1449. Storage.Batch.doc.examples.batchForkWrite : Doc
  1450. Storage.Batch.doc.examples.batchOptional : Doc
  1451. Storage.Batch.doc.examples.batchScope : Doc
  1452. Storage.Batch.doc.examples.batchSimple : Doc
  1453. Storage.Batch.doc.examples.batchTransaction : Doc
  1454. Storage.Batch.doc.failures : Doc
  1455. Storage.Batch.doc.semantics : Doc
  1456. Storage.Batch.forkRead : Table k v -> k ->{Batch} Read v
  1457. type Storage.Batch.Read a
  1458. type Storage.Batch.Read.Id
  1459. Storage.Batch.Read.Id.Id : Bytes -> Read.Id
  1460. Storage.Batch.Read.Read : Read.Id
                                  -> Text
                                  -> Any
                                  -> Read a
  1461. Storage.Batch.tryAwaitRead : Read v ->{Batch} Optional v
  1462. Storage.batchRead : Database
                            -> '{Exception, Batch} a
                            ->{Exception, Storage} a
  1463. Storage.catchAbort : '{g, Exception} a
                             ->{g, Exception} Optional a
  1464. Storage.delete : Database
                         -> Table k v
                         -> k
                         ->{Remote} ()
  1465. Storage.delete.tx : Table k v -> k ->{Transaction} ()
  1466. Storage.delete.tx.doc : Doc
  1467. Storage.doc : Doc
  1468. Storage.doc.example : '{Exception,
                              Storage,
                              Remote,
                              Random,
                              Scratch} a
                              -> Either Failure a
  1469. Storage.doc.example.doc : Doc
  1470. Storage.doc.example.test : [Result]
  1471. Storage.doc.exampleDb : Database
  1472. Storage.doc.exampleDb.doc : Doc
  1473. Storage.doc.examples.dateTable : Table LocalDate Json
  1474. Storage.doc.examples.initializeStorage : '{Exception,
                                                 Cloud} ()
  1475. Storage.doc.examples.readWriteInteraction : Database
                                                    -> '{Exception,
                                                    Storage} ()
  1476. Storage.doc.exampleWithDb : (Database
                                    ->{Exception,
                                    Storage,
                                    Remote,
                                    Random,
                                    Scratch} a)
                                    -> Either Failure a
  1477. Storage.doc.exampleWithDb.doc : Doc
  1478. Storage.modifyGet : Database
                            -> Table k t
                            -> k
                            -> t
                            -> (t -> t)
                            ->{Remote} t
  1479. Storage.modifyGet.doc : Doc
  1480. Storage.modifyGet.tx : Table k v
                               -> k
                               -> v
                               -> (v ->{g} v)
                               ->{g, Transaction} v
  1481. Storage.modifyGet.tx.doc : Doc
  1482. Storage.read : Database -> Table k v -> k ->{Remote} v
  1483. Storage.read.doc : Doc
  1484. Storage.read.tx : Table k v
                          -> k
                          ->{Transaction, Exception} v
  1485. Storage.readOr.tx : Table k v
                            -> v
                            -> k
                            ->{Transaction} v
  1486. Storage.readOr.tx.doc : Doc
  1487. Storage.run.local : '{g, Exception, Storage} a
                            ->{g, Exception, Random} a
  1488. Storage.run.local.doc : Doc
  1489. Storage.run.local.implTransaction : data.Map
                                              (Text, Any) Any
                                            -> '{Transaction,
                                            Exception,
                                            Random,
                                            Batch} a
                                            ->{Exception,
                                            Random} ( data.Map
                                              (Text, Any) Any,
                                              a)
  1490. type Storage.Table k v
  1491. Storage.Table.doc : Doc
  1492. Storage.Table.name : Table k v -> Text
  1493. Storage.Table.Table : Text -> Table k v
  1494. Storage.transact : Database
                           -> '{Transaction,
                           Exception,
                           Random,
                           Batch} a
                           ->{Exception, Storage} a
  1495. Storage.transact.random.deprecated : Database
                                             -> '{Transaction,
                                             Exception,
                                             Random} a
                                             ->{Exception,
                                             Storage,
                                             Random} a
  1496. Storage.transact.random.deprecated.doc : Doc
  1497. Storage.transact.stream : Database
                                  -> '{Transaction,
                                  Exception,
                                  Random,
                                  Batch,
                                  Stream a} r
                                  -> '{Remote, Stream a} r
  1498. Storage.transact.stream.doc : Doc
  1499. ability Storage.Transaction
  1500. Storage.Transaction.abort : '{Exception} r
  1501. Storage.Transaction.abort.doc : Doc
  1502. type Storage.Transaction.AbortTransaction
  1503. Storage.Transaction.abortWith : Text
                                        -> a
                                        ->{Exception} r
  1504. Storage.Transaction.abortWith.doc : Doc
  1505. Storage.Transaction.delete.tx : Table k v
                                        -> k
                                        ->{Transaction} ()
  1506. Storage.Transaction.read : Table k v
                                   -> k
                                   ->{Transaction, Exception} v
  1507. Storage.Transaction.read.doc : Doc
  1508. Storage.Transaction.tryRead.tx : Table k v
                                         -> k
                                         ->{Transaction} Optional
                                           v
  1509. Storage.Transaction.write.tx : Table k v
                                       -> k
                                       -> v
                                       ->{Transaction} ()
  1510. Storage.tryBatchRead : Database
                               -> '{Exception, Batch} a
                               ->{Storage} Either Failure a
  1511. Storage.tryRead : Database
                          -> Table k v
                          -> k
                          ->{Remote} Optional v
  1512. Storage.tryRead.doc : Doc
  1513. Storage.tryRead.tx : Table k v
                             -> k
                             ->{Transaction} Optional v
  1514. Storage.tryRead.tx.doc : Doc
  1515. Storage.tryTransact : Database
                              -> '{Transaction,
                              Exception,
                              Random,
                              Batch} a
                              ->{Storage} Either Failure a
  1516. Storage.write : Database
                        -> Table k v
                        -> k
                        -> v
                        ->{Remote} ()
  1517. Storage.write.doc : Doc
  1518. up.base.crypto.blake2b_256 : a -> Bytes
  1519. up.base.crypto.blake2b_256.doc : Doc
  1520. up.base.data.List.parMap : (a ->{IO} b)
                                   -> [a]
                                   ->{IO} [b]
  1521. up.base.IO.concurrent.runForked : '{IO} a
                                          ->{IO} concurrent.Promise
                                            a
  1522. up.base.IO.randomNat : '{IO} Nat
  1523. up.base.Nat.floorPowerOf2 : Nat -> Nat
  1524. up.base.Nat.floorPowerOf2.tests : [Result]
  1525. up.base.Ordering.product : (a ->{g3} a ->{g2} Ordering)
                                   -> (b
                                   ->{g1} b
                                   ->{g} Ordering)
                                   -> (a, b)
                                   -> (a, b)
                                   ->{g3, g2, g1, g} Ordering
  1526. up.base.Ordering.product.tests : [Result]
  1527. up.base.Pattern.captureAs : a -> Pattern a -> Pattern a
  1528. up.base.Random.rng.io : '{IO, Random} (∀ a g.
                                  '{g, Random} a ->{g, IO} a)
  1529. up.base.Random.rng.mix : RNG -> RNG -> RNG
  1530. up.base.Random.rng.mix.tests.bytes : '{IO} [Result]
  1531. up.base.Random.rng.mix.tests.nat : '{IO} [Result]
  1532. up.base.Random.rng.scope : '{Random, Scope s} (∀ a g.
                                     '{g, Random} a
                                     ->{g, Scope s} a)
  1533. up.concurrent.Map.foldLeft : (a -> b ->{g} a)
                                     -> a
                                     -> systemfw_concurrent_2_2_0.Map
                                       k b
                                     ->{g, IO} a
  1534. up.http.HttpRequest.asCurl : HttpRequest
                                     ->{Exception} Text
  1535. up.json.Decoder.instant : '{Decoder} Instant
  1536. up.json.Decoder.instant.doc : Doc
  1537. up.json.Decoder.uri : '{Decoder} URI
  1538. up.json.Decoder.uri.doc : Doc
  1539. type UserInfo
  1540. UserInfo.avatarUrl : UserInfo -> URI
  1541. UserInfo.avatarUrl.modify : (URI ->{g} URI)
                                    -> UserInfo
                                    ->{g} UserInfo
  1542. UserInfo.avatarUrl.set : URI -> UserInfo -> UserInfo
  1543. UserInfo.doc : Doc
  1544. UserInfo.email : UserInfo -> Text
  1545. UserInfo.email.modify : (Text ->{g} Text)
                                -> UserInfo
                                ->{g} UserInfo
  1546. UserInfo.email.set : Text -> UserInfo -> UserInfo
  1547. UserInfo.fromJson : '{Decoder} UserInfo
  1548. UserInfo.fromJson.doc : Doc
  1549. UserInfo.handl : UserInfo -> Text
  1550. UserInfo.handl.modify : (Text ->{g} Text)
                                -> UserInfo
                                ->{g} UserInfo
  1551. UserInfo.handl.set : Text -> UserInfo -> UserInfo
  1552. UserInfo.id : UserInfo -> Text
  1553. UserInfo.id.modify : (Text ->{g} Text)
                             -> UserInfo
                             ->{g} UserInfo
  1554. UserInfo.id.set : Text -> UserInfo -> UserInfo
  1555. UserInfo.UserInfo : URI
                            -> Text
                            -> Text
                            -> Text
                            -> UserInfo
  1556. ability websockets.HttpWebSocket
  1557. websockets.HttpWebSocket.doc : Doc
  1558. websockets.HttpWebSocket.tryWebSocket : HttpRequest
                                                ->{websockets.HttpWebSocket} Either
                                                  Failure
                                                  websockets.WebSocket
  1559. websockets.HttpWebSocket.webSocket : HttpRequest
                                             ->{Remote,
                                             websockets.HttpWebSocket} websockets.WebSocket
  1560. websockets.HttpWebSocket.webSocket.doc : Doc
  1561. type websockets.WebSocket
  1562. websockets.WebSocket.doc : Doc
  1563. type websockets.WebSocket.Id
  1564. websockets.WebSocket.Id.Id : Bytes -> WebSocket.Id
  1565. websockets.WebSocket.WebSocket : Location.Id
                                         -> WebSocket.Id
                                         -> websockets.WebSocket
  1566. ability websockets.WebSockets
  1567. websockets.WebSockets.close : websockets.WebSocket
                                      ->{Exception, WebSockets} ()
  1568. websockets.WebSockets.receive : websockets.WebSocket
                                        ->{Exception,
                                        WebSockets} Message
  1569. websockets.WebSockets.send : websockets.WebSocket
                                     -> Message
                                     ->{Exception, WebSockets} ()
  1570. websockets.WebSockets.tryClose : websockets.WebSocket
                                         ->{WebSockets} Either
                                           Failure ()
  1571. websockets.WebSockets.tryReceive : websockets.WebSocket
                                           ->{WebSockets} Either
                                             Failure Message
  1572. websockets.WebSockets.trySend : websockets.WebSocket
                                        -> Message
                                        ->{WebSockets} Either
                                          Failure ()
```

## Code examples

``` ucm
@unison/cloud/main> edit 1-1600
```

