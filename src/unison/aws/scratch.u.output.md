# Aws

Provides a high-level interface to the Amazon Web Services (AWS) api. Currently this SDK supports Simple Storage Service (S3), Lambda, and SQS.

## Library contents list

``` ucm
@unison/aws/main> pull.without-history @unison/aws/releases/4.2.1

  Downloaded 34914 entities.

  ✅

  Successfully updated @unison/aws/main from
  @unison/aws/releases/4.2.1.

@unison/aws/main> find

  1.   addAwsHeaders : Config
                       -> Instant
                       -> HttpRequest
                       ->{Exception} HttpRequest
  2.   addAwsHeaders.doc : Doc
  3.   auth.addAuthorizationHeader : Credentials
                                     -> Instant
                                     -> Region
                                     -> Service
                                     -> HttpRequest
                                     ->{Exception} HttpRequest
  4.   auth.addAuthorizationHeader.doc : Doc
  5.   auth.addSecurityTokenHeader : Credentials
                                     -> HttpRequest
                                     -> HttpRequest
  6.   auth.addSecurityTokenHeader.doc : Doc
  7.   type auth.CanonicalHeaders
  8.   auth.canonicalHeaders : Headers -> CanonicalHeaders
  9.   auth.CanonicalHeaders.CanonicalHeaders : Text
                                                -> CanonicalHeaders
  10.  auth.canonicalHeaders.doc : Doc
  11.  auth.CanonicalHeaders.doc : Doc
  12.  auth.CanonicalHeaders.toText : CanonicalHeaders -> Text
  13.  type auth.CanonicalQuery
  14.  auth.canonicalQuery : Query ->{Exception} CanonicalQuery
  15.  auth.CanonicalQuery.CanonicalQuery : Text
                                            -> CanonicalQuery
  16.  auth.canonicalQuery.doc : Doc
  17.  auth.CanonicalQuery.doc : Doc
  18.  auth.canonicalQuery.tests : [Result]
  19.  auth.CanonicalQuery.toText : CanonicalQuery -> Text
  20.  auth.CanonicalQuery.toText.doc : Doc
  21.  type auth.CanonicalRequest
  22.  auth.canonicalRequest : HttpRequest
                               ->{Exception} CanonicalRequest
  23.  auth.CanonicalRequest.CanonicalRequest : Text
                                                -> CanonicalRequest
  24.  auth.CanonicalRequest.doc : Doc
  25.  auth.canonicalRequest.doc : Doc
  26.  auth.CanonicalRequest.toText : CanonicalRequest -> Text
  27.  type auth.CredentialScope
  28.  auth.CredentialScope.CredentialScope : LocalDate
                                              -> Region
                                              -> Service
                                              -> Text
                                              -> CredentialScope
  29.  auth.CredentialScope.date : CredentialScope -> LocalDate
  30.  auth.CredentialScope.date.modify : (LocalDate
                                          ->{g} LocalDate)
                                          -> CredentialScope
                                          ->{g} CredentialScope
  31.  auth.CredentialScope.date.set : LocalDate
                                       -> CredentialScope
                                       -> CredentialScope
  32.  auth.CredentialScope.doc : Doc
  33.  auth.CredentialScope.new : LocalDate
                                  -> Region
                                  -> Service
                                  -> CredentialScope
  34.  auth.CredentialScope.new.doc : Doc
  35.  auth.CredentialScope.region : CredentialScope -> Region
  36.  auth.CredentialScope.region.modify : (Region
                                            ->{g} Region)
                                            -> CredentialScope
                                            ->{g} CredentialScope
  37.  auth.CredentialScope.region.set : Region
                                         -> CredentialScope
                                         -> CredentialScope
  38.  auth.CredentialScope.service : CredentialScope -> Service
  39.  auth.CredentialScope.service.modify : (Service
                                             ->{g} Service)
                                             -> CredentialScope
                                             ->{g} CredentialScope
  40.  auth.CredentialScope.service.set : Service
                                          -> CredentialScope
                                          -> CredentialScope
  41.  auth.CredentialScope.terminationString : CredentialScope
                                                -> Text
  42.  auth.CredentialScope.terminationString.modify : (Text
                                                       ->{g} Text)
                                                       -> CredentialScope
                                                       ->{g} CredentialScope
  43.  auth.CredentialScope.terminationString.set : Text
                                                    -> CredentialScope
                                                    -> CredentialScope
  44.  auth.CredentialScope.toText : CredentialScope -> Text
  45.  auth.CredentialScope.toText.doc : Doc
  46.  auth.hashCanonicalRequest : CanonicalRequest -> Text
  47.  auth.hashCanonicalRequest.doc : Doc
  48.  auth.hashPayload : Body -> Text
  49.  auth.hashPayload.doc : Doc
  50.  auth.sign : Credentials
                   -> CredentialScope
                   -> StringToSign
                   -> auth.Signature
  51.  auth.sign.doc : Doc
  52.  type auth.Signature
  53.  auth.Signature.doc : Doc
  54.  auth.Signature.Signature : Text -> auth.Signature
  55.  auth.Signature.toText : auth.Signature -> Text
  56.  auth.Signature.toText.doc : Doc
  57.  type auth.SignedHeaders
  58.  auth.signedHeaders : Headers -> SignedHeaders
  59.  auth.signedHeaders.doc : Doc
  60.  auth.SignedHeaders.doc : Doc
  61.  auth.SignedHeaders.SignedHeaders : Text -> SignedHeaders
  62.  auth.SignedHeaders.toText : SignedHeaders -> Text
  63.  auth.SignedHeaders.toText.doc : Doc
  64.  type auth.StringToSign
  65.  auth.stringToSign : Instant
                           -> Region
                           -> Service
                           -> CanonicalRequest
                           -> StringToSign
  66.  auth.stringToSign.doc : Doc
  67.  auth.StringToSign.doc : Doc
  68.  auth.StringToSign.StringToSign : Text -> StringToSign
  69.  auth.StringToSign.toText : StringToSign -> Text
  70.  auth.uriEncode : Text -> Text
  71.  auth.uriEncode.doc : Doc
  72.  auth.uriEncode.tests : [Result]
  73.  ability AWSEnv
  74.  AWSEnv.doc : Doc
  75.  AWSEnv.handler : Region
                        -> Credentials
                        -> Request AWSEnv a
                        ->{IO, Exception} a
  76.  AWSEnv.handler.fromEnv : '{IO, Exception} (Request
                                  AWSEnv a
                                ->{IO, Exception} a)
  77.  AWSEnv.provide.fromEnv : '{g, AWSEnv} r
                                ->{g, IO, Exception} r
  78.  AWSEnv.region : {AWSEnv} Text
  79.  AWSEnv.sign : Service
                     -> HttpRequest
                     ->{AWSEnv} HttpRequest
  80.  type AWSError
  81.  AWSError.AccessDenied : AWSError
  82.  AWSError.fromText : Text -> AWSError
  83.  AWSError.InvalidArgument : AWSError
  84.  AWSError.InvalidDigest : AWSError
  85.  AWSError.MalformedXML : AWSError
  86.  AWSError.SignatureDoesNotMatch : AWSError
  87.  AWSError.UnknownError : Text -> AWSError
  88.  type Config
  89.  Config.Config : HostName
                       -> Optional Port
                       -> Region
                       -> Service
                       -> Boolean
                       -> Credentials
                       -> Config
  90.  Config.credentials : Config -> Credentials
  91.  Config.credentials.modify : (Credentials
                                   ->{g} Credentials)
                                   -> Config
                                   ->{g} Config
  92.  Config.credentials.set : Credentials -> Config -> Config
  93.  Config.hostName : Config -> HostName
  94.  Config.hostName.modify : (HostName ->{g} HostName)
                                -> Config
                                ->{g} Config
  95.  Config.hostName.set : HostName -> Config -> Config
  96.  Config.isHttps : Config -> Boolean
  97.  Config.isHttps.modify : (Boolean ->{g} Boolean)
                               -> Config
                               ->{g} Config
  98.  Config.isHttps.set : Boolean -> Config -> Config
  99.  Config.port : Config -> Optional Port
  100. Config.port.modify : (Optional Port ->{g} Optional Port)
                            -> Config
                            ->{g} Config
  101. Config.port.set : Optional Port -> Config -> Config
  102. Config.region : Config -> Region
  103. Config.region.modify : (Region ->{g} Region)
                              -> Config
                              ->{g} Config
  104. Config.region.set : Region -> Config -> Config
  105. Config.scheme : Config -> Scheme
  106. Config.service : Config -> Service
  107. Config.service.modify : (Service ->{g} Service)
                               -> Config
                               ->{g} Config
  108. Config.service.set : Service -> Config -> Config
  109. type Credentials
  110. Credentials.accessKey : Credentials -> Text
  111. Credentials.accessKey.modify : (Text ->{g} Text)
                                      -> Credentials
                                      ->{g} Credentials
  112. Credentials.accessKey.set : Text
                                   -> Credentials
                                   -> Credentials
  113. Credentials.anonymous : Credentials
  114. Credentials.anonymous.doc : Doc
  115. Credentials.Credentials : Text
                                 -> Text
                                 -> Optional Text
                                 -> Credentials
  116. Credentials.defaultCredentials : '{IO, Exception} Credentials
  117. Credentials.defaultCredentials.doc : Doc
  118. Credentials.doc : Doc
  119. Credentials.fromCredentialsFile : FilePath
                                         -> Text
                                         ->{IO, Exception} Credentials
  120. Credentials.fromCredentialsFile.doc : Doc
  121. Credentials.fromDefaultCredentialsFile : Text
                                                ->{IO,
                                                Exception} Credentials
  122. Credentials.fromDefaultCredentialsFile.doc : Doc
  123. Credentials.fromEnv : '{IO, Exception} Credentials
  124. Credentials.fromEnv.doc : Doc
  125. Credentials.isAnonymous : Credentials -> Boolean
  126. Credentials.isAnonymous.doc : Doc
  127. Credentials.longLived : Text -> Text -> Credentials
  128. Credentials.longLived.doc : Doc
  129. Credentials.parse : Text
                           ->{Exception} Map
                             Text (Map Text Text)
  130. Credentials.secretKey : Credentials -> Text
  131. Credentials.secretKey.modify : (Text ->{g} Text)
                                      -> Credentials
                                      ->{g} Credentials
  132. Credentials.secretKey.set : Text
                                   -> Credentials
                                   -> Credentials
  133. Credentials.sessionToken : Credentials -> Optional Text
  134. Credentials.sessionToken.modify : (Optional Text
                                         ->{g} Optional Text)
                                         -> Credentials
                                         ->{g} Credentials
  135. Credentials.sessionToken.set : Optional Text
                                      -> Credentials
                                      -> Credentials
  136. Credentials.tryDefaultCredentials : '{IO} Optional
                                             Credentials
  137. Credentials.tryDefaultCredentials.doc : Doc
  138. Credentials.tryFromCredentialsFile : FilePath
                                            -> Text
                                            ->{IO, Exception} Optional
                                              Credentials
  139. Credentials.tryFromCredentialsFile.doc : Doc
  140. Credentials.tryFromDefaultCredentialsFile : Text
                                                   ->{IO} Optional
                                                     Credentials
  141. Credentials.tryFromDefaultCredentialsFile.doc : Doc
  142. Credentials.tryFromEnv : '{IO} Optional Credentials
  143. Credentials.tryFromEnv.doc : Doc
  144. Credentials.tryParse : Text
                              -> Either
                                IO.Failure
                                (Map Text (Map Text Text))
  145. invalidArgument : Text ->{Exception} a
  146. invalidArgument.doc : Doc
  147. type Key
  148. Key.doc : Doc
  149. Key.Key : Bytes -> Key
  150. Key.toBytes : Key -> Bytes
  151. lambda.defaultConfig : Credentials -> Config
  152. lambda.defaultConfig.doc : Doc
  153. lambda.invokeFunction : FunctionName
                               -> Bytes
                               -> Optional InvocationType
                               -> Optional LogType
                               -> Optional ClientContext
                               -> Optional Qualifier
                               -> Config
                               -> Instant
                               ->{Exception, Http} InvokeLambdaResponse
  154. lambda.invokeFunction.addAwsInvokeLambdaHeaders : Optional
                                                           InvocationType
                                                         -> Optional
                                                           LogType
                                                         -> Optional
                                                           ClientContext
                                                         -> HttpRequest
                                                         ->{Exception} HttpRequest
  155. lambda.invokeFunction.addAwsInvokeLambdaHeaders.doc : Doc
  156. lambda.invokeFunction.doc : Doc
  157. type lambda.types.ClientContext
  158. lambda.types.ClientContext.ClientContext : Text
                                                  -> ClientContext
  159. lambda.types.ClientContext.doc : Doc
  160. lambda.types.ClientContext.encodeBase64 : ClientContext
                                                 ->{Exception} Text
  161. lambda.types.ClientContext.encodeBase64.doc : Doc
  162. type lambda.types.FunctionName
  163. lambda.types.FunctionName.doc : Doc
  164. lambda.types.FunctionName.FunctionName : Text
                                                -> FunctionName
  165. type lambda.types.InvocationType
  166. lambda.types.InvocationType.doc : Doc
  167. lambda.types.InvocationType.DryRun : InvocationType
  168. lambda.types.InvocationType.Event : InvocationType
  169. lambda.types.InvocationType.RequestResponse : InvocationType
  170. lambda.types.InvocationType.toText : InvocationType
                                            -> Text
  171. lambda.types.InvocationType.toText.doc : Doc
  172. type lambda.types.InvokeLambdaResponse
  173. lambda.types.InvokeLambdaResponse.doc : Doc
  174. lambda.types.InvokeLambdaResponse.error : InvokeLambdaResponse
                                                 -> Optional
                                                   Text
  175. lambda.types.InvokeLambdaResponse.error.modify : (Optional
                                                          Text
                                                        ->{g} Optional
                                                          Text)
                                                        -> InvokeLambdaResponse
                                                        ->{g} InvokeLambdaResponse
  176. lambda.types.InvokeLambdaResponse.error.set : Optional
                                                       Text
                                                     -> InvokeLambdaResponse
                                                     -> InvokeLambdaResponse
  177. lambda.types.InvokeLambdaResponse.InvokeLambdaResponse : HttpResponse.Status
                                                                -> Bytes
                                                                -> Optional
                                                                  Text
                                                                -> Optional
                                                                  Text
                                                                -> Optional
                                                                  Text
                                                                -> HttpResponse
                                                                -> InvokeLambdaResponse
  178. lambda.types.InvokeLambdaResponse.log : InvokeLambdaResponse
                                               -> Optional Text
  179. lambda.types.InvokeLambdaResponse.log.modify : (Optional
                                                        Text
                                                      ->{g} Optional
                                                        Text)
                                                      -> InvokeLambdaResponse
                                                      ->{g} InvokeLambdaResponse
  180. lambda.types.InvokeLambdaResponse.log.set : Optional Text
                                                   -> InvokeLambdaResponse
                                                   -> InvokeLambdaResponse
  181. lambda.types.InvokeLambdaResponse.payload : InvokeLambdaResponse
                                                   -> Bytes
  182. lambda.types.InvokeLambdaResponse.payload.modify : (Bytes
                                                          ->{g} Bytes)
                                                          -> InvokeLambdaResponse
                                                          ->{g} InvokeLambdaResponse
  183. lambda.types.InvokeLambdaResponse.payload.set : Bytes
                                                       -> InvokeLambdaResponse
                                                       -> InvokeLambdaResponse
  184. lambda.types.InvokeLambdaResponse.rawResponse : InvokeLambdaResponse
                                                       -> HttpResponse
  185. lambda.types.InvokeLambdaResponse.rawResponse.modify : (HttpResponse
                                                              ->{g} HttpResponse)
                                                              -> InvokeLambdaResponse
                                                              ->{g} InvokeLambdaResponse
  186. lambda.types.InvokeLambdaResponse.rawResponse.set : HttpResponse
                                                           -> InvokeLambdaResponse
                                                           -> InvokeLambdaResponse
  187. lambda.types.InvokeLambdaResponse.status : InvokeLambdaResponse
                                                  -> HttpResponse.Status
  188. lambda.types.InvokeLambdaResponse.status.modify : (HttpResponse.Status
                                                         ->{g} HttpResponse.Status)
                                                         -> InvokeLambdaResponse
                                                         ->{g} InvokeLambdaResponse
  189. lambda.types.InvokeLambdaResponse.status.set : HttpResponse.Status
                                                      -> InvokeLambdaResponse
                                                      -> InvokeLambdaResponse
  190. lambda.types.InvokeLambdaResponse.versionExecuted : InvokeLambdaResponse
                                                           -> Optional
                                                             Text
  191. lambda.types.InvokeLambdaResponse.versionExecuted.modify : (Optional
                                                                    Text
                                                                  ->{g} Optional
                                                                    Text)
                                                                  -> InvokeLambdaResponse
                                                                  ->{g} InvokeLambdaResponse
  192. lambda.types.InvokeLambdaResponse.versionExecuted.set : Optional
                                                                 Text
                                                               -> InvokeLambdaResponse
                                                               -> InvokeLambdaResponse
  193. type lambda.types.LogType
  194. lambda.types.LogType.doc : Doc
  195. lambda.types.LogType.LogNone : LogType
  196. lambda.types.LogType.LogTail : LogType
  197. lambda.types.LogType.toText : LogType -> Text
  198. lambda.types.LogType.toText.doc : Doc
  199. type lambda.types.Qualifier
  200. lambda.types.Qualifier.doc : Doc
  201. lambda.types.Qualifier.Qualifier : Text -> Qualifier
  202. metadata.authors.GerardFinol : Author
  203. metadata.authors.GerardFinol.guid : GUID
  204. metadata.copyrightHolders.GerardFinol : CopyrightHolder
  205. metadata.licenses.GerardFinol2023 : License
  206. README : Doc
  207. type Region
  208. Region.doc : Doc
  209. Region.name : Region -> Text
  210. Region.name.doc : Doc
  211. Region.Region : Text -> Region
  212. ReleaseNotes : Doc
  213. s3.defaultConfig : Credentials -> Config
  214. s3.defaultConfig.doc : Doc
  215. s3.examples.getObjectExample : '{IO, Exception} Optional
                                        Text
  216. s3.examples.headObjectExample : '{IO, Exception} Optional
                                         HeadObjectResponse
  217. s3.examples.listBucketsExample : '{IO, Exception} ListBucketsResponse
  218. s3.examples.putObjectExample : '{IO, Exception} ETag
  219. s3.getObject : BucketName
                      -> types.Key
                      -> Config
                      -> Instant
                      ->{Exception, Http} Optional
                        GetObjectResponse
  220. s3.getObject.doc : Doc
  221. s3.headObject : BucketName
                       -> types.Key
                       -> Config
                       -> Instant
                       ->{Exception, Http} Optional
                         HeadObjectResponse
  222. s3.headObject.doc : Doc
  223. s3.listBuckets : Config
                        -> Instant
                        ->{Exception, Http} ListBucketsResponse
  224. s3.listBuckets.doc : Doc
  225. s3.putObject : BucketName
                      -> types.Key
                      -> Bytes
                      -> Config
                      -> Instant
                      ->{Exception, Http} ETag
  226. s3.putObject.doc : Doc
  227. s3.requireObject : BucketName
                          -> types.Key
                          -> Config
                          -> Instant
                          ->{Exception, Http} GetObjectResponse
  228. s3.requireObject.doc : Doc
  229. type s3.types.Bucket
  230. s3.types.Bucket.Bucket : Text
                                -> Optional Instant
                                -> Bucket
  231. s3.types.Bucket.creationDate : Bucket -> Optional Instant
  232. s3.types.Bucket.creationDate.modify : (Optional Instant
                                             ->{g} Optional
                                               Instant)
                                             -> Bucket
                                             ->{g} Bucket
  233. s3.types.Bucket.creationDate.set : Optional Instant
                                          -> Bucket
                                          -> Bucket
  234. s3.types.Bucket.doc : Doc
  235. s3.types.Bucket.name : Bucket -> Text
  236. s3.types.Bucket.name.modify : (Text ->{g} Text)
                                     -> Bucket
                                     ->{g} Bucket
  237. s3.types.Bucket.name.set : Text -> Bucket -> Bucket
  238. type s3.types.BucketName
  239. s3.types.BucketName.BucketName : Text -> BucketName
  240. s3.types.BucketName.doc : Doc
  241. s3.types.BucketName.toText : BucketName -> Text
  242. s3.types.BucketName.toText.modify : (Text ->{g} Text)
                                           -> BucketName
                                           ->{g} BucketName
  243. s3.types.BucketName.toText.set : Text
                                        -> BucketName
                                        -> BucketName
  244. type s3.types.ETag
  245. s3.types.ETag.doc : Doc
  246. s3.types.ETag.ETag : Text -> ETag
  247. s3.types.ETag.toText : ETag -> Text
  248. s3.types.ETag.toText.modify : (Text ->{g} Text)
                                     -> ETag
                                     ->{g} ETag
  249. s3.types.ETag.toText.set : Text -> ETag -> ETag
  250. type s3.types.GetObjectResponse
  251. s3.types.GetObjectResponse.doc : Doc
  252. s3.types.GetObjectResponse.etag : GetObjectResponse
                                         -> Optional ETag
  253. s3.types.GetObjectResponse.etag.modify : (Optional ETag
                                                ->{g} Optional
                                                  ETag)
                                                -> GetObjectResponse
                                                ->{g} GetObjectResponse
  254. s3.types.GetObjectResponse.etag.set : Optional ETag
                                             -> GetObjectResponse
                                             -> GetObjectResponse
  255. s3.types.GetObjectResponse.GetObjectResponse : Optional
                                                        ETag
                                                      -> Bytes
                                                      -> GetObjectResponse
  256. s3.types.GetObjectResponse.objectBody : GetObjectResponse
                                               -> Bytes
  257. s3.types.GetObjectResponse.objectBody.modify : (Bytes
                                                      ->{g} Bytes)
                                                      -> GetObjectResponse
                                                      ->{g} GetObjectResponse
  258. s3.types.GetObjectResponse.objectBody.set : Bytes
                                                   -> GetObjectResponse
                                                   -> GetObjectResponse
  259. type s3.types.HeadObjectResponse
  260. s3.types.HeadObjectResponse.contentLength : HeadObjectResponse
                                                   -> Nat
  261. s3.types.HeadObjectResponse.contentLength.modify : (Nat
                                                          ->{g} Nat)
                                                          -> HeadObjectResponse
                                                          ->{g} HeadObjectResponse
  262. s3.types.HeadObjectResponse.contentLength.set : Nat
                                                       -> HeadObjectResponse
                                                       -> HeadObjectResponse
  263. s3.types.HeadObjectResponse.contentType : HeadObjectResponse
                                                 -> Text
  264. s3.types.HeadObjectResponse.contentType.modify : (Text
                                                        ->{g} Text)
                                                        -> HeadObjectResponse
                                                        ->{g} HeadObjectResponse
  265. s3.types.HeadObjectResponse.contentType.set : Text
                                                     -> HeadObjectResponse
                                                     -> HeadObjectResponse
  266. s3.types.HeadObjectResponse.doc : Doc
  267. s3.types.HeadObjectResponse.etag : HeadObjectResponse
                                          -> ETag
  268. s3.types.HeadObjectResponse.etag.modify : (ETag
                                                 ->{g} ETag)
                                                 -> HeadObjectResponse
                                                 ->{g} HeadObjectResponse
  269. s3.types.HeadObjectResponse.etag.set : ETag
                                              -> HeadObjectResponse
                                              -> HeadObjectResponse
  270. s3.types.HeadObjectResponse.HeadObjectResponse : ETag
                                                        -> Instant
                                                        -> Nat
                                                        -> Text
                                                        -> Map
                                                          Text
                                                          [Text]
                                                        -> HeadObjectResponse
  271. s3.types.HeadObjectResponse.lastModified : HeadObjectResponse
                                                  -> Instant
  272. s3.types.HeadObjectResponse.lastModified.modify : (Instant
                                                         ->{g} Instant)
                                                         -> HeadObjectResponse
                                                         ->{g} HeadObjectResponse
  273. s3.types.HeadObjectResponse.lastModified.set : Instant
                                                      -> HeadObjectResponse
                                                      -> HeadObjectResponse
  274. s3.types.HeadObjectResponse.rawMetadata : HeadObjectResponse
                                                 -> Map
                                                   Text [Text]
  275. s3.types.HeadObjectResponse.rawMetadata.modify : (Map
                                                          Text
                                                          [Text]
                                                        ->{g} Map
                                                          Text
                                                          [Text])
                                                        -> HeadObjectResponse
                                                        ->{g} HeadObjectResponse
  276. s3.types.HeadObjectResponse.rawMetadata.set : Map
                                                       Text
                                                       [Text]
                                                     -> HeadObjectResponse
                                                     -> HeadObjectResponse
  277. type s3.types.Key
  278. s3.types.Key.Key : Text -> types.Key
  279. s3.types.Key.toPath : types.Key -> Path
  280. s3.types.Key.toText : types.Key -> Text
  281. s3.types.Key.toText.modify : (Text ->{g} Text)
                                    -> types.Key
                                    ->{g} types.Key
  282. s3.types.Key.toText.set : Text -> types.Key -> types.Key
  283. type s3.types.ListBucketsResponse
  284. s3.types.ListBucketsResponse.buckets : ListBucketsResponse
                                              -> [Bucket]
  285. s3.types.ListBucketsResponse.buckets.modify : ([Bucket]
                                                     ->{g} [Bucket])
                                                     -> ListBucketsResponse
                                                     ->{g} ListBucketsResponse
  286. s3.types.ListBucketsResponse.buckets.set : [Bucket]
                                                  -> ListBucketsResponse
                                                  -> ListBucketsResponse
  287. s3.types.ListBucketsResponse.doc : Doc
  288. s3.types.ListBucketsResponse.ListBucketsResponse : Owner
                                                          -> [Bucket]
                                                          -> ListBucketsResponse
  289. s3.types.ListBucketsResponse.owner : ListBucketsResponse
                                            -> Owner
  290. s3.types.ListBucketsResponse.owner.modify : (Owner
                                                   ->{g} Owner)
                                                   -> ListBucketsResponse
                                                   ->{g} ListBucketsResponse
  291. s3.types.ListBucketsResponse.owner.set : Owner
                                                -> ListBucketsResponse
                                                -> ListBucketsResponse
  292. type s3.types.Owner
  293. s3.types.Owner.displayName : Owner -> Text
  294. s3.types.Owner.displayName.modify : (Text ->{g} Text)
                                           -> Owner
                                           ->{g} Owner
  295. s3.types.Owner.displayName.set : Text -> Owner -> Owner
  296. s3.types.Owner.id : Owner -> Text
  297. s3.types.Owner.id.modify : (Text ->{g} Text)
                                  -> Owner
                                  ->{g} Owner
  298. s3.types.Owner.id.set : Text -> Owner -> Owner
  299. s3.types.Owner.Owner : Text -> Text -> Owner
  300. type s3.types.PutObjectResponse
  301. s3.types.PutObjectResponse.etag : PutObjectResponse
                                         -> Optional ETag
  302. s3.types.PutObjectResponse.etag.modify : (Optional ETag
                                                ->{g} Optional
                                                  ETag)
                                                -> PutObjectResponse
                                                ->{g} PutObjectResponse
  303. s3.types.PutObjectResponse.etag.set : Optional ETag
                                             -> PutObjectResponse
                                             -> PutObjectResponse
  304. s3.types.PutObjectResponse.PutObjectResponse : Optional
                                                        ETag
                                                      -> PutObjectResponse
  305. type s3.types.S3Error
  306. s3.types.S3Error.code : S3Error -> Text
  307. s3.types.S3Error.code.modify : (Text ->{g} Text)
                                      -> S3Error
                                      ->{g} S3Error
  308. s3.types.S3Error.code.set : Text -> S3Error -> S3Error
  309. s3.types.S3Error.message : S3Error -> Text
  310. s3.types.S3Error.message.modify : (Text ->{g} Text)
                                         -> S3Error
                                         ->{g} S3Error
  311. s3.types.S3Error.message.set : Text -> S3Error -> S3Error
  312. s3.types.S3Error.requestId : S3Error -> Text
  313. s3.types.S3Error.requestId.modify : (Text ->{g} Text)
                                           -> S3Error
                                           ->{g} S3Error
  314. s3.types.S3Error.requestId.set : Text
                                        -> S3Error
                                        -> S3Error
  315. s3.types.S3Error.resouce : S3Error -> Text
  316. s3.types.S3Error.resouce.modify : (Text ->{g} Text)
                                         -> S3Error
                                         ->{g} S3Error
  317. s3.types.S3Error.resouce.set : Text -> S3Error -> S3Error
  318. s3.types.S3Error.S3Error : Text
                                  -> Text
                                  -> Text
                                  -> Text
                                  -> S3Error
  319. s3.types.S3Error.toFailure : S3Error -> IO.Failure
  320. s3.xml.parseBucket : Soup ->{Exception} Bucket
  321. s3.xml.parseBucketsResult : Text
                                   ->{Exception} ListBucketsResponse
  322. s3.xml.parseOwner : Soup ->{Exception} Owner
  323. type Service
  324. Service.abbreviation : Service -> Text
  325. Service.abbreviation.doc : Doc
  326. Service.doc : Doc
  327. Service.Service : Text -> Service
  328. sqs.send : send.Message
                  ->{IO, AWSEnv, Exception} Either
                    (send.Failure, send.Message) send.Success
  329. sqs.send.doc : Doc
  330. type sqs.send.Failure
  331. sqs.send.Failure.description : send.Failure -> Text
  332. sqs.send.Failure.description.modify : (Text ->{g} Text)
                                             -> send.Failure
                                             ->{g} send.Failure
  333. sqs.send.Failure.description.set : Text
                                          -> send.Failure
                                          -> send.Failure
  334. sqs.send.Failure.errorType : send.Failure -> Text
  335. sqs.send.Failure.errorType.modify : (Text ->{g} Text)
                                           -> send.Failure
                                           ->{g} send.Failure
  336. sqs.send.Failure.errorType.set : Text
                                        -> send.Failure
                                        -> send.Failure
  337. sqs.send.Failure.Failure : Nat
                                  -> Text
                                  -> Text
                                  -> send.Failure
  338. sqs.send.Failure.fromJson : Nat
                                   -> Text
                                   ->{Exception} send.Failure
  339. sqs.send.Failure.status : send.Failure -> Nat
  340. sqs.send.Failure.status.modify : (Nat ->{g} Nat)
                                        -> send.Failure
                                        ->{g} send.Failure
  341. sqs.send.Failure.status.set : Nat
                                     -> send.Failure
                                     -> send.Failure
  342. type sqs.send.Message
  343. type sqs.send.Message.Attribute
  344. sqs.send.Message.Attribute.Binary : Bytes -> Attribute
  345. sqs.send.Message.Attribute.String : Text -> Attribute
  346. sqs.send.Message.Attribute.toJson : Attribute
                                           ->{Exception} Json
  347. sqs.send.Message.attributes : send.Message
                                     -> [(Text, Attribute)]
  348. sqs.send.Message.attributes.modify : ([(Text, Attribute)]
                                            ->{g} [( Text,
                                              Attribute)])
                                            -> send.Message
                                            ->{g} send.Message
  349. sqs.send.Message.attributes.set : [(Text, Attribute)]
                                         -> send.Message
                                         -> send.Message
  350. sqs.send.Message.body : send.Message -> Text
  351. sqs.send.Message.body.modify : (Text ->{g} Text)
                                      -> send.Message
                                      ->{g} send.Message
  352. sqs.send.Message.body.set : Text
                                   -> send.Message
                                   -> send.Message
  353. sqs.send.Message.deduplicationId : send.Message
                                          -> Optional Text
  354. sqs.send.Message.deduplicationId.modify : (Optional Text
                                                 ->{g} Optional
                                                   Text)
                                                 -> send.Message
                                                 ->{g} send.Message
  355. sqs.send.Message.deduplicationId.set : Optional Text
                                              -> send.Message
                                              -> send.Message
  356. sqs.send.Message.delaySeconds : send.Message
                                       -> Optional Nat
  357. sqs.send.Message.delaySeconds.modify : (Optional Nat
                                              ->{g} Optional Nat)
                                              -> send.Message
                                              ->{g} send.Message
  358. sqs.send.Message.delaySeconds.set : Optional Nat
                                           -> send.Message
                                           -> send.Message
  359. sqs.send.Message.doc : Doc
  360. sqs.send.Message.groupId : send.Message -> Optional Text
  361. sqs.send.Message.groupId.modify : (Optional Text
                                         ->{g} Optional Text)
                                         -> send.Message
                                         ->{g} send.Message
  362. sqs.send.Message.groupId.set : Optional Text
                                      -> send.Message
                                      -> send.Message
  363. sqs.send.Message.message : Text -> Text -> send.Message
  364. sqs.send.Message.Message : Text
                                  -> Text
                                  -> [(Text, Attribute)]
                                  -> Optional Nat
                                  -> Optional Text
                                  -> Optional Text
                                  -> [(Text, Attribute)]
                                  -> send.Message
  365. sqs.send.Message.queue : send.Message -> Text
  366. sqs.send.Message.queue.modify : (Text ->{g} Text)
                                       -> send.Message
                                       ->{g} send.Message
  367. sqs.send.Message.queue.set : Text
                                    -> send.Message
                                    -> send.Message
  368. sqs.send.Message.systemAttributes : send.Message
                                           -> [(Text, Attribute)]
  369. sqs.send.Message.systemAttributes.modify : ([( Text,
                                                    Attribute)]
                                                  ->{g} [( Text,
                                                    Attribute)])
                                                  -> send.Message
                                                  ->{g} send.Message
  370. sqs.send.Message.systemAttributes.set : [( Text,
                                                 Attribute)]
                                               -> send.Message
                                               -> send.Message
  371. sqs.send.Message.toJson : send.Message ->{Exception} Text
  372. sqs.send.parseResponse : HttpResponse
                                ->{Exception} Either
                                  send.Failure send.Success
  373. type sqs.send.Success
  374. sqs.send.Success.fromJson : Text
                                   ->{Exception} send.Success
  375. sqs.send.Success.md5 : send.Success -> Text
  376. sqs.send.Success.md5.modify : (Text ->{g} Text)
                                     -> send.Success
                                     ->{g} send.Success
  377. sqs.send.Success.md5.set : Text
                                  -> send.Success
                                  -> send.Success
  378. sqs.send.Success.messageId : send.Success -> Text
  379. sqs.send.Success.messageId.modify : (Text ->{g} Text)
                                           -> send.Success
                                           ->{g} send.Success
  380. sqs.send.Success.messageId.set : Text
                                        -> send.Success
                                        -> send.Success
  381. sqs.send.Success.Success : Text -> Text -> send.Success
  382. sqs.send.test : '{IO, Exception} Either
                         (send.Failure, send.Message)
                         send.Success
  383. up.base.abilities.Abort.toException : Type
                                             -> Text
                                             -> '{e, Abort} a
                                             ->{e, Exception} a
  384. up.base.Bytes.toHex : Bytes -> Text
  385. up.base.Optional.toException : Text
                                      -> Type
                                      -> Optional a
                                      ->{Exception} a
  386. up.base.Optional.toException.doc : Doc
  387. up.base.Pattern.oneOf : List.Nonempty (Pattern a)
                               -> Pattern a
  388. up.base.time.Instant.fromIso8601 : Text
                                          -> Optional Instant
  389. up.base.time.Instant.toBasicISO8601 : Instant -> Text
  390. up.base.time.Instant.toBasicISO8601.doc : Doc
  391. up.base.time.LocalDate.fromBasicISO8601 : Text
                                                 -> Optional
                                                   LocalDate
  392. up.base.time.LocalDate.fromBasicISO8601.doc : Doc
  393. up.base.time.LocalDate.fromIso8601 : Text
                                            -> Optional
                                              LocalDate
  394. up.base.time.LocalDate.toBasicISO8601 : LocalDate -> Text
  395. up.base.time.LocalDate.toBasicISO8601.doc : Doc
  396. up.base.time.LocalDateTime.fromIso8601 : Text
                                                -> Optional
                                                  LocalDateTime
  397. up.base.time.LocalDateTime.toBasicISO8601 : LocalDateTime
                                                   -> Text
  398. up.base.time.LocalDateTime.toBasicISO8601.doc : Doc
  399. up.base.time.LocalTime.fromBasicISO8601 : Text
                                                 -> Optional
                                                   LocalTime
  400. up.base.time.LocalTime.fromBasicISO8601.doc : Doc
  401. up.base.time.LocalTime.fromIso8601 : Text
                                            -> Optional
                                              LocalTime
  402. up.base.time.LocalTime.toBasicISO8601 : LocalTime -> Text
  403. up.base.time.LocalTime.toBasicISO8601.doc : Doc
  404. up.base.time.OffsetDateTime.fromIso8601 : Text
                                                 -> Optional
                                                   OffsetDateTime
  405. up.base.time.OffsetDateTime.toBasicISO8601 : OffsetDateTime
                                                    -> Text
  406. up.base.time.OffsetDateTime.toBasicISO8601.doc : Doc
  407. up.base.time.patterns.iso8601Date : Pattern Text
  408. up.base.time.patterns.iso8601DateTime : Pattern Text
  409. up.base.time.patterns.iso8601LocalDateTime : Pattern Text
  410. up.base.time.patterns.iso8601LocalTime : Pattern Text
  411. up.base.time.patterns.iso8601Time : Pattern Text
  412. up.base.time.patterns.iso8601Timezone : Pattern Text
  413. up.base.time.UTCOffset.fromBasicISO8601 : Text
                                                 -> Optional
                                                   UTCOffset
  414. up.base.time.UTCOffset.fromBasicISO8601.doc : Doc
  415. up.base.time.UTCOffset.fromIso8601 : Text
                                            -> Optional
                                              UTCOffset
  416. up.base.time.UTCOffset.toBasicISO8601 : UTCOffset -> Text
  417. up.base.time.UTCOffset.toBasicISO8601.doc : Doc
  418. up.http.addHeader : Text
                           -> Text
                           -> HttpRequest
                           -> HttpRequest
  419. up.http.addHeader.doc : Doc
  420. up.http.Headers.getDateTime : Text
                                     -> Headers
                                     ->{Exception} [OffsetDateTime]
  421. up.http.Headers.getInstant : Text
                                    -> Headers
                                    ->{Exception} [Instant]
  422. up.http.Headers.HttpDate.parse.localDate : Text
                                                  ->{Abort} LocalDate
  423. up.http.Headers.HttpDate.parse.localDateTime : Text
                                                      ->{Abort} LocalDateTime
  424. up.http.Headers.HttpDate.parse.localTime : Text
                                                  ->{Abort} LocalTime
  425. up.http.Headers.HttpDate.parse.offsetDateTime : Text
                                                       ->{Abort} OffsetDateTime
  426. up.http.Headers.HttpDate.patterns.asctimeFormat : Pattern
                                                           Text
  427. up.http.Headers.HttpDate.patterns.asctimeFormat.doc : Doc
  428. up.http.Headers.HttpDate.patterns.asctimeFormat.test : [Result]
  429. up.http.Headers.HttpDate.patterns.rfc7231Date : Pattern
                                                         Text
  430. up.http.Headers.HttpDate.patterns.rfc7231DateTime : Pattern
                                                             Text
  431. up.http.Headers.HttpDate.patterns.rfc7231DateTime.doc : Doc
  432. up.http.Headers.HttpDate.patterns.rfc7231DateTime.test850 : [Result]
  433. up.http.Headers.HttpDate.patterns.rfc7231DateTime.testIMF : [Result]
  434. up.http.Headers.HttpDate.patterns.rfc7231Time : Pattern
                                                         Text
  435. up.http.Headers.requireHeader : Text
                                       -> Headers
                                       ->{Exception} Text
  436. up.http.Headers.requireHeader.doc : Doc
  437. up.http.setHeader : Text
                           -> [Text]
                           -> HttpRequest
                           -> HttpRequest
  438. up.http.setHeader.doc : Doc
  439. up.xml.XMLError.message : XMLError -> Text
  440. up.xml.XMLError.toException : '{e, Throw XMLError} a
                                     ->{e, Exception} a
  441. up.xml.XMLError.toExceptionWith : e
                                         -> '{g, Throw XMLError} a
                                         ->{g, Exception} a
  442. up.xml.XMLError.toFailure : XMLError -> IO.Failure
  443. up.xml.XMLError.toFailureWith : e
                                       -> XMLError
                                       -> IO.Failure
```

## Code examples

``` ucm
@unison/aws/main> edit 1-5000

  ☝️

  I added 399 definitions to the top of scratch.u

  You can edit them there, then run `update` to replace the
  definitions currently in this namespace.
```
