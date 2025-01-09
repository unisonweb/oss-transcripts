# Auth

This project provides an ability and interpreter for easily adding OAuth2 authentication to your application.

## Library contents list

``` ucm
@unison/auth/main> pull.without-history @unison/auth/releases/1.0.0

  Downloaded 44513 entities.

  ✅

  Successfully updated @unison/auth/main from
  @unison/auth/releases/1.0.0.

@unison/auth/main> find

  1.   ability abilities.Auth session
  2.   abilities.Auth.doc : Doc
  3.   abilities.Auth.getSession : {Auth session} (Optional
                                     session)
  4.   abilities.Auth.requireSession : {Auth session} session
  5.   type anonymous.Config
  6.   anonymous.Config.Config : HMACKey
                                 -> Boolean
                                 -> anonymous.Config
  7.   anonymous.Config.doc : Doc
  8.   anonymous.Config.hmacKey : anonymous.Config -> HMACKey
  9.   anonymous.Config.hmacKey.modify : (HMACKey ->{g} HMACKey)
                                         -> anonymous.Config
                                         ->{g} anonymous.Config
  10.  anonymous.Config.hmacKey.set : HMACKey
                                      -> anonymous.Config
                                      -> anonymous.Config
  11.  anonymous.Config.useSecureCookies : anonymous.Config
                                           -> Boolean
  12.  anonymous.Config.useSecureCookies.modify : (Boolean
                                                  ->{g} Boolean)
                                                  -> anonymous.Config
                                                  ->{g} anonymous.Config
  13.  anonymous.Config.useSecureCookies.set : Boolean
                                               -> anonymous.Config
                                               -> anonymous.Config
  14.  anonymous.example.main : '{IO, Exception} ()
  15.  anonymous.handler : anonymous.Config
                           -> '{g, Auth UserId} a
                           ->{g, Route, Exception, Random} a
  16.  anonymous.handler.doc : Doc
  17.  anonymous.README : Doc
  18.  type anonymous.UserId
  19.  anonymous.UserId.bytes : UserId -> Bytes
  20.  anonymous.UserId.UserId : Text -> UserId
  21.  type oauth2.config.AuthConfig g idToken session
  22.  oauth2.config.AuthConfig.AuthConfig : (Path
                                             ->{Route,
                                             Exception} URI)
                                             -> Path
                                             -> Path
                                             -> Path
                                             -> Path
                                             -> Oauth2Client
                                               idToken
                                             -> Optional Text
                                             -> (TokenResponse
                                               idToken
                                             ->{g,
                                             Route,
                                             Exception} session)
                                             -> '{g, Route} Optional
                                               session
                                             -> (session
                                             ->{g, Route} ())
                                             -> (session
                                             ->{g, Route} ())
                                             -> Boolean
                                             -> AuthConfig
                                               g idToken session
  23.  oauth2.config.AuthConfig.doc : Doc
  24.  oauth2.config.AuthConfig.kickoffOAuthLoginPath : AuthConfig
                                                          g
                                                          idToken
                                                          session
                                                        -> Path
  25.  oauth2.config.AuthConfig.kickoffOAuthLoginPath.modify : (Path
                                                               ->{h1} Path)
                                                               -> AuthConfig
                                                                 g
                                                                 idToken
                                                                 session
                                                               ->{h1} AuthConfig
                                                                 {h,
                                                                 g}
                                                                 idToken
                                                                 session
  26.  oauth2.config.AuthConfig.kickoffOAuthLoginPath.set : Path
                                                            -> AuthConfig
                                                              g
                                                              idToken
                                                              session
                                                            -> AuthConfig
                                                              {h,
                                                              g}
                                                              idToken
                                                              session
  27.  oauth2.config.AuthConfig.loginPagePath : AuthConfig
                                                  g
                                                  idToken
                                                  session
                                                -> Path
  28.  oauth2.config.AuthConfig.loginPagePath.modify : (Path
                                                       ->{h1} Path)
                                                       -> AuthConfig
                                                         g
                                                         idToken
                                                         session
                                                       ->{h1} AuthConfig
                                                         {h, g}
                                                         idToken
                                                         session
  29.  oauth2.config.AuthConfig.loginPagePath.set : Path
                                                    -> AuthConfig
                                                      g
                                                      idToken
                                                      session
                                                    -> AuthConfig
                                                      {h, g}
                                                      idToken
                                                      session
  30.  oauth2.config.AuthConfig.logoutPagePath : AuthConfig
                                                   g
                                                   idToken
                                                   session
                                                 -> Path
  31.  oauth2.config.AuthConfig.logoutPagePath.modify : (Path
                                                        ->{h1} Path)
                                                        -> AuthConfig
                                                          g
                                                          idToken
                                                          session
                                                        ->{h1} AuthConfig
                                                          {h, g}
                                                          idToken
                                                          session
  32.  oauth2.config.AuthConfig.logoutPagePath.set : Path
                                                     -> AuthConfig
                                                       g
                                                       idToken
                                                       session
                                                     -> AuthConfig
                                                       {h, g}
                                                       idToken
                                                       session
  33.  oauth2.config.AuthConfig.oauth2Client : AuthConfig
                                                 g
                                                 idToken
                                                 session
                                               -> Oauth2Client
                                                 idToken
  34.  oauth2.config.AuthConfig.oauth2Client.modify : (Oauth2Client
                                                        idToken
                                                      ->{h1} Oauth2Client
                                                        idToken)
                                                      -> AuthConfig
                                                        g
                                                        idToken
                                                        session
                                                      ->{h1} AuthConfig
                                                        {h, g}
                                                        idToken
                                                        session
  35.  oauth2.config.AuthConfig.oauth2Client.set : Oauth2Client
                                                     idToken
                                                   -> AuthConfig
                                                     g
                                                     idToken
                                                     session
                                                   -> AuthConfig
                                                     {h, g}
                                                     idToken
                                                     session
  36.  oauth2.config.AuthConfig.oauth2Scopes : AuthConfig
                                                 g
                                                 idToken
                                                 session
                                               -> Optional Text
  37.  oauth2.config.AuthConfig.oauth2Scopes.modify : (Optional
                                                        Text
                                                      ->{h1} Optional
                                                        Text)
                                                      -> AuthConfig
                                                        g
                                                        idToken
                                                        session
                                                      ->{h1} AuthConfig
                                                        {h, g}
                                                        idToken
                                                        session
  38.  oauth2.config.AuthConfig.oauth2Scopes.set : Optional Text
                                                   -> AuthConfig
                                                     g
                                                     idToken
                                                     session
                                                   -> AuthConfig
                                                     {h, g}
                                                     idToken
                                                     session
  39.  oauth2.config.AuthConfig.redirectHandlerPath : AuthConfig
                                                        g
                                                        idToken
                                                        session
                                                      -> Path
  40.  oauth2.config.AuthConfig.redirectHandlerPath.modify : (Path
                                                             ->{h1} Path)
                                                             -> AuthConfig
                                                               g
                                                               idToken
                                                               session
                                                             ->{h1} AuthConfig
                                                               {h,
                                                               g}
                                                               idToken
                                                               session
  41.  oauth2.config.AuthConfig.redirectHandlerPath.set : Path
                                                          -> AuthConfig
                                                            g
                                                            idToken
                                                            session
                                                          -> AuthConfig
                                                            {h,
                                                            g}
                                                            idToken
                                                            session
  42.  oauth2.config.AuthConfig.removeSession : AuthConfig
                                                  g
                                                  idToken
                                                  session
                                                -> session
                                                ->{g, Route} ()
  43.  oauth2.config.AuthConfig.removeSession.modify : ((session
                                                       ->{g,
                                                       Route} ())
                                                       ->{h1} session
                                                       ->{g,
                                                       h,
                                                       Route} ())
                                                       -> AuthConfig
                                                         g
                                                         idToken
                                                         session
                                                       ->{h1} AuthConfig
                                                         {h, g}
                                                         idToken
                                                         session
  44.  oauth2.config.AuthConfig.removeSession.set : (session
                                                    ->{g,
                                                    h,
                                                    Route} ())
                                                    -> AuthConfig
                                                      g
                                                      idToken
                                                      session
                                                    -> AuthConfig
                                                      {h, g}
                                                      idToken
                                                      session
  45.  oauth2.config.AuthConfig.saveSession : AuthConfig
                                                g
                                                idToken
                                                session
                                              -> session
                                              ->{g, Route} ()
  46.  oauth2.config.AuthConfig.saveSession.modify : ((session
                                                     ->{g,
                                                     Route} ())
                                                     ->{h1} session
                                                     ->{g,
                                                     h,
                                                     Route} ())
                                                     -> AuthConfig
                                                       g
                                                       idToken
                                                       session
                                                     ->{h1} AuthConfig
                                                       {h, g}
                                                       idToken
                                                       session
  47.  oauth2.config.AuthConfig.saveSession.set : (session
                                                  ->{g,
                                                  h,
                                                  Route} ())
                                                  -> AuthConfig
                                                    g
                                                    idToken
                                                    session
                                                  -> AuthConfig
                                                    {h, g}
                                                    idToken
                                                    session
  48.  oauth2.config.AuthConfig.successCallback : AuthConfig
                                                    g
                                                    idToken
                                                    session
                                                  -> TokenResponse
                                                    idToken
                                                  ->{g,
                                                  Route,
                                                  Exception} session
  49.  oauth2.config.AuthConfig.successCallback.modify : ((TokenResponse
                                                           idToken
                                                         ->{g,
                                                         Route,
                                                         Exception} t)
                                                         ->{h1} TokenResponse
                                                           idToken
                                                         ->{g,
                                                         h,
                                                         Route,
                                                         Exception} t)
                                                         -> AuthConfig
                                                           g
                                                           idToken
                                                           t
                                                         ->{h1} AuthConfig
                                                           {h,
                                                           g}
                                                           idToken
                                                           t
  50.  oauth2.config.AuthConfig.successCallback.set : (TokenResponse
                                                        idToken
                                                      ->{g,
                                                      h,
                                                      Route,
                                                      Exception} t)
                                                      -> AuthConfig
                                                        g
                                                        idToken
                                                        t
                                                      -> AuthConfig
                                                        {h, g}
                                                        idToken
                                                        t
  51.  oauth2.config.AuthConfig.uriFromPath : AuthConfig
                                                g
                                                idToken
                                                session
                                              -> Path
                                              ->{Route,
                                              Exception} URI
  52.  oauth2.config.AuthConfig.uriFromPath.modify : ((Path
                                                     ->{Route,
                                                     Exception} URI)
                                                     ->{h1} Path
                                                     ->{Route,
                                                     Exception} URI)
                                                     -> AuthConfig
                                                       g
                                                       idToken
                                                       session
                                                     ->{h1} AuthConfig
                                                       {h, g}
                                                       idToken
                                                       session
  53.  oauth2.config.AuthConfig.uriFromPath.set : (Path
                                                  ->{Route,
                                                  Exception} URI)
                                                  -> AuthConfig
                                                    g
                                                    idToken
                                                    session
                                                  -> AuthConfig
                                                    {h, g}
                                                    idToken
                                                    session
  54.  oauth2.config.AuthConfig.useSecureCookies : AuthConfig
                                                     g
                                                     idToken
                                                     session
                                                   -> Boolean
  55.  oauth2.config.AuthConfig.useSecureCookies.modify : (Boolean
                                                          ->{h1} Boolean)
                                                          -> AuthConfig
                                                            g
                                                            idToken
                                                            session
                                                          ->{h1} AuthConfig
                                                            {h,
                                                            g}
                                                            idToken
                                                            session
  56.  oauth2.config.AuthConfig.useSecureCookies.set : Boolean
                                                       -> AuthConfig
                                                         g
                                                         idToken
                                                         session
                                                       -> AuthConfig
                                                         {h, g}
                                                         idToken
                                                         session
  57.  oauth2.config.AuthConfig.validateSession : AuthConfig
                                                    g
                                                    idToken
                                                    session
                                                  -> '{g, Route} Optional
                                                    session
  58.  oauth2.config.AuthConfig.validateSession.modify : ('{g,
                                                         Route} Optional
                                                           session
                                                         ->{h1} '{g,
                                                         h,
                                                         Route} Optional
                                                           session)
                                                         -> AuthConfig
                                                           g
                                                           idToken
                                                           session
                                                         ->{h1} AuthConfig
                                                           {h,
                                                           g}
                                                           idToken
                                                           session
  59.  oauth2.config.AuthConfig.validateSession.set : '{g,
                                                      h,
                                                      Route} Optional
                                                        session
                                                      -> AuthConfig
                                                        g
                                                        idToken
                                                        session
                                                      -> AuthConfig
                                                        {h, g}
                                                        idToken
                                                        session
  60.  oauth2.config.defaultCloud : HMACKey
                                    -> Oauth2Client idToken
                                    -> Optional Text
                                    -> (TokenResponse idToken
                                    ->{g, Route, Exception} session)
                                    -> '{g, Decoder} session
                                    -> (session ->{g} Json)
                                    -> Boolean
                                    -> AuthConfig
                                      {Exception, g}
                                      idToken
                                      session
  61.  oauth2.config.defaultWeb : HMACKey
                                  -> URI
                                  -> Oauth2Client idToken
                                  -> Optional Text
                                  -> (TokenResponse idToken
                                  ->{g, Route, Exception} session)
                                  -> '{g, Decoder} session
                                  -> (session ->{g} Json)
                                  -> Boolean
                                  -> AuthConfig
                                    {Exception, g}
                                    idToken
                                    session
  62.  oauth2.example.appRoutes : '{Route, Auth UserId} ()
  63.  oauth2.example.httpServer.doc : Doc
  64.  oauth2.example.main : '{IO, Exception} ()
  65.  oauth2.handler : AuthConfig g idToken session
                        -> '{h, Route, Auth session} ()
                        ->{g, h, Route, Exception, Http, Random} ()
  66.  oauth2.handler.doc : Doc
  67.  type oauth2.internal.Base64UrlUnpadded format
  68.  oauth2.internal.Base64UrlUnpadded.Base64UrlUnpadded : format
                                                             -> Base64UrlUnpadded
                                                               format
  69.  oauth2.internal.Base64UrlUnpadded.decodeText : Base64UrlUnpadded
                                                        Text
                                                      ->{Exception} Optional
                                                        Text
  70.  oauth2.internal.Base64UrlUnpadded.encodeText : Text
                                                      ->{Exception} Base64UrlUnpadded
                                                        Text
  71.  oauth2.internal.decodeState : Base64UrlUnpadded Text
                                     ->{Exception} Optional
                                       internal.State
  72.  oauth2.internal.encodeState : internal.State
                                     ->{Exception} Base64UrlUnpadded
                                       Text
  73.  oauth2.internal.newState : Optional URI
                                  ->{Random} internal.State
  74.  oauth2.internal.parseAuthParams : '{Route, Throw Text} ( Text,
                                           Text)
  75.  oauth2.internal.parseAuthParams.doc : Doc
  76.  oauth2.internal.pathToURIOnCloud : Path
                                          ->{Route, Exception} URI
  77.  type oauth2.internal.State
  78.  oauth2.internal.State.continueTo : internal.State
                                          -> Optional URI
  79.  oauth2.internal.State.continueTo.modify : (Optional URI
                                                 ->{g} Optional
                                                   URI)
                                                 -> internal.State
                                                 ->{g} internal.State
  80.  oauth2.internal.State.continueTo.set : Optional URI
                                              -> internal.State
                                              -> internal.State
  81.  oauth2.internal.State.State : Optional URI
                                     -> Text
                                     -> internal.State
  82.  oauth2.internal.State.stateId : internal.State -> Text
  83.  oauth2.internal.State.stateId.modify : (Text ->{g} Text)
                                              -> internal.State
                                              ->{g} internal.State
  84.  oauth2.internal.State.stateId.set : Text
                                           -> internal.State
                                           -> internal.State
  85.  oauth2.internal.State.uuid : internal.State -> Text
  86.  oauth2.README : Doc
  87.  oauth2.requireSessionOrSkip : '{Route, Auth session} session
  88.  oauth2.requireSessionOrSkip.doc : Doc
  89.  type oauth2.routes.internal.BadRequest
  90.  oauth2.routes.internal.BadRequest.BadRequest : Text
                                                      -> internal.BadRequest
  91.  oauth2.routes.internal.BadRequest.toBytes : internal.BadRequest
                                                   -> Bytes
  92.  oauth2.routes.internal.kickoffOAuthRoute : Text
                                                  -> Boolean
                                                  -> Optional
                                                    URI
                                                  -> oauth2_main.Scope
                                                  -> URI
                                                  -> Oauth2Client
                                                    t
                                                  ->{Route,
                                                  Exception,
                                                  Random} ()
  93.  oauth2.routes.internal.kickoffOAuthRoute.doc : Doc
  94.  oauth2.routes.internal.redirectHandlerRoute : Text
                                                     -> AuthConfig
                                                       g
                                                       idToken
                                                       session
                                                     ->{g,
                                                     Route,
                                                     Exception,
                                                     Http} Either
                                                       Text ()
  95.  oauth2.routes.internal.redirectHandlerRoute.doc : Doc
  96.  README : Doc
  97.  ReleaseNotes : Doc
  98.  up.oauth2.requestAccessToken : AuthorizationCode
                                      -> URI
                                      -> Oauth2Client a
                                      ->{Exception, Http} TokenResponse
                                        a
  99.  utils.handleBadRequest : '{g, Throw internal.BadRequest} ()
                                -> '{g, Route} ()
  100. type utils.hmac.HMACKey
  101. utils.hmac.HMACKey.bytes : HMACKey -> Bytes
  102. utils.hmac.HMACKey.HMACKey : Bytes -> HMACKey
  103. utils.hmac.signBundle : HMACKey
                               -> Bytes
                               ->{Exception} Text
  104. utils.hmac.verify : HMACKey -> Bytes -> Bytes -> Boolean
  105. utils.hmac.verifyBundle : HMACKey
                                 -> Text
                                 -> Optional Bytes
  106. utils.http.redirect : URI ->{Route} ()
  107. utils.pathToUriParser : Path -> Parser a a
```
