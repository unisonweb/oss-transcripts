# Cloud start

This project contains sample Unison Cloud applications and stubs for practicing writing Unison Cloud services.

## Library contents list

``` ucm
@unison/cloud-start/main> pull.without-history @unison/cloud-start/releases/8.0.0

  Downloaded 50667 entities.

  ✅

  Successfully updated @unison/cloud-start/main from
  @unison/cloud-start/releases/8.0.0.

@unison/cloud-start/main> find

  1.   examples.authDemo.appRoutes : '{Route,
                                     Auth anonymous.UserId} ()
  2.   examples.authDemo.deploy : '{IO, Exception} ()
  3.   examples.authDemo.server : '{IO, Exception} (HttpRequest
                                  ->{Exception,
                                  Http,
                                  Random,
                                  Log} HttpResponse)
  4.   examples.chat.deploy : '{IO, Exception} URI
  5.   examples.chat.index : HttpResponse
  6.   examples.chat.index.txt : Text
  7.   examples.chat.js : HttpResponse
  8.   examples.chat.js.txt : Text
  9.   type examples.chat.Message
  10.  examples.chat.Message.message : chat.Message -> Text
  11.  examples.chat.Message.Message : Sender
                                       -> Text
                                       -> chat.Message
  12.  examples.chat.Message.message.modify : (Text ->{g} Text)
                                              -> chat.Message
                                              ->{g} chat.Message
  13.  examples.chat.Message.message.set : Text
                                           -> chat.Message
                                           -> chat.Message
  14.  examples.chat.Message.sender : chat.Message -> Sender
  15.  examples.chat.Message.sender.modify : (Sender
                                             ->{g} Sender)
                                             -> chat.Message
                                             ->{g} chat.Message
  16.  examples.chat.Message.sender.set : Sender
                                          -> chat.Message
                                          -> chat.Message
  17.  examples.chat.Message.toText : chat.Message -> Text
  18.  type examples.chat.Room
  19.  examples.chat.Room.Room : Text -> Room
  20.  type examples.chat.RoomState
  21.  examples.chat.RoomState.empty : RoomState
  22.  examples.chat.RoomState.messages : RoomState
                                          -> [chat.Message]
  23.  examples.chat.RoomState.messages.modify : ([chat.Message]
                                                 ->{g} [chat.Message])
                                                 -> RoomState
                                                 ->{g} RoomState
  24.  examples.chat.RoomState.messages.set : [chat.Message]
                                              -> RoomState
                                              -> RoomState
  25.  examples.chat.RoomState.newUser : Cell RoomState
                                         -> Sender
                                         ->{Remote} ()
  26.  examples.chat.RoomState.newUser.doc : Doc
  27.  examples.chat.RoomState.RoomState : Set Sender
                                           -> [chat.Message]
                                           -> RoomState
  28.  examples.chat.RoomState.saveMessage : Cell RoomState
                                             -> chat.Message
                                             ->{Remote} ()
  29.  examples.chat.RoomState.saveMessage.doc : Doc
  30.  examples.chat.RoomState.sendBacklog : Cell RoomState
                                             -> Sender
                                             ->{Remote} ()
  31.  examples.chat.RoomState.sendBacklog.doc : Doc
  32.  examples.chat.RoomState.senders : RoomState -> Set Sender
  33.  examples.chat.RoomState.senders.modify : (Set Sender
                                                ->{g} Set Sender)
                                                -> RoomState
                                                ->{g} RoomState
  34.  examples.chat.RoomState.senders.set : Set Sender
                                             -> RoomState
                                             -> RoomState
  35.  examples.chat.RoomState.sendMessage : Cell RoomState
                                             -> Text
                                             -> Sender
                                             ->{Remote} ()
  36.  examples.chat.RoomState.sendMessage.doc : Doc
  37.  examples.chat.RoomState.userLeft : Cell RoomState
                                          -> Sender
                                          ->{Remote} ()
  38.  examples.chat.RoomState.userLeft.doc : Doc
  39.  type examples.chat.Sender
  40.  type examples.chat.Sender.Id
  41.  examples.chat.Sender.id : Sender -> Sender.Id
  42.  examples.chat.Sender.Id.Id : Bytes -> Sender.Id
  43.  examples.chat.Sender.id.modify : (Sender.Id
                                        ->{g} Sender.Id)
                                        -> Sender
                                        ->{g} Sender
  44.  examples.chat.Sender.Id.random : '{Random} Sender.Id
  45.  examples.chat.Sender.id.set : Sender.Id
                                     -> Sender
                                     -> Sender
  46.  examples.chat.Sender.Id.toText : Sender.Id -> Text
  47.  examples.chat.Sender.name : Sender -> Text
  48.  examples.chat.Sender.name.modify : (Text ->{g} Text)
                                          -> Sender
                                          ->{g} Sender
  49.  examples.chat.Sender.name.set : Text -> Sender -> Sender
  50.  examples.chat.Sender.Sender : Sender.Id
                                     -> Text
                                     -> unison_cloud_19_0_0.websockets.WebSocket
                                     -> Sender
  51.  examples.chat.Sender.socket : Sender
                                     -> unison_cloud_19_0_0.websockets.WebSocket
  52.  examples.chat.Sender.socket.modify : (unison_cloud_19_0_0.websockets.WebSocket
                                            ->{g} unison_cloud_19_0_0.websockets.WebSocket)
                                            -> Sender
                                            ->{g} Sender
  53.  examples.chat.Sender.socket.set : unison_cloud_19_0_0.websockets.WebSocket
                                         -> Sender
                                         -> Sender
  54.  examples.chat.Sender.toText : Sender -> Text
  55.  examples.chat.style : HttpResponse
  56.  examples.chat.style.txt : Text
  57.  examples.counter.deploy : '{IO, Exception} URI
  58.  examples.counter.deploy.doc : Doc
  59.  examples.counter.logic : Cell Nat
                                -> HttpRequest
                                ->{Exception, Remote, Log} HttpResponse
  60.  examples.counter.logic.doc : Doc
  61.  examples.helloWorld.deploy : '{IO, Exception} ()
  62.  examples.helloWorld.logic : HttpRequest
                                   ->{Exception, Log} HttpResponse
  63.  examples.jokeDaemon.daemon : Cell Text
                                    -> '{Exception,
                                    Http,
                                    Remote} r
  64.  examples.jokeDaemon.daemon.doc : Doc
  65.  examples.jokeDaemon.deploy : '{IO, Exception} URI
  66.  examples.jokeDaemon.deploy.doc : Doc
  67.  examples.jokeDaemon.fetchJoke : '{Exception, Http} Text
  68.  examples.jokeDaemon.fetchJoke.doc : Doc
  69.  type examples.jokeDaemon.Joke
  70.  examples.jokeDaemon.Joke.fromJson : '{Exception, Decoder} Joke
  71.  examples.jokeDaemon.Joke.Single : Text -> Joke
  72.  examples.jokeDaemon.Joke.toText : Joke -> Text
  73.  examples.jokeDaemon.Joke.TwoPart : Text -> Text -> Joke
  74.  examples.jokeDaemon.jokeServer : Cell Text
                                        -> HttpRequest
                                        ->{Remote} HttpResponse
  75.  examples.jokeDaemon.jokeServer.doc : Doc
  76.  examples.LICENSE : License
  77.  examples.LICENSE.doc : Doc
  78.  examples.messages.serviceUrls : ServiceHash a b -> Text
  79.  examples.multiService.deploy : '{IO, Exception} ()
  80.  examples.multiService.deploy.doc : Doc
  81.  examples.servePage.api : Database
                                -> [Key]
                                -> HttpRequest
                                ->{Exception, Blobs} HttpResponse
  82.  examples.servePage.api.doc : Doc
  83.  examples.servePage.assets.css : Database
                                       -> Key
                                       -> '{Route,
                                       Exception,
                                       Blobs} ()
  84.  examples.servePage.assets.decompressBlobResult : Optional
                                                          (Tuple
                                                            Bytes
                                                            b)
                                                        ->{Exception} Text
  85.  examples.servePage.assets.home : Database
                                        -> Key
                                        -> '{Route,
                                        Exception,
                                        Blobs} ()
  86.  examples.servePage.assets.js : Database
                                      -> Key
                                      -> '{Route,
                                      Exception,
                                      Blobs} ()
  87.  examples.servePage.deploy : '{IO, Exception} URI
  88.  examples.servePage.deploy.doc : Doc
  89.  examples.servePage.deploy.writeSampleAssets : '{IO,
                                                     Exception} ()
  90.  examples.servePage.deploy.writeSampleAssets.css : Text
  91.  examples.servePage.deploy.writeSampleAssets.html : Text
  92.  examples.servePage.deploy.writeSampleAssets.js : Text
  93.  examples.todoApp.deploy : '{IO, Exception} ServiceHash
                                   HttpRequest HttpResponse
  94.  examples.todoApp.deploy.doc : Doc
  95.  examples.todoApp.deploy.todoAppHash : ServiceHash
                                               HttpRequest
                                               HttpResponse
  96.  type examples.todoApp.models.TodoItem
  97.  examples.todoApp.models.TodoItem.completed : TodoItem
                                                    -> Boolean
  98.  examples.todoApp.models.TodoItem.completed.modify : (Boolean
                                                           ->{g} Boolean)
                                                           -> TodoItem
                                                           ->{g} TodoItem
  99.  examples.todoApp.models.TodoItem.completed.set : Boolean
                                                        -> TodoItem
                                                        -> TodoItem
  100. examples.todoApp.models.TodoItem.entry : TodoItem -> Text
  101. examples.todoApp.models.TodoItem.entry.modify : (Text
                                                       ->{g} Text)
                                                       -> TodoItem
                                                       ->{g} TodoItem
  102. examples.todoApp.models.TodoItem.entry.set : Text
                                                    -> TodoItem
                                                    -> TodoItem
  103. examples.todoApp.models.TodoItem.fromJson : '{Decoder} TodoItem
  104. examples.todoApp.models.TodoItem.id : TodoItem -> Text
  105. examples.todoApp.models.TodoItem.id.modify : (Text
                                                    ->{g} Text)
                                                    -> TodoItem
                                                    ->{g} TodoItem
  106. examples.todoApp.models.TodoItem.id.set : Text
                                                 -> TodoItem
                                                 -> TodoItem
  107. examples.todoApp.models.TodoItem.TodoItem : Text
                                                   -> Boolean
                                                   -> Text
                                                   -> TodoItem
  108. examples.todoApp.models.TodoItem.toJson : TodoItem
                                                 -> Json
  109. examples.todoApp.README : Doc
  110. examples.todoApp.resources.addKey : Table Type (Set Text)
                                           -> Text
                                           ->{Transaction,
                                           Exception} ()
  111. examples.todoApp.resources.deleteKey : Table
                                                Type (Set Text)
                                              -> Text
                                              ->{Transaction,
                                              Exception} ()
  112. examples.todoApp.routes.todoService : OrderedTable
                                               Text TodoItem
                                             -> Database
                                             -> '{Route,
                                             Exception,
                                             unison_cloud_19_0_0.Storage,
                                             Remote,
                                             Log} ()
  113. examples.todoApp.routes.todoService.doc : Doc
  114. examples.todoApp.undeploy : '{IO, Exception} ()
  115. examples.todoApp.undeploy.doc : Doc
  116. exercises.admin.console.print : (i ->{g1} Text)
                                       -> (o ->{g} Text)
                                       -> ExerciseResult i o
                                       ->{g, g1, IO, Exception} ()
  117. exercises.admin.console.print.HttpRequest : HttpRequest
                                                   ->{Exception} Text
  118. exercises.admin.console.print.HttpResponse : HttpResponse
                                                    ->{Exception} Text
  119. exercises.admin.console.printProgress : TrackProgress
                                               ->{IO, Exception} ()
  120. exercises.admin.console.printProgress.formatTextTuple : List.Nonempty
                                                                 ( Exercise.Number,
                                                                   models.Status)
                                                               -> ( Text,
                                                                 Text)
  121. exercises.admin.console.printProgress.padHeader : Exercise.Number
                                                         -> Text
                                                         -> ( Text,
                                                           Text)
  122. exercises.admin.console.Reporting.toText : (i
                                                  ->{g1} Text)
                                                  -> (o
                                                  ->{g} Text)
                                                  -> Reporting
                                                    i o
                                                  ->{g, g1} Text
  123. exercises.admin.console.Result.toText : (i ->{g1} Text)
                                               -> (o ->{g} Text)
                                               -> models.Result
                                                 i o
                                               ->{g, g1} Text
  124. type exercises.admin.console.TrackProgress
  125. exercises.admin.console.TrackProgress.attempted : TrackProgress
                                                         -> [( Exercise.Number,
                                                           models.Status)]
  126. exercises.admin.console.TrackProgress.attempted.modify : ([( Exercise.Number,
                                                                  models.Status)]
                                                                ->{g} [( Exercise.Number,
                                                                  models.Status)])
                                                                -> TrackProgress
                                                                ->{g} TrackProgress
  127. exercises.admin.console.TrackProgress.attempted.set : [( Exercise.Number,
                                                               models.Status)]
                                                             -> TrackProgress
                                                             -> TrackProgress
  128. exercises.admin.console.TrackProgress.next : TrackProgress
                                                    -> Optional
                                                      Exercise.Number
  129. exercises.admin.console.TrackProgress.next.modify : (Optional
                                                             Exercise.Number
                                                           ->{g} Optional
                                                             Exercise.Number)
                                                           -> TrackProgress
                                                           ->{g} TrackProgress
  130. exercises.admin.console.TrackProgress.next.set : Optional
                                                          Exercise.Number
                                                        -> TrackProgress
                                                        -> TrackProgress
  131. exercises.admin.console.TrackProgress.TrackProgress : [( Exercise.Number,
                                                               models.Status)]
                                                             -> Optional
                                                               Exercise.Number
                                                             -> TrackProgress
  132. type exercises.admin.models.Exercise.Id
  133. exercises.admin.models.Exercise.Id.Id : Track
                                               -> Exercise.Number
                                               -> Exercise.Id
  134. type exercises.admin.models.Exercise.Number
  135. exercises.admin.models.Exercise.Number.Number : Nat
                                                       -> Part
                                                       -> Exercise.Number
  136. exercises.admin.models.Exercise.Number.toText : Exercise.Number
                                                       -> Text
  137. type exercises.admin.models.Exercise.Part
  138. exercises.admin.models.Exercise.Part.Part : Nat -> Part
  139. type exercises.admin.models.ExerciseResult a b
  140. exercises.admin.models.ExerciseResult.ExerciseResult : Exercise.Number
                                                              -> Text
                                                              -> [models.Result
                                                                a
                                                                b]
                                                              -> ExerciseResult
                                                                a
                                                                b
  141. exercises.admin.models.ExerciseResult.isSuccess : ExerciseResult
                                                           a b
                                                         -> models.Status
  142. type exercises.admin.models.Reporting i o
  143. exercises.admin.models.Reporting.ErrorReporting : Failure
                                                         -> Reporting
                                                           i o
                                                         -> Reporting
                                                           i o
  144. exercises.admin.models.Reporting.Expected : o
                                                   -> Reporting
                                                     i o
  145. exercises.admin.models.Reporting.InputOutput : Optional i
                                                      -> Optional
                                                        o
                                                      -> Reporting
                                                        i o
  146. exercises.admin.models.Reporting.InputOutputExpected : i
                                                              -> o
                                                              -> o
                                                              -> Reporting
                                                                i
                                                                o
  147. type exercises.admin.models.Result i o
  148. exercises.admin.models.Result.Correct : Text
                                               -> Reporting i o
                                               -> models.Result
                                                 i o
  149. exercises.admin.models.Result.Error : Text
                                             -> Reporting i o
                                             -> models.Result
                                               i o
  150. exercises.admin.models.Result.Incorrect : Text
                                                 -> Reporting
                                                   i o
                                                 -> models.Result
                                                   i o
  151. exercises.admin.models.Result.isSuccess : models.Result
                                                   i o
                                                 -> Boolean
  152. exercises.admin.models.Result.PassThrough : Text
                                                   -> Reporting
                                                     i o
                                                   -> models.Result
                                                     i o
  153. exercises.admin.resultsService.admin.addChallenge : resultsService.Storage
                                                           -> Track.Number
                                                           -> Exercise.Number
                                                           ->{Exception,
                                                           unison_cloud_19_0_0.Storage,
                                                           Random} ()
  154. exercises.admin.resultsService.admin.countSubmissionsByExercise : '{IO,
                                                                         Exception} [( Exercise.Number,
                                                                           Nat)]
  155. exercises.admin.resultsService.admin.countSubmissionsByUserExercise : '{IO,
                                                                             Exception} [( ( models.User,
                                                                               Track.Number,
                                                                               Exercise.Number),
                                                                               Nat)]
  156. exercises.admin.resultsService.admin.replaceAllTrackChallenges : resultsService.Storage
                                                                        -> Track.Number
                                                                        -> [Exercise.Number]
                                                                        ->{Remote} ()
  157. exercises.admin.resultsService.admin.setTrackState : '{IO,
                                                            Exception} ()
  158. exercises.admin.resultsService.createStorage : '{Exception,
                                                      Cloud} resultsService.Storage
  159. exercises.admin.resultsService.db.addResult : resultsService.Storage
                                                     -> models.User
                                                     -> AttemptRecord
                                                     ->{Exception,
                                                     unison_cloud_19_0_0.Storage,
                                                     Random} ()
  160. exercises.admin.resultsService.db.getAllTrackChallenges : resultsService.Storage
                                                                 -> Track.Number
                                                                 ->{Remote} [Exercise.Number]
  161. exercises.admin.resultsService.db.getDistinctLatestAttempts : resultsService.Storage
                                                                     -> models.User
                                                                     -> Track.Number
                                                                     ->{Remote} [AttemptRecord]
  162. exercises.admin.resultsService.db.getUserTrackProgress : resultsService.Storage
                                                                -> models.User
                                                                -> Track.Number
                                                                ->{Remote} TrackProgress
  163. exercises.admin.resultsService.db.getUserTrackResults : resultsService.Storage
                                                               -> models.User
                                                               -> Track.Number
                                                               ->{Remote} [AttemptRecord]
  164. exercises.admin.resultsService.db.readUserResults : resultsService.Storage
                                                           -> ( models.User,
                                                             Track.Number,
                                                             Exercise.Number)
                                                           ->{Remote} Optional
                                                             [AttemptRecord]
  165. exercises.admin.resultsService.db.userResultsPrefix : resultsService.Storage
                                                             -> models.User
                                                             ->{Remote} [AttemptRecord]
  166. exercises.admin.resultsService.db.userStartsTrack : resultsService.Storage
                                                           -> models.User
                                                           -> Track.Number
                                                           ->{Exception,
                                                           unison_cloud_19_0_0.Storage,
                                                           Random} ()
  167. exercises.admin.resultsService.deploys.putUserAttempt : '{IO,
                                                               Exception} ServiceHash
                                                                 ( models.User,
                                                                   AttemptRecord)
                                                                 ( )
  168. exercises.admin.resultsService.deploys.putUserAttempt.impl : resultsService.Storage
                                                                    -> ( models.User,
                                                                      AttemptRecord)
                                                                    ->{Exception,
                                                                    unison_cloud_19_0_0.Storage,
                                                                    Remote,
                                                                    Random} ()
  169. exercises.admin.resultsService.deploys.trackProgressService : '{IO,
                                                                     Exception} ServiceHash
                                                                       ( models.User,
                                                                         Track.Number)
                                                                       TrackProgress
  170. exercises.admin.resultsService.env : '{Exception, Cloud} Environment
  171. exercises.admin.resultsService.hashes.putUserAttempt2 : ServiceHash
                                                                 ( models.User,
                                                                   AttemptRecord)
                                                                 ( )
  172. exercises.admin.resultsService.hashes.putUserAttemptv1 : ServiceHash
                                                                  ( models.User,
                                                                    AttemptRecord)
                                                                  ( )
  173. exercises.admin.resultsService.hashes.putUserAttemptV3 : ServiceHash
                                                                  ( models.User,
                                                                    AttemptRecord)
                                                                  ( )
  174. exercises.admin.resultsService.hashes.trackProgressV1 : ServiceHash
                                                                 ( models.User,
                                                                   Track.Number)
                                                                 TrackProgress
  175. exercises.admin.resultsService.hashes.trackProgressv2 : ServiceHash
                                                                 ( models.User,
                                                                   Track.Number)
                                                                 TrackProgress
  176. exercises.admin.resultsService.hashes.trackProgressV3 : ServiceHash
                                                                 ( models.User,
                                                                   Track.Number)
                                                                 TrackProgress
  177. exercises.admin.resultsService.hashes.v1 : ServiceHash
                                                    ( models.User,
                                                      AttemptRecord)
                                                    ()
  178. exercises.admin.resultsService.hashes.v2 : ServiceHash
                                                    ( models.User,
                                                      AttemptRecord)
                                                    ()
  179. exercises.admin.resultsService.hashes.v3 : ServiceHash
                                                    ( models.User,
                                                      AttemptRecord)
                                                    ()
  180. type exercises.admin.resultsService.impl.CredentialsError
  181. exercises.admin.resultsService.impl.CredentialsError.CredentialsError : impl.CredentialsError
  182. exercises.admin.resultsService.impl.getUser : '{IO,
                                                     Exception} ( Text,
                                                       Text)
  183. type exercises.admin.resultsService.models.AttemptRecord
  184. exercises.admin.resultsService.models.AttemptRecord.AttemptRecord : Track.Number
                                                                           -> Exercise.Number
                                                                           -> OffsetDateTime
                                                                           -> models.Status
                                                                           -> AttemptRecord
  185. exercises.admin.resultsService.models.AttemptRecord.fromChallengeResult : OffsetDateTime
                                                                                 -> Track.Number
                                                                                 -> ExerciseResult
                                                                                   i
                                                                                   o
                                                                                 -> AttemptRecord
  186. exercises.admin.resultsService.models.AttemptRecord.number : AttemptRecord
                                                                    -> Exercise.Number
  187. exercises.admin.resultsService.models.AttemptRecord.number.modify : (Exercise.Number
                                                                           ->{g} Exercise.Number)
                                                                           -> AttemptRecord
                                                                           ->{g} AttemptRecord
  188. exercises.admin.resultsService.models.AttemptRecord.number.set : Exercise.Number
                                                                        -> AttemptRecord
                                                                        -> AttemptRecord
  189. exercises.admin.resultsService.models.AttemptRecord.status : AttemptRecord
                                                                    -> models.Status
  190. exercises.admin.resultsService.models.AttemptRecord.status.modify : (models.Status
                                                                           ->{g} models.Status)
                                                                           -> AttemptRecord
                                                                           ->{g} AttemptRecord
  191. exercises.admin.resultsService.models.AttemptRecord.status.set : models.Status
                                                                        -> AttemptRecord
                                                                        -> AttemptRecord
  192. exercises.admin.resultsService.models.AttemptRecord.timeStamp : AttemptRecord
                                                                       -> OffsetDateTime
  193. exercises.admin.resultsService.models.AttemptRecord.timeStamp.modify : (OffsetDateTime
                                                                              ->{g} OffsetDateTime)
                                                                              -> AttemptRecord
                                                                              ->{g} AttemptRecord
  194. exercises.admin.resultsService.models.AttemptRecord.timeStamp.set : OffsetDateTime
                                                                           -> AttemptRecord
                                                                           -> AttemptRecord
  195. exercises.admin.resultsService.models.AttemptRecord.toText : AttemptRecord
                                                                    -> Text
  196. exercises.admin.resultsService.models.AttemptRecord.track : AttemptRecord
                                                                   -> Track.Number
  197. exercises.admin.resultsService.models.AttemptRecord.track.modify : (Track.Number
                                                                          ->{g} Track.Number)
                                                                          -> AttemptRecord
                                                                          ->{g} AttemptRecord
  198. exercises.admin.resultsService.models.AttemptRecord.track.set : Track.Number
                                                                       -> AttemptRecord
                                                                       -> AttemptRecord
  199. type exercises.admin.resultsService.models.Difficulty
  200. exercises.admin.resultsService.models.Difficulty.Easy : Difficulty
  201. exercises.admin.resultsService.models.Difficulty.Hard : Difficulty
  202. exercises.admin.resultsService.models.Difficulty.Medium : Difficulty
  203. type exercises.admin.resultsService.models.Errors.ChallengeExistsForTrack
  204. type exercises.admin.resultsService.models.Errors.TrackNotCreated
  205. type exercises.admin.resultsService.models.Status
  206. exercises.admin.resultsService.models.Status.Failed : models.Status
  207. exercises.admin.resultsService.models.Status.NotStarted : models.Status
  208. exercises.admin.resultsService.models.Status.Passed : models.Status
  209. exercises.admin.resultsService.models.Status.toText : models.Status
                                                             -> Text
  210. type exercises.admin.resultsService.models.Track
  211. type exercises.admin.resultsService.models.Track.Number
  212. exercises.admin.resultsService.models.Track.number : Track
                                                            -> Track.Number
  213. exercises.admin.resultsService.models.Track.number.modify : (Track.Number
                                                                   ->{g} Track.Number)
                                                                   -> Track
                                                                   ->{g} Track
  214. exercises.admin.resultsService.models.Track.Number.Number : Nat
                                                                   -> Track.Number
  215. exercises.admin.resultsService.models.Track.number.set : Track.Number
                                                                -> Track
                                                                -> Track
  216. exercises.admin.resultsService.models.Track.Number.toText : Track.Number
                                                                   -> Text
  217. exercises.admin.resultsService.models.Track.title : Track
                                                           -> Text
  218. exercises.admin.resultsService.models.Track.title.modify : (Text
                                                                  ->{g} Text)
                                                                  -> Track
                                                                  ->{g} Track
  219. exercises.admin.resultsService.models.Track.title.set : Text
                                                               -> Track
                                                               -> Track
  220. exercises.admin.resultsService.models.Track.Track : Track.Number
                                                           -> Text
                                                           -> Track
  221. type exercises.admin.resultsService.models.User
  222. exercises.admin.resultsService.models.User.User : Text
                                                         -> Text
                                                         -> models.User
  223. type exercises.admin.resultsService.Storage
  224. exercises.admin.resultsService.Storage.database : resultsService.Storage
                                                         -> Database
  225. exercises.admin.resultsService.Storage.database.modify : (Database
                                                                ->{g} Database)
                                                                -> resultsService.Storage
                                                                ->{g} resultsService.Storage
  226. exercises.admin.resultsService.Storage.database.set : Database
                                                             -> resultsService.Storage
                                                             -> resultsService.Storage
  227. exercises.admin.resultsService.Storage.Storage : Database
                                                        -> OrderedTable
                                                          ( models.User,
                                                            Track.Number,
                                                            Exercise.Number)
                                                          [AttemptRecord]
                                                        -> OrderedTable
                                                          ( Track.Number,
                                                            models.User)
                                                          [AttemptRecord]
                                                        -> OrderedTable
                                                          models.User
                                                          [Track.Number]
                                                        -> OrderedTable
                                                          Track.Number
                                                          [Exercise.Number]
                                                        -> resultsService.Storage
  228. exercises.admin.resultsService.Storage.tracks : resultsService.Storage
                                                       -> OrderedTable
                                                         Track.Number
                                                         [Exercise.Number]
  229. exercises.admin.resultsService.Storage.tracks.modify : (OrderedTable
                                                                Track.Number
                                                                [Exercise.Number]
                                                              ->{g} OrderedTable
                                                                Track.Number
                                                                [Exercise.Number])
                                                              -> resultsService.Storage
                                                              ->{g} resultsService.Storage
  230. exercises.admin.resultsService.Storage.tracks.set : OrderedTable
                                                             Track.Number
                                                             [Exercise.Number]
                                                           -> resultsService.Storage
                                                           -> resultsService.Storage
  231. exercises.admin.resultsService.Storage.tracksByUser : resultsService.Storage
                                                             -> OrderedTable
                                                               ( Track.Number,
                                                                 models.User)
                                                               [AttemptRecord]
  232. exercises.admin.resultsService.Storage.tracksByUser.modify : (OrderedTable
                                                                      ( Track.Number,
                                                                        models.User)
                                                                      [AttemptRecord]
                                                                    ->{g} OrderedTable
                                                                      ( Track.Number,
                                                                        models.User)
                                                                      [AttemptRecord])
                                                                    -> resultsService.Storage
                                                                    ->{g} resultsService.Storage
  233. exercises.admin.resultsService.Storage.tracksByUser.set : OrderedTable
                                                                   ( Track.Number,
                                                                     models.User)
                                                                   [AttemptRecord]
                                                                 -> resultsService.Storage
                                                                 -> resultsService.Storage
  234. exercises.admin.resultsService.Storage.userProgress : resultsService.Storage
                                                             -> OrderedTable
                                                               ( models.User,
                                                                 Track.Number,
                                                                 Exercise.Number)
                                                               [AttemptRecord]
  235. exercises.admin.resultsService.Storage.userProgress.modify : (OrderedTable
                                                                      ( models.User,
                                                                        Track.Number,
                                                                        Exercise.Number)
                                                                      [AttemptRecord]
                                                                    ->{g} OrderedTable
                                                                      ( models.User,
                                                                        Track.Number,
                                                                        Exercise.Number)
                                                                      [AttemptRecord])
                                                                    -> resultsService.Storage
                                                                    ->{g} resultsService.Storage
  236. exercises.admin.resultsService.Storage.userProgress.set : OrderedTable
                                                                   ( models.User,
                                                                     Track.Number,
                                                                     Exercise.Number)
                                                                   [AttemptRecord]
                                                                 -> resultsService.Storage
                                                                 -> resultsService.Storage
  237. exercises.admin.resultsService.Storage.usersTracks : resultsService.Storage
                                                            -> OrderedTable
                                                              models.User
                                                              [Track.Number]
  238. exercises.admin.resultsService.Storage.usersTracks.modify : (OrderedTable
                                                                     models.User
                                                                     [Track.Number]
                                                                   ->{g} OrderedTable
                                                                     models.User
                                                                     [Track.Number])
                                                                   -> resultsService.Storage
                                                                   ->{g} resultsService.Storage
  239. exercises.admin.resultsService.Storage.usersTracks.set : OrderedTable
                                                                  models.User
                                                                  [Track.Number]
                                                                -> resultsService.Storage
                                                                -> resultsService.Storage
  240. exercises.admin.resultsService.test.latestChallenges : '{IO,
                                                              Exception} ()
  241. exercises.admin.resultsService.test.printTestProgress : '{IO,
                                                               Exception} ()
  242. exercises.admin.resultsService.test.readUserChallenges : '{IO,
                                                                Exception} [AttemptRecord]
  243. exercises.admin.resultsService.test.testAddChallenge : '{IO,
                                                              Exception} [Exercise.Number]
  244. exercises.admin.resultsService.test.testAddChallengeRoundtrip : '{IO,
                                                                       Exception} ()
  245. exercises.admin.resultsService.up.tup3.prefixOrdering : k1
                                                               -> ( k1,
                                                                 k2,
                                                                 k3)
                                                               -> Ordering
  246. exercises.admin.validator.callHttpService : HttpRequest
                                                   ->{Cloud} Either
                                                     Failure
                                                     HttpResponse
  247. exercises.admin.validator.callService : ServiceHash a b
                                               -> a
                                               ->{Cloud} Either
                                                 Failure b
  248. exercises.admin.validator.callWebSocketService : URI
                                                        -> (unison_http_3_3_2.websockets.WebSocket
                                                        ->{g,
                                                        IO} ())
                                                        ->{g,
                                                        IO,
                                                        Exception} ()
  249. exercises.admin.validator.decodeHttpResponse : HttpRequest
                                                      -> (Body
                                                      ->{Exception} a)
                                                      -> Text
                                                      ->{Cloud,
                                                      Stream
                                                        (models.Result
                                                          HttpRequest
                                                          HttpResponse)} Either
                                                        Failure
                                                        a
  250. exercises.admin.validator.Either.tupleRight : Either a b
                                                     -> Either
                                                       a c
                                                     -> Either
                                                       a (b, c)
  251. exercises.admin.validator.env : '{Exception, Cloud} Environment
  252. exercises.admin.validator.exercise : Track.Number
                                            -> Exercise.Number
                                            -> Text
                                            -> '{g,
                                            Cloud,
                                            Stream
                                              (models.Result i o)} a
                                            ->{g, IO, Exception} ( ExerciseResult
                                              i o,
                                              TrackProgress)
  253. exercises.admin.validator.expect : ServiceHash a b
                                          -> a
                                          -> b
                                          -> Text
                                          ->{Cloud,
                                          Stream
                                            (models.Result a b)} ()
  254. exercises.admin.validator.expectFailure : ServiceHash a b
                                                 -> a
                                                 -> Text
                                                 -> Text
                                                 ->{Cloud,
                                                 Stream
                                                   (models.Result
                                                     a b)} ()
  255. exercises.admin.validator.expectHttpBodyString : HttpRequest
                                                        -> Nat
                                                        -> Text
                                                        -> Text
                                                        ->{Exception,
                                                        Cloud,
                                                        Stream
                                                          (models.Result
                                                            HttpRequest
                                                            HttpResponse)} ()
  256. exercises.admin.validator.expectHttpCode : HttpRequest
                                                  -> Nat
                                                  -> Text
                                                  ->{Cloud,
                                                  Stream
                                                    (models.Result
                                                      HttpRequest
                                                      HttpResponse)} ()
  257. exercises.admin.validator.expectHttpJsonKeys : HttpRequest
                                                      -> Nat
                                                      -> [Text]
                                                      -> Text
                                                      ->{Cloud,
                                                      Stream
                                                        (models.Result
                                                          HttpRequest
                                                          HttpResponse)} ()
  258. exercises.admin.validator.expectHttpJsonKeys.doc : Doc
  259. exercises.admin.validator.expectHttpJsonKeys.getKeySet : Json
                                                                -> Set
                                                                  Text
  260. exercises.admin.validator.expectJson : HttpRequest
                                              -> Nat
                                              -> (Json
                                              -> Json
                                              -> Boolean)
                                              -> Json
                                              -> Text
                                              ->{Cloud,
                                              Stream
                                                (models.Result
                                                  HttpRequest
                                                  HttpResponse)} ()
  261. exercises.admin.validator.expectTimed : ServiceHash a b
                                               -> a
                                               -> b
                                               -> Remote.Duration
                                               -> Text
                                               ->{Cloud,
                                               Stream
                                                 (models.Result
                                                   a b)} ()
  262. exercises.admin.validator.expectValue : a
                                               -> a
                                               -> Text
                                               ->{Stream
                                                 (models.Result
                                                   a a)} ()
  263. exercises.admin.validator.expectWebSocketEcho : Text
                                                       -> unison_http_3_3_2.websockets.WebSocket
                                                       ->{IO,
                                                       Stream
                                                         (models.Result
                                                           websockets.Message
                                                           websockets.Message)} ()
  264. exercises.admin.validator.Json.Array.contains : Json
                                                       -> Json
                                                       -> Boolean
  265. exercises.admin.validator.Json.Array.contains.doc : Doc
  266. exercises.admin.validator.Json.isSubset : Json
                                                 -> Json
                                                 -> Boolean
  267. exercises.admin.validator.Json.isSubset.doc : Doc
  268. exercises.admin.validator.runHttpWith : HttpRequest
                                               -> Text
                                               ->{Cloud,
                                               Stream
                                                 (models.Result
                                                   HttpRequest
                                                   HttpResponse)} Either
                                                 Failure
                                                 HttpResponse
  269. exercises.admin.validator.runWith : ServiceHash a b
                                           -> a
                                           -> Text
                                           ->{Cloud,
                                           Stream
                                             (models.Result a b)} Either
                                             Failure b
  270. exercises.env : '{Exception, Cloud} Environment
  271. exercises.ex1_quickstart.deploy : '{IO, Exception} URI
  272. exercises.ex1_quickstart.doc : Doc
  273. exercises.ex1_quickstart.helloWorld.logic : HttpRequest
                                                   ->{Exception,
                                                   Log} HttpResponse
  274. exercises.ex2_nativeService.callService : '{IO,
                                                 Exception} Nat
  275. exercises.ex2_nativeService.deploy : '{IO, Exception} ServiceHash
                                              Nat Nat
  276. exercises.ex2_nativeService.doc : Doc
  277. exercises.ex2_nativeService.failure : Failure
  278. exercises.ex2_nativeService.solutions.callService : '{IO,
                                                           Exception} Nat
  279. exercises.ex2_nativeService.solutions.squareService : '{IO,
                                                             Exception} ServiceHash
                                                               Nat
                                                               Nat
  280. exercises.ex3_microblog.api.createPost : '{Route} ()
  281. exercises.ex3_microblog.api.getPostById : '{Route} ()
  282. type exercises.ex3_microblog.client.User
  283. exercises.ex3_microblog.client.User.avatar : client.User
                                                    -> Optional
                                                      Text
  284. exercises.ex3_microblog.client.User.avatar.modify : (Optional
                                                             Text
                                                           ->{g} Optional
                                                             Text)
                                                           -> client.User
                                                           ->{g} client.User
  285. exercises.ex3_microblog.client.User.avatar.set : Optional
                                                          Text
                                                        -> client.User
                                                        -> client.User
  286. exercises.ex3_microblog.client.User.fromJson : '{Decoder} client.User
  287. exercises.ex3_microblog.client.User.toJson : client.User
                                                    -> Json
  288. exercises.ex3_microblog.client.User.User : Optional Text
                                                  -> Text
                                                  -> Text
                                                  -> Optional
                                                    Text
                                                  -> client.User
  289. exercises.ex3_microblog.client.User.userHandle : client.User
                                                        -> Text
  290. exercises.ex3_microblog.client.User.userHandle.modify : (Text
                                                               ->{g} Text)
                                                               -> client.User
                                                               ->{g} client.User
  291. exercises.ex3_microblog.client.User.userHandle.set : Text
                                                            -> client.User
                                                            -> client.User
  292. exercises.ex3_microblog.client.User.userId : client.User
                                                    -> Optional
                                                      Text
  293. exercises.ex3_microblog.client.User.userId.modify : (Optional
                                                             Text
                                                           ->{g} Optional
                                                             Text)
                                                           -> client.User
                                                           ->{g} client.User
  294. exercises.ex3_microblog.client.User.userId.set : Optional
                                                          Text
                                                        -> client.User
                                                        -> client.User
  295. exercises.ex3_microblog.client.User.userName : client.User
                                                      -> Text
  296. exercises.ex3_microblog.client.User.userName.modify : (Text
                                                             ->{g} Text)
                                                             -> client.User
                                                             ->{g} client.User
  297. exercises.ex3_microblog.client.User.userName.set : Text
                                                          -> client.User
                                                          -> client.User
  298. exercises.ex3_microblog.db.createAppStorage : '{Exception,
                                                     Cloud} AppStorage
  299. exercises.ex3_microblog.db.v1.createPost : v1.Storage
                                                  -> v1.UserId
                                                  -> Text
                                                  ->{Exception,
                                                  unison_cloud_19_0_0.Storage,
                                                  Remote,
                                                  Random} v1.PostRow
  300. exercises.ex3_microblog.db.v1.createuser : v1.Storage
                                                  -> UserHandle
                                                  -> Text
                                                  -> Optional
                                                    URI
                                                  ->{Exception,
                                                  unison_cloud_19_0_0.Storage,
                                                  Remote,
                                                  Random} v1.UserRow
  301. type exercises.ex3_microblog.db.v1.FollowingId
  302. exercises.ex3_microblog.db.v1.FollowingId.FollowingId : Text
                                                               -> v1.FollowingId
  303. type exercises.ex3_microblog.db.v1.FollowingRow
  304. exercises.ex3_microblog.db.v1.FollowingRow.createdAt : v1.FollowingRow
                                                              -> OffsetDateTime
  305. exercises.ex3_microblog.db.v1.FollowingRow.createdAt.modify : (OffsetDateTime
                                                                     ->{g} OffsetDateTime)
                                                                     -> v1.FollowingRow
                                                                     ->{g} v1.FollowingRow
  306. exercises.ex3_microblog.db.v1.FollowingRow.createdAt.set : OffsetDateTime
                                                                  -> v1.FollowingRow
                                                                  -> v1.FollowingRow
  307. exercises.ex3_microblog.db.v1.FollowingRow.follower : v1.FollowingRow
                                                             -> v1.UserId
  308. exercises.ex3_microblog.db.v1.FollowingRow.follower.modify : (v1.UserId
                                                                    ->{g} v1.UserId)
                                                                    -> v1.FollowingRow
                                                                    ->{g} v1.FollowingRow
  309. exercises.ex3_microblog.db.v1.FollowingRow.follower.set : v1.UserId
                                                                 -> v1.FollowingRow
                                                                 -> v1.FollowingRow
  310. exercises.ex3_microblog.db.v1.FollowingRow.FollowingRow : v1.UserId
                                                                 -> v1.UserId
                                                                 -> OffsetDateTime
                                                                 -> OffsetDateTime
                                                                 -> v1.FollowingRow
  311. exercises.ex3_microblog.db.v1.FollowingRow.target : v1.FollowingRow
                                                           -> v1.UserId
  312. exercises.ex3_microblog.db.v1.FollowingRow.target.modify : (v1.UserId
                                                                  ->{g} v1.UserId)
                                                                  -> v1.FollowingRow
                                                                  ->{g} v1.FollowingRow
  313. exercises.ex3_microblog.db.v1.FollowingRow.target.set : v1.UserId
                                                               -> v1.FollowingRow
                                                               -> v1.FollowingRow
  314. exercises.ex3_microblog.db.v1.FollowingRow.updatedAt : v1.FollowingRow
                                                              -> OffsetDateTime
  315. exercises.ex3_microblog.db.v1.FollowingRow.updatedAt.modify : (OffsetDateTime
                                                                     ->{g} OffsetDateTime)
                                                                     -> v1.FollowingRow
                                                                     ->{g} v1.FollowingRow
  316. exercises.ex3_microblog.db.v1.FollowingRow.updatedAt.set : OffsetDateTime
                                                                  -> v1.FollowingRow
                                                                  -> v1.FollowingRow
  317. exercises.ex3_microblog.db.v1.followUser : v1.Storage
                                                  -> v1.UserId
                                                  -> v1.UserId
                                                  ->{Exception,
                                                  unison_cloud_19_0_0.Storage,
                                                  Remote} v1.FollowingRow
  318. exercises.ex3_microblog.db.v1.getPostById : v1.Storage
                                                   -> v1.PostId
                                                   ->{Exception,
                                                   unison_cloud_19_0_0.Storage,
                                                   Remote} v1.PostRow
  319. exercises.ex3_microblog.db.v1.getPostsByUserId : v1.Storage
                                                        -> UserHandle
                                                        ->{Exception,
                                                        unison_cloud_19_0_0.Storage,
                                                        Remote} [v1.PostRow]
  320. exercises.ex3_microblog.db.v1.getUserByHandle : v1.Storage
                                                       -> UserHandle
                                                       ->{Exception,
                                                       unison_cloud_19_0_0.Storage,
                                                       Remote} v1.UserRow
  321. type exercises.ex3_microblog.db.v1.PostId
  322. exercises.ex3_microblog.db.v1.PostId.PostId : Text
                                                     -> v1.PostId
  323. type exercises.ex3_microblog.db.v1.PostRow
  324. exercises.ex3_microblog.db.v1.PostRow.body : v1.PostRow
                                                    -> Text
  325. exercises.ex3_microblog.db.v1.PostRow.body.modify : (Text
                                                           ->{g} Text)
                                                           -> v1.PostRow
                                                           ->{g} v1.PostRow
  326. exercises.ex3_microblog.db.v1.PostRow.body.set : Text
                                                        -> v1.PostRow
                                                        -> v1.PostRow
  327. exercises.ex3_microblog.db.v1.PostRow.createdAt : v1.PostRow
                                                         -> OffsetDateTime
  328. exercises.ex3_microblog.db.v1.PostRow.createdAt.modify : (OffsetDateTime
                                                                ->{g} OffsetDateTime)
                                                                -> v1.PostRow
                                                                ->{g} v1.PostRow
  329. exercises.ex3_microblog.db.v1.PostRow.createdAt.set : OffsetDateTime
                                                             -> v1.PostRow
                                                             -> v1.PostRow
  330. exercises.ex3_microblog.db.v1.PostRow.id : v1.PostRow
                                                  -> v1.PostId
  331. exercises.ex3_microblog.db.v1.PostRow.id.modify : (v1.PostId
                                                         ->{g} v1.PostId)
                                                         -> v1.PostRow
                                                         ->{g} v1.PostRow
  332. exercises.ex3_microblog.db.v1.PostRow.id.set : v1.PostId
                                                      -> v1.PostRow
                                                      -> v1.PostRow
  333. exercises.ex3_microblog.db.v1.PostRow.PostRow : v1.PostId
                                                       -> OffsetDateTime
                                                       -> OffsetDateTime
                                                       -> Text
                                                       -> v1.UserId
                                                       -> v1.PostRow
  334. exercises.ex3_microblog.db.v1.PostRow.updatedAt : v1.PostRow
                                                         -> OffsetDateTime
  335. exercises.ex3_microblog.db.v1.PostRow.updatedAt.modify : (OffsetDateTime
                                                                ->{g} OffsetDateTime)
                                                                -> v1.PostRow
                                                                ->{g} v1.PostRow
  336. exercises.ex3_microblog.db.v1.PostRow.updatedAt.set : OffsetDateTime
                                                             -> v1.PostRow
                                                             -> v1.PostRow
  337. exercises.ex3_microblog.db.v1.PostRow.userId : v1.PostRow
                                                      -> v1.UserId
  338. exercises.ex3_microblog.db.v1.PostRow.userId.modify : (v1.UserId
                                                             ->{g} v1.UserId)
                                                             -> v1.PostRow
                                                             ->{g} v1.PostRow
  339. exercises.ex3_microblog.db.v1.PostRow.userId.set : v1.UserId
                                                          -> v1.PostRow
                                                          -> v1.PostRow
  340. type exercises.ex3_microblog.db.v1.Storage
  341. exercises.ex3_microblog.db.v1.Storage.database : v1.Storage
                                                        -> Database
  342. exercises.ex3_microblog.db.v1.Storage.database.modify : (Database
                                                               ->{g} Database)
                                                               -> v1.Storage
                                                               ->{g} v1.Storage
  343. exercises.ex3_microblog.db.v1.Storage.database.set : Database
                                                            -> v1.Storage
                                                            -> v1.Storage
  344. exercises.ex3_microblog.db.v1.Storage.following : v1.Storage
                                                         -> OrderedTable
                                                           ( v1.UserId,
                                                             v1.UserId)
                                                           v1.FollowingRow
  345. exercises.ex3_microblog.db.v1.Storage.following.modify : (OrderedTable
                                                                  ( v1.UserId,
                                                                    v1.UserId)
                                                                  v1.FollowingRow
                                                                ->{g} OrderedTable
                                                                  ( v1.UserId,
                                                                    v1.UserId)
                                                                  v1.FollowingRow)
                                                                -> v1.Storage
                                                                ->{g} v1.Storage
  346. exercises.ex3_microblog.db.v1.Storage.following.set : OrderedTable
                                                               ( v1.UserId,
                                                                 v1.UserId)
                                                               v1.FollowingRow
                                                             -> v1.Storage
                                                             -> v1.Storage
  347. exercises.ex3_microblog.db.v1.Storage.postsTable : v1.Storage
                                                          -> OrderedTable
                                                            v1.PostId
                                                            v1.PostRow
  348. exercises.ex3_microblog.db.v1.Storage.postsTable.modify : (OrderedTable
                                                                   v1.PostId
                                                                   v1.PostRow
                                                                 ->{g} OrderedTable
                                                                   v1.PostId
                                                                   v1.PostRow)
                                                                 -> v1.Storage
                                                                 ->{g} v1.Storage
  349. exercises.ex3_microblog.db.v1.Storage.postsTable.set : OrderedTable
                                                                v1.PostId
                                                                v1.PostRow
                                                              -> v1.Storage
                                                              -> v1.Storage
  350. exercises.ex3_microblog.db.v1.Storage.Storage : Database
                                                       -> Cell
                                                         v1.UserId
                                                       -> OrderedTable
                                                         UserHandle
                                                         v1.UserId
                                                       -> OrderedTable
                                                         v1.UserId
                                                         v1.UserRow
                                                       -> OrderedTable
                                                         ( v1.UserId,
                                                           OffsetDateTime)
                                                         v1.PostId
                                                       -> OrderedTable
                                                         v1.PostId
                                                         v1.PostRow
                                                       -> OrderedTable
                                                         ( v1.UserId,
                                                           v1.UserId)
                                                         v1.FollowingRow
                                                       -> v1.Storage
  351. exercises.ex3_microblog.db.v1.Storage.userHandleIdTable : v1.Storage
                                                                 -> OrderedTable
                                                                   UserHandle
                                                                   v1.UserId
  352. exercises.ex3_microblog.db.v1.Storage.userHandleIdTable.modify : (OrderedTable
                                                                          UserHandle
                                                                          v1.UserId
                                                                        ->{g} OrderedTable
                                                                          UserHandle
                                                                          v1.UserId)
                                                                        -> v1.Storage
                                                                        ->{g} v1.Storage
  353. exercises.ex3_microblog.db.v1.Storage.userHandleIdTable.set : OrderedTable
                                                                       UserHandle
                                                                       v1.UserId
                                                                     -> v1.Storage
                                                                     -> v1.Storage
  354. exercises.ex3_microblog.db.v1.Storage.userIdsTable : v1.Storage
                                                            -> Cell
                                                              v1.UserId
  355. exercises.ex3_microblog.db.v1.Storage.userIdsTable.modify : (Cell
                                                                     v1.UserId
                                                                   ->{g} Cell
                                                                     v1.UserId)
                                                                   -> v1.Storage
                                                                   ->{g} v1.Storage
  356. exercises.ex3_microblog.db.v1.Storage.userIdsTable.set : Cell
                                                                  v1.UserId
                                                                -> v1.Storage
                                                                -> v1.Storage
  357. exercises.ex3_microblog.db.v1.Storage.userPostsTable : v1.Storage
                                                              -> OrderedTable
                                                                ( v1.UserId,
                                                                  OffsetDateTime)
                                                                v1.PostId
  358. exercises.ex3_microblog.db.v1.Storage.userPostsTable.modify : (OrderedTable
                                                                       ( v1.UserId,
                                                                         OffsetDateTime)
                                                                       v1.PostId
                                                                     ->{g} OrderedTable
                                                                       ( v1.UserId,
                                                                         OffsetDateTime)
                                                                       v1.PostId)
                                                                     -> v1.Storage
                                                                     ->{g} v1.Storage
  359. exercises.ex3_microblog.db.v1.Storage.userPostsTable.set : OrderedTable
                                                                    ( v1.UserId,
                                                                      OffsetDateTime)
                                                                    v1.PostId
                                                                  -> v1.Storage
                                                                  -> v1.Storage
  360. exercises.ex3_microblog.db.v1.Storage.usersTable : v1.Storage
                                                          -> OrderedTable
                                                            v1.UserId
                                                            v1.UserRow
  361. exercises.ex3_microblog.db.v1.Storage.usersTable.modify : (OrderedTable
                                                                   v1.UserId
                                                                   v1.UserRow
                                                                 ->{g} OrderedTable
                                                                   v1.UserId
                                                                   v1.UserRow)
                                                                 -> v1.Storage
                                                                 ->{g} v1.Storage
  362. exercises.ex3_microblog.db.v1.Storage.usersTable.set : OrderedTable
                                                                v1.UserId
                                                                v1.UserRow
                                                              -> v1.Storage
                                                              -> v1.Storage
  363. type exercises.ex3_microblog.db.v1.UserId
  364. exercises.ex3_microblog.db.v1.UserId.UserId : Text
                                                     -> v1.UserId
  365. type exercises.ex3_microblog.db.v1.UserRow
  366. exercises.ex3_microblog.db.v1.UserRow.avatar : v1.UserRow
                                                      -> Optional
                                                        URI
  367. exercises.ex3_microblog.db.v1.UserRow.avatar.modify : (Optional
                                                               URI
                                                             ->{g} Optional
                                                               URI)
                                                             -> v1.UserRow
                                                             ->{g} v1.UserRow
  368. exercises.ex3_microblog.db.v1.UserRow.avatar.set : Optional
                                                            URI
                                                          -> v1.UserRow
                                                          -> v1.UserRow
  369. exercises.ex3_microblog.db.v1.UserRow.createdAt : v1.UserRow
                                                         -> OffsetDateTime
  370. exercises.ex3_microblog.db.v1.UserRow.createdAt.modify : (OffsetDateTime
                                                                ->{g} OffsetDateTime)
                                                                -> v1.UserRow
                                                                ->{g} v1.UserRow
  371. exercises.ex3_microblog.db.v1.UserRow.createdAt.set : OffsetDateTime
                                                             -> v1.UserRow
                                                             -> v1.UserRow
  372. exercises.ex3_microblog.db.v1.UserRow.id : v1.UserRow
                                                  -> v1.UserId
  373. exercises.ex3_microblog.db.v1.UserRow.id.modify : (v1.UserId
                                                         ->{g} v1.UserId)
                                                         -> v1.UserRow
                                                         ->{g} v1.UserRow
  374. exercises.ex3_microblog.db.v1.UserRow.id.set : v1.UserId
                                                      -> v1.UserRow
                                                      -> v1.UserRow
  375. exercises.ex3_microblog.db.v1.UserRow.name : v1.UserRow
                                                    -> Text
  376. exercises.ex3_microblog.db.v1.UserRow.name.modify : (Text
                                                           ->{g} Text)
                                                           -> v1.UserRow
                                                           ->{g} v1.UserRow
  377. exercises.ex3_microblog.db.v1.UserRow.name.set : Text
                                                        -> v1.UserRow
                                                        -> v1.UserRow
  378. exercises.ex3_microblog.db.v1.UserRow.updatedAt : v1.UserRow
                                                         -> OffsetDateTime
  379. exercises.ex3_microblog.db.v1.UserRow.updatedAt.modify : (OffsetDateTime
                                                                ->{g} OffsetDateTime)
                                                                -> v1.UserRow
                                                                ->{g} v1.UserRow
  380. exercises.ex3_microblog.db.v1.UserRow.updatedAt.set : OffsetDateTime
                                                             -> v1.UserRow
                                                             -> v1.UserRow
  381. exercises.ex3_microblog.db.v1.UserRow.userHandle : v1.UserRow
                                                          -> UserHandle
  382. exercises.ex3_microblog.db.v1.UserRow.userHandle.modify : (UserHandle
                                                                 ->{g} UserHandle)
                                                                 -> v1.UserRow
                                                                 ->{g} v1.UserRow
  383. exercises.ex3_microblog.db.v1.UserRow.userHandle.set : UserHandle
                                                              -> v1.UserRow
                                                              -> v1.UserRow
  384. exercises.ex3_microblog.db.v1.UserRow.UserRow : v1.UserId
                                                       -> OffsetDateTime
                                                       -> OffsetDateTime
                                                       -> UserHandle
                                                       -> Text
                                                       -> Optional
                                                         URI
                                                       -> v1.UserRow
  385. type exercises.ex3_microblog.db.v2.AppStorage
  386. exercises.ex3_microblog.db.v2.AppStorage.AppStorage : Database
                                                             -> OrderedTable
                                                               UserHandle
                                                               v2.UserRow
                                                             -> OrderedTable
                                                               ( UserHandle,
                                                                 OffsetDateTime)
                                                               v2.PostRow
                                                             -> OrderedTable
                                                               v2.PostId
                                                               v2.PostRow
                                                             -> OrderedTable
                                                               ( UserHandle,
                                                                 UserHandle)
                                                               v2.FollowingRow
                                                             -> AppStorage
  387. exercises.ex3_microblog.db.v2.AppStorage.database : AppStorage
                                                           -> Database
  388. exercises.ex3_microblog.db.v2.AppStorage.database.modify : (Database
                                                                  ->{g} Database)
                                                                  -> AppStorage
                                                                  ->{g} AppStorage
  389. exercises.ex3_microblog.db.v2.AppStorage.database.set : Database
                                                               -> AppStorage
                                                               -> AppStorage
  390. exercises.ex3_microblog.db.v2.AppStorage.followingTable : AppStorage
                                                                 -> OrderedTable
                                                                   ( UserHandle,
                                                                     UserHandle)
                                                                   v2.FollowingRow
  391. exercises.ex3_microblog.db.v2.AppStorage.followingTable.modify : (OrderedTable
                                                                          ( UserHandle,
                                                                            UserHandle)
                                                                          v2.FollowingRow
                                                                        ->{g} OrderedTable
                                                                          ( UserHandle,
                                                                            UserHandle)
                                                                          v2.FollowingRow)
                                                                        -> AppStorage
                                                                        ->{g} AppStorage
  392. exercises.ex3_microblog.db.v2.AppStorage.followingTable.set : OrderedTable
                                                                       ( UserHandle,
                                                                         UserHandle)
                                                                       v2.FollowingRow
                                                                     -> AppStorage
                                                                     -> AppStorage
  393. exercises.ex3_microblog.db.v2.AppStorage.postsTable : AppStorage
                                                             -> OrderedTable
                                                               v2.PostId
                                                               v2.PostRow
  394. exercises.ex3_microblog.db.v2.AppStorage.postsTable.modify : (OrderedTable
                                                                      v2.PostId
                                                                      v2.PostRow
                                                                    ->{g} OrderedTable
                                                                      v2.PostId
                                                                      v2.PostRow)
                                                                    -> AppStorage
                                                                    ->{g} AppStorage
  395. exercises.ex3_microblog.db.v2.AppStorage.postsTable.set : OrderedTable
                                                                   v2.PostId
                                                                   v2.PostRow
                                                                 -> AppStorage
                                                                 -> AppStorage
  396. exercises.ex3_microblog.db.v2.AppStorage.userHandleToUser : AppStorage
                                                                   -> OrderedTable
                                                                     UserHandle
                                                                     v2.UserRow
  397. exercises.ex3_microblog.db.v2.AppStorage.userHandleToUser.modify : (OrderedTable
                                                                            UserHandle
                                                                            v2.UserRow
                                                                          ->{g} OrderedTable
                                                                            UserHandle
                                                                            v2.UserRow)
                                                                          -> AppStorage
                                                                          ->{g} AppStorage
  398. exercises.ex3_microblog.db.v2.AppStorage.userHandleToUser.set : OrderedTable
                                                                         UserHandle
                                                                         v2.UserRow
                                                                       -> AppStorage
                                                                       -> AppStorage
  399. exercises.ex3_microblog.db.v2.AppStorage.userPostsTable : AppStorage
                                                                 -> OrderedTable
                                                                   ( UserHandle,
                                                                     OffsetDateTime)
                                                                   v2.PostRow
  400. exercises.ex3_microblog.db.v2.AppStorage.userPostsTable.modify : (OrderedTable
                                                                          ( UserHandle,
                                                                            OffsetDateTime)
                                                                          v2.PostRow
                                                                        ->{g} OrderedTable
                                                                          ( UserHandle,
                                                                            OffsetDateTime)
                                                                          v2.PostRow)
                                                                        -> AppStorage
                                                                        ->{g} AppStorage
  401. exercises.ex3_microblog.db.v2.AppStorage.userPostsTable.set : OrderedTable
                                                                       ( UserHandle,
                                                                         OffsetDateTime)
                                                                       v2.PostRow
                                                                     -> AppStorage
                                                                     -> AppStorage
  402. type exercises.ex3_microblog.db.v2.FollowingId
  403. exercises.ex3_microblog.db.v2.FollowingId.FollowingId : UID
                                                               -> v2.FollowingId
  404. type exercises.ex3_microblog.db.v2.FollowingRow
  405. exercises.ex3_microblog.db.v2.FollowingRow.createdAt : v2.FollowingRow
                                                              -> OffsetDateTime
  406. exercises.ex3_microblog.db.v2.FollowingRow.createdAt.modify : (OffsetDateTime
                                                                     ->{g} OffsetDateTime)
                                                                     -> v2.FollowingRow
                                                                     ->{g} v2.FollowingRow
  407. exercises.ex3_microblog.db.v2.FollowingRow.createdAt.set : OffsetDateTime
                                                                  -> v2.FollowingRow
                                                                  -> v2.FollowingRow
  408. exercises.ex3_microblog.db.v2.FollowingRow.follower : v2.FollowingRow
                                                             -> UserHandle
  409. exercises.ex3_microblog.db.v2.FollowingRow.follower.modify : (UserHandle
                                                                    ->{g} UserHandle)
                                                                    -> v2.FollowingRow
                                                                    ->{g} v2.FollowingRow
  410. exercises.ex3_microblog.db.v2.FollowingRow.follower.set : UserHandle
                                                                 -> v2.FollowingRow
                                                                 -> v2.FollowingRow
  411. exercises.ex3_microblog.db.v2.FollowingRow.followingId : v2.FollowingRow
                                                                -> v2.FollowingId
  412. exercises.ex3_microblog.db.v2.FollowingRow.followingId.modify : (v2.FollowingId
                                                                       ->{g} v2.FollowingId)
                                                                       -> v2.FollowingRow
                                                                       ->{g} v2.FollowingRow
  413. exercises.ex3_microblog.db.v2.FollowingRow.followingId.set : v2.FollowingId
                                                                    -> v2.FollowingRow
                                                                    -> v2.FollowingRow
  414. exercises.ex3_microblog.db.v2.FollowingRow.FollowingRow : v2.FollowingId
                                                                 -> UserHandle
                                                                 -> UserHandle
                                                                 -> OffsetDateTime
                                                                 -> v2.FollowingRow
  415. exercises.ex3_microblog.db.v2.FollowingRow.target : v2.FollowingRow
                                                           -> UserHandle
  416. exercises.ex3_microblog.db.v2.FollowingRow.target.modify : (UserHandle
                                                                  ->{g} UserHandle)
                                                                  -> v2.FollowingRow
                                                                  ->{g} v2.FollowingRow
  417. exercises.ex3_microblog.db.v2.FollowingRow.target.set : UserHandle
                                                               -> v2.FollowingRow
                                                               -> v2.FollowingRow
  418. type exercises.ex3_microblog.db.v2.PostId
  419. exercises.ex3_microblog.db.v2.PostId.PostId : UID
                                                     -> v2.PostId
  420. type exercises.ex3_microblog.db.v2.PostRow
  421. exercises.ex3_microblog.db.v2.PostRow.body : v2.PostRow
                                                    -> Text
  422. exercises.ex3_microblog.db.v2.PostRow.body.modify : (Text
                                                           ->{g} Text)
                                                           -> v2.PostRow
                                                           ->{g} v2.PostRow
  423. exercises.ex3_microblog.db.v2.PostRow.body.set : Text
                                                        -> v2.PostRow
                                                        -> v2.PostRow
  424. exercises.ex3_microblog.db.v2.PostRow.createdAt : v2.PostRow
                                                         -> OffsetDateTime
  425. exercises.ex3_microblog.db.v2.PostRow.createdAt.modify : (OffsetDateTime
                                                                ->{g} OffsetDateTime)
                                                                -> v2.PostRow
                                                                ->{g} v2.PostRow
  426. exercises.ex3_microblog.db.v2.PostRow.createdAt.set : OffsetDateTime
                                                             -> v2.PostRow
                                                             -> v2.PostRow
  427. exercises.ex3_microblog.db.v2.PostRow.id : v2.PostRow
                                                  -> v2.PostId
  428. exercises.ex3_microblog.db.v2.PostRow.id.modify : (v2.PostId
                                                         ->{g} v2.PostId)
                                                         -> v2.PostRow
                                                         ->{g} v2.PostRow
  429. exercises.ex3_microblog.db.v2.PostRow.id.set : v2.PostId
                                                      -> v2.PostRow
                                                      -> v2.PostRow
  430. exercises.ex3_microblog.db.v2.PostRow.PostRow : v2.PostId
                                                       -> OffsetDateTime
                                                       -> Text
                                                       -> UserHandle
                                                       -> v2.PostRow
  431. exercises.ex3_microblog.db.v2.PostRow.userHandle : v2.PostRow
                                                          -> UserHandle
  432. exercises.ex3_microblog.db.v2.PostRow.userHandle.modify : (UserHandle
                                                                 ->{g} UserHandle)
                                                                 -> v2.PostRow
                                                                 ->{g} v2.PostRow
  433. exercises.ex3_microblog.db.v2.PostRow.userHandle.set : UserHandle
                                                              -> v2.PostRow
                                                              -> v2.PostRow
  434. type exercises.ex3_microblog.db.v2.UserHandle
  435. exercises.ex3_microblog.db.v2.UserHandle.UserHandle : Text
                                                             -> UserHandle
  436. type exercises.ex3_microblog.db.v2.UserRow
  437. exercises.ex3_microblog.db.v2.UserRow.avatar : v2.UserRow
                                                      -> Optional
                                                        URI
  438. exercises.ex3_microblog.db.v2.UserRow.avatar.modify : (Optional
                                                               URI
                                                             ->{g} Optional
                                                               URI)
                                                             -> v2.UserRow
                                                             ->{g} v2.UserRow
  439. exercises.ex3_microblog.db.v2.UserRow.avatar.set : Optional
                                                            URI
                                                          -> v2.UserRow
                                                          -> v2.UserRow
  440. exercises.ex3_microblog.db.v2.UserRow.name : v2.UserRow
                                                    -> Text
  441. exercises.ex3_microblog.db.v2.UserRow.name.modify : (Text
                                                           ->{g} Text)
                                                           -> v2.UserRow
                                                           ->{g} v2.UserRow
  442. exercises.ex3_microblog.db.v2.UserRow.name.set : Text
                                                        -> v2.UserRow
                                                        -> v2.UserRow
  443. exercises.ex3_microblog.db.v2.UserRow.userHandle : v2.UserRow
                                                          -> UserHandle
  444. exercises.ex3_microblog.db.v2.UserRow.userHandle.modify : (UserHandle
                                                                 ->{g} UserHandle)
                                                                 -> v2.UserRow
                                                                 ->{g} v2.UserRow
  445. exercises.ex3_microblog.db.v2.UserRow.userHandle.set : UserHandle
                                                              -> v2.UserRow
                                                              -> v2.UserRow
  446. exercises.ex3_microblog.db.v2.UserRow.UserRow : UserHandle
                                                       -> Text
                                                       -> Optional
                                                         URI
                                                       -> v2.UserRow
  447. exercises.ex3_microblog.deploy : '{IO, Exception} URI
  448. exercises.ex3_microblog.doc : Doc
  449. exercises.ex3_microblog.doc.expectedRoutes : Doc
  450. exercises.ex3_microblog.doc.JsonSchema : Doc
  451. exercises.ex4_oauth.deploy : '{IO, Exception} URI
  452. exercises.ex4_oauth.doc : Doc
  453. exercises.ex4_oauth.doc.pt1 : Doc
  454. exercises.ex4_oauth.doc.pt2 : Doc
  455. exercises.ex4_oauth.doc.pt3 : Doc
  456. exercises.ex4_oauth.doc.pt4 : Doc
  457. exercises.ex4_oauth.solutions.deploy : '{IO, Exception} URI
  458. exercises.ex4_oauth.solutions.todoService : OrderedTable
                                                     ( ex4_oauth.UserId,
                                                       Text)
                                                     TodoItem
                                                   -> Database
                                                   -> '{Route,
                                                   Exception,
                                                   unison_cloud_19_0_0.Storage,
                                                   Remote,
                                                   Log,
                                                   Auth
                                                     ex4_oauth.UserId} ()
  459. exercises.ex4_oauth.todoService : OrderedTable
                                           ( ex4_oauth.UserId,
                                             Text)
                                           TodoItem
                                         -> Database
                                         -> '{Route,
                                         Exception,
                                         unison_cloud_19_0_0.Storage,
                                         Remote,
                                         Log} ()
  460. exercises.ex4_oauth.todoService.html : Text
  461. type exercises.ex4_oauth.UserId
  462. exercises.ex4_oauth.UserId.UserId : Text
                                           -> ex4_oauth.UserId
  463. exercises.ex5_webSockets.aboutWebsockets.summary : Doc
  464. exercises.ex5_webSockets.chatHandlerService : Cell
                                                       (Set
                                                         unison_cloud_19_0_0.websockets.WebSocket)
                                                     -> HttpRequest
                                                     -> Either
                                                       HttpResponse
                                                       (unison_cloud_19_0_0.websockets.WebSocket
                                                       ->{Exception,
                                                       Remote,
                                                       WebSockets} ())
  465. exercises.ex5_webSockets.deploy : '{IO, Exception} URI
  466. exercises.ex5_webSockets.doc : Doc
  467. exercises.ex5_webSockets.doc.aboutWebSockets : Doc
  468. exercises.ex5_webSockets.doc.pt1 : Doc
  469. exercises.ex5_webSockets.doc.pt2 : Doc
  470. exercises.ex5_webSockets.doc.pt3 : Doc
  471. exercises.ex5_webSockets.doc.summary : Doc
  472. exercises.ex5_webSockets.webSocketChatHandler : Cell
                                                         (Set
                                                           unison_cloud_19_0_0.websockets.WebSocket)
                                                       -> Text
                                                       -> unison_cloud_19_0_0.websockets.WebSocket
                                                       ->{Exception,
                                                       Remote,
                                                       WebSockets} ()
  473. exercises.ex5_webSockets.webSocketHandler : unison_cloud_19_0_0.websockets.WebSocket
                                                   ->{Exception,
                                                   Remote,
                                                   WebSockets} ()
  474. exercises.ex5_webSockets.webSocketHandler.doc : Doc
  475. exercises.ex5_webSockets.webSocketHttpHandler : HttpRequest
                                                       -> Either
                                                         HttpResponse
                                                         (unison_cloud_19_0_0.websockets.WebSocket
                                                         ->{Exception,
                                                         Remote,
                                                         WebSockets} ())
  476. exercises.ex5_webSockets.webSocketStateHandler : Cell
                                                          (Set
                                                            unison_cloud_19_0_0.websockets.WebSocket)
                                                        -> unison_cloud_19_0_0.websockets.WebSocket
                                                        ->{Exception,
                                                        Remote,
                                                        WebSockets} ()
  477. exercises.README : Doc
  478. exercises.README.ch1 : Doc
  479. exercises.solutions.ex1_quickstart.deploy : '{IO,
                                                   Exception} URI
  480. exercises.solutions.ex2_nativeService.callService : '{IO,
                                                           Exception} Nat
  481. exercises.solutions.ex2_nativeService.deploy : '{IO,
                                                      Exception} ServiceHash
                                                        Nat Nat
  482. exercises.solutions.ex3_microblog.api : AppStorage
                                               -> HttpRequest
                                               ->{Exception,
                                               unison_cloud_19_0_0.Storage,
                                               Remote,
                                               Random} HttpResponse
  483. exercises.solutions.ex3_microblog.api.createPost : AppStorage
                                                          -> '{Route,
                                                          Exception,
                                                          unison_cloud_19_0_0.Storage,
                                                          Remote,
                                                          Random} ()
  484. exercises.solutions.ex3_microblog.api.createUser : AppStorage
                                                          -> '{Route,
                                                          Exception,
                                                          unison_cloud_19_0_0.Storage,
                                                          Remote,
                                                          Random} ()
  485. exercises.solutions.ex3_microblog.api.followUser : AppStorage
                                                          -> '{Route,
                                                          Exception,
                                                          unison_cloud_19_0_0.Storage,
                                                          Remote,
                                                          Random} ()
  486. exercises.solutions.ex3_microblog.api.getFeed : AppStorage
                                                       -> '{Route,
                                                       Exception,
                                                       unison_cloud_19_0_0.Storage,
                                                       Remote} ()
  487. exercises.solutions.ex3_microblog.api.getPostById : AppStorage
                                                           -> '{Route,
                                                           Exception,
                                                           unison_cloud_19_0_0.Storage,
                                                           Remote} ()
  488. exercises.solutions.ex3_microblog.api.getUserPosts : AppStorage
                                                            -> '{Route,
                                                            Exception,
                                                            unison_cloud_19_0_0.Storage} ()
  489. type exercises.solutions.ex3_microblog.client.CreatePost
  490. exercises.solutions.ex3_microblog.client.CreatePost.CreatePost : Text
                                                                        -> Text
                                                                        -> CreatePost
  491. exercises.solutions.ex3_microblog.client.CreatePost.fromJson : '{Decoder} CreatePost
  492. exercises.solutions.ex3_microblog.client.FollowingId.toJson : v2.FollowingId
                                                                     ->{Exception} Json
  493. exercises.solutions.ex3_microblog.client.FollowRequest.fromJson : '{Decoder} ( Text,
                                                                           Text)
  494. exercises.solutions.ex3_microblog.client.FollowRequest.fromJson.doc : Doc
  495. type exercises.solutions.ex3_microblog.client.Post
  496. exercises.solutions.ex3_microblog.client.Post.body : Post
                                                            -> Text
  497. exercises.solutions.ex3_microblog.client.Post.body.modify : (Text
                                                                   ->{g} Text)
                                                                   -> Post
                                                                   ->{g} Post
  498. exercises.solutions.ex3_microblog.client.Post.body.set : Text
                                                                -> Post
                                                                -> Post
  499. exercises.solutions.ex3_microblog.client.Post.doc : Doc
  500. exercises.solutions.ex3_microblog.client.Post.name : Post
                                                            -> Text
  501. exercises.solutions.ex3_microblog.client.Post.name.modify : (Text
                                                                   ->{g} Text)
                                                                   -> Post
                                                                   ->{g} Post
  502. exercises.solutions.ex3_microblog.client.Post.name.set : Text
                                                                -> Post
                                                                -> Post
  503. exercises.solutions.ex3_microblog.client.Post.Post : Text
                                                            -> Text
                                                            -> Text
                                                            -> Text
                                                            -> Post
  504. exercises.solutions.ex3_microblog.client.Post.timestamp : Post
                                                                 -> Text
  505. exercises.solutions.ex3_microblog.client.Post.timestamp.modify : (Text
                                                                        ->{g} Text)
                                                                        -> Post
                                                                        ->{g} Post
  506. exercises.solutions.ex3_microblog.client.Post.timestamp.set : Text
                                                                     -> Post
                                                                     -> Post
  507. exercises.solutions.ex3_microblog.client.Post.toJson : Post
                                                              -> Json
  508. exercises.solutions.ex3_microblog.client.Post.userHandle : Post
                                                                  -> Text
  509. exercises.solutions.ex3_microblog.client.Post.userHandle.modify : (Text
                                                                         ->{g} Text)
                                                                         -> Post
                                                                         ->{g} Post
  510. exercises.solutions.ex3_microblog.client.Post.userHandle.set : Text
                                                                      -> Post
                                                                      -> Post
  511. exercises.solutions.ex3_microblog.client.PostId.toJson : v2.PostId
                                                                ->{Exception} Json
  512. exercises.solutions.ex3_microblog.client.Posts.toJson : [Post]
                                                               -> Json
  513. type exercises.solutions.ex3_microblog.client.UserId
  514. exercises.solutions.ex3_microblog.client.UserId.toJson : client.UserId
                                                                -> Json
  515. exercises.solutions.ex3_microblog.client.UserId.UserId : Text
                                                                -> client.UserId
  516. exercises.solutions.ex3_microblog.db.createPost : AppStorage
                                                         -> UserHandle
                                                         -> Text
                                                         ->{Exception,
                                                         unison_cloud_19_0_0.Storage,
                                                         Remote,
                                                         Random} v2.PostRow
  517. exercises.solutions.ex3_microblog.db.followUser : AppStorage
                                                         -> UserHandle
                                                         -> UserHandle
                                                         ->{Exception,
                                                         unison_cloud_19_0_0.Storage,
                                                         Remote,
                                                         Random} v2.FollowingRow
  518. exercises.solutions.ex3_microblog.db.getFeedPosts : AppStorage
                                                           -> UserHandle
                                                           ->{Remote} [v2.PostRow]
  519. exercises.solutions.ex3_microblog.db.getPostsByUserHandle : AppStorage
                                                                   -> UserHandle
                                                                   ->{Transaction,
                                                                   Exception} [v2.PostRow]
  520. exercises.solutions.ex3_microblog.deploy : '{IO,
                                                  Exception} URI
  521. exercises.solutions.ex3_microblog.instantToOffsetDateTime : '{Remote} OffsetDateTime
  522. exercises.solutions.ex4_oauth.deploy : '{IO, Exception} URI
  523. exercises.solutions.ex4_oauth.getSessionOr401 : (ex4_oauth.UserId
                                                       ->{g} ())
                                                       ->{g,
                                                       Route,
                                                       Auth
                                                         ex4_oauth.UserId} ()
  524. exercises.solutions.ex4_oauth.todoService : OrderedTable
                                                     ( ex4_oauth.UserId,
                                                       Text)
                                                     TodoItem
                                                   -> Database
                                                   -> '{Route,
                                                   Exception,
                                                   unison_cloud_19_0_0.Storage,
                                                   Remote,
                                                   Log,
                                                   Auth
                                                     ex4_oauth.UserId} ()
  525. exercises.submit.ex1_quickstart : '{IO, Exception} ()
  526. exercises.submit.ex2_nativeService : '{IO, Exception} ()
  527. exercises.submit.ex3_microblog.bobFollowsAlice : URI
                                                        -> Text
                                                        -> Text
                                                        ->{Cloud,
                                                        Stream
                                                          (models.Result
                                                            HttpRequest
                                                            HttpResponse)} Either
                                                          Failure
                                                          Text
  528. exercises.submit.ex3_microblog.createPostForUser : URI
                                                          -> Text
                                                          -> Text
                                                          ->{Cloud,
                                                          Stream
                                                            (models.Result
                                                              HttpRequest
                                                              HttpResponse)} Either
                                                            Failure
                                                            Text
  529. exercises.submit.ex3_microblog.createSampleUserAlice : URI
                                                              ->{Cloud,
                                                              Stream
                                                                (models.Result
                                                                  HttpRequest
                                                                  HttpResponse)} Either
                                                                Failure
                                                                Text
  530. exercises.submit.ex3_microblog.createSampleUserBob : URI
                                                            ->{Cloud,
                                                            Stream
                                                              (models.Result
                                                                HttpRequest
                                                                HttpResponse)} Either
                                                              Failure
                                                              Text
  531. exercises.submit.ex3_microblog.FollowingId.fromJson : Body
                                                             ->{Exception} Text
  532. exercises.submit.ex3_microblog.getPostById : URI
                                                    -> Text
                                                    ->{Cloud,
                                                    Stream
                                                      (models.Result
                                                        HttpRequest
                                                        HttpResponse)} ()
  533. exercises.submit.ex3_microblog.getUserFeed : URI
                                                    -> Text
                                                    ->{Cloud,
                                                    Stream
                                                      (models.Result
                                                        HttpRequest
                                                        HttpResponse)} ()
  534. exercises.submit.ex3_microblog.PostId.fromJson : Body
                                                        ->{Exception} Text
  535. exercises.submit.ex3_microblog.pt1 : '{IO, Exception} ()
  536. exercises.submit.ex3_microblog.pt2 : '{IO, Exception} ()
  537. exercises.submit.ex3_microblog.roundTrip : '{IO,
                                                  Exception} ()
  538. exercises.submit.ex3_microblog.UserId.fromJson : Body
                                                        ->{Exception} Text
  539. exercises.submit.ex4_oauth.roundTrip : '{IO, Exception} ()
  540. exercises.submit.ex5_webSockets.pt1 : '{IO, Exception} ()
  541. exercises.submit.ex5_webSockets.pt2 : '{IO, Exception} ()
  542. exercises.submit.track1_title : Text
  543. metadata.licenses.cc0 : LicenseType
  544. metadata.licenses.cc0.doc : Doc
  545. metadata.licenses.types.cc0.text : Doc
  546. README : Doc
  547. ReleaseNotes : Doc
```

## Code examples

The `find` command in the previous section will have listed the contents of the library, take note of the last numbered argument in the list and use it in the `edit` command below.

``` ucm
@unison/cloud-start/main> edit 1-547

  ☝️

  I added 489 definitions to the top of scratch.u

  You can edit them there, then run `update` to replace the
  definitions currently in this namespace.
```

```` unison :added-by-ucm scratch.u
type examples.chat.Message
  = { sender : Sender, message : Text }

type examples.chat.Room
  = Room Text

type examples.chat.RoomState
  = { senders : Set Sender, messages : [chat.Message] }

type examples.chat.Sender
  = { id : Sender.Id,
      name : Text,
      socket : unison_cloud_19_0_0.websockets.WebSocket }

type examples.chat.Sender.Id
  = Id Bytes

type examples.jokeDaemon.Joke
  = TwoPart Text Text
  | Single Text

type examples.todoApp.models.TodoItem
  = { entry : Text, completed : Boolean, id : Text }

type exercises.admin.console.TrackProgress
  = { attempted : [(Exercise.Number, models.Status)],
      next : Optional Exercise.Number }

type exercises.admin.models.Exercise.Id
  = Id Track Exercise.Number

type exercises.admin.models.Exercise.Number
  = Number Nat Part

type exercises.admin.models.Exercise.Part
  = Part Nat

type exercises.admin.models.ExerciseResult a b
  = ExerciseResult Exercise.Number Text [models.Result a b]

type exercises.admin.models.Reporting i o
  = ErrorReporting Failure (exercises.admin.models.Reporting i o)
  | InputOutput (Optional i) (Optional o)
  | InputOutputExpected i o o
  | Expected o

type exercises.admin.models.Result i o
  = Correct Text (Reporting i o)
  | Incorrect Text (Reporting i o)
  | PassThrough Text (Reporting i o)
  | Error Text (Reporting i o)

type exercises.admin.resultsService.impl.CredentialsError
  = CredentialsError

type exercises.admin.resultsService.models.AttemptRecord
  = { track : Track.Number,
      number : Exercise.Number,
      timeStamp : OffsetDateTime,
      status : models.Status }

type exercises.admin.resultsService.models.Difficulty
  = Easy
  | Medium
  | Hard

type exercises.admin.resultsService.models.Errors.ChallengeExistsForTrack
  = 

type exercises.admin.resultsService.models.Errors.TrackNotCreated
  = 

type exercises.admin.resultsService.models.Status
  = Passed
  | Failed
  | NotStarted

type exercises.admin.resultsService.models.Track
  = { number : Track.Number, title : Text }

type exercises.admin.resultsService.models.Track.Number
  = Number Nat

type exercises.admin.resultsService.models.User
  = User Text Text

type exercises.admin.resultsService.Storage
  = { database : Database,
      userProgress :
  OrderedTable (models.User, Track.Number, Exercise.Number) [AttemptRecord],
      tracksByUser : OrderedTable (Track.Number, models.User) [AttemptRecord],
      usersTracks : OrderedTable models.User [Track.Number],
      tracks : OrderedTable Track.Number [Exercise.Number] }

type exercises.ex3_microblog.client.User
  = { userId : Optional Text,
      userHandle : Text,
      userName : Text,
      avatar : Optional Text }

type exercises.ex3_microblog.db.v1.FollowingId
  = FollowingId Text

type exercises.ex3_microblog.db.v1.FollowingRow
  = { follower : v1.UserId,
      target : v1.UserId,
      createdAt : OffsetDateTime,
      updatedAt : OffsetDateTime }

type exercises.ex3_microblog.db.v1.PostId
  = PostId Text

type exercises.ex3_microblog.db.v1.PostRow
  = { id : v1.PostId,
      createdAt : OffsetDateTime,
      updatedAt : OffsetDateTime,
      body : Text,
      userId : v1.UserId }

type exercises.ex3_microblog.db.v1.Storage
  = { database : Database,
      userIdsTable : Cell v1.UserId,
      userHandleIdTable : OrderedTable UserHandle v1.UserId,
      usersTable : OrderedTable v1.UserId v1.UserRow,
      userPostsTable : OrderedTable (v1.UserId, OffsetDateTime) v1.PostId,
      postsTable : OrderedTable v1.PostId v1.PostRow,
      following : OrderedTable (v1.UserId, v1.UserId) v1.FollowingRow }

type exercises.ex3_microblog.db.v1.UserId
  = UserId Text

type exercises.ex3_microblog.db.v1.UserRow
  = { id : v1.UserId,
      createdAt : OffsetDateTime,
      updatedAt : OffsetDateTime,
      userHandle : UserHandle,
      name : Text,
      avatar : Optional URI }

type exercises.ex3_microblog.db.v2.AppStorage
  = { database : Database,
      userHandleToUser : OrderedTable UserHandle v2.UserRow,
      userPostsTable : OrderedTable (UserHandle, OffsetDateTime) v2.PostRow,
      postsTable : OrderedTable v2.PostId v2.PostRow,
      followingTable : OrderedTable (UserHandle, UserHandle) v2.FollowingRow }

type exercises.ex3_microblog.db.v2.FollowingId
  = FollowingId UID

type exercises.ex3_microblog.db.v2.FollowingRow
  = { followingId : v2.FollowingId,
      follower : UserHandle,
      target : UserHandle,
      createdAt : OffsetDateTime }

type exercises.ex3_microblog.db.v2.PostId
  = PostId UID

type exercises.ex3_microblog.db.v2.PostRow
  = { id : v2.PostId,
      createdAt : OffsetDateTime,
      body : Text,
      userHandle : UserHandle }

type exercises.ex3_microblog.db.v2.UserHandle
  = UserHandle Text

type exercises.ex3_microblog.db.v2.UserRow
  = { userHandle : UserHandle, name : Text, avatar : Optional URI }

type exercises.ex4_oauth.UserId
  = UserId Text

type exercises.solutions.ex3_microblog.client.CreatePost
  = CreatePost Text Text

type exercises.solutions.ex3_microblog.client.Post
  = { body : Text, name : Text, userHandle : Text, timestamp : Text }

type exercises.solutions.ex3_microblog.client.UserId
  = UserId Text

examples.authDemo.appRoutes : '{Route, Auth anonymous.UserId} ()
examples.authDemo.appRoutes =
  use Route <|> noCapture
  use Text ++ toUtf8
  use anonymous UserId.UserId
  use respond ok
  publicRoute : '{Route, Auth anonymous.UserId} ()
  publicRoute =
    do
      noCapture GET Parser.root
      match getSession with
        Optional.None -> unauthorized (toUtf8 "Hello mysterious stranger!")
        Some (UserId.UserId uid) -> ok (toUtf8 ("Hello user " ++ uid ++ "!"))
  privateRoute : '{Route, Auth anonymous.UserId} ()
  privateRoute = do
    noCapture GET (Parser.s "private")
    let
      (UserId.UserId uid) = requireSession
      ok (toUtf8 ("This is your super secret page " ++ uid ++ "!"))
  publicRoute <|> privateRoute

examples.authDemo.deploy : '{IO, Exception} ()
examples.authDemo.deploy = Cloud.main do
  name = ServiceName.named "auth-demo"
  serviceHash = deployHttp Environment.default() authDemo.server()
  unison_base_3_23_1.ignore (ServiceName.assign name serviceHash)
  printLine "Logs available at:\n  https://app.unison.cloud"

examples.authDemo.server :
  '{IO, Exception} (HttpRequest ->{Exception, Http, Random, Log} HttpResponse)
examples.authDemo.server =
  do
    use Optional None
    use anonymous UserId.UserId
    _ =
      "Load our oauth client information from the environment and build a google oauth client."
    googleClientId = getEnv "GOOGLE_TEST_CLIENT_ID"
    googleClientSecret = getEnv "GOOGLE_TEST_CLIENT_SECRET"
    oauthClient =
      google (ClientId googleClientId) (ClientSecret googleClientSecret)
    _ =
      """
      The secret key used to sign session cookies in our app. Make sure to change
      this to your own cryptographically secure secret of a sufficient length.
      """
    hmacKey = HMACKey (getEnv "HMAC_KEY" |> Text.toUtf8)
    _ =
      """
      This callback will be called when the user successfully completes an
      OAuth flow. You can use the tokens provided by the Identity Provider to
      fetch user credentials and generate your user session, and/or save the user
      in your storage layer.
      
      In this example, we use the OpenID Connect ID Token provided by google, and
      decode it to get the google user ID, which we then use as our session. In
      your app you'll likely want to create a user in your own app, or take
      measures to distinguish between users logging in via different identity
      providers.
      
      Note that whatever this function returns will be stored in the user's browser cookies.
      It is signed, but not encrypted, so avoid any sensitive information here.
      """
    successCallback :
      TokenResponse IdToken ->{Exception, Http} anonymous.UserId
    successCallback tokenResponse =
      (IdToken jwtText) = idToken tokenResponse
      jwt = alvaroc1_jwt_0_0_1.decode jwtText
      match Jwt.sub jwt with
        None     -> raiseGeneric "No sub in JWT" jwt
        Some sub -> UserId.UserId sub
    _ =
      "We need to define serializers for our session type since it will be stored as text in a cookie."
    encodeUserId : anonymous.UserId -> Json
    encodeUserId = cases UserId.UserId uid -> Json.text uid
    decodeUserId : '{Decoder} anonymous.UserId
    decodeUserId = do UserId.UserId Decoder.text()
    authConfig : AuthConfig {Http, Exception} IdToken anonymous.UserId
    authConfig =
      defaultCloud
        hmacKey oauthClient None successCallback decodeUserId encodeUserId
    authDemo.appRoutes
      |> Function.delay (oauth2.handler authConfig)
      |> Route.run

examples.chat.deploy : '{IO, Exception} URI
examples.chat.deploy =
  do
    Cloud.run do
      use Environment default
      use HttpResponse badRequest
      use unison_cloud_19_0_0.websockets WebSocket
      database = Database.named "chat"
      Database.assign database default()
      state : Cell RoomState
      state = Cell.named database "state" RoomState.empty
      wsHandler : Text -> WebSocket ->{Remote, WebSockets} ()
      wsHandler name websocket = toRemote do
        id = Id.random()
        sender = Sender id name websocket
        newUser state sender
        addFinalizer do userLeft state sender
        go = do match WebSockets.receive websocket with
          TextMessage message ->
            saveMessage state (Message sender message)
            go()
          _                   ->
            sendMessage state "only accept text messages" sender
            go()
        toRemote go
        userLeft state sender
      service :
        HttpRequest
        -> Either HttpResponse (WebSocket ->{Exception, Remote, WebSockets} ())
      service = cases
        HttpRequest.HttpRequest GET _ (URI _ _ (Path [""]) _ _) _ _ ->
          Left chat.index
        HttpRequest.HttpRequest GET _ (URI _ _ (Path ["style.css"]) _ _) _ _ ->
          Left chat.style
        HttpRequest.HttpRequest GET _ (URI _ _ (Path ["script.js"]) _ _) _ _ ->
          Left chat.js
        HttpRequest.HttpRequest GET _ (URI _ _ (Path ["chat"]) rq _) _ _ ->
          match rq |> fromRawQuery with
            Optional.None -> Left badRequest
            Some q        ->
              match q |> getParam "name" with
                [name] -> Right (wsHandler name)
                _      -> Left badRequest
        _ -> Left HttpResponse.notFound
      hash = deployHttpWebSocket default() service
      serviceName = ServiceName.named "chat"
      ServiceName.assign serviceName hash

examples.chat.index : HttpResponse
examples.chat.index = index.txt |> Text.toUtf8 |> Body |> HttpResponse.ok

examples.chat.index.txt : Text
examples.chat.index.txt =
  """
  <!DOCTYPE html>
  <html lang="en">
  <head>
      <meta charset="UTF-8">
      <title>Simple Chat Application</title>
      <link rel="stylesheet" href="style.css">
  </head>
  <body>
      <div id="join-container">
          <input type="text" id="name-input" placeholder="Enter your name" />
          <button id="join-button">Join Chat</button>
      </div>
      <div id="chat-container" style="display:none;">
          <div id="chat-box"></div>
          <input type="text" id="message-input" placeholder="Type a message" />
          <button id="send-button">Send</button>
      </div>
      <script src="script.js"></script>
  </body>
  </html>
  """

examples.chat.js : HttpResponse
examples.chat.js = js.txt |> Text.toUtf8 |> Body |> HttpResponse.ok

examples.chat.js.txt : Text
examples.chat.js.txt =
  """
  document.addEventListener('DOMContentLoaded', function() {
      const chatBox = document.getElementById('chat-box');
      const messageInput = document.getElementById('message-input');
      const nameInput = document.getElementById('name-input');
      const sendButton = document.getElementById('send-button');
      const joinButton = document.getElementById('join-button');
      const joinContainer = document.getElementById('join-container');
      const chatContainer = document.getElementById('chat-container');
      let socket = null;
  
      function getWebSocketUrl() {
          const protocol = window.location.protocol === 'https:' ? 'wss:' : 'ws:';
          const host = window.location.host; // Includes hostname and port if available
          const pathname = window.location.pathname + 'chat'; // Adjust the path as needed
          return `${protocol}//${host}${pathname}`;
      }
  
      function displayMessage(message) {
          const messageElement = document.createElement('div');
          messageElement.textContent = message;
          chatBox.appendChild(messageElement);
          chatBox.scrollTop = chatBox.scrollHeight;
      }
      function send() {
          const message = messageInput.value.trim();
          if(message !== '' && socket && socket.readyState === WebSocket.OPEN) {
              socket.send(message);
              messageInput.value = '';
          }
      }
  
      function connect() {
          const name = nameInput.value.trim();
          if(name === '') {
              alert('Please enter your name.');
              return;
          }
          const wsUrl = `${getWebSocketUrl()}?name=${encodeURIComponent(name)}`;
          try {
              socket = new WebSocket(wsUrl);
              
              socket.onopen = function(event) {
                  displayMessage('Connected to the chat as ' + name + '.');
                  joinContainer.style.display = 'none';
                  chatContainer.style.display = 'block';
              };
              
              socket.onmessage = function(event) {
                  displayMessage(event.data);
              };
              
              socket.onclose = function(event) {
                  displayMessage('You have been disconnected from the chat.');
                  joinContainer.style.display = 'block';
                  chatContainer.style.display = 'none';
              };
              
              socket.onerror = function(error) {
                  console.error('WebSocket Error:', error);
              };
          } catch (error) {
              console.error('Failed to connect:', error);
          }
      }
  
      joinButton.addEventListener('click', connect);
  
      nameInput.addEventListener('keypress', function(e) {
          if(e.key === 'Enter') {
              connect();
          }
      });
  
      messageInput.addEventListener('keypress', function(e) {
          if(e.key === 'Enter') {
              send();
          }
      });
  
      sendButton.addEventListener('click', send);
  
  
  });
  """

examples.chat.Message.message : chat.Message -> Text
examples.chat.Message.message = cases Message _ message -> message

examples.chat.Message.message.modify :
  (Text ->{g} Text) -> chat.Message ->{g} chat.Message
examples.chat.Message.message.modify f = cases
  Message sender message -> Message sender (f message)

examples.chat.Message.message.set : Text -> chat.Message -> chat.Message
examples.chat.Message.message.set message1 = cases
  Message sender _ -> Message sender message1

examples.chat.Message.sender : chat.Message -> Sender
examples.chat.Message.sender = cases Message sender _ -> sender

examples.chat.Message.sender.modify :
  (Sender ->{g} Sender) -> chat.Message ->{g} chat.Message
examples.chat.Message.sender.modify f = cases
  Message sender message -> Message (f sender) message

examples.chat.Message.sender.set : Sender -> chat.Message -> chat.Message
examples.chat.Message.sender.set sender1 = cases
  Message _ message -> Message sender1 message

examples.chat.Message.toText : chat.Message -> Text
examples.chat.Message.toText = cases
  Message s m -> "<" Text.++ Sender.name s Text.++ "> " Text.++ m

examples.chat.RoomState.empty : RoomState
examples.chat.RoomState.empty = RoomState Set.empty []

examples.chat.RoomState.messages : RoomState -> [chat.Message]
examples.chat.RoomState.messages = cases RoomState _ messages -> messages

examples.chat.RoomState.messages.modify :
  ([chat.Message] ->{g} [chat.Message]) -> RoomState ->{g} RoomState
examples.chat.RoomState.messages.modify f = cases
  RoomState senders messages -> RoomState senders (f messages)

examples.chat.RoomState.messages.set : [chat.Message] -> RoomState -> RoomState
examples.chat.RoomState.messages.set messages1 = cases
  RoomState senders _ -> RoomState senders messages1

examples.chat.RoomState.newUser : Cell RoomState -> Sender ->{Remote} ()
examples.chat.RoomState.newUser state sender = 
  toRemote do
    use Text ++
    toNotify = Cell.modify state cases
      RoomState senders messages ->
        senders' = Set.insert sender senders
        (RoomState senders' messages, senders)
    Set.foldLeft
      (const
        (sendMessage state (Sender.toText sender ++ " has joined the Chat")))
      ()
      toNotify
    sendBacklog state sender

examples.chat.RoomState.newUser.doc : Doc
examples.chat.RoomState.newUser.doc =
  {{ Add the given user to the room state, and notify the users. }}

examples.chat.RoomState.saveMessage :
  Cell RoomState -> chat.Message ->{Remote} ()
examples.chat.RoomState.saveMessage state msg = 
  toRemote do
    use List :+
    sender = Message.sender msg
    toNotify = Cell.modify state cases
      RoomState senders messages ->
        messages' = messages :+ msg |> List.take 20
        (RoomState senders messages', senders)
    Set.foldLeft
      (const (sender -> sendMessage state (Message.toText msg) sender))
      ()
      toNotify

examples.chat.RoomState.saveMessage.doc : Doc
examples.chat.RoomState.saveMessage.doc =
  {{ Save the given message to the room state, and notify the users. }}

examples.chat.RoomState.sendBacklog : Cell RoomState -> Sender ->{Remote} ()
examples.chat.RoomState.sendBacklog state sender = 
  toRemote do
    Cell.read state
      |> messages
      |> foreach.deprecated
           (msg -> sendMessage state (Message.toText msg) sender)

examples.chat.RoomState.sendBacklog.doc : Doc
examples.chat.RoomState.sendBacklog.doc =
  {{ Send the backlog of messages to the given user. }}

examples.chat.RoomState.senders : RoomState -> Set Sender
examples.chat.RoomState.senders = cases RoomState senders _ -> senders

examples.chat.RoomState.senders.modify :
  (Set Sender ->{g} Set Sender) -> RoomState ->{g} RoomState
examples.chat.RoomState.senders.modify f = cases
  RoomState senders messages -> RoomState (f senders) messages

examples.chat.RoomState.senders.set : Set Sender -> RoomState -> RoomState
examples.chat.RoomState.senders.set senders1 = cases
  RoomState _ messages -> RoomState senders1 messages

examples.chat.RoomState.sendMessage :
  Cell RoomState -> Text -> Sender ->{Remote} ()
examples.chat.RoomState.sendMessage state message sender = 
  toRemote do match trySend (Sender.socket sender) (TextMessage message) with
    Right _ -> ()
    Left _  -> examples.chat.RoomState.userLeft state sender

examples.chat.RoomState.sendMessage.doc : Doc
examples.chat.RoomState.sendMessage.doc =
  {{
  Send the given message to the given user, If the message fails to send,
  assume the user left.
  }}

examples.chat.RoomState.userLeft : Cell RoomState -> Sender ->{Remote} ()
examples.chat.RoomState.userLeft state sender = 
  toRemote do
    use Text ++
    toNotify = Cell.modify state cases
      RoomState senders messages ->
        senders' = Set.delete sender senders
        (RoomState senders' messages, senders')
    Set.foldLeft
      (const
        (examples.chat.RoomState.sendMessage
          state (Sender.toText sender ++ " has left the Chat")))
      ()
      toNotify

examples.chat.RoomState.userLeft.doc : Doc
examples.chat.RoomState.userLeft.doc =
  {{
  Update the state of the room when a user leaves, and notify the remaining
  users.
  }}

examples.chat.Sender.id : Sender -> Sender.Id
examples.chat.Sender.id = cases Sender id _ _ -> id

examples.chat.Sender.id.modify :
  (Sender.Id ->{g} Sender.Id) -> Sender ->{g} Sender
examples.chat.Sender.id.modify f = cases
  Sender id name socket -> Sender (f id) name socket

examples.chat.Sender.Id.random : '{Random} Sender.Id
examples.chat.Sender.Id.random = do Sender.Id.Id (Random.bytes 8)

examples.chat.Sender.id.set : Sender.Id -> Sender -> Sender
examples.chat.Sender.id.set id1 = cases
  Sender _ name socket -> Sender id1 name socket

examples.chat.Sender.Id.toText : Sender.Id -> Text
examples.chat.Sender.Id.toText = cases Sender.Id.Id id -> Bytes.toHex id

examples.chat.Sender.name : Sender -> Text
examples.chat.Sender.name = cases Sender _ name _ -> name

examples.chat.Sender.name.modify : (Text ->{g} Text) -> Sender ->{g} Sender
examples.chat.Sender.name.modify f = cases
  Sender id name socket -> Sender id (f name) socket

examples.chat.Sender.name.set : Text -> Sender -> Sender
examples.chat.Sender.name.set name1 = cases
  Sender id _ socket -> Sender id name1 socket

examples.chat.Sender.socket :
  Sender -> unison_cloud_19_0_0.websockets.WebSocket
examples.chat.Sender.socket = cases Sender _ _ socket -> socket

examples.chat.Sender.socket.modify :
  (unison_cloud_19_0_0.websockets.WebSocket
  ->{g} unison_cloud_19_0_0.websockets.WebSocket)
  -> Sender
  ->{g} Sender
examples.chat.Sender.socket.modify f = cases
  Sender id name socket -> Sender id name (f socket)

examples.chat.Sender.socket.set :
  unison_cloud_19_0_0.websockets.WebSocket -> Sender -> Sender
examples.chat.Sender.socket.set socket1 = cases
  Sender id name _ -> Sender id name socket1

examples.chat.Sender.toText : Sender -> Text
examples.chat.Sender.toText = cases
  Sender id name _ -> name Text.++ " «" Text.++ Sender.Id.toText id Text.++ "»"

examples.chat.style : HttpResponse
examples.chat.style = style.txt |> Text.toUtf8 |> Body |> HttpResponse.ok

examples.chat.style.txt : Text
examples.chat.style.txt =
  """
  #chat-container {
      display: flex;
      flex-direction: column;
      align-items: center;
      margin-top: 20px;
  }
  
  #chat-box {
      width: 600px;
      height: 400px;
      border: 1px solid #000;
      margin-bottom: 10px;
      overflow-y: auto;
  }
  
  #name-input, #message-input {
      width: 595px;
      margin-bottom: 5px;
  }
  
  #send-button {
      cursor: pointer;
  }
  """

examples.counter.deploy : '{IO, Exception} URI
examples.counter.deploy = Cloud.main do
  db = Database.named "counter-service-db"
  env = Environment.named "counter-env"
  Database.assign db env
  count = Cell.named db "count" 0
  h = deployHttp env (counter.logic count)
  ServiceName.assign (ServiceName.named "counter-service") h

examples.counter.deploy.doc : Doc
examples.counter.deploy.doc = {{ Deployment script for the counter service. }}

examples.counter.logic :
  Cell Nat -> HttpRequest ->{Exception, Remote, Log} HttpResponse
examples.counter.logic cell =
  use Cell modifyGet
  use Nat toText
  use Parser / nat s
  use Route <|>
  use ok text
  incr = do
    use Nat +
    by = route GET (s "increment" / nat)
    count = modifyGet cell (x -> x + by)
    info "increment" [("by", toText by), ("new-count", toText count)]
    text (toText count)
  decr = do
    use Nat -
    by = route GET (s "decrement" / nat)
    count = modifyGet cell (x -> x - by)
    info "decremented" [("by", toText by), ("new-count", toText count)]
    text (toText count)
  Route.run (incr <|> decr)

examples.counter.logic.doc : Doc
examples.counter.logic.doc =
  {{
  A simple service that uses durable storage. It keeps a count that can be
  incremented or decremented using the `/increment/:number` and
  `/decrement/:number` routes.
  }}

examples.helloWorld.deploy : '{IO, Exception} ()
examples.helloWorld.deploy = Cloud.main do
  name = ServiceName.named "hello-world"
  serviceHash = deployHttp Environment.default() examples.helloWorld.logic
  unison_base_3_23_1.ignore (ServiceName.assign name serviceHash)
  printLine "Logs available at:\n  https://app.unison.cloud"

examples.jokeDaemon.daemon : Cell Text -> '{Exception, Http, Remote} r
examples.jokeDaemon.daemon cell = do
  go = do
    use Nat *
    joke = fetchJoke()
    Cell.write cell joke
    oneMinute = 60 * 1000000
    Remote.sleepMicroseconds oneMinute
    go()
  go()

examples.jokeDaemon.daemon.doc : Doc
examples.jokeDaemon.daemon.doc =
  {{
  A daemon which periodically fetches a joke from the jokeAPI:
  https://jokeapi.dev/ and updates a Cell which our {jokeServer} can serve
  }}

examples.jokeDaemon.deploy : '{IO, Exception} URI
examples.jokeDaemon.deploy = Cloud.main do
  env = Environment.default()
  db = Database.named "joke-db"
  cell = Cell.named db "joke" "No joke yet!"
  Database.assign db env
  daemon = Daemon.named "joke-daemon"
  hash = DaemonHash.create env (jokeDaemon.daemon cell)
  Daemon.assign daemon hash
  jokeServerHash = deployHttp env (jokeServer cell)
  jokeServerName = ServiceName.named "jokeserver"
  ServiceName.assign jokeServerName jokeServerHash

examples.jokeDaemon.deploy.doc : Doc
examples.jokeDaemon.deploy.doc =
  {{
  Deploy both our {daemon} which periodically updates our joke {type Cell} and
  our {jokeServer} which serves the joke in the cell via HTTP.
  }}

examples.jokeDaemon.fetchJoke : '{Exception, Http} Text
examples.jokeDaemon.fetchJoke = do
  url = URI.parse "https://v2.jokeapi.dev/joke/Programming"
  response = Http.get url
  expectSuccess response
  let
    (Body body) = HttpResponse.body response
    text = fromUtf8 body
    Decoder.run Joke.fromJson text |> Joke.toText

examples.jokeDaemon.fetchJoke.doc : Doc
examples.jokeDaemon.fetchJoke.doc =
  {{
  Fetch a joke from the jokeAPI and decode it into our Joke type see
  [the Joke API website](https://jokeapi.dev/)
  }}

examples.jokeDaemon.Joke.fromJson : '{Exception, Decoder} Joke
examples.jokeDaemon.Joke.fromJson = do
  use Decoder text
  use object at!
  t = at! "type" text
  match t with
    "single"  -> Joke.Single (at! "joke" text)
    "twopart" ->
      setup = at! "setup" text
      punchline = at! "delivery" text
      TwoPart setup punchline
    _         -> Exception.raise (Generic.failure "couldn't parse joke" ())

examples.jokeDaemon.Joke.toText : Joke -> Text
examples.jokeDaemon.Joke.toText = cases
  Joke.Single joke        -> joke
  TwoPart setup punchline -> setup Text.++ "\n" Text.++ punchline

examples.jokeDaemon.jokeServer :
  Cell Text -> HttpRequest ->{Remote} HttpResponse
examples.jokeDaemon.jokeServer cell _ =
  joke = Cell.read cell
  HttpResponse.ok (Body (Text.toUtf8 joke))

examples.jokeDaemon.jokeServer.doc : Doc
examples.jokeDaemon.jokeServer.doc =
  {{
  A very simple web service that returns the contents of the joke {type Cell}
  }}

examples.LICENSE : License
examples.LICENSE = License [unisoncomputing] [Year 2023] licenses.cc0

examples.LICENSE.doc : Doc
examples.LICENSE.doc =
  {{
  All example code under the `examples` namespace is licensed
  {{ docLink (docEmbedTermLink do licenses.cc0) }}. No need to attribute us if
  you use any of the examples as a starting point for your applications!
  }}

examples.messages.serviceUrls : ServiceHash a b -> Text
examples.messages.serviceUrls sh =
  use Text ++
  "View all logs at:\n  https://app.unison.cloud\n"
    ++ "Logs for this deploy:\n  https://app.unison.cloud/service-deploys/"
    ++ ServiceHash.toText sh

examples.multiService.deploy : '{IO, Exception} ()
examples.multiService.deploy = 
  Cloud.main do
    use Cloud deploy
    use Environment default
    use Nat + -
    use ServiceName assign named
    use unison_base_3_23_1 ignore
    ignore
      "In a more complicated example, these would\nlikely be declared as separate top-level \nservices, deployed independently."
    h1 = deploy default() (x -> x + 1)
    incrService = named "increment"
    ignore (assign incrService h1)
    h2 = deploy default() (y -> y - 1)
    decrService = named "decrement"
    ignore (assign decrService h2)
    ignore
      "And here's the edge service. Notice it calls\nthe increment and decrement services in its routes."
    edge : HttpRequest -> HttpResponse
    edge =
      use Nat toText
      use Parser / nat s
      use Route <|>
      use ok text
      incr = do
        n = route GET (s "increment" / nat)
        n' = callName incrService n
        text (toText n')
      decr = do
        n = route GET (s "decrement" / nat)
        n' = callName decrService n
        text (toText n')
      Route.run (incr <|> decr)
    n = named "counter-edge-service"
    ignore (assign n (deployHttp default() edge))

examples.multiService.deploy.doc : Doc
examples.multiService.deploy.doc =
  {{
  An example of splitting a backend into multiple native Unison services, with
  a single HTTP edge service.
  
  This is definitely overkill given the services are stateless and very simple
  and are all being deployed together. But but this shows the basic idea.
  }}

examples.servePage.api :
  Database -> [Key] -> HttpRequest ->{Exception, Blobs} HttpResponse
examples.servePage.api db keys =
  use Route <|>
  routesL : [Key -> '{Route, Exception, Blobs} ()]
  routesL = [assets.css db, assets.js db, home db]
  routesWithKey : ['{Route, Exception, Blobs} ()]
  routesWithKey = List.zipWith (r k -> r k) routesL keys
  Route.run (List.foldRight (<|>) (do notFound.text "not found") routesWithKey)

examples.servePage.api.doc : Doc
examples.servePage.api.doc =
  {{
  Sets up endpoints for serving css, js, and html for a simple web page. The
  home route, "/" serves the html file.
  }}

examples.servePage.assets.css :
  Database -> Key -> '{Route, Exception, Blobs} ()
examples.servePage.assets.css db csskey = do
  Route.noCapture GET (Parser.s "styles.css")
  bytes = bytes.read db csskey
  ok.css (decompressBlobResult bytes)

examples.servePage.assets.decompressBlobResult :
  Optional (Tuple Bytes b) ->{Exception} Text
examples.servePage.assets.decompressBlobResult maybeBytes =
  bytes = maybeBytes |> Optional.map at1 |> Optional.getOrElse Bytes.empty
  zlib.decompress.impl bytes |> Either.mapRight fromUtf8 |> Either.unwrap

examples.servePage.assets.home :
  Database -> Key -> '{Route, Exception, Blobs} ()
examples.servePage.assets.home db htmlKey = do
  Route.noCapture GET top
  bytes = bytes.read db htmlKey
  ok.html (decompressBlobResult bytes)

examples.servePage.assets.js : Database -> Key -> '{Route, Exception, Blobs} ()
examples.servePage.assets.js db jsKey = do
  Route.noCapture GET (Parser.s "scripts.js")
  bytes = bytes.read db jsKey
  ok.js (decompressBlobResult bytes)

examples.servePage.deploy : '{IO, Exception} URI
examples.servePage.deploy = 
  Cloud.main do
    use Environment default
    use IO.FilePath /
    use List map
    database = Database.named "blobStore"
    Database.assign database default()
    hostDir = FilePath "assets"
    css = hostDir / "styles.css"
    js = hostDir / "scripts.js"
    html = hostDir / "index.html"
    keyedBytes : [(Key, Bytes)]
    keyedBytes =
      map
        (file -> (Key (FilePath.toText file), readFile file |> zlib.compress))
        [css, js, html]
    Cloud.submit default() do
      etags = keyedBytes |> (map cases (k, v) -> bytes.write database k v)
      debug.json
        "Uploaded files"
        (Json.array (etags |> (map cases ETag txt -> Json.text txt)))
    keys : [Key]
    keys = keyedBytes |> List.unzip |> at1
    hash = deployHttp default() (servePage.api database keys)
    ServiceName.assign (ServiceName.named "serve-page") hash

examples.servePage.deploy.doc : Doc
examples.servePage.deploy.doc =
  {{
  This deploy function reads from a directory called "assets" which contains a
  css, js, and html file. It compresses the files and uploads them to a
  {type Blobs} object store. It then deploys an http service that serves the
  files. If you'd like to run this example with a trivial set of files, you can
  use the {writeSampleAssets} function to write the files to disk.
  }}

examples.servePage.deploy.writeSampleAssets : '{IO, Exception} ()
examples.servePage.deploy.writeSampleAssets =
  do
    use IO.FilePath /
    use Text toUtf8
    hostDir = FilePath "assets"
    if FilePath.exists hostDir then
      raiseGeneric "Directory already exists" hostDir
    else
      createDirectory hostDir
      css = hostDir / "styles.css"
      js = hostDir / "scripts.js"
      html = hostDir / "index.html"
      writeFile css (toUtf8 writeSampleAssets.css)
      writeFile js (toUtf8 writeSampleAssets.js)
      writeFile html (toUtf8 writeSampleAssets.html)

examples.servePage.deploy.writeSampleAssets.css : Text
examples.servePage.deploy.writeSampleAssets.css =
  """
  header {
    color: #1E90FF; /* DodgerBlue */
    font-family: sans-serif;
  }
  
  p {
    font-family: sans-serif;
  }
  
  #unison-logo {
    width: 100px;
    height: 100px;
    cursor: pointer;
  }
  """

examples.servePage.deploy.writeSampleAssets.html : Text
examples.servePage.deploy.writeSampleAssets.html =
  """
  <!DOCTYPE html>
  <html lang="en">
  
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sample Page</title>
    <link rel="stylesheet" href="styles.css">
    <script src="scripts.js" defer></script>
  </head>
  
  <body>
    <header>
      <h1>Hello world!</h1>
    </header>
    <main>
      <p>This html, its css, and script files were all served from Blob storage. You should fill it with your own site!</p>
  
      <svg id="unison-logo" width="100%" height="100%" viewBox="0 0 14 14" fill="currentColor"
        xmlns="http://www.w3.org/2000/svg">
        <path fill-rule="evenodd" clip-rule="evenodd"
          d="M12.4255 3.88396C12.5728 4.03084 12.5728 4.27245 12.4255 4.41933C12.2781 4.56611 12.0357 4.56611 11.8883 4.41933C11.8181 4.34848 11.7786 4.25278 11.7786 4.15318C11.7786 3.94545 11.9502 3.77451 12.1586 3.77451C12.2585 3.77451 12.3545 3.81375 12.4256 3.88368L12.4255 3.88396ZM10.101 2.67362C10.3854 2.73037 10.6635 2.81492 10.9313 2.92603C11.1184 3.00356 11.2086 3.22155 11.1313 3.40898C11.0744 3.54687 10.9395 3.63726 10.7905 3.63726C10.7421 3.63726 10.6941 3.62769 10.6493 3.60909H10.6486C10.4285 3.51767 10.2 3.44784 9.9664 3.40056C9.96017 3.39947 9.95406 3.39825 9.94783 3.39689C9.72002 3.35208 9.48851 3.32893 9.25636 3.32775H9.23738C8.71087 3.32772 8.22275 3.04541 7.9594 2.58858C7.95777 2.58573 7.95601 2.58274 7.95452 2.57975C7.71294 2.16293 7.39237 1.79741 7.01087 1.50381C5.39448 0.260973 3.07902 0.566435 1.83819 2.18619C1.76839 2.27743 1.65998 2.33102 1.54526 2.33102C1.34279 2.33102 1.17619 2.16408 1.17619 1.96122C1.17619 1.8799 1.20296 1.80079 1.25233 1.73625C1.25613 1.73136 1.26006 1.7266 1.26399 1.72185C1.61619 1.266 2.05371 0.883267 2.55202 0.595099C4.66885 -0.629803 7.37586 0.0968651 8.59893 2.21798V2.21866L8.60205 2.22395C8.73138 2.44458 8.96621 2.58275 9.22152 2.58844H9.23793C9.52789 2.58843 9.81717 2.61696 10.1016 2.67362H10.101ZM0.938748 7.40106C0.941867 7.39509 0.945394 7.38913 0.94892 7.38329C1.07449 7.15898 1.07413 6.88464 0.947971 6.66067C0.944309 6.65456 0.940918 6.64846 0.937527 6.64235C0.355767 5.62773 0.198945 4.42288 0.5016 3.29314C0.544712 3.1323 0.691589 3.01961 0.858114 3.01961C1.06059 3.01961 1.22721 3.18621 1.22721 3.38869C1.22721 3.42096 1.22298 3.45308 1.21463 3.48424C0.962375 4.42608 1.09339 5.43053 1.5788 6.27616C1.58287 6.28294 1.58681 6.28986 1.5906 6.29691C1.84472 6.74743 1.84426 7.2998 1.58938 7.7499C1.58464 7.75844 1.57975 7.76699 1.57433 7.77526C1.33695 8.19126 1.18276 8.64948 1.12036 9.12436C0.854384 11.1452 2.27678 12.9983 4.29772 13.2644V13.2652C4.48043 13.2893 4.61854 13.4467 4.61854 13.631C4.61854 13.6471 4.61748 13.6632 4.61538 13.6792C4.58897 13.8796 4.40247 14.023 4.20196 13.9969H4.20264C3.62598 13.9209 3.06993 13.732 2.56636 13.4409C0.449924 12.2202 -0.276801 9.51768 0.938748 7.40106ZM1.57567 7.83712C1.58516 7.82889 1.59391 7.82021 1.60185 7.81114L1.60287 7.80994C1.59462 7.81942 1.58554 7.8285 1.57567 7.83712ZM5.92411 13.9186C5.72232 13.9723 5.51173 13.8517 5.45758 13.6515C5.40344 13.4511 5.52504 13.2419 5.72697 13.1882C5.75772 13.1804 5.78932 13.1765 5.82104 13.1765C6.03004 13.1765 6.20202 13.3472 6.20202 13.5546C6.20202 13.7235 6.08803 13.8728 5.92425 13.9186H5.92411ZM9.26784 11.4315C9.00745 11.4315 8.76555 11.5688 8.63223 11.7921C8.6306 11.7952 8.62883 11.7983 8.62706 11.8013C8.48168 12.0527 8.31191 12.2891 8.12021 12.5073C8.18166 12.4372 8.1818 12.4376 8.12021 12.5073C8.1164 12.5116 8.11259 12.5158 8.10865 12.5199C7.91991 12.733 7.71107 12.9275 7.48501 13.1007C7.32408 13.2241 7.08995 13.1935 6.96633 13.0328C6.84279 12.8721 6.87348 12.6384 7.03431 12.5149C7.22655 12.3676 7.40383 12.2017 7.56359 12.0198C7.50432 12.0877 7.50418 12.0868 7.56359 12.0198C7.56822 12.0146 7.57284 12.0096 7.57719 12.0048C7.72865 11.8304 7.86338 11.6421 7.97963 11.4425C7.9818 11.4384 7.98411 11.4345 7.98642 11.4304C8.25061 10.9746 8.73969 10.693 9.26716 10.693C9.75298 10.693 10.2341 10.5974 10.6829 10.4117C12.5666 9.63257 13.4634 7.47928 12.6898 5.5967C12.6881 5.59317 12.6865 5.5895 12.685 5.58583C12.6673 5.54197 12.6582 5.49512 12.6582 5.44783C12.6582 5.24519 12.8252 5.07843 13.0282 5.07843C13.176 5.07843 13.3102 5.16691 13.3684 5.30264C13.5915 5.84064 13.7063 6.41731 13.7063 6.99964C13.7063 9.4478 11.7188 11.4325 9.26702 11.4325L9.26784 11.4315ZM8.90925 4.10364C9.00698 4.09299 9.10507 4.08713 9.20352 4.08604C9.21359 4.08594 9.22367 4.08589 9.23375 4.08589C10.8564 4.08589 12.1917 5.41648 12.1917 7.03349C12.1917 8.65049 10.8564 9.9811 9.23375 9.9811C9.12557 9.9811 9.01746 9.97518 8.90993 9.96337C8.3027 9.91688 7.726 10.2485 7.46261 10.7957C6.99167 11.865 5.9257 12.5588 4.7539 12.5588C3.13114 12.5588 1.79581 11.2282 1.79581 9.61109C1.79581 8.97743 2.00085 8.36035 2.38034 7.85191C2.71505 7.35132 2.71057 6.69472 2.36906 6.19873C2.33374 6.15062 2.29991 6.10156 2.26757 6.05156C1.96073 5.5761 1.79753 5.02257 1.79753 4.45727C1.79753 2.84034 3.13273 1.5098 4.75535 1.5098C5.92658 1.5098 6.99212 2.20304 7.46329 3.27157C7.72665 3.81823 8.30274 4.14967 8.90952 4.10364H8.90925ZM2.91426 10.7573C3.30758 11.4466 4.03686 11.8726 4.82354 11.8726C6.03297 11.8726 7.02818 10.8657 7.02818 9.64216C7.02818 8.4186 6.03297 7.41177 4.82354 7.41177C4.43655 7.41177 4.0563 7.51485 3.72116 7.71062C2.67393 8.32252 2.30972 9.69771 2.91426 10.7573ZM7.32043 8.14944C7.71374 8.83871 8.44305 9.26471 9.22974 9.26471C10.4392 9.26471 11.4344 8.25788 11.4344 7.03431C11.4344 5.81076 10.4392 4.80392 9.22974 4.80392C8.84279 4.80392 8.46258 4.90699 8.12747 5.10272C7.08019 5.71456 6.71592 7.08977 7.32043 8.14944ZM4.82575 6.65686C6.03408 6.65648 7.02818 5.64976 7.02818 4.42647C7.02818 3.20292 6.03366 2.19608 4.82508 2.19608C3.61648 2.19608 2.62197 3.20292 2.62197 4.42647C2.62197 4.42661 2.62197 4.42674 2.62197 4.42688C2.62227 5.65031 3.61675 6.65686 4.82521 6.65686C4.82539 6.65686 4.82556 6.65686 4.82575 6.65686Z" />
      </svg>
    </main>
  </body>
  
  </html>
  """

examples.servePage.deploy.writeSampleAssets.js : Text
examples.servePage.deploy.writeSampleAssets.js =
  """
  document.addEventListener('DOMContentLoaded', () => {
  
    const logo = document.querySelector('#unison-logo');
    logo.addEventListener('click', () => {
      logo.setAttribute('fill', getRandomColor());
    });
  
    function getRandomColor() {
      const letters = '0123456789ABCDEF';
      let color = '#';
      for (let i = 0; i < 6; i++) {
        color += letters[Math.floor(Math.random() * 16)];
      }
      return color;
    }
  });
  """

examples.todoApp.deploy : '{IO, Exception} ServiceHash HttpRequest HttpResponse
examples.todoApp.deploy =
  do
    Cloud.run do
      environment = Environment.named "cloudTodoAppEnv"
      storagePool = Database.named "todoAppPool"
      todoTreeTable : OrderedTable Text TodoItem
      todoTreeTable =
        OrderedTable.named storagePool "todoItemTable" Universal.ordering
      Database.assign storagePool environment
      service = Route.run (routes.todoService todoTreeTable storagePool)
      serviceHash = deployHttp environment service
      unison_base_3_23_1.ignore
        (ServiceName.assign (ServiceName.named "todo-service") serviceHash)
      serviceHash

examples.todoApp.deploy.doc : Doc
examples.todoApp.deploy.doc =
  use todoApp deploy
  {{
  {{ docLink (docEmbedTermLink do deploy) }} is the runnable entry point for
  our Todo app service. Running it creates the service's cloud resources,
  deploys your application code to the cloud, and starts the http service with
  the given service name.
  
  After having authenticated your account with `auth.login`, enter `run deploy`
  in the UCM. The UCM will print the root URL of the deployed service. Unison
  Cloud http service URLs for named services can be called at
  
  `https://<username>.services.unison.cloud/s/<serviceName>`
  
  {{
  docCallout
    (Some {{ 🎉 }})
    {{
    Congratulations, your service and database are now deployed to the cloud
    and available to accept requests!
    }} }}
  
  Finally, run `add.run deploy.todoAppHash` to add the service hash value
  returned as a result of running {{ docLink (docEmbedTermLink do deploy) }} to
  your codebase. You'll use it for un-deploying a service later.
  }}

examples.todoApp.deploy.todoAppHash : ServiceHash HttpRequest HttpResponse
examples.todoApp.deploy.todoAppHash =
  ServiceHash "1HfufIqMS8L07Va4h17T3oSqrZcY03y0S-EHEWbSGlQ"

examples.todoApp.models.TodoItem.completed : TodoItem -> Boolean
examples.todoApp.models.TodoItem.completed = cases
  TodoItem _ completed _ -> completed

examples.todoApp.models.TodoItem.completed.modify :
  (Boolean ->{g} Boolean) -> TodoItem ->{g} TodoItem
examples.todoApp.models.TodoItem.completed.modify f = cases
  TodoItem entry completed id -> TodoItem entry (f completed) id

examples.todoApp.models.TodoItem.completed.set :
  Boolean -> TodoItem -> TodoItem
examples.todoApp.models.TodoItem.completed.set completed1 = cases
  TodoItem entry _ id -> TodoItem entry completed1 id

examples.todoApp.models.TodoItem.entry : TodoItem -> Text
examples.todoApp.models.TodoItem.entry = cases TodoItem entry _ _ -> entry

examples.todoApp.models.TodoItem.entry.modify :
  (Text ->{g} Text) -> TodoItem ->{g} TodoItem
examples.todoApp.models.TodoItem.entry.modify f = cases
  TodoItem entry completed id -> TodoItem (f entry) completed id

examples.todoApp.models.TodoItem.entry.set : Text -> TodoItem -> TodoItem
examples.todoApp.models.TodoItem.entry.set entry1 = cases
  TodoItem _ completed id -> TodoItem entry1 completed id

examples.todoApp.models.TodoItem.fromJson : '{Decoder} TodoItem
examples.todoApp.models.TodoItem.fromJson = do
  use Decoder text
  use object at
  entry = at "entry" text
  completed = at "completed" Decoder.boolean
  id = at "id" text
  TodoItem entry() completed() id()

examples.todoApp.models.TodoItem.id : TodoItem -> Text
examples.todoApp.models.TodoItem.id = cases TodoItem _ _ id -> id

examples.todoApp.models.TodoItem.id.modify :
  (Text ->{g} Text) -> TodoItem ->{g} TodoItem
examples.todoApp.models.TodoItem.id.modify f = cases
  TodoItem entry completed id -> TodoItem entry completed (f id)

examples.todoApp.models.TodoItem.id.set : Text -> TodoItem -> TodoItem
examples.todoApp.models.TodoItem.id.set id1 = cases
  TodoItem entry completed _ -> TodoItem entry completed id1

examples.todoApp.models.TodoItem.toJson : TodoItem -> Json
examples.todoApp.models.TodoItem.toJson = cases
  TodoItem entry completed id ->
    Json.object
      [ ("entry", Json.text entry)
      , ("completed", Json.boolean completed)
      , ("id", Json.text id)
      ]

examples.todoApp.README : Doc
examples.todoApp.README =
  {{
  # ✅ A simple todo app deployed on Unison Cloud
  
    This is a simple HTTP service todo app demonstrating the Storage API
    available on the [Unison Cloud](https://www.unison.cloud/). It uses the
    {type unison_cloud_19_0_0.Storage} ability to create a table of todo items
    and then exposes a simple set of routes for interacting with the items.
    
    ## Deploying the app to the cloud
    
       {{ todoApp.deploy.doc }}
    
    ## Calling the service
    
       {{ todoService.doc }}
    
    ## Un-deploying the service
    
       {{ todoApp.undeploy.doc }}
    
    ## Dependencies
    
       * [base](https://share.unison-lang.org/@unison/base)
         * The standard library for Unison
       * [cloud](https://share.unison-lang.org/@unison/cloud)
         * The Unison Cloud client which provides the {type Cloud} ability for
           managing and deploying services
       * [routes](https://share.unison-lang.org/@unison/routes)
         * A library for defining HTTP server routes
       * [json](https://share.unison-lang.org/@unison/json)
         * A library for encoding and decoding JSON data into Unison data types
  }}

examples.todoApp.resources.addKey :
  Table Type (Set Text) -> Text ->{Transaction, Exception} ()
examples.todoApp.resources.addKey keysTable key =
  match catch do Transaction.read keysTable (typeLink TodoItem) with
    Right keySet ->
      Transaction.write.tx
        keysTable (typeLink TodoItem) (Set.insert key keySet)
    Left _ ->
      Transaction.write.tx keysTable (typeLink TodoItem) (Set.singleton key)

examples.todoApp.resources.deleteKey :
  Table Type (Set Text) -> Text ->{Transaction, Exception} ()
examples.todoApp.resources.deleteKey keysTable key =
  match catch do Transaction.read keysTable (typeLink TodoItem) with
    Right keySet ->
      Transaction.write.tx
        keysTable (typeLink TodoItem) (Set.delete key keySet)
    Left _ -> ()

examples.todoApp.routes.todoService :
  OrderedTable Text TodoItem
  -> Database
  -> '{Route, Exception, unison_cloud_19_0_0.Storage, Remote, Log} ()
examples.todoApp.routes.todoService todoTable db =
  use Parser / s
  use Route <|> noCapture
  use Text ++
  use TodoItem toJson
  healthCheck : '{Route, Exception, Remote} ()
  healthCheck = do
    name = noCapture GET (s "health")
    ok.text "ok 👍"
  getTodoItem : '{Route, Exception, Remote} ()
  getTodoItem = do
    id = route GET (s "todo" / Parser.text)
    match catch do OrderedTable.read todoTable id with
      Right todoItem -> ok.json (toJson todoItem)
      Left _         -> notFound.text ("todo item not found " ++ id)
  getTodoItems : '{Route, Exception, Remote, Log} ()
  getTodoItems = do
    name = noCapture GET (s "todos")
    records = OrderedTable.toStream todoTable |> Stream.toList
    jsonRecords = Json.array (List.map (r -> at2 r |> toJson) records)
    info.json "records" jsonRecords
    ok.json jsonRecords
  putTodoItem : '{Route, Exception, Remote} ()
  putTodoItem = do
    name = noCapture PUT (s "todo")
    todoItem : {Route, Exception} TodoItem
    todoItem = decodeJson TodoItem.fromJson
    key = TodoItem.id todoItem
    match catch do randomly do BTree.write todoTable key todoItem with
      Left e  -> badRequest.text ("failed to write todo item " ++ key)
      Right _ -> ok.text ("created todo item " ++ key)
  deleteTodoItem : '{Route, Exception, Remote} ()
  deleteTodoItem = do
    id = route DELETE (s "todo" / Parser.text)
    match catch do OrderedTable.delete todoTable id with
      Left _  -> badRequest.text ("todo item failed to be  found " ++ id)
      Right _ -> ok.text ("deleted todo item " ++ id)
  getTodoItem
    <|> putTodoItem
    <|> deleteTodoItem
    <|> getTodoItems
    <|> healthCheck

examples.todoApp.routes.todoService.doc : Doc
examples.todoApp.routes.todoService.doc =
  {{
  {{ docLink (docEmbedTermLink do routes.todoService) }} defines the following
  routes:
  
  * GET /health - returns "ok 👍" if the service is running
  * GET /todo/<id> - returns the todo item with the given id
  * GET /todos - returns all todo items
  * PUT /todo - creates or updates a {type TodoItem}
  * DELETE /todo/<id> - deletes the todo item with the given id
  }}

examples.todoApp.undeploy : '{IO, Exception} ()
examples.todoApp.undeploy = Cloud.main do Cloud.undeploy todoAppHash

examples.todoApp.undeploy.doc : Doc
examples.todoApp.undeploy.doc =
  {{
  {{ docLink (docEmbedTermLink do todoApp.undeploy) }} removes a deployed
  service from the cloud. It takes a {type ServiceHash} value as an argument.
  The {type ServiceHash} is returned as a result of running
  {{ docLink (docEmbedTermLink do todoApp.deploy) }}.
  }}

exercises.admin.console.print :
  (i ->{g1} Text)
  -> (o ->{g} Text)
  -> ExerciseResult i o
  ->{g, g1, IO, Exception} ()
exercises.admin.console.print iText oText = cases
  ExerciseResult number title res ->
    use Text ++
    resultText = List.map (r -> Result.toText iText oText r) res
    printLine
      ("\nExercise "
        ++ Exercise.Number.toText number
        ++ " "
        ++ title
        ++ "\n\n"
        ++ Text.join "\n" resultText
        ++ "\n")

exercises.admin.console.print.HttpRequest : HttpRequest ->{Exception} Text
exercises.admin.console.print.HttpRequest = cases
  HttpRequest.HttpRequest method _ uri headers (Body body) ->
    use Text ++
    m = Method.toText method
    u = URI.toText uri
    b = fromUtf8 body
    m ++ " " ++ u ++ " " ++ b

exercises.admin.console.print.HttpResponse : HttpResponse ->{Exception} Text
exercises.admin.console.print.HttpResponse = cases
  HttpResponse.HttpResponse (Status code _) _ (Headers headers) (Body bytes) ->
    use List map
    use Text ++ join
    headersText =
      Map.toList headers
        |> (map cases (k, vs) -> map (v -> k ++ ": " ++ v) vs |> join "\n")
        |> join "\n"
    Nat.toText code ++ " " ++ fromUtf8 bytes

exercises.admin.console.printProgress : TrackProgress ->{IO, Exception} ()
exercises.admin.console.printProgress = cases
  TrackProgress attempted _ ->
    use Exercise Number.Number
    use List sort
    use models Status
    groupFn : (Exercise.Number, Status) -> (Exercise.Number, Status) -> Boolean
    groupFn a b =
      (Number.Number n1 _, Number.Number n2 _) = (at1 a, at1 b)
      n1 === n2
    groupedAttemptsTuple : [(Text, Text)]
    groupedAttemptsTuple =
      groupSublistsBy groupFn (sort attempted)
        |> List.map formatTextTuple
        |> sort
    statusToEmoji = cases
      status ->
        match status with
          Status.Passed        -> "⭐️"
          models.Status.Failed -> "🔁"
          NotStarted           -> "🔏"
    mapVersion =
      groupMapReduce
        (cases (Number.Number n _, status) -> n)
        (cases (exn, status) -> [status])
        (List.++)
        (sort attempted)
    keyedMap = Map.mapKeys Nat.toText mapVersion
    emojiMap =
      Map.map
        (cases status -> List.map statusToEmoji status |> Text.join " ")
        keyedMap
    emojiMapList = Map.toList emojiMap
    printLine ""
    emojiMapList
      |> (foreach.deprecated cases
        (header, emojis) -> printLine (header Text.++ "\n" Text.++ emojis))
    printLine ""

exercises.admin.console.printProgress.formatTextTuple :
  List.Nonempty (Exercise.Number, models.Status) -> (Text, Text)
exercises.admin.console.printProgress.formatTextTuple group =
  attemptString attempted =
    statusToEmoji = cases
      (number, status) ->
        match status with
          Status.Passed        -> "⭐️"
          models.Status.Failed -> "🔁"
          NotStarted           -> "🔏"
    List.Nonempty.map statusToEmoji attempted
      |> List.Nonempty.toList
      |> Text.join " "
  groupEmojis = attemptString group
  headerElem = at1 (Nonempty.head group)
  headerText =
    (Exercise.Number.Number n _) = headerElem
    Nat.toText n
  (headerText, groupEmojis)

exercises.admin.console.printProgress.padHeader :
  Exercise.Number -> Text -> (Text, Text)
exercises.admin.console.printProgress.padHeader headerNum emojiList =
  use Nat - >
  use Text ++ repeat size
  header =
    (Exercise.Number.Number n _) = headerNum
    Nat.toText n
  headerLength = size header
  emojiLength = size emojiList
  if headerLength > emojiLength then
    padding = repeat (headerLength - emojiLength) " "
    (header, emojiList ++ padding)
  else
    padding = repeat (emojiLength - headerLength) " "
    (header ++ padding, emojiList)

exercises.admin.console.Reporting.toText :
  (i ->{g1} Text) -> (o ->{g} Text) -> Reporting i o ->{g, g1} Text
exercises.admin.console.Reporting.toText iText oText ioReport =
  use Optional None fold
  use Text ++
  textIO =
    match ioReport with
      InputOutput None None -> ""
      InputOutput maybeIn maybeOut ->
        inputText = fold (do "") (i -> "Input: " ++ iText i ++ " ") maybeIn
        outputText = fold (do "") (o -> "Output: " ++ oText o) maybeOut
        inputText ++ "\n" ++ outputText
      Reporting.Expected o -> "Expected: " ++ oText o
      InputOutputExpected i o e ->
        inputText = iText i
        outputText = oText o
        expected = oText e
        "Input: "
          ++ inputText
          ++ "\n"
          ++ "Output: "
          ++ outputText
          ++ "\nExpected: "
          ++ expected
      ErrorReporting (Failure tpe msg any) io ->
        "Failure: "
          ++ msg
          ++ "\n"
          ++ exercises.admin.console.Reporting.toText iText oText io
  textIO

exercises.admin.console.Result.toText :
  (i ->{g1} Text) -> (o ->{g} Text) -> models.Result i o ->{g, g1} Text
exercises.admin.console.Result.toText iText oText = cases
  Correct label r ->
    "✅ " Text.++ label Text.++ "\n" Text.++ Reporting.toText iText oText r
  Incorrect label r ->
    "❌ " Text.++ label Text.++ "\n" Text.++ Reporting.toText iText oText r
  Result.Error label r ->
    "🔥 " Text.++ label Text.++ "\n" Text.++ Reporting.toText iText oText r
  PassThrough label r ->
    "🆗 " Text.++ label Text.++ "\n" Text.++ Reporting.toText iText oText r

exercises.admin.console.TrackProgress.attempted :
  TrackProgress -> [(Exercise.Number, models.Status)]
exercises.admin.console.TrackProgress.attempted = cases
  TrackProgress attempted _ -> attempted

exercises.admin.console.TrackProgress.attempted.modify :
  ([(Exercise.Number, models.Status)] ->{g} [(Exercise.Number, models.Status)])
  -> TrackProgress
  ->{g} TrackProgress
exercises.admin.console.TrackProgress.attempted.modify f = cases
  TrackProgress attempted next -> TrackProgress (f attempted) next

exercises.admin.console.TrackProgress.attempted.set :
  [(Exercise.Number, models.Status)] -> TrackProgress -> TrackProgress
exercises.admin.console.TrackProgress.attempted.set attempted1 = cases
  TrackProgress _ next -> TrackProgress attempted1 next

exercises.admin.console.TrackProgress.next :
  TrackProgress -> Optional Exercise.Number
exercises.admin.console.TrackProgress.next = cases TrackProgress _ next -> next

exercises.admin.console.TrackProgress.next.modify :
  (Optional Exercise.Number ->{g} Optional Exercise.Number)
  -> TrackProgress
  ->{g} TrackProgress
exercises.admin.console.TrackProgress.next.modify f = cases
  TrackProgress attempted next -> TrackProgress attempted (f next)

exercises.admin.console.TrackProgress.next.set :
  Optional Exercise.Number -> TrackProgress -> TrackProgress
exercises.admin.console.TrackProgress.next.set next1 = cases
  TrackProgress attempted _ -> TrackProgress attempted next1

exercises.admin.models.Exercise.Number.toText : Exercise.Number -> Text
exercises.admin.models.Exercise.Number.toText = cases
  Exercise.Number.Number n (Part p) ->
    Nat.toText n Text.++ " Part " Text.++ Nat.toText p

exercises.admin.models.ExerciseResult.isSuccess :
  ExerciseResult a b -> models.Status
exercises.admin.models.ExerciseResult.isSuccess = cases
  ExerciseResult _ _ results ->
    if List.all Result.isSuccess results then Status.Passed
    else models.Status.Failed

exercises.admin.models.Result.isSuccess : models.Result i o -> Boolean
exercises.admin.models.Result.isSuccess = cases
  Correct _ _      -> true
  Incorrect _ _    -> false
  PassThrough _ _  -> true
  Result.Error _ _ -> false

exercises.admin.resultsService.admin.addChallenge :
  resultsService.Storage
  -> Track.Number
  -> Exercise.Number
  ->{Exception, unison_cloud_19_0_0.Storage, Random} ()
exercises.admin.resultsService.admin.addChallenge storage track challenge =
  use BTree write.tx
  use List :+
  tracksTable = tracks storage
  transact.random (resultsService.Storage.database storage) do
    trackChallenges = OrderedTable.tryRead.tx tracksTable track
    match trackChallenges with
      Some challenges
        | List.contains challenge challenges  ->
          Exception.raise
            (Failure
              (typeLink ChallengeExistsForTrack)
              "Challenge number already exists for this track"
              (Any challenge))
        | otherwise                           ->
          write.tx tracksTable track (challenges :+ challenge)
      Optional.None -> write.tx tracksTable track [challenge]

exercises.admin.resultsService.admin.countSubmissionsByExercise :
  '{IO, Exception} [(Exercise.Number, Nat)]
exercises.admin.resultsService.admin.countSubmissionsByExercise = 
  Cloud.main do
    use Nat +
    storage = createStorage()
    progressTable = userProgress storage
    Cloud.submit resultsService.env() do
      OrderedTable.toStream progressTable
        |> (Stream.filter cases
             ((user, track, exercise), attempts) ->
               Boolean.not (user === models.User.User "rlmark" "Rebecca"))
        |> (Stream.map cases
             ((user, track, exercise), attempts) ->
               (exercise, List.size attempts))
        |> Stream.toList
        |> Map.fromListWith (+)
        |> Map.toList

exercises.admin.resultsService.admin.countSubmissionsByUserExercise :
  '{IO, Exception} [((models.User, Track.Number, Exercise.Number), Nat)]
exercises.admin.resultsService.admin.countSubmissionsByUserExercise = 
  Cloud.main do
    storage = createStorage()
    progressTable = userProgress storage
    Cloud.submit resultsService.env() do
      OrderedTable.toStream progressTable
        |> (Stream.map cases
             (userInfo, attempts) -> (userInfo, List.size attempts))
        |> Stream.toList

exercises.admin.resultsService.admin.replaceAllTrackChallenges :
  resultsService.Storage -> Track.Number -> [Exercise.Number] ->{Remote} ()
exercises.admin.resultsService.admin.replaceAllTrackChallenges
  storage track numbers =
  BTree.write (tracks storage) track numbers

exercises.admin.resultsService.admin.setTrackState : '{IO, Exception} ()
exercises.admin.resultsService.admin.setTrackState = 
  Cloud.main do
    storage = createStorage()
    track = Track.Number.Number 1
    numbers =
      [ Exercise.Number.Number 1 (Part 1)
      , Exercise.Number.Number 2 (Part 1)
      , Exercise.Number.Number 2 (Part 2)
      , Exercise.Number.Number 2 (Part 3)
      , Exercise.Number.Number 3 (Part 1)
      , Exercise.Number.Number 3 (Part 2)
      , Exercise.Number.Number 3 (Part 3)
      , Exercise.Number.Number 3 (Part 4)
      , Exercise.Number.Number 4 (Part 1)
      , Exercise.Number.Number 4 (Part 2)
      ]
    Cloud.submit resultsService.env() do
      replaceAllTrackChallenges storage track numbers

exercises.admin.resultsService.createStorage :
  '{Exception, Cloud} resultsService.Storage
exercises.admin.resultsService.createStorage =
  do
    use Universal ordering
    use models User
    database = Database.named "cloudExerciseDB3"
    Database.assign database resultsService.env()
    userProgress :
      OrderedTable (User, Track.Number, Exercise.Number) [AttemptRecord]
    userProgress = OrderedTable.named database "userProgress3" ordering
    tracksByUser : OrderedTable (Track.Number, User) [AttemptRecord]
    tracksByUser = OrderedTable.named database "tracksByUser3" ordering
    usersTracks : OrderedTable User [Track.Number]
    usersTracks = OrderedTable.named database "usersTracks" ordering
    tracks = OrderedTable.named database "tracks4" ordering
    resultsService.Storage.Storage
      database userProgress tracksByUser usersTracks tracks

exercises.admin.resultsService.db.addResult :
  resultsService.Storage
  -> models.User
  -> AttemptRecord
  ->{Exception, unison_cloud_19_0_0.Storage, Random} ()
exercises.admin.resultsService.db.addResult storage user attempt =
  use BTree write.tx
  use List +:
  progressTable = userProgress storage
  number = AttemptRecord.number attempt
  trackNum = AttemptRecord.track attempt
  transact.random (resultsService.Storage.database storage) do
    maybeResult =
      OrderedTable.tryRead.tx progressTable (user, trackNum, number)
    match maybeResult with
      Optional.None ->
        write.tx progressTable (user, trackNum, number) [attempt]
      Some resultList ->
        write.tx progressTable (user, trackNum, number) (attempt +: resultList)

exercises.admin.resultsService.db.getAllTrackChallenges :
  resultsService.Storage -> Track.Number ->{Remote} [Exercise.Number]
exercises.admin.resultsService.db.getAllTrackChallenges storage track =
  OrderedTable.read (tracks storage) track

exercises.admin.resultsService.db.getDistinctLatestAttempts :
  resultsService.Storage
  -> models.User
  -> Track.Number
  ->{Remote} [AttemptRecord]
exercises.admin.resultsService.db.getDistinctLatestAttempts storage user track =
  trackAttempts = getUserTrackResults storage user track
  List.distinctBy (attempt -> AttemptRecord.number attempt) trackAttempts

exercises.admin.resultsService.db.getUserTrackProgress :
  resultsService.Storage
  -> models.User
  -> Track.Number
  ->{Remote} TrackProgress
exercises.admin.resultsService.db.getUserTrackProgress storage user track =
  use AttemptRecord number
  use List ++
  use Set fromList
  trackAttempts = getDistinctLatestAttempts storage user track
  exerciseKeys = List.map number trackAttempts |> fromList
  trackExercises = getAllTrackChallenges storage track |> fromList
  unattemptedExercises = Set.difference trackExercises exerciseKeys
  notAttempted =
    Set.toList unattemptedExercises
      |> List.sort
      |> List.map (n -> (n, NotStarted))
  started = List.map (a -> (number a, AttemptRecord.status a)) trackAttempts
  TrackProgress
    (started ++ notAttempted) (List.head notAttempted |> Optional.map at1)

exercises.admin.resultsService.db.getUserTrackResults :
  resultsService.Storage
  -> models.User
  -> Track.Number
  ->{Remote} [AttemptRecord]
exercises.admin.resultsService.db.getUserTrackResults storage user track =
  progressTable = userProgress storage
  prefixOrdering : (k1, k2) -> (k1, k2, k3) -> Ordering
  prefixOrdering tup = cases
    (t1, t2, _) -> Universal.ordering (at1 tup, at2 tup) (t1, t2)
  streamResults =
    rangeClosed.prefix progressTable prefixOrdering (user, track) (user, track)
      |> Stream.map at2
  Stream.toList streamResults |> List.flatMap Function.id

exercises.admin.resultsService.db.readUserResults :
  resultsService.Storage
  -> (models.User, Track.Number, Exercise.Number)
  ->{Remote} Optional [AttemptRecord]
exercises.admin.resultsService.db.readUserResults storage userTup =
  progressTable = userProgress storage
  OrderedTable.tryRead progressTable userTup

exercises.admin.resultsService.db.userResultsPrefix :
  resultsService.Storage -> models.User ->{Remote} [AttemptRecord]
exercises.admin.resultsService.db.userResultsPrefix storage user =
  progressTable = userProgress storage
  streamResults =
    rangeClosed.prefix progressTable tup3.prefixOrdering user user
      |> Stream.map at2
  Stream.toList streamResults |> List.flatMap Function.id

exercises.admin.resultsService.db.userStartsTrack :
  resultsService.Storage
  -> models.User
  -> Track.Number
  ->{Exception, unison_cloud_19_0_0.Storage, Random} ()
exercises.admin.resultsService.db.userStartsTrack storage user track = 
  transact.random (resultsService.Storage.database storage) do
    use BTree write.tx
    use List :+
    maybeTracks = OrderedTable.tryRead.tx (usersTracks storage) user
    match maybeTracks with
      Optional.None -> write.tx (usersTracks storage) user [track]
      Some tracks
        | List.contains track tracks  -> ()
        | otherwise                   ->
          write.tx (usersTracks storage) user (tracks :+ track)

exercises.admin.resultsService.deploys.putUserAttempt :
  '{IO, Exception} ServiceHash (models.User, AttemptRecord) ()
exercises.admin.resultsService.deploys.putUserAttempt = Cloud.main do
  storage = createStorage()
  Cloud.deploy resultsService.env() (putUserAttempt.impl storage)

exercises.admin.resultsService.deploys.putUserAttempt.impl :
  resultsService.Storage
  -> (models.User, AttemptRecord)
  ->{Exception, unison_cloud_19_0_0.Storage, Remote, Random} ()
exercises.admin.resultsService.deploys.putUserAttempt.impl storage = cases
  (userEntity, res) -> addResult storage userEntity res

exercises.admin.resultsService.deploys.trackProgressService :
  '{IO, Exception} ServiceHash (models.User, Track.Number) TrackProgress
exercises.admin.resultsService.deploys.trackProgressService = 
  Cloud.main do
    storage = createStorage()
    Cloud.deploy resultsService.env() cases
      (user, track) -> getUserTrackProgress storage user track

exercises.admin.resultsService.env : '{Exception, Cloud} Environment
exercises.admin.resultsService.env = do Environment.named "cloud-exercises-env"

exercises.admin.resultsService.hashes.putUserAttempt2 :
  ServiceHash (models.User, AttemptRecord) ()
exercises.admin.resultsService.hashes.putUserAttempt2 =
  ServiceHash "vsdfaenuf2fsco6q3d4qd5jj2vnvfuanjdcaxfugrovxllrdeu7q"

exercises.admin.resultsService.hashes.putUserAttemptv1 :
  ServiceHash (models.User, AttemptRecord) ()
exercises.admin.resultsService.hashes.putUserAttemptv1 =
  ServiceHash "ltl54ecq3qjmsxkc3gf4ylubuex3drji37qjwfkwakej7fh7kxya"

exercises.admin.resultsService.hashes.putUserAttemptV3 :
  ServiceHash (models.User, AttemptRecord) ()
exercises.admin.resultsService.hashes.putUserAttemptV3 =
  ServiceHash "psptd2zba3bjet5q7bnvx7sllu74ccmx3atqa34drlc2wkf3fn6q"

exercises.admin.resultsService.hashes.trackProgressV1 :
  ServiceHash (models.User, Track.Number) TrackProgress
exercises.admin.resultsService.hashes.trackProgressV1 =
  ServiceHash "fkzph3jzq7ex4zapvnyiiwoc33j5xg7sqpjutnlcbvfz3gxuifua"

exercises.admin.resultsService.hashes.trackProgressv2 :
  ServiceHash (models.User, Track.Number) TrackProgress
exercises.admin.resultsService.hashes.trackProgressv2 =
  ServiceHash "627hlxcjeoehluyh3jczfrdnpudyedrq66wp3cgthcynzblgseuq"

exercises.admin.resultsService.hashes.trackProgressV3 :
  ServiceHash (models.User, Track.Number) TrackProgress
exercises.admin.resultsService.hashes.trackProgressV3 =
  ServiceHash "gii56rv3af2btb7iog2ghaqxdyia3zlz6q6b652wo4fq7zjucx6q"

exercises.admin.resultsService.hashes.v1 :
  ServiceHash (models.User, AttemptRecord) ()
exercises.admin.resultsService.hashes.v1 =
  ServiceHash "peixnalvrngazsxfyipmunqffdquog5mdep6yx74rypdgpiyhxqq"

exercises.admin.resultsService.hashes.v2 :
  ServiceHash (models.User, AttemptRecord) ()
exercises.admin.resultsService.hashes.v2 =
  ServiceHash "2tmd722s2nj722wrodv6c54wydepyx3jse7i6yk7mgqgu6elbd5a"

exercises.admin.resultsService.hashes.v3 :
  ServiceHash (models.User, AttemptRecord) ()
exercises.admin.resultsService.hashes.v3 =
  ServiceHash "ybzgqofhr326eqwxcm5ci7oiybxgx7c7ds34c53c56j53jyt6qea"

exercises.admin.resultsService.impl.getUser : '{IO, Exception} (Text, Text)
exercises.admin.resultsService.impl.getUser =
  do
    use HostName toText
    use Text ++
    credentialsHost = match getEnv.impl "UNISON_CLOUD_CREDENTIALS_HOST" with
      Right host -> HostName host
      Left _     -> HostName "api.unison-lang.org"
    decoder =
      do
        use Decoder text
        use object at at!
        activeProfile = at! "active_profile" text
        hostName = toText credentialsHost
        getUserInfo = do
          getHandle = at! "handle" text
          getName = at! "name" text
          (getHandle, getName)
        handleText =
          at!
            "credentials"
            (at activeProfile (at hostName (at "user_info" getUserInfo)))
        handleText
    out = do
      use up.FilePath /
      path = dataDirectory() / "unisonlanguage" / "credentials.json"
      readFile path |> fromUtf8 |> Decoder.run decoder
    userFriendlyMsg =
      "Error reading credentials for '"
        ++ toText credentialsHost
        ++ "'. You may need to run the ucm `auth.login` command."
    catch out
      |> Either.mapLeft
           (e ->
             Failure
               (typeLink impl.CredentialsError)
               userFriendlyMsg
               (Any (Failure.message e)))
      |> Either.toException

exercises.admin.resultsService.models.AttemptRecord.fromChallengeResult :
  OffsetDateTime -> Track.Number -> ExerciseResult i o -> AttemptRecord
exercises.admin.resultsService.models.AttemptRecord.fromChallengeResult
  timeStamp tmpTrack = cases
  cr@(ExerciseResult number title res) ->
    AttemptRecord tmpTrack number timeStamp (ExerciseResult.isSuccess cr)

exercises.admin.resultsService.models.AttemptRecord.number :
  AttemptRecord -> Exercise.Number
exercises.admin.resultsService.models.AttemptRecord.number = cases
  AttemptRecord _ number _ _ -> number

exercises.admin.resultsService.models.AttemptRecord.number.modify :
  (Exercise.Number ->{g} Exercise.Number) -> AttemptRecord ->{g} AttemptRecord
exercises.admin.resultsService.models.AttemptRecord.number.modify f = cases
  AttemptRecord track number timeStamp status ->
    AttemptRecord track (f number) timeStamp status

exercises.admin.resultsService.models.AttemptRecord.number.set :
  Exercise.Number -> AttemptRecord -> AttemptRecord
exercises.admin.resultsService.models.AttemptRecord.number.set number1 = cases
  AttemptRecord track _ timeStamp status ->
    AttemptRecord track number1 timeStamp status

exercises.admin.resultsService.models.AttemptRecord.status :
  AttemptRecord -> models.Status
exercises.admin.resultsService.models.AttemptRecord.status = cases
  AttemptRecord _ _ _ status -> status

exercises.admin.resultsService.models.AttemptRecord.status.modify :
  (models.Status ->{g} models.Status) -> AttemptRecord ->{g} AttemptRecord
exercises.admin.resultsService.models.AttemptRecord.status.modify f = cases
  AttemptRecord track number timeStamp status ->
    AttemptRecord track number timeStamp (f status)

exercises.admin.resultsService.models.AttemptRecord.status.set :
  models.Status -> AttemptRecord -> AttemptRecord
exercises.admin.resultsService.models.AttemptRecord.status.set status1 = cases
  AttemptRecord track number timeStamp _ ->
    AttemptRecord track number timeStamp status1

exercises.admin.resultsService.models.AttemptRecord.timeStamp :
  AttemptRecord -> OffsetDateTime
exercises.admin.resultsService.models.AttemptRecord.timeStamp = cases
  AttemptRecord _ _ timeStamp _ -> timeStamp

exercises.admin.resultsService.models.AttemptRecord.timeStamp.modify :
  (OffsetDateTime ->{g} OffsetDateTime) -> AttemptRecord ->{g} AttemptRecord
exercises.admin.resultsService.models.AttemptRecord.timeStamp.modify f = cases
  AttemptRecord track number timeStamp status ->
    AttemptRecord track number (f timeStamp) status

exercises.admin.resultsService.models.AttemptRecord.timeStamp.set :
  OffsetDateTime -> AttemptRecord -> AttemptRecord
exercises.admin.resultsService.models.AttemptRecord.timeStamp.set timeStamp1 = cases
  AttemptRecord track number _ status ->
    AttemptRecord track number timeStamp1 status

exercises.admin.resultsService.models.AttemptRecord.toText :
  AttemptRecord -> Text
exercises.admin.resultsService.models.AttemptRecord.toText = cases
  AttemptRecord track number timeStamp status ->
    "Track: "
      Text.++ Track.Number.toText track
      Text.++ ", Number: "
      Text.++ Exercise.Number.toText number
      Text.++ ", Time: "
      Text.++ OffsetDateTime.toBasicISO8601 timeStamp
      Text.++ ", Success: "
      Text.++ models.Status.toText status

exercises.admin.resultsService.models.AttemptRecord.track :
  AttemptRecord -> Track.Number
exercises.admin.resultsService.models.AttemptRecord.track = cases
  AttemptRecord track _ _ _ -> track

exercises.admin.resultsService.models.AttemptRecord.track.modify :
  (Track.Number ->{g} Track.Number) -> AttemptRecord ->{g} AttemptRecord
exercises.admin.resultsService.models.AttemptRecord.track.modify f = cases
  AttemptRecord track number timeStamp status ->
    AttemptRecord (f track) number timeStamp status

exercises.admin.resultsService.models.AttemptRecord.track.set :
  Track.Number -> AttemptRecord -> AttemptRecord
exercises.admin.resultsService.models.AttemptRecord.track.set track1 = cases
  AttemptRecord _ number timeStamp status ->
    AttemptRecord track1 number timeStamp status

exercises.admin.resultsService.models.Status.toText : models.Status -> Text
exercises.admin.resultsService.models.Status.toText = cases
  Status.Passed        -> "Passed"
  models.Status.Failed -> "Failed"
  NotStarted           -> "Not Started"

exercises.admin.resultsService.models.Track.number : Track -> Track.Number
exercises.admin.resultsService.models.Track.number = cases
  Track number _ -> number

exercises.admin.resultsService.models.Track.number.modify :
  (Track.Number ->{g} Track.Number) -> Track ->{g} Track
exercises.admin.resultsService.models.Track.number.modify f = cases
  Track number title -> Track (f number) title

exercises.admin.resultsService.models.Track.number.set :
  Track.Number -> Track -> Track
exercises.admin.resultsService.models.Track.number.set number1 = cases
  Track _ title -> Track number1 title

exercises.admin.resultsService.models.Track.Number.toText :
  Track.Number -> Text
exercises.admin.resultsService.models.Track.Number.toText = cases
  Track.Number.Number n -> Nat.toText n

exercises.admin.resultsService.models.Track.title : Track -> Text
exercises.admin.resultsService.models.Track.title = cases
  Track _ title -> title

exercises.admin.resultsService.models.Track.title.modify :
  (Text ->{g} Text) -> Track ->{g} Track
exercises.admin.resultsService.models.Track.title.modify f = cases
  Track number title -> Track number (f title)

exercises.admin.resultsService.models.Track.title.set : Text -> Track -> Track
exercises.admin.resultsService.models.Track.title.set title1 = cases
  Track number _ -> Track number title1

exercises.admin.resultsService.Storage.database :
  resultsService.Storage -> Database
exercises.admin.resultsService.Storage.database = cases
  resultsService.Storage.Storage database _ _ _ _ -> database

exercises.admin.resultsService.Storage.database.modify :
  (Database ->{g} Database)
  -> resultsService.Storage
  ->{g} resultsService.Storage
exercises.admin.resultsService.Storage.database.modify f = cases
  resultsService.Storage.Storage
    database userProgress tracksByUser usersTracks tracks ->
    resultsService.Storage.Storage
      (f database) userProgress tracksByUser usersTracks tracks

exercises.admin.resultsService.Storage.database.set :
  Database -> resultsService.Storage -> resultsService.Storage
exercises.admin.resultsService.Storage.database.set database1 = cases
  resultsService.Storage.Storage _ userProgress tracksByUser usersTracks tracks ->
    resultsService.Storage.Storage
      database1 userProgress tracksByUser usersTracks tracks

exercises.admin.resultsService.Storage.tracks :
  resultsService.Storage -> OrderedTable Track.Number [Exercise.Number]
exercises.admin.resultsService.Storage.tracks = cases
  resultsService.Storage.Storage _ _ _ _ tracks -> tracks

exercises.admin.resultsService.Storage.tracks.modify :
  (OrderedTable Track.Number [Exercise.Number]
  ->{g} OrderedTable Track.Number [Exercise.Number])
  -> resultsService.Storage
  ->{g} resultsService.Storage
exercises.admin.resultsService.Storage.tracks.modify f = cases
  resultsService.Storage.Storage
    database userProgress tracksByUser usersTracks tracks ->
    resultsService.Storage.Storage
      database userProgress tracksByUser usersTracks (f tracks)

exercises.admin.resultsService.Storage.tracks.set :
  OrderedTable Track.Number [Exercise.Number]
  -> resultsService.Storage
  -> resultsService.Storage
exercises.admin.resultsService.Storage.tracks.set tracks1 = cases
  resultsService.Storage.Storage
    database userProgress tracksByUser usersTracks _ ->
    resultsService.Storage.Storage
      database userProgress tracksByUser usersTracks tracks1

exercises.admin.resultsService.Storage.tracksByUser :
  resultsService.Storage
  -> OrderedTable (Track.Number, models.User) [AttemptRecord]
exercises.admin.resultsService.Storage.tracksByUser = cases
  resultsService.Storage.Storage _ _ tracksByUser _ _ -> tracksByUser

exercises.admin.resultsService.Storage.tracksByUser.modify :
  (OrderedTable (Track.Number, models.User) [AttemptRecord]
  ->{g} OrderedTable (Track.Number, models.User) [AttemptRecord])
  -> resultsService.Storage
  ->{g} resultsService.Storage
exercises.admin.resultsService.Storage.tracksByUser.modify f = cases
  resultsService.Storage.Storage
    database userProgress tracksByUser usersTracks tracks ->
    resultsService.Storage.Storage
      database userProgress (f tracksByUser) usersTracks tracks

exercises.admin.resultsService.Storage.tracksByUser.set :
  OrderedTable (Track.Number, models.User) [AttemptRecord]
  -> resultsService.Storage
  -> resultsService.Storage
exercises.admin.resultsService.Storage.tracksByUser.set tracksByUser1 = cases
  resultsService.Storage.Storage database userProgress _ usersTracks tracks ->
    resultsService.Storage.Storage
      database userProgress tracksByUser1 usersTracks tracks

exercises.admin.resultsService.Storage.userProgress :
  resultsService.Storage
  -> OrderedTable (models.User, Track.Number, Exercise.Number) [AttemptRecord]
exercises.admin.resultsService.Storage.userProgress = cases
  resultsService.Storage.Storage _ userProgress _ _ _ -> userProgress

exercises.admin.resultsService.Storage.userProgress.modify :
  (OrderedTable (models.User, Track.Number, Exercise.Number) [AttemptRecord]
  ->{g} OrderedTable
    (models.User, Track.Number, Exercise.Number) [AttemptRecord])
  -> resultsService.Storage
  ->{g} resultsService.Storage
exercises.admin.resultsService.Storage.userProgress.modify f = cases
  resultsService.Storage.Storage
    database userProgress tracksByUser usersTracks tracks ->
    resultsService.Storage.Storage
      database (f userProgress) tracksByUser usersTracks tracks

exercises.admin.resultsService.Storage.userProgress.set :
  OrderedTable (models.User, Track.Number, Exercise.Number) [AttemptRecord]
  -> resultsService.Storage
  -> resultsService.Storage
exercises.admin.resultsService.Storage.userProgress.set userProgress1 = cases
  resultsService.Storage.Storage database _ tracksByUser usersTracks tracks ->
    resultsService.Storage.Storage
      database userProgress1 tracksByUser usersTracks tracks

exercises.admin.resultsService.Storage.usersTracks :
  resultsService.Storage -> OrderedTable models.User [Track.Number]
exercises.admin.resultsService.Storage.usersTracks = cases
  resultsService.Storage.Storage _ _ _ usersTracks _ -> usersTracks

exercises.admin.resultsService.Storage.usersTracks.modify :
  (OrderedTable models.User [Track.Number]
  ->{g} OrderedTable models.User [Track.Number])
  -> resultsService.Storage
  ->{g} resultsService.Storage
exercises.admin.resultsService.Storage.usersTracks.modify f = cases
  resultsService.Storage.Storage
    database userProgress tracksByUser usersTracks tracks ->
    resultsService.Storage.Storage
      database userProgress tracksByUser (f usersTracks) tracks

exercises.admin.resultsService.Storage.usersTracks.set :
  OrderedTable models.User [Track.Number]
  -> resultsService.Storage
  -> resultsService.Storage
exercises.admin.resultsService.Storage.usersTracks.set usersTracks1 = cases
  resultsService.Storage.Storage database userProgress tracksByUser _ tracks ->
    resultsService.Storage.Storage
      database userProgress tracksByUser usersTracks1 tracks

exercises.admin.resultsService.test.latestChallenges : '{IO, Exception} ()
exercises.admin.resultsService.test.latestChallenges = 
  Cloud.main do
    user = getUser() |> uncurry models.User.User
    track = Track.Number.Number 1
    storage = createStorage()
    (Cloud.submit resultsService.env() do
      getDistinctLatestAttempts storage user track)
      |> foreach.deprecated (a -> printLine (AttemptRecord.toText a))

exercises.admin.resultsService.test.printTestProgress : '{IO, Exception} ()
exercises.admin.resultsService.test.printTestProgress = 
  Cloud.main do
    user = getUser() |> uncurry models.User.User
    track = Track.Number.Number 1
    storage = createStorage()
    progress = 
      Cloud.submit resultsService.env() do
        getUserTrackProgress storage user track
    printProgress progress

exercises.admin.resultsService.test.readUserChallenges :
  '{IO, Exception} [AttemptRecord]
exercises.admin.resultsService.test.readUserChallenges = Cloud.main do
  user = getUser() |> uncurry models.User.User
  storage = createStorage()
  now = OffsetDateTime.current()
  Cloud.submit resultsService.env() do userResultsPrefix storage user

exercises.admin.resultsService.test.testAddChallenge :
  '{IO, Exception} [Exercise.Number]
exercises.admin.resultsService.test.testAddChallenge = main.local do
  storage = createStorage()
  newTrack = Track.Number.Number 1
  Cloud.submit resultsService.env() do
    addChallenge storage newTrack (Exercise.Number.Number 3 (Part 2))
    resultList = getAllTrackChallenges storage newTrack
    resultList

exercises.admin.resultsService.test.testAddChallengeRoundtrip :
  '{IO, Exception} ()
exercises.admin.resultsService.test.testAddChallengeRoundtrip = main.local do
  storage = createStorage()
  newTrack = Track.Number.Number 1
  Cloud.submit resultsService.env() do
    use Exercise.Number Number
    addChallenge storage newTrack (Number 1 (Part 1))
    addChallenge storage newTrack (Number 1 (Part 2))
    resultList = getAllTrackChallenges storage newTrack
    test.ensureEqual (List.size resultList) 2

exercises.admin.resultsService.up.tup3.prefixOrdering :
  k1 -> (k1, k2, k3) -> Ordering
exercises.admin.resultsService.up.tup3.prefixOrdering prefix = cases
  (target, _, _) -> Universal.ordering prefix target

exercises.admin.validator.callHttpService :
  HttpRequest ->{Cloud} Either Failure HttpResponse
exercises.admin.validator.callHttpService httpRequest =
  serviceCall = do Cloud.submit validator.env() do request httpRequest
  catch serviceCall

exercises.admin.validator.callService :
  ServiceHash a b -> a ->{Cloud} Either Failure b
exercises.admin.validator.callService service input =
  serviceCall = do Cloud.submit validator.env() do Services.call service input
  catch serviceCall

exercises.admin.validator.callWebSocketService :
  URI
  -> (unison_http_3_3_2.websockets.WebSocket ->{g, IO} ())
  ->{g, IO, Exception} ()
exercises.admin.validator.callWebSocketService uri validator =
  use URI /
  _ =
    {{
    NOTE THIS IS TEMPORARY! Once the new cloud client version which does not
    strip the trailing slash ships, delete this
    }}
  newUri = uri / ""
  go = do
    req = HttpRequest.get newUri
    ws = Http.webSocket req
    validator ws
  handle go() with HttpWebSocket.handler

exercises.admin.validator.decodeHttpResponse :
  HttpRequest
  -> (Body ->{Exception} a)
  -> Text
  ->{Cloud, Stream (models.Result HttpRequest HttpResponse)} Either Failure a
exercises.admin.validator.decodeHttpResponse request decoder label =
  use Optional None
  use Result Error
  serviceResult = callHttpService request
  tryDecodeResponse body = match catch do decoder body with
    Left e  ->
      emit (Error label (ErrorReporting e (InputOutput (Some request) None)))
      Left e
    Right a ->
      emit (PassThrough label (InputOutput (Some request) None))
      Right a
  res =
    serviceResult |> (Either.bimap (e -> let
      emit (Error label (ErrorReporting e (InputOutput (Some request) None)))
      e) cases HttpResponse.HttpResponse _ _ _ body -> tryDecodeResponse body)
  flattenRight res

exercises.admin.validator.Either.tupleRight :
  Either a b -> Either a c -> Either a (b, c)
exercises.admin.validator.Either.tupleRight = cases
  Left a1, Left a2 -> Left a1
  Right b, Left a  -> Left a
  Left a, Right c  -> Left a
  Right b, Right c -> Right (b, c)

exercises.admin.validator.env : '{Exception, Cloud} Environment
exercises.admin.validator.env = do Environment.named "validation-service-env"

exercises.admin.validator.exercise :
  Track.Number
  -> Exercise.Number
  -> Text
  -> '{g, Cloud, Stream (models.Result i o)} a
  ->{g, IO, Exception} (ExerciseResult i o, TrackProgress)
exercises.admin.validator.exercise track number title challengeBody =
  use Cloud run
  use Services call
  runJobs = do run challengeBody
  results = Stream.toList runJobs
  res = ExerciseResult number title results
  userEntity = getUser() |> uncurry models.User.User
  now = realtime() |> atUTC
  record = fromChallengeResult now track res
  trackProgress = run do
    Cloud.submit resultsService.env() do
      call putUserAttemptV3 (userEntity, record)
      call trackProgressV3 (userEntity, track)
  (res, trackProgress)

exercises.admin.validator.expect :
  ServiceHash a b -> a -> b -> Text ->{Cloud, Stream (models.Result a b)} ()
exercises.admin.validator.expect service input expected label =
  match validator.callService service input with
    Left err ->
      emit
        (Result.Error
          label (ErrorReporting err (InputOutput (Some input) Optional.None)))
    Right result
      | result === expected  ->
        emit (Correct label (InputOutput (Some input) (Some expected)))
      | otherwise            ->
        emit (Incorrect label (InputOutputExpected input result expected))

exercises.admin.validator.expectFailure :
  ServiceHash a b -> a -> Text -> Text ->{Cloud, Stream (models.Result a b)} ()
exercises.admin.validator.expectFailure service input msgSubstring label =
  match validator.callService service input with
    Left (Failure tpe msg any)
      | Text.contains msg msgSubstring  ->
        emit (Correct label (InputOutput (Some input) Optional.None))
      | otherwise                       ->
        emit
          (Incorrect
            label
            (ErrorReporting
              (Failure tpe msg any) (InputOutput (Some input) Optional.None)))
    Right result ->
      emit (Incorrect label (InputOutput (Some input) (Some result)))

exercises.admin.validator.expectHttpBodyString :
  HttpRequest
  -> Nat
  -> Text
  -> Text
  ->{Exception, Cloud, Stream (models.Result HttpRequest HttpResponse)} ()
exercises.admin.validator.expectHttpBodyString
  httpReq statusCode responseBody label =
  match callHttpService httpReq with
    Left failure ->
      emit
        (Result.Error
          label
          (ErrorReporting failure (InputOutput (Some httpReq) Optional.None)))
    Right resp@(HttpResponse.HttpResponse (Status code _) _ _ (Body bytes)) ->
      textBody = fromUtf8 bytes
      if code === statusCode && Text.contains responseBody textBody then
        emit (Correct label (InputOutput (Some httpReq) (Some resp)))
      else emit (Incorrect label (InputOutput (Some httpReq) (Some resp)))

exercises.admin.validator.expectHttpCode :
  HttpRequest
  -> Nat
  -> Text
  ->{Cloud, Stream (models.Result HttpRequest HttpResponse)} ()
exercises.admin.validator.expectHttpCode httpReq expectedCode label =
  match callHttpService httpReq with
    Left err ->
      use Optional None
      resultReport : Reporting HttpRequest HttpResponse
      resultReport = InputOutput (Some httpReq) None
      emit
        (Result.Error
          label (ErrorReporting err (InputOutput (Some httpReq) None)))
    Right resp@(HttpResponse.HttpResponse (Status code _) _ _ _) ->
      if code === expectedCode then
        emit (Correct label (InputOutput (Some httpReq) (Some resp)))
      else emit (Incorrect label (InputOutput (Some httpReq) (Some resp)))

exercises.admin.validator.expectHttpJsonKeys :
  HttpRequest
  -> Nat
  -> [Text]
  -> Text
  ->{Cloud, Stream (models.Result HttpRequest HttpResponse)} ()
exercises.admin.validator.expectHttpJsonKeys
  httpReq statusCode expectedKeys label =
  use Optional None
  use Result Error
  use Set ==
  expectedKeySet = Set.fromList expectedKeys
  getJsonKeySubset : Json -> Set Text -> Set Text
  getJsonKeySubset json expectedKeys =
    foundJsonKeySet = getKeySet json
    intersection = Set.intersect foundJsonKeySet expectedKeys
    intersection
  match callHttpService httpReq with
    Left failure ->
      emit
        (Error label (ErrorReporting failure (InputOutput (Some httpReq) None)))
    Right resp@(HttpResponse.HttpResponse (Status code _) _ _ (Body bytes)) ->
      jsonSuccess :
        {Stream (models.Result HttpRequest HttpResponse)} (Either Failure ())
      jsonSuccess = 
        catch do
          textBody = fromUtf8 bytes
          json = Json.fromText textBody
          jsonResponseKeys = getKeySet json
          producedSubset = getJsonKeySubset json expectedKeySet
          if code === statusCode
            && producedSubset == expectedKeySet then
            emit (Correct label (InputOutput (Some httpReq) (Some resp)))
          else
            unison_base_3_23_1.ignore
              {{
              Note, consider changing the InputOutput generic types to support
              arbitrary reporting of text data or make the "expected" type more
              generic.
              }}
            missingKeys = Set.difference expectedKeySet producedSubset
            emit (Incorrect label (InputOutput (Some httpReq) (Some resp)))
      match jsonSuccess with
        Left e ->
          emit
            (Error label (ErrorReporting e (InputOutput (Some httpReq) None)))
        Right r -> r

exercises.admin.validator.expectHttpJsonKeys.doc : Doc
exercises.admin.validator.expectHttpJsonKeys.doc =
  {{
  {{
  docExample 4 do
    request statusCode expectedKeys label ->
      expectHttpJsonKeys request statusCode expectedKeys label }} performs a
  request to the service and inspects the response Json body for the presence
  of the expected keys. It performs a Json tree walk checking for the existence
  of the keys. It does not check the values or the structure of the json.
  }}

exercises.admin.validator.expectHttpJsonKeys.getKeySet : Json -> Set Text
exercises.admin.validator.expectHttpJsonKeys.getKeySet json =
  use List foldLeft
  loop : Set Text -> Json -> Set Text
  loop acc = cases
    Object fields ->
      go : Set Text -> (Text, Json) -> Set Text
      go acc = cases
        (field, value) ->
          newSet = Set.insert field acc
          loop newSet value
      foldLeft go acc fields
    Array values  -> foldLeft loop acc values
    _             -> acc
  loop Set.empty json

exercises.admin.validator.expectJson :
  HttpRequest
  -> Nat
  -> (Json -> Json -> Boolean)
  -> Json
  -> Text
  ->{Cloud, Stream (models.Result HttpRequest HttpResponse)} ()
exercises.admin.validator.expectJson
  httpReq statusCode jsonTest expectedJson label =
  match callHttpService httpReq with
    Left failure ->
      emit
        (Result.Error
          label
          (ErrorReporting failure (InputOutput (Some httpReq) Optional.None)))
    Right resp@(HttpResponse.HttpResponse (Status code _) _ _ (Body bytes)) ->
      successDecoding = 
        catch do
          textBody = fromUtf8 bytes
          jsonSuperset = Json.fromText textBody
          if code === statusCode && jsonTest jsonSuperset expectedJson then
            emit (Correct label (InputOutput (Some httpReq) (Some resp)))
          else emit (Incorrect label (InputOutput (Some httpReq) (Some resp)))
      match successDecoding with
        Left e ->
          emit
            (Result.Error
              label
              (ErrorReporting e (InputOutput (Some httpReq) Optional.None)))
        Right success -> ()

exercises.admin.validator.expectTimed :
  ServiceHash a b
  -> a
  -> b
  -> Remote.Duration
  -> Text
  ->{Cloud, Stream (models.Result a b)} ()
exercises.admin.validator.expectTimed service input expectation duration label =
  serviceCall = do
    Cloud.submit validator.env() do
      remoteServiceCall = do toRemote do Services.call service input
      Remote.timeout duration remoteServiceCall
  match catch serviceCall with
    Left timeout ->
      emit
        (Result.Error
          label
          (ErrorReporting timeout (InputOutput (Some input) Optional.None)))
    Right result
      | result === expectation  ->
        emit (Correct label (InputOutput (Some input) (Some expectation)))
      | otherwise               ->
        emit (Incorrect label (InputOutputExpected input result expectation))

exercises.admin.validator.expectValue :
  a -> a -> Text ->{Stream (models.Result a a)} ()
exercises.admin.validator.expectValue expected actual message =
  if expected === actual then
    emit (Correct message (InputOutput (Some expected) (Some actual)))
  else emit (Incorrect message (InputOutput (Some expected) (Some actual)))

exercises.admin.validator.expectWebSocketEcho :
  Text
  -> unison_http_3_3_2.websockets.WebSocket
  ->{IO, Stream (models.Result websockets.Message websockets.Message)} ()
exercises.admin.validator.expectWebSocketEcho label ws =
  use Reporting Expected
  use Result Error
  msg = TextMessage "hello world"
  go =
    do
      WebSocket.send ws msg
      msg' : websockets.Message
      msg' = WebSocket.receive ws
      if msg === msg' then
        emit (Correct label (InputOutput (Some msg) (Some msg')))
      else emit (Incorrect label (InputOutputExpected msg msg' msg))
  handle go()
  with cases
    { a } -> a
    { Exception.raise (Failure _ t _) -> _ } -> emit (Error t (Expected msg))
    { Abort.abort -> _ } ->
      emit (Error "Remote WebSocket hung up" (Expected msg))

exercises.admin.validator.Json.Array.contains : Json -> Json -> Boolean
exercises.admin.validator.Json.Array.contains = cases
  Array elems, target ->
    List.find (containing -> isSubset containing target) elems |> isSome
  json1, json2 -> false

exercises.admin.validator.Json.Array.contains.doc : Doc
exercises.admin.validator.Json.Array.contains.doc =
  use Array contains
  use Json Text
  {{
  {{ docExample 2 do enclosing target -> contains enclosing target }} checks if
  the target is contained by the enclosing array.
  
  ```
  contains (Array [Text "a", Text "b"]) (Text "a")
  ```
  
  ```
  contains (Array [Text "a", Text "b"]) (Text "c")
  ```
  
  ```
  contains
    (Array [Object [("key1", Text "a")], Text "b"])
    (Object [("key1", Text "a")])
  ```
  
  ```
  contains
    (Array [Object [("key1", Text "a")], Text "b"])
    (Object [("key1", Text "z")])
  ```
  }}

exercises.admin.validator.Json.isSubset : Json -> Json -> Boolean
exercises.admin.validator.Json.isSubset = cases
  Object valuesSuper, Object valuesSub ->
    checkSubsetPair : Boolean -> (Text, Json) -> Boolean
    checkSubsetPair isMatch = cases
      (subKey, subVal) ->
        List.find
          (cases
            (superKey, superVal) ->
              superKey === subKey
                && exercises.admin.validator.Json.isSubset superVal subVal)
          valuesSuper
          |> isSome
    List.foldLeft checkSubsetPair true valuesSub
  Array superVals, Array subVals ->
    List.zip superVals subVals
      |> List.map (tup -> uncurry exercises.admin.validator.Json.isSubset tup)
      |> List.all Function.id
  json1, json2 -> json1 === json2

exercises.admin.validator.Json.isSubset.doc : Doc
exercises.admin.validator.Json.isSubset.doc = {{ TODO optimize this later. }}

exercises.admin.validator.runHttpWith :
  HttpRequest
  -> Text
  ->{Cloud, Stream (models.Result HttpRequest HttpResponse)} Either
    Failure HttpResponse
exercises.admin.validator.runHttpWith request label =
  serviceResult = callHttpService request
  serviceResult
    |> Either.bimap
      (e ->
        let
          emit
            (Result.Error
              label
              (ErrorReporting e (InputOutput (Some request) Optional.None)))
          e)
      (r -> let
        emit (PassThrough label (InputOutput (Some request) (Some r)))
        r)

exercises.admin.validator.runWith :
  ServiceHash a b
  -> a
  -> Text
  ->{Cloud, Stream (models.Result a b)} Either Failure b
exercises.admin.validator.runWith service input label =
  serviceResult = validator.callService service input
  serviceResult
    |> Either.bimap
      (e ->
        let
          emit
            (Result.Error
              label (ErrorReporting e (InputOutput (Some input) Optional.None)))
          e)
      (r -> let
        emit (PassThrough label (InputOutput (Some input) (Some r)))
        r)

exercises.env : '{Exception, Cloud} Environment
exercises.env = do Environment.named "cloud-exercises"

exercises.ex1_quickstart.deploy : '{IO, Exception} URI
exercises.ex1_quickstart.deploy =
  todo
    "Implement the deployment function, the http service to deploy is called `ex1_quickstart.helloWorld.logic`"

exercises.ex1_quickstart.doc : Doc
exercises.ex1_quickstart.doc =
  use ex1_quickstart.helloWorld logic
  {{
  # 🏁 Quickstart Http Service Deployment
  
    In this exercise, you'll deploy a simple HTTP service that responds with a
    greeting message.
    
    {{ docCallout
      (Some {{ 📚 }}) {{
      **What We'll cover**
      
      * Deploying a service to the Cloud
      * Naming services
      * Cloud administration basics
      }} }}
    
    The HTTP service logic is technically implemented for you, but you'll still
    need to deploy it to the Cloud. 😉
    
    ## Getting started
    
       If you haven't yet, make sure you've done the following:
       
       * [Install or upgrade Unison](https://www.unison-lang.org/learn/quickstart/#installation-options)
       * [Sign up for a Unison Cloud account](https://unison.cloud/#pricing)
       
       Then authorize your account to run on the Cloud with the `auth.login`
       command:
       
       ``` ucm
       $ ucm
       
       Now starting the Unison Codebase Manager (UCM)...
       
        _____     _
       |  |  |___|_|___ ___ ___
       |  |  |   | |_ -| . |   |
       |_____|_|_|_|___|___|_|_|
       
       👋 Welcome to Unison!
       
       ./> auth.login
       ```
       
       Great! Unison is set up to deploy to the Unison Cloud.
       
       Create a repository for the `cloud-start` project and pull the latest
       release to retrieve the stubs and tests.
       
       ``` ucm
       .> project-create cloud-start
       cloud-start/main> pull @unison/cloud-start/releases/latest
       ```
    
    ## Cloud deployment basics
    
       You'll implement the {{
       docLink (docEmbedTermLink do exercises.ex1_quickstart.deploy) }}
       function, which should deploy the service to the Cloud and return a URI
       to call it.
       
       {{
       docCallout
         (Some {{ 📝 }})
         {{
         **Instructions**
         
         To get started run the following command in the UCM:
         
         ``` ucm
         cloud-start/main> edit exercises.ex1_quickstart.deploy
         ```
         
         You'll be implementing `ex1_quickstart.deploy`, which should do the
         following:
         
         * Deploy the `helloWorld.logic` function as an HTTP service to the
           Cloud via `deployHttp`
         * Create a name for the service with `ServiceName.create`
         * Assign the name to a service hash with `ServiceName.assign`
         * Provide a handler for the `Cloud` ability to interact with the Cloud
         
         We'll discuss the details of these functions next.
         }} }}
       
       Unison HTTP services are deployed to the Cloud using the `deployHttp`
       function. This function takes two arguments: an {type Environment} where
       the service should be deployed and a function that describes what the
       service should do when it receives an {type HttpRequest}.
       
           @signature{deployHttp}
       
       For convenience, we've provided a helper function {exercises.env} as
       your environment and the Http service function to deploy is implemented
       in the {{ docLink (docEmbedTermLink do logic) }} function.
       
       {{ docSource [docSourceElement (docEmbedTermLink do logic) []] }}
       
       This function sets up a simple HTTP service with the path '/<name>'
       
       Create a name for your service with the {ServiceName.named} function and
       link it to the service hash returned by {deployHttp} with the
       {ServiceName.assign} function.
       
       These functions require the {type Cloud} ability, so you'll need to
       enclose all the functions which interact with the Cloud in the
       {Cloud.main} handler.
       
       {{
       docCallout
         (Some {{ 📝 }})
         {{
         Test that everything is working by submitting your solution for
         validation:
         
         ``` ucm
         cloud-start/main> run submit.ex1_quickstart
         ```
         }} }}
    
    ## Cloud admin panel
    
       Once your service is deployed, you can view it in the Unison Cloud admin
       page at [app.unison.cloud](https://app.unison.cloud/)
       
       You should see your service listed in the "Named Services" tab. Service
       logs are automatically collected and displayed in the activity tab for
       the service.
       
       Use a browser or CURL to call with the root URI returned by the `deploy`
       function and you should see additional log lines appear.
    
    ## 👉 What's next?
    
       [Deploy a Unison native service]({{
       docLink (docEmbedTermLink do ex2_nativeService.doc)
       }})
  }}

exercises.ex1_quickstart.helloWorld.logic :
  HttpRequest ->{Exception, Log} HttpResponse
exercises.ex1_quickstart.helloWorld.logic = Route.run do
  use Text ++
  name = route GET Parser.text
  info "request for greeting" [("name", name)]
  ok.text ("👋 hello " ++ name ++ "\n")

exercises.ex2_nativeService.callService : '{IO, Exception} Nat
exercises.ex2_nativeService.callService = do
  _ = "Implement the callService function"
  100

exercises.ex2_nativeService.deploy : '{IO, Exception} ServiceHash Nat Nat
exercises.ex2_nativeService.deploy =
  todo
    "Implement the Cloud deployment and service logic. The deployed service should square a `Nat` value"

exercises.ex2_nativeService.doc : Doc
exercises.ex2_nativeService.doc =
  use Cloud submit
  use Services call
  use exercises ex2_nativeService.deploy
  {{
  # 📡 Native Services: Typed Function Calls Over the Network
  
    With the Cloud it's possible to host arbitrary typed Unison functions as
    services. Calls to Unison native services take place over the network
    without the need for HTTP requests, JSON blobs, or other serialization
    formats. We'll write a simple one here to introduce the {type Services}
    API.
    
    {{ docCallout
      (Some {{ 📚 }}) {{
      **What you'll learn**
      
      * Deploying a Unison native service to the Cloud
      * Using the {type Services} ability for calling remote functions
      * The API for running cloud jobs vs deploying cloud services
      }} }}
    
    ## 🟪 Part 1: Deploy a simple native service
    
       Implement a Unison Cloud Native service that expects a {type Nat} as its
       argument and returns a {type Nat} that is the square of the input.
       (Again, we're just focusing on the mechanics of deploying and calling a
       service here. 😊)
       
       {{
       docSource
         [docSourceElement (docEmbedTermLink do ex2_nativeService.deploy) []]
       }}
       
       When called with ``3``, the service should return ``9``.
       
       {{ docCallout
         (Some {{ 📝 }}) {{
         **Instructions**
         
         To get started run the following command in the UCM:
         
         ``` ucm
         cloud-start/main> edit exercises.ex2_nativeService.squareService
         ```
         }} }}
       
       Unison native services are deployed to the Cloud using the
       {Cloud.deploy} function. {Cloud.deploy} takes two arguments, an
       {type Environment} where the service should be deployed and a function
       to be run as a service.
       
       The {Cloud.deploy} function returns a {type ServiceHash}, which is a
       typed identifier for the code being deployed. You'll get a new one if
       you change the function you're deploying.
       
       {{
       docCallout
         (Some {{ 📝 }})
         {{
         When you're ready to submit your solution, save the file and run the
         following commands:
         
         ``` ucm
         cloud-start/main> update
         cloud-start/main> run submit.ex2_nativeService
         ```
         }} }}
       
       The general pattern for these service exercises will involve writing
       service "business logic" functionality, creating the cloud resources
       that your service needs to run, and then deploying it. We'll use the
       {type ServiceHash} returned by {Cloud.deploy} to call your service in
       tests.
    
    ## 🔥 Part 2: Practice returning errors
    
       In this part of the exercise, you'll practice completing a task that
       requires representing an error. Update the implementation of the service
       to raise an error when trying to square a number that would cause a
       {type Nat} overflow.
       
       Your service should raise a {type Exception} with a message containing
       the string "cannot be squared".
       
       Check out {{ docLink (docEmbedTermLink do ex2_nativeService.failure) }}
       for a pre-made error type to use.
       
       {{
       docCallout
         (Some {{ 📝 }})
         {{
         Change the logic of the deployed function in
         {ex2_nativeService.deploy}, then save the file again and run the
         following:
         
         ``` ucm
         cloud-start/main> update
         cloud-start/main> run submit.ex2_nativeService
         ```
         }} }}
    
    ## 📞 Part 3: How do you call a native service?
    
       Let's say you need to call the service you just deployed in another
       Unison cloud job. You can't use an Http client for a native service, but
       you __can__ use the {type Services} ability for calling typed remote
       functions.
       
       The {type Services} ability exposes two functions for calling remote
       services: {call} and {callName}.
       
           @signatures{call, callName}
       
       The difference between the two is that service hashes identify a single
       service deployment while a service name refers to the latest of
       potentially many service deployments over time via a name.
       
       {{
       docCallout
         (Some {{ 📝 }})
         {{
         Call the the {{
         (docLink (docEmbedTermLink do ex2_nativeService.deploy)) }} you
         deployed with the argument `` 5 `` in a new cloud job function,
         {exercises.ex2_nativeService.callService}.
         
         ``` ucm
         cloud-start/main> edit exercises.ex2_nativeService.callService
         ```
         }} }}
       
       Two functions, {deployHttp} and {Cloud.deploy} are used to send code to
       be executed on the Cloud. Both lift a function to the Cloud as a
       __service__, with inputs and outputs, but simple jobs like this one can
       be run on the cloud with {submit}.
       
           @signature{submit}
       
       {{
       docCallout
         (Some {{ 📝 }})
         {{
         When you're ready to submit your solution, save the file and run the
         following commands:
         
         ``` ucm
           cloud-start/main> update
           cloud-start/main> run submit.ex2_nativeService
         ```
         }} }}
    
    ## 👉 What's next?
    
       [Write a Micro-blog app]({{
       docLink (docEmbedTermLink do ex3_microblog.doc)
       }})
  }}

exercises.ex2_nativeService.failure : Failure
exercises.ex2_nativeService.failure =
  Failure (typeLink Nat) "cannot be squared" (Any ())

exercises.ex3_microblog.api.createPost : '{Route} ()
exercises.ex3_microblog.api.createPost = do
  use Parser / s
  Route.noCapture POST (s "api" / s "posts")
  ok.json (Json.object [("postId", Json.text "uuidPost")])

exercises.ex3_microblog.api.getPostById : '{Route} ()
exercises.ex3_microblog.api.getPostById = do
  use Parser / s
  postId = v1.PostId.PostId (route GET (s "api" / s "posts" / Parser.text))
  ok.text "ok"

exercises.ex3_microblog.client.User.avatar : client.User -> Optional Text
exercises.ex3_microblog.client.User.avatar = cases
  client.User.User _ _ _ avatar -> avatar

exercises.ex3_microblog.client.User.avatar.modify :
  (Optional Text ->{g} Optional Text) -> client.User ->{g} client.User
exercises.ex3_microblog.client.User.avatar.modify f = cases
  client.User.User userId userHandle userName avatar ->
    client.User.User userId userHandle userName (f avatar)

exercises.ex3_microblog.client.User.avatar.set :
  Optional Text -> client.User -> client.User
exercises.ex3_microblog.client.User.avatar.set avatar1 = cases
  client.User.User userId userHandle userName _ ->
    client.User.User userId userHandle userName avatar1

exercises.ex3_microblog.client.User.fromJson : '{Decoder} client.User
exercises.ex3_microblog.client.User.fromJson = do
  use Decoder optional! text
  use object at at!
  userId = optional! (at "userId" text)
  userHandle = at! "userHandle" text
  name = at! "name" text
  avatar = optional! (at "avatar" text)
  client.User.User userId userHandle name avatar

exercises.ex3_microblog.client.User.toJson : client.User -> Json
exercises.ex3_microblog.client.User.toJson = cases
  client.User.User userId userHandle name avatar ->
    use Json text
    use List ++
    use Optional map
    maybeAvatar = map (uri -> ("avatar", text uri)) avatar
    maybeUserId = map (uid -> ("userId", text uid)) userId
    jsonFields = [("userHandle", text userHandle), ("userName", text name)]
    optionalJsonFields = List.somes [maybeAvatar, maybeUserId]
    Object (jsonFields ++ optionalJsonFields)

exercises.ex3_microblog.client.User.userHandle : client.User -> Text
exercises.ex3_microblog.client.User.userHandle = cases
  client.User.User _ userHandle _ _ -> userHandle

exercises.ex3_microblog.client.User.userHandle.modify :
  (Text ->{g} Text) -> client.User ->{g} client.User
exercises.ex3_microblog.client.User.userHandle.modify f = cases
  client.User.User userId userHandle userName avatar ->
    client.User.User userId (f userHandle) userName avatar

exercises.ex3_microblog.client.User.userHandle.set :
  Text -> client.User -> client.User
exercises.ex3_microblog.client.User.userHandle.set userHandle1 = cases
  client.User.User userId _ userName avatar ->
    client.User.User userId userHandle1 userName avatar

exercises.ex3_microblog.client.User.userId : client.User -> Optional Text
exercises.ex3_microblog.client.User.userId = cases
  client.User.User userId _ _ _ -> userId

exercises.ex3_microblog.client.User.userId.modify :
  (Optional Text ->{g} Optional Text) -> client.User ->{g} client.User
exercises.ex3_microblog.client.User.userId.modify f = cases
  client.User.User userId userHandle userName avatar ->
    client.User.User (f userId) userHandle userName avatar

exercises.ex3_microblog.client.User.userId.set :
  Optional Text -> client.User -> client.User
exercises.ex3_microblog.client.User.userId.set userId1 = cases
  client.User.User _ userHandle userName avatar ->
    client.User.User userId1 userHandle userName avatar

exercises.ex3_microblog.client.User.userName : client.User -> Text
exercises.ex3_microblog.client.User.userName = cases
  client.User.User _ _ userName _ -> userName

exercises.ex3_microblog.client.User.userName.modify :
  (Text ->{g} Text) -> client.User ->{g} client.User
exercises.ex3_microblog.client.User.userName.modify f = cases
  client.User.User userId userHandle userName avatar ->
    client.User.User userId userHandle (f userName) avatar

exercises.ex3_microblog.client.User.userName.set :
  Text -> client.User -> client.User
exercises.ex3_microblog.client.User.userName.set userName1 = cases
  client.User.User userId userHandle _ avatar ->
    client.User.User userId userHandle userName1 avatar

exercises.ex3_microblog.db.createAppStorage : '{Exception, Cloud} AppStorage
exercises.ex3_microblog.db.createAppStorage = do
  use Universal ordering
  use v2 PostRow
  db = Database.named "microblog-solutions-v2"
  Database.assign db exercises.env()
  userHandleToUser : OrderedTable UserHandle v2.UserRow
  userHandleToUser = OrderedTable.named db "userHandleToUser-v2" ordering
  userPostsTable : OrderedTable (UserHandle, OffsetDateTime) PostRow
  userPostsTable = OrderedTable.named db "userPostsTable-v2" ordering
  postsTable : OrderedTable v2.PostId PostRow
  postsTable = OrderedTable.named db "postsTable-v2" ordering
  followingTable : OrderedTable (UserHandle, UserHandle) v2.FollowingRow
  followingTable = OrderedTable.named db "followingTable-v2" ordering
  AppStorage db userHandleToUser userPostsTable postsTable followingTable

exercises.ex3_microblog.db.v1.createPost :
  v1.Storage
  -> v1.UserId
  -> Text
  ->{Exception, unison_cloud_19_0_0.Storage, Remote, Random} v1.PostRow
exercises.ex3_microblog.db.v1.createPost storage userId body =
  use BTree.write tx
  postId = randomly do v1.PostId.PostId text.base32Hex()
  timeStamp = atUTC now!
  postTable = Storage.postsTable storage
  userPostsTable = Storage.userPostsTable storage
  transact.random (v1.Storage.database storage) do
    postRow = v1.PostRow.PostRow postId timeStamp timeStamp body userId
    tx postTable postId postRow
    tx userPostsTable (userId, timeStamp) postId
    postRow

exercises.ex3_microblog.db.v1.createuser :
  v1.Storage
  -> UserHandle
  -> Text
  -> Optional URI
  ->{Exception, unison_cloud_19_0_0.Storage, Remote, Random} v1.UserRow
exercises.ex3_microblog.db.v1.createuser storage userHandle name avatar =
  use BTree.write tx
  userId = v1.UserId.UserId (Remote.randomBytes 256 |> Bytes.toHex)
  timeStamp = atUTC now!
  userRow =
    v1.UserRow.UserRow userId timeStamp timeStamp userHandle name avatar
  transact.random (v1.Storage.database storage) do
    tx (usersTable storage) userId userRow
    tx (userHandleIdTable storage) userHandle userId
  userRow

exercises.ex3_microblog.db.v1.FollowingRow.createdAt :
  v1.FollowingRow -> OffsetDateTime
exercises.ex3_microblog.db.v1.FollowingRow.createdAt = cases
  v1.FollowingRow.FollowingRow _ _ createdAt _ -> createdAt

exercises.ex3_microblog.db.v1.FollowingRow.createdAt.modify :
  (OffsetDateTime ->{g} OffsetDateTime)
  -> v1.FollowingRow
  ->{g} v1.FollowingRow
exercises.ex3_microblog.db.v1.FollowingRow.createdAt.modify f = cases
  v1.FollowingRow.FollowingRow follower target createdAt updatedAt ->
    v1.FollowingRow.FollowingRow follower target (f createdAt) updatedAt

exercises.ex3_microblog.db.v1.FollowingRow.createdAt.set :
  OffsetDateTime -> v1.FollowingRow -> v1.FollowingRow
exercises.ex3_microblog.db.v1.FollowingRow.createdAt.set createdAt1 = cases
  v1.FollowingRow.FollowingRow follower target _ updatedAt ->
    v1.FollowingRow.FollowingRow follower target createdAt1 updatedAt

exercises.ex3_microblog.db.v1.FollowingRow.follower :
  v1.FollowingRow -> v1.UserId
exercises.ex3_microblog.db.v1.FollowingRow.follower = cases
  v1.FollowingRow.FollowingRow follower _ _ _ -> follower

exercises.ex3_microblog.db.v1.FollowingRow.follower.modify :
  (v1.UserId ->{g} v1.UserId) -> v1.FollowingRow ->{g} v1.FollowingRow
exercises.ex3_microblog.db.v1.FollowingRow.follower.modify f = cases
  v1.FollowingRow.FollowingRow follower target createdAt updatedAt ->
    v1.FollowingRow.FollowingRow (f follower) target createdAt updatedAt

exercises.ex3_microblog.db.v1.FollowingRow.follower.set :
  v1.UserId -> v1.FollowingRow -> v1.FollowingRow
exercises.ex3_microblog.db.v1.FollowingRow.follower.set follower1 = cases
  v1.FollowingRow.FollowingRow _ target createdAt updatedAt ->
    v1.FollowingRow.FollowingRow follower1 target createdAt updatedAt

exercises.ex3_microblog.db.v1.FollowingRow.target :
  v1.FollowingRow -> v1.UserId
exercises.ex3_microblog.db.v1.FollowingRow.target = cases
  v1.FollowingRow.FollowingRow _ target _ _ -> target

exercises.ex3_microblog.db.v1.FollowingRow.target.modify :
  (v1.UserId ->{g} v1.UserId) -> v1.FollowingRow ->{g} v1.FollowingRow
exercises.ex3_microblog.db.v1.FollowingRow.target.modify f = cases
  v1.FollowingRow.FollowingRow follower target createdAt updatedAt ->
    v1.FollowingRow.FollowingRow follower (f target) createdAt updatedAt

exercises.ex3_microblog.db.v1.FollowingRow.target.set :
  v1.UserId -> v1.FollowingRow -> v1.FollowingRow
exercises.ex3_microblog.db.v1.FollowingRow.target.set target1 = cases
  v1.FollowingRow.FollowingRow follower _ createdAt updatedAt ->
    v1.FollowingRow.FollowingRow follower target1 createdAt updatedAt

exercises.ex3_microblog.db.v1.FollowingRow.updatedAt :
  v1.FollowingRow -> OffsetDateTime
exercises.ex3_microblog.db.v1.FollowingRow.updatedAt = cases
  v1.FollowingRow.FollowingRow _ _ _ updatedAt -> updatedAt

exercises.ex3_microblog.db.v1.FollowingRow.updatedAt.modify :
  (OffsetDateTime ->{g} OffsetDateTime)
  -> v1.FollowingRow
  ->{g} v1.FollowingRow
exercises.ex3_microblog.db.v1.FollowingRow.updatedAt.modify f = cases
  v1.FollowingRow.FollowingRow follower target createdAt updatedAt ->
    v1.FollowingRow.FollowingRow follower target createdAt (f updatedAt)

exercises.ex3_microblog.db.v1.FollowingRow.updatedAt.set :
  OffsetDateTime -> v1.FollowingRow -> v1.FollowingRow
exercises.ex3_microblog.db.v1.FollowingRow.updatedAt.set updatedAt1 = cases
  v1.FollowingRow.FollowingRow follower target createdAt _ ->
    v1.FollowingRow.FollowingRow follower target createdAt updatedAt1

exercises.ex3_microblog.db.v1.followUser :
  v1.Storage
  -> v1.UserId
  -> v1.UserId
  ->{Exception, unison_cloud_19_0_0.Storage, Remote} v1.FollowingRow
exercises.ex3_microblog.db.v1.followUser storage follower target =
  use v1.FollowingRow FollowingRow
  followingTable = following storage
  followingId = randomly do v1.FollowingId.FollowingId text.base32Hex()
  timeStamp = atUTC now!
  followingRow = FollowingRow follower target timeStamp timeStamp
  BTree.write
    (following storage)
    (follower, target)
    (FollowingRow follower target timeStamp timeStamp)
  followingRow

exercises.ex3_microblog.db.v1.getPostById :
  v1.Storage
  -> v1.PostId
  ->{Exception, unison_cloud_19_0_0.Storage, Remote} v1.PostRow
exercises.ex3_microblog.db.v1.getPostById storage postId =
  OrderedTable.read (Storage.postsTable storage) postId

exercises.ex3_microblog.db.v1.getPostsByUserId :
  v1.Storage
  -> UserHandle
  ->{Exception, unison_cloud_19_0_0.Storage, Remote} [v1.PostRow]
exercises.ex3_microblog.db.v1.getPostsByUserId storage userHandle =
  use OrderedTable read
  use Stream map
  userPostsTable = Storage.userPostsTable storage
  userHandleIdTable = Storage.userHandleIdTable storage
  userId = read userHandleIdTable userHandle
  resultStream =
    rangeClosed.prefix userPostsTable OrderedTable.prefixOrdering userId userId
  map at2 resultStream
    |> map (id -> read (Storage.postsTable storage) id)
    |> Stream.toList

exercises.ex3_microblog.db.v1.getUserByHandle :
  v1.Storage
  -> UserHandle
  ->{Exception, unison_cloud_19_0_0.Storage, Remote} v1.UserRow
exercises.ex3_microblog.db.v1.getUserByHandle storage userHandle =
  use OrderedTable read
  userId = read (userHandleIdTable storage) userHandle
  read (usersTable storage) userId

exercises.ex3_microblog.db.v1.PostRow.body : v1.PostRow -> Text
exercises.ex3_microblog.db.v1.PostRow.body = cases
  v1.PostRow.PostRow _ _ _ body _ -> body

exercises.ex3_microblog.db.v1.PostRow.body.modify :
  (Text ->{g} Text) -> v1.PostRow ->{g} v1.PostRow
exercises.ex3_microblog.db.v1.PostRow.body.modify f = cases
  v1.PostRow.PostRow id createdAt updatedAt body userId ->
    v1.PostRow.PostRow id createdAt updatedAt (f body) userId

exercises.ex3_microblog.db.v1.PostRow.body.set :
  Text -> v1.PostRow -> v1.PostRow
exercises.ex3_microblog.db.v1.PostRow.body.set body1 = cases
  v1.PostRow.PostRow id createdAt updatedAt _ userId ->
    v1.PostRow.PostRow id createdAt updatedAt body1 userId

exercises.ex3_microblog.db.v1.PostRow.createdAt : v1.PostRow -> OffsetDateTime
exercises.ex3_microblog.db.v1.PostRow.createdAt = cases
  v1.PostRow.PostRow _ createdAt _ _ _ -> createdAt

exercises.ex3_microblog.db.v1.PostRow.createdAt.modify :
  (OffsetDateTime ->{g} OffsetDateTime) -> v1.PostRow ->{g} v1.PostRow
exercises.ex3_microblog.db.v1.PostRow.createdAt.modify f = cases
  v1.PostRow.PostRow id createdAt updatedAt body userId ->
    v1.PostRow.PostRow id (f createdAt) updatedAt body userId

exercises.ex3_microblog.db.v1.PostRow.createdAt.set :
  OffsetDateTime -> v1.PostRow -> v1.PostRow
exercises.ex3_microblog.db.v1.PostRow.createdAt.set createdAt1 = cases
  v1.PostRow.PostRow id _ updatedAt body userId ->
    v1.PostRow.PostRow id createdAt1 updatedAt body userId

exercises.ex3_microblog.db.v1.PostRow.id : v1.PostRow -> v1.PostId
exercises.ex3_microblog.db.v1.PostRow.id = cases
  v1.PostRow.PostRow id _ _ _ _ -> id

exercises.ex3_microblog.db.v1.PostRow.id.modify :
  (v1.PostId ->{g} v1.PostId) -> v1.PostRow ->{g} v1.PostRow
exercises.ex3_microblog.db.v1.PostRow.id.modify f = cases
  v1.PostRow.PostRow id createdAt updatedAt body userId ->
    v1.PostRow.PostRow (f id) createdAt updatedAt body userId

exercises.ex3_microblog.db.v1.PostRow.id.set :
  v1.PostId -> v1.PostRow -> v1.PostRow
exercises.ex3_microblog.db.v1.PostRow.id.set id1 = cases
  v1.PostRow.PostRow _ createdAt updatedAt body userId ->
    v1.PostRow.PostRow id1 createdAt updatedAt body userId

exercises.ex3_microblog.db.v1.PostRow.updatedAt : v1.PostRow -> OffsetDateTime
exercises.ex3_microblog.db.v1.PostRow.updatedAt = cases
  v1.PostRow.PostRow _ _ updatedAt _ _ -> updatedAt

exercises.ex3_microblog.db.v1.PostRow.updatedAt.modify :
  (OffsetDateTime ->{g} OffsetDateTime) -> v1.PostRow ->{g} v1.PostRow
exercises.ex3_microblog.db.v1.PostRow.updatedAt.modify f = cases
  v1.PostRow.PostRow id createdAt updatedAt body userId ->
    v1.PostRow.PostRow id createdAt (f updatedAt) body userId

exercises.ex3_microblog.db.v1.PostRow.updatedAt.set :
  OffsetDateTime -> v1.PostRow -> v1.PostRow
exercises.ex3_microblog.db.v1.PostRow.updatedAt.set updatedAt1 = cases
  v1.PostRow.PostRow id createdAt _ body userId ->
    v1.PostRow.PostRow id createdAt updatedAt1 body userId

exercises.ex3_microblog.db.v1.PostRow.userId : v1.PostRow -> v1.UserId
exercises.ex3_microblog.db.v1.PostRow.userId = cases
  v1.PostRow.PostRow _ _ _ _ userId -> userId

exercises.ex3_microblog.db.v1.PostRow.userId.modify :
  (v1.UserId ->{g} v1.UserId) -> v1.PostRow ->{g} v1.PostRow
exercises.ex3_microblog.db.v1.PostRow.userId.modify f = cases
  v1.PostRow.PostRow id createdAt updatedAt body userId ->
    v1.PostRow.PostRow id createdAt updatedAt body (f userId)

exercises.ex3_microblog.db.v1.PostRow.userId.set :
  v1.UserId -> v1.PostRow -> v1.PostRow
exercises.ex3_microblog.db.v1.PostRow.userId.set userId1 = cases
  v1.PostRow.PostRow id createdAt updatedAt body _ ->
    v1.PostRow.PostRow id createdAt updatedAt body userId1

exercises.ex3_microblog.db.v1.Storage.database : v1.Storage -> Database
exercises.ex3_microblog.db.v1.Storage.database = cases
  v1.Storage.Storage database _ _ _ _ _ _ -> database

exercises.ex3_microblog.db.v1.Storage.database.modify :
  (Database ->{g} Database) -> v1.Storage ->{g} v1.Storage
exercises.ex3_microblog.db.v1.Storage.database.modify f = cases
  v1.Storage.Storage
    database
    userIdsTable
    userHandleIdTable
    usersTable
    userPostsTable
    postsTable
    following ->
    v1.Storage.Storage
      (f database)
      userIdsTable
      userHandleIdTable
      usersTable
      userPostsTable
      postsTable
      following

exercises.ex3_microblog.db.v1.Storage.database.set :
  Database -> v1.Storage -> v1.Storage
exercises.ex3_microblog.db.v1.Storage.database.set database1 = cases
  v1.Storage.Storage
    _
    userIdsTable
    userHandleIdTable
    usersTable
    userPostsTable
    postsTable
    following ->
    v1.Storage.Storage
      database1
      userIdsTable
      userHandleIdTable
      usersTable
      userPostsTable
      postsTable
      following

exercises.ex3_microblog.db.v1.Storage.following :
  v1.Storage -> OrderedTable (v1.UserId, v1.UserId) v1.FollowingRow
exercises.ex3_microblog.db.v1.Storage.following = cases
  v1.Storage.Storage _ _ _ _ _ _ following -> following

exercises.ex3_microblog.db.v1.Storage.following.modify :
  (OrderedTable (v1.UserId, v1.UserId) v1.FollowingRow
  ->{g} OrderedTable (v1.UserId, v1.UserId) v1.FollowingRow)
  -> v1.Storage
  ->{g} v1.Storage
exercises.ex3_microblog.db.v1.Storage.following.modify f = cases
  v1.Storage.Storage
    database
    userIdsTable
    userHandleIdTable
    usersTable
    userPostsTable
    postsTable
    following ->
    v1.Storage.Storage
      database
      userIdsTable
      userHandleIdTable
      usersTable
      userPostsTable
      postsTable
      (f following)

exercises.ex3_microblog.db.v1.Storage.following.set :
  OrderedTable (v1.UserId, v1.UserId) v1.FollowingRow
  -> v1.Storage
  -> v1.Storage
exercises.ex3_microblog.db.v1.Storage.following.set following1 = cases
  v1.Storage.Storage
    database
    userIdsTable
    userHandleIdTable
    usersTable
    userPostsTable
    postsTable
    _ ->
    v1.Storage.Storage
      database
      userIdsTable
      userHandleIdTable
      usersTable
      userPostsTable
      postsTable
      following1

exercises.ex3_microblog.db.v1.Storage.postsTable :
  v1.Storage -> OrderedTable v1.PostId v1.PostRow
exercises.ex3_microblog.db.v1.Storage.postsTable = cases
  v1.Storage.Storage _ _ _ _ _ postsTable _ -> postsTable

exercises.ex3_microblog.db.v1.Storage.postsTable.modify :
  (OrderedTable v1.PostId v1.PostRow ->{g} OrderedTable v1.PostId v1.PostRow)
  -> v1.Storage
  ->{g} v1.Storage
exercises.ex3_microblog.db.v1.Storage.postsTable.modify f = cases
  v1.Storage.Storage
    database
    userIdsTable
    userHandleIdTable
    usersTable
    userPostsTable
    postsTable
    following ->
    v1.Storage.Storage
      database
      userIdsTable
      userHandleIdTable
      usersTable
      userPostsTable
      (f postsTable)
      following

exercises.ex3_microblog.db.v1.Storage.postsTable.set :
  OrderedTable v1.PostId v1.PostRow -> v1.Storage -> v1.Storage
exercises.ex3_microblog.db.v1.Storage.postsTable.set postsTable1 = cases
  v1.Storage.Storage
    database
    userIdsTable
    userHandleIdTable
    usersTable
    userPostsTable
    _
    following ->
    v1.Storage.Storage
      database
      userIdsTable
      userHandleIdTable
      usersTable
      userPostsTable
      postsTable1
      following

exercises.ex3_microblog.db.v1.Storage.userHandleIdTable :
  v1.Storage -> OrderedTable UserHandle v1.UserId
exercises.ex3_microblog.db.v1.Storage.userHandleIdTable = cases
  v1.Storage.Storage _ _ userHandleIdTable _ _ _ _ -> userHandleIdTable

exercises.ex3_microblog.db.v1.Storage.userHandleIdTable.modify :
  (OrderedTable UserHandle v1.UserId ->{g} OrderedTable UserHandle v1.UserId)
  -> v1.Storage
  ->{g} v1.Storage
exercises.ex3_microblog.db.v1.Storage.userHandleIdTable.modify f = cases
  v1.Storage.Storage
    database
    userIdsTable
    userHandleIdTable
    usersTable
    userPostsTable
    postsTable
    following ->
    v1.Storage.Storage
      database
      userIdsTable
      (f userHandleIdTable)
      usersTable
      userPostsTable
      postsTable
      following

exercises.ex3_microblog.db.v1.Storage.userHandleIdTable.set :
  OrderedTable UserHandle v1.UserId -> v1.Storage -> v1.Storage
exercises.ex3_microblog.db.v1.Storage.userHandleIdTable.set userHandleIdTable1 = cases
  v1.Storage.Storage
    database userIdsTable _ usersTable userPostsTable postsTable following ->
    v1.Storage.Storage
      database
      userIdsTable
      userHandleIdTable1
      usersTable
      userPostsTable
      postsTable
      following

exercises.ex3_microblog.db.v1.Storage.userIdsTable :
  v1.Storage -> Cell v1.UserId
exercises.ex3_microblog.db.v1.Storage.userIdsTable = cases
  v1.Storage.Storage _ userIdsTable _ _ _ _ _ -> userIdsTable

exercises.ex3_microblog.db.v1.Storage.userIdsTable.modify :
  (Cell v1.UserId ->{g} Cell v1.UserId) -> v1.Storage ->{g} v1.Storage
exercises.ex3_microblog.db.v1.Storage.userIdsTable.modify f = cases
  v1.Storage.Storage
    database
    userIdsTable
    userHandleIdTable
    usersTable
    userPostsTable
    postsTable
    following ->
    v1.Storage.Storage
      database
      (f userIdsTable)
      userHandleIdTable
      usersTable
      userPostsTable
      postsTable
      following

exercises.ex3_microblog.db.v1.Storage.userIdsTable.set :
  Cell v1.UserId -> v1.Storage -> v1.Storage
exercises.ex3_microblog.db.v1.Storage.userIdsTable.set userIdsTable1 = cases
  v1.Storage.Storage
    database _ userHandleIdTable usersTable userPostsTable postsTable following ->
    v1.Storage.Storage
      database
      userIdsTable1
      userHandleIdTable
      usersTable
      userPostsTable
      postsTable
      following

exercises.ex3_microblog.db.v1.Storage.userPostsTable :
  v1.Storage -> OrderedTable (v1.UserId, OffsetDateTime) v1.PostId
exercises.ex3_microblog.db.v1.Storage.userPostsTable = cases
  v1.Storage.Storage _ _ _ _ userPostsTable _ _ -> userPostsTable

exercises.ex3_microblog.db.v1.Storage.userPostsTable.modify :
  (OrderedTable (v1.UserId, OffsetDateTime) v1.PostId
  ->{g} OrderedTable (v1.UserId, OffsetDateTime) v1.PostId)
  -> v1.Storage
  ->{g} v1.Storage
exercises.ex3_microblog.db.v1.Storage.userPostsTable.modify f = cases
  v1.Storage.Storage
    database
    userIdsTable
    userHandleIdTable
    usersTable
    userPostsTable
    postsTable
    following ->
    v1.Storage.Storage
      database
      userIdsTable
      userHandleIdTable
      usersTable
      (f userPostsTable)
      postsTable
      following

exercises.ex3_microblog.db.v1.Storage.userPostsTable.set :
  OrderedTable (v1.UserId, OffsetDateTime) v1.PostId
  -> v1.Storage
  -> v1.Storage
exercises.ex3_microblog.db.v1.Storage.userPostsTable.set userPostsTable1 = cases
  v1.Storage.Storage
    database userIdsTable userHandleIdTable usersTable _ postsTable following ->
    v1.Storage.Storage
      database
      userIdsTable
      userHandleIdTable
      usersTable
      userPostsTable1
      postsTable
      following

exercises.ex3_microblog.db.v1.Storage.usersTable :
  v1.Storage -> OrderedTable v1.UserId v1.UserRow
exercises.ex3_microblog.db.v1.Storage.usersTable = cases
  v1.Storage.Storage _ _ _ usersTable _ _ _ -> usersTable

exercises.ex3_microblog.db.v1.Storage.usersTable.modify :
  (OrderedTable v1.UserId v1.UserRow ->{g} OrderedTable v1.UserId v1.UserRow)
  -> v1.Storage
  ->{g} v1.Storage
exercises.ex3_microblog.db.v1.Storage.usersTable.modify f = cases
  v1.Storage.Storage
    database
    userIdsTable
    userHandleIdTable
    usersTable
    userPostsTable
    postsTable
    following ->
    v1.Storage.Storage
      database
      userIdsTable
      userHandleIdTable
      (f usersTable)
      userPostsTable
      postsTable
      following

exercises.ex3_microblog.db.v1.Storage.usersTable.set :
  OrderedTable v1.UserId v1.UserRow -> v1.Storage -> v1.Storage
exercises.ex3_microblog.db.v1.Storage.usersTable.set usersTable1 = cases
  v1.Storage.Storage
    database
    userIdsTable
    userHandleIdTable
    _
    userPostsTable
    postsTable
    following ->
    v1.Storage.Storage
      database
      userIdsTable
      userHandleIdTable
      usersTable1
      userPostsTable
      postsTable
      following

exercises.ex3_microblog.db.v1.UserRow.avatar : v1.UserRow -> Optional URI
exercises.ex3_microblog.db.v1.UserRow.avatar = cases
  v1.UserRow.UserRow _ _ _ _ _ avatar -> avatar

exercises.ex3_microblog.db.v1.UserRow.avatar.modify :
  (Optional URI ->{g} Optional URI) -> v1.UserRow ->{g} v1.UserRow
exercises.ex3_microblog.db.v1.UserRow.avatar.modify f = cases
  v1.UserRow.UserRow id createdAt updatedAt userHandle name avatar ->
    v1.UserRow.UserRow id createdAt updatedAt userHandle name (f avatar)

exercises.ex3_microblog.db.v1.UserRow.avatar.set :
  Optional URI -> v1.UserRow -> v1.UserRow
exercises.ex3_microblog.db.v1.UserRow.avatar.set avatar1 = cases
  v1.UserRow.UserRow id createdAt updatedAt userHandle name _ ->
    v1.UserRow.UserRow id createdAt updatedAt userHandle name avatar1

exercises.ex3_microblog.db.v1.UserRow.createdAt : v1.UserRow -> OffsetDateTime
exercises.ex3_microblog.db.v1.UserRow.createdAt = cases
  v1.UserRow.UserRow _ createdAt _ _ _ _ -> createdAt

exercises.ex3_microblog.db.v1.UserRow.createdAt.modify :
  (OffsetDateTime ->{g} OffsetDateTime) -> v1.UserRow ->{g} v1.UserRow
exercises.ex3_microblog.db.v1.UserRow.createdAt.modify f = cases
  v1.UserRow.UserRow id createdAt updatedAt userHandle name avatar ->
    v1.UserRow.UserRow id (f createdAt) updatedAt userHandle name avatar

exercises.ex3_microblog.db.v1.UserRow.createdAt.set :
  OffsetDateTime -> v1.UserRow -> v1.UserRow
exercises.ex3_microblog.db.v1.UserRow.createdAt.set createdAt1 = cases
  v1.UserRow.UserRow id _ updatedAt userHandle name avatar ->
    v1.UserRow.UserRow id createdAt1 updatedAt userHandle name avatar

exercises.ex3_microblog.db.v1.UserRow.id : v1.UserRow -> v1.UserId
exercises.ex3_microblog.db.v1.UserRow.id = cases
  v1.UserRow.UserRow id _ _ _ _ _ -> id

exercises.ex3_microblog.db.v1.UserRow.id.modify :
  (v1.UserId ->{g} v1.UserId) -> v1.UserRow ->{g} v1.UserRow
exercises.ex3_microblog.db.v1.UserRow.id.modify f = cases
  v1.UserRow.UserRow id createdAt updatedAt userHandle name avatar ->
    v1.UserRow.UserRow (f id) createdAt updatedAt userHandle name avatar

exercises.ex3_microblog.db.v1.UserRow.id.set :
  v1.UserId -> v1.UserRow -> v1.UserRow
exercises.ex3_microblog.db.v1.UserRow.id.set id1 = cases
  v1.UserRow.UserRow _ createdAt updatedAt userHandle name avatar ->
    v1.UserRow.UserRow id1 createdAt updatedAt userHandle name avatar

exercises.ex3_microblog.db.v1.UserRow.name : v1.UserRow -> Text
exercises.ex3_microblog.db.v1.UserRow.name = cases
  v1.UserRow.UserRow _ _ _ _ name _ -> name

exercises.ex3_microblog.db.v1.UserRow.name.modify :
  (Text ->{g} Text) -> v1.UserRow ->{g} v1.UserRow
exercises.ex3_microblog.db.v1.UserRow.name.modify f = cases
  v1.UserRow.UserRow id createdAt updatedAt userHandle name avatar ->
    v1.UserRow.UserRow id createdAt updatedAt userHandle (f name) avatar

exercises.ex3_microblog.db.v1.UserRow.name.set :
  Text -> v1.UserRow -> v1.UserRow
exercises.ex3_microblog.db.v1.UserRow.name.set name1 = cases
  v1.UserRow.UserRow id createdAt updatedAt userHandle _ avatar ->
    v1.UserRow.UserRow id createdAt updatedAt userHandle name1 avatar

exercises.ex3_microblog.db.v1.UserRow.updatedAt : v1.UserRow -> OffsetDateTime
exercises.ex3_microblog.db.v1.UserRow.updatedAt = cases
  v1.UserRow.UserRow _ _ updatedAt _ _ _ -> updatedAt

exercises.ex3_microblog.db.v1.UserRow.updatedAt.modify :
  (OffsetDateTime ->{g} OffsetDateTime) -> v1.UserRow ->{g} v1.UserRow
exercises.ex3_microblog.db.v1.UserRow.updatedAt.modify f = cases
  v1.UserRow.UserRow id createdAt updatedAt userHandle name avatar ->
    v1.UserRow.UserRow id createdAt (f updatedAt) userHandle name avatar

exercises.ex3_microblog.db.v1.UserRow.updatedAt.set :
  OffsetDateTime -> v1.UserRow -> v1.UserRow
exercises.ex3_microblog.db.v1.UserRow.updatedAt.set updatedAt1 = cases
  v1.UserRow.UserRow id createdAt _ userHandle name avatar ->
    v1.UserRow.UserRow id createdAt updatedAt1 userHandle name avatar

exercises.ex3_microblog.db.v1.UserRow.userHandle : v1.UserRow -> UserHandle
exercises.ex3_microblog.db.v1.UserRow.userHandle = cases
  v1.UserRow.UserRow _ _ _ userHandle _ _ -> userHandle

exercises.ex3_microblog.db.v1.UserRow.userHandle.modify :
  (UserHandle ->{g} UserHandle) -> v1.UserRow ->{g} v1.UserRow
exercises.ex3_microblog.db.v1.UserRow.userHandle.modify f = cases
  v1.UserRow.UserRow id createdAt updatedAt userHandle name avatar ->
    v1.UserRow.UserRow id createdAt updatedAt (f userHandle) name avatar

exercises.ex3_microblog.db.v1.UserRow.userHandle.set :
  UserHandle -> v1.UserRow -> v1.UserRow
exercises.ex3_microblog.db.v1.UserRow.userHandle.set userHandle1 = cases
  v1.UserRow.UserRow id createdAt updatedAt _ name avatar ->
    v1.UserRow.UserRow id createdAt updatedAt userHandle1 name avatar

exercises.ex3_microblog.db.v2.AppStorage.database : AppStorage -> Database
exercises.ex3_microblog.db.v2.AppStorage.database = cases
  AppStorage database _ _ _ _ -> database

exercises.ex3_microblog.db.v2.AppStorage.database.modify :
  (Database ->{g} Database) -> AppStorage ->{g} AppStorage
exercises.ex3_microblog.db.v2.AppStorage.database.modify f = cases
  AppStorage database userHandleToUser userPostsTable postsTable followingTable ->
    AppStorage
      (f database) userHandleToUser userPostsTable postsTable followingTable

exercises.ex3_microblog.db.v2.AppStorage.database.set :
  Database -> AppStorage -> AppStorage
exercises.ex3_microblog.db.v2.AppStorage.database.set database1 = cases
  AppStorage _ userHandleToUser userPostsTable postsTable followingTable ->
    AppStorage
      database1 userHandleToUser userPostsTable postsTable followingTable

exercises.ex3_microblog.db.v2.AppStorage.followingTable :
  AppStorage -> OrderedTable (UserHandle, UserHandle) v2.FollowingRow
exercises.ex3_microblog.db.v2.AppStorage.followingTable = cases
  AppStorage _ _ _ _ followingTable -> followingTable

exercises.ex3_microblog.db.v2.AppStorage.followingTable.modify :
  (OrderedTable (UserHandle, UserHandle) v2.FollowingRow
  ->{g} OrderedTable (UserHandle, UserHandle) v2.FollowingRow)
  -> AppStorage
  ->{g} AppStorage
exercises.ex3_microblog.db.v2.AppStorage.followingTable.modify f = cases
  AppStorage database userHandleToUser userPostsTable postsTable followingTable ->
    AppStorage
      database userHandleToUser userPostsTable postsTable (f followingTable)

exercises.ex3_microblog.db.v2.AppStorage.followingTable.set :
  OrderedTable (UserHandle, UserHandle) v2.FollowingRow
  -> AppStorage
  -> AppStorage
exercises.ex3_microblog.db.v2.AppStorage.followingTable.set followingTable1 = cases
  AppStorage database userHandleToUser userPostsTable postsTable _ ->
    AppStorage
      database userHandleToUser userPostsTable postsTable followingTable1

exercises.ex3_microblog.db.v2.AppStorage.postsTable :
  AppStorage -> OrderedTable v2.PostId v2.PostRow
exercises.ex3_microblog.db.v2.AppStorage.postsTable = cases
  AppStorage _ _ _ postsTable _ -> postsTable

exercises.ex3_microblog.db.v2.AppStorage.postsTable.modify :
  (OrderedTable v2.PostId v2.PostRow ->{g} OrderedTable v2.PostId v2.PostRow)
  -> AppStorage
  ->{g} AppStorage
exercises.ex3_microblog.db.v2.AppStorage.postsTable.modify f = cases
  AppStorage database userHandleToUser userPostsTable postsTable followingTable ->
    AppStorage
      database userHandleToUser userPostsTable (f postsTable) followingTable

exercises.ex3_microblog.db.v2.AppStorage.postsTable.set :
  OrderedTable v2.PostId v2.PostRow -> AppStorage -> AppStorage
exercises.ex3_microblog.db.v2.AppStorage.postsTable.set postsTable1 = cases
  AppStorage database userHandleToUser userPostsTable _ followingTable ->
    AppStorage
      database userHandleToUser userPostsTable postsTable1 followingTable

exercises.ex3_microblog.db.v2.AppStorage.userHandleToUser :
  AppStorage -> OrderedTable UserHandle v2.UserRow
exercises.ex3_microblog.db.v2.AppStorage.userHandleToUser = cases
  AppStorage _ userHandleToUser _ _ _ -> userHandleToUser

exercises.ex3_microblog.db.v2.AppStorage.userHandleToUser.modify :
  (OrderedTable UserHandle v2.UserRow ->{g} OrderedTable UserHandle v2.UserRow)
  -> AppStorage
  ->{g} AppStorage
exercises.ex3_microblog.db.v2.AppStorage.userHandleToUser.modify f = cases
  AppStorage database userHandleToUser userPostsTable postsTable followingTable ->
    AppStorage
      database (f userHandleToUser) userPostsTable postsTable followingTable

exercises.ex3_microblog.db.v2.AppStorage.userHandleToUser.set :
  OrderedTable UserHandle v2.UserRow -> AppStorage -> AppStorage
exercises.ex3_microblog.db.v2.AppStorage.userHandleToUser.set userHandleToUser1 = cases
  AppStorage database _ userPostsTable postsTable followingTable ->
    AppStorage
      database userHandleToUser1 userPostsTable postsTable followingTable

exercises.ex3_microblog.db.v2.AppStorage.userPostsTable :
  AppStorage -> OrderedTable (UserHandle, OffsetDateTime) v2.PostRow
exercises.ex3_microblog.db.v2.AppStorage.userPostsTable = cases
  AppStorage _ _ userPostsTable _ _ -> userPostsTable

exercises.ex3_microblog.db.v2.AppStorage.userPostsTable.modify :
  (OrderedTable (UserHandle, OffsetDateTime) v2.PostRow
  ->{g} OrderedTable (UserHandle, OffsetDateTime) v2.PostRow)
  -> AppStorage
  ->{g} AppStorage
exercises.ex3_microblog.db.v2.AppStorage.userPostsTable.modify f = cases
  AppStorage database userHandleToUser userPostsTable postsTable followingTable ->
    AppStorage
      database userHandleToUser (f userPostsTable) postsTable followingTable

exercises.ex3_microblog.db.v2.AppStorage.userPostsTable.set :
  OrderedTable (UserHandle, OffsetDateTime) v2.PostRow
  -> AppStorage
  -> AppStorage
exercises.ex3_microblog.db.v2.AppStorage.userPostsTable.set userPostsTable1 = cases
  AppStorage database userHandleToUser _ postsTable followingTable ->
    AppStorage
      database userHandleToUser userPostsTable1 postsTable followingTable

exercises.ex3_microblog.db.v2.FollowingRow.createdAt :
  v2.FollowingRow -> OffsetDateTime
exercises.ex3_microblog.db.v2.FollowingRow.createdAt = cases
  v2.FollowingRow.FollowingRow _ _ _ createdAt -> createdAt

exercises.ex3_microblog.db.v2.FollowingRow.createdAt.modify :
  (OffsetDateTime ->{g} OffsetDateTime)
  -> v2.FollowingRow
  ->{g} v2.FollowingRow
exercises.ex3_microblog.db.v2.FollowingRow.createdAt.modify f = cases
  v2.FollowingRow.FollowingRow followingId follower target createdAt ->
    v2.FollowingRow.FollowingRow followingId follower target (f createdAt)

exercises.ex3_microblog.db.v2.FollowingRow.createdAt.set :
  OffsetDateTime -> v2.FollowingRow -> v2.FollowingRow
exercises.ex3_microblog.db.v2.FollowingRow.createdAt.set createdAt1 = cases
  v2.FollowingRow.FollowingRow followingId follower target _ ->
    v2.FollowingRow.FollowingRow followingId follower target createdAt1

exercises.ex3_microblog.db.v2.FollowingRow.follower :
  v2.FollowingRow -> UserHandle
exercises.ex3_microblog.db.v2.FollowingRow.follower = cases
  v2.FollowingRow.FollowingRow _ follower _ _ -> follower

exercises.ex3_microblog.db.v2.FollowingRow.follower.modify :
  (UserHandle ->{g} UserHandle) -> v2.FollowingRow ->{g} v2.FollowingRow
exercises.ex3_microblog.db.v2.FollowingRow.follower.modify f = cases
  v2.FollowingRow.FollowingRow followingId follower target createdAt ->
    v2.FollowingRow.FollowingRow followingId (f follower) target createdAt

exercises.ex3_microblog.db.v2.FollowingRow.follower.set :
  UserHandle -> v2.FollowingRow -> v2.FollowingRow
exercises.ex3_microblog.db.v2.FollowingRow.follower.set follower1 = cases
  v2.FollowingRow.FollowingRow followingId _ target createdAt ->
    v2.FollowingRow.FollowingRow followingId follower1 target createdAt

exercises.ex3_microblog.db.v2.FollowingRow.followingId :
  v2.FollowingRow -> v2.FollowingId
exercises.ex3_microblog.db.v2.FollowingRow.followingId = cases
  v2.FollowingRow.FollowingRow followingId _ _ _ -> followingId

exercises.ex3_microblog.db.v2.FollowingRow.followingId.modify :
  (v2.FollowingId ->{g} v2.FollowingId)
  -> v2.FollowingRow
  ->{g} v2.FollowingRow
exercises.ex3_microblog.db.v2.FollowingRow.followingId.modify f = cases
  v2.FollowingRow.FollowingRow followingId follower target createdAt ->
    v2.FollowingRow.FollowingRow (f followingId) follower target createdAt

exercises.ex3_microblog.db.v2.FollowingRow.followingId.set :
  v2.FollowingId -> v2.FollowingRow -> v2.FollowingRow
exercises.ex3_microblog.db.v2.FollowingRow.followingId.set followingId1 = cases
  v2.FollowingRow.FollowingRow _ follower target createdAt ->
    v2.FollowingRow.FollowingRow followingId1 follower target createdAt

exercises.ex3_microblog.db.v2.FollowingRow.target :
  v2.FollowingRow -> UserHandle
exercises.ex3_microblog.db.v2.FollowingRow.target = cases
  v2.FollowingRow.FollowingRow _ _ target _ -> target

exercises.ex3_microblog.db.v2.FollowingRow.target.modify :
  (UserHandle ->{g} UserHandle) -> v2.FollowingRow ->{g} v2.FollowingRow
exercises.ex3_microblog.db.v2.FollowingRow.target.modify f = cases
  v2.FollowingRow.FollowingRow followingId follower target createdAt ->
    v2.FollowingRow.FollowingRow followingId follower (f target) createdAt

exercises.ex3_microblog.db.v2.FollowingRow.target.set :
  UserHandle -> v2.FollowingRow -> v2.FollowingRow
exercises.ex3_microblog.db.v2.FollowingRow.target.set target1 = cases
  v2.FollowingRow.FollowingRow followingId follower _ createdAt ->
    v2.FollowingRow.FollowingRow followingId follower target1 createdAt

exercises.ex3_microblog.db.v2.PostRow.body : v2.PostRow -> Text
exercises.ex3_microblog.db.v2.PostRow.body = cases
  v2.PostRow.PostRow _ _ body _ -> body

exercises.ex3_microblog.db.v2.PostRow.body.modify :
  (Text ->{g} Text) -> v2.PostRow ->{g} v2.PostRow
exercises.ex3_microblog.db.v2.PostRow.body.modify f = cases
  v2.PostRow.PostRow id createdAt body userHandle ->
    v2.PostRow.PostRow id createdAt (f body) userHandle

exercises.ex3_microblog.db.v2.PostRow.body.set :
  Text -> v2.PostRow -> v2.PostRow
exercises.ex3_microblog.db.v2.PostRow.body.set body1 = cases
  v2.PostRow.PostRow id createdAt _ userHandle ->
    v2.PostRow.PostRow id createdAt body1 userHandle

exercises.ex3_microblog.db.v2.PostRow.createdAt : v2.PostRow -> OffsetDateTime
exercises.ex3_microblog.db.v2.PostRow.createdAt = cases
  v2.PostRow.PostRow _ createdAt _ _ -> createdAt

exercises.ex3_microblog.db.v2.PostRow.createdAt.modify :
  (OffsetDateTime ->{g} OffsetDateTime) -> v2.PostRow ->{g} v2.PostRow
exercises.ex3_microblog.db.v2.PostRow.createdAt.modify f = cases
  v2.PostRow.PostRow id createdAt body userHandle ->
    v2.PostRow.PostRow id (f createdAt) body userHandle

exercises.ex3_microblog.db.v2.PostRow.createdAt.set :
  OffsetDateTime -> v2.PostRow -> v2.PostRow
exercises.ex3_microblog.db.v2.PostRow.createdAt.set createdAt1 = cases
  v2.PostRow.PostRow id _ body userHandle ->
    v2.PostRow.PostRow id createdAt1 body userHandle

exercises.ex3_microblog.db.v2.PostRow.id : v2.PostRow -> v2.PostId
exercises.ex3_microblog.db.v2.PostRow.id = cases
  v2.PostRow.PostRow id _ _ _ -> id

exercises.ex3_microblog.db.v2.PostRow.id.modify :
  (v2.PostId ->{g} v2.PostId) -> v2.PostRow ->{g} v2.PostRow
exercises.ex3_microblog.db.v2.PostRow.id.modify f = cases
  v2.PostRow.PostRow id createdAt body userHandle ->
    v2.PostRow.PostRow (f id) createdAt body userHandle

exercises.ex3_microblog.db.v2.PostRow.id.set :
  v2.PostId -> v2.PostRow -> v2.PostRow
exercises.ex3_microblog.db.v2.PostRow.id.set id1 = cases
  v2.PostRow.PostRow _ createdAt body userHandle ->
    v2.PostRow.PostRow id1 createdAt body userHandle

exercises.ex3_microblog.db.v2.PostRow.userHandle : v2.PostRow -> UserHandle
exercises.ex3_microblog.db.v2.PostRow.userHandle = cases
  v2.PostRow.PostRow _ _ _ userHandle -> userHandle

exercises.ex3_microblog.db.v2.PostRow.userHandle.modify :
  (UserHandle ->{g} UserHandle) -> v2.PostRow ->{g} v2.PostRow
exercises.ex3_microblog.db.v2.PostRow.userHandle.modify f = cases
  v2.PostRow.PostRow id createdAt body userHandle ->
    v2.PostRow.PostRow id createdAt body (f userHandle)

exercises.ex3_microblog.db.v2.PostRow.userHandle.set :
  UserHandle -> v2.PostRow -> v2.PostRow
exercises.ex3_microblog.db.v2.PostRow.userHandle.set userHandle1 = cases
  v2.PostRow.PostRow id createdAt body _ ->
    v2.PostRow.PostRow id createdAt body userHandle1

exercises.ex3_microblog.db.v2.UserRow.avatar : v2.UserRow -> Optional URI
exercises.ex3_microblog.db.v2.UserRow.avatar = cases
  v2.UserRow.UserRow _ _ avatar -> avatar

exercises.ex3_microblog.db.v2.UserRow.avatar.modify :
  (Optional URI ->{g} Optional URI) -> v2.UserRow ->{g} v2.UserRow
exercises.ex3_microblog.db.v2.UserRow.avatar.modify f = cases
  v2.UserRow.UserRow userHandle name avatar ->
    v2.UserRow.UserRow userHandle name (f avatar)

exercises.ex3_microblog.db.v2.UserRow.avatar.set :
  Optional URI -> v2.UserRow -> v2.UserRow
exercises.ex3_microblog.db.v2.UserRow.avatar.set avatar1 = cases
  v2.UserRow.UserRow userHandle name _ ->
    v2.UserRow.UserRow userHandle name avatar1

exercises.ex3_microblog.db.v2.UserRow.name : v2.UserRow -> Text
exercises.ex3_microblog.db.v2.UserRow.name = cases
  v2.UserRow.UserRow _ name _ -> name

exercises.ex3_microblog.db.v2.UserRow.name.modify :
  (Text ->{g} Text) -> v2.UserRow ->{g} v2.UserRow
exercises.ex3_microblog.db.v2.UserRow.name.modify f = cases
  v2.UserRow.UserRow userHandle name avatar ->
    v2.UserRow.UserRow userHandle (f name) avatar

exercises.ex3_microblog.db.v2.UserRow.name.set :
  Text -> v2.UserRow -> v2.UserRow
exercises.ex3_microblog.db.v2.UserRow.name.set name1 = cases
  v2.UserRow.UserRow userHandle _ avatar ->
    v2.UserRow.UserRow userHandle name1 avatar

exercises.ex3_microblog.db.v2.UserRow.userHandle : v2.UserRow -> UserHandle
exercises.ex3_microblog.db.v2.UserRow.userHandle = cases
  v2.UserRow.UserRow userHandle _ _ -> userHandle

exercises.ex3_microblog.db.v2.UserRow.userHandle.modify :
  (UserHandle ->{g} UserHandle) -> v2.UserRow ->{g} v2.UserRow
exercises.ex3_microblog.db.v2.UserRow.userHandle.modify f = cases
  v2.UserRow.UserRow userHandle name avatar ->
    v2.UserRow.UserRow (f userHandle) name avatar

exercises.ex3_microblog.db.v2.UserRow.userHandle.set :
  UserHandle -> v2.UserRow -> v2.UserRow
exercises.ex3_microblog.db.v2.UserRow.userHandle.set userHandle1 = cases
  v2.UserRow.UserRow _ name avatar ->
    v2.UserRow.UserRow userHandle1 name avatar

exercises.ex3_microblog.deploy : '{IO, Exception} URI
exercises.ex3_microblog.deploy =
  todo "implement the deploy function for the microblogging site"

exercises.ex3_microblog.doc : Doc
exercises.ex3_microblog.doc =
  use Route <|> noCapture run
  use exercises.ex3_microblog.api createPost getPostById
  {{
  # 📰 Microblogging Site with Cloud Storage
  
    In this exercise, we'll build a simple microblogging web-service with a
    Cloud storage backend. The site will allow users to create posts, follow
    other users, and view posts from the users they are following.
    
    {{ docCallout
      (Some {{ 📚 }}) {{
      **What you'll learn:**
      
      * Routing and handling HTTP requests with the Routes library
      * Json serialization and deserialization with the Json library
      * Database schema design with multiple BTrees
      * Transactionality when storing and retrieving data
      }} }}
    
    We've broken this exercise down into three parts. Each part will guide you
    through a different aspect of building the microblogging service. We'll
    start with the basic HTTP service layer, then move on to JSON serialization
    and deserialization for the service, and finally, we'll design the storage
    layer and link it to the API.
    
    This exercise will involve some creativity and decision-making on your
    part, so feel free to experiment and try different approaches.
    
    ## Part 1: Writing the HTTP service API
    
       Let's start by defining a few endpoints for our service. We'll be
       implementing the logic for each of these endpoints later; for now, we'll
       ensure the following routes are present in the API and return 200 OK
       responses.
       
       {{ expectedRoutes }}
       
       ### Routes library basics
       
           We'll be using the
           [Routes](https://share.unison-lang.org/@unison/routes) library to
           define our endpoints.
           
           There are two top-level functions for defining an endpoint,
           {noCapture} and {route}. Use {noCapture} if your route does not
           capture any path parameters or {route}, if it extracts a path
           segment for use as a variable.
           
           The Routes library provides a few functions, such as {ok.text} or
           {headers.add}, that help build HTTP responses. Combining the two,
           route definition and http response construction, will create a
           complete endpoint:
           
               @source{createPost, getPostById}
           
           We recommend defining one function per route, and then combining
           them all together with {<|>} in a final call to {run}. {run}
           produces a function that takes an `HttpRequest` and returns an
           `HttpResponse`, which is the expected type for deploying an HTTP
           service.
           
               @signature{run}
           
           {{
           docCallout
             (Some {{ 📚 }})
             {{
             **Instructions**
             
             Define the remaining endpoints by having them return a 200 OK
             response for each route. The response body does not matter for
             now.
             
             We've provided two route stubs to use as a reference for this part
             of the exercise:
             
             * {getPostById} - "GET /api/posts/:id"
             * {createPost} - "POST /api/posts"
             
             Deploy all your routes as an HTTP service inside the provided
             {exercises.ex3_microblog.deploy} function. It should return the
             URI where the service is deployed.
             
             ``` ucm
             cloud-start/main> edit ex3_microblog.deploy
             ```
             
             When you're ready, `update` your codebase and run your solution.
             
             ``` ucm
             cloud-start/main> run submit.ex3_microblog.pt1
             ```
             }} }}
    
    ## Part 2: JSON serialization and deserialization
    
       Let's set up the service to return JSON responses. We'll need to define
       the data types for our posts, users, and followers, and then write
       functions to serialize and deserialize these data types to and from
       JSON. You can __name__ your data types and __add fields__ as you see
       fit, but they should conform to this JSON schema at minimum:
       
       {{ JsonSchema }}
       
       ### Using the Json library
       
           You may want to define the following data types for your service:
           
           ``` unison
           type client.User =
           type client.CreatePost =
           type client.Post =
           type client.Following =
           ```
           
           These "client-facing" models might have more or less information
           than what you'll eventually need in the database, so while it's
           possible to directly save the client-facing models in Cloud storage,
           its a good practice to decouple layers of the application which
           contain different data or evolve at different rates.
           
           Once you have your target data types, you'll need to use the
           [Json library](https://share.unison-lang.org/@unison/json) to
           serialize and deserialize them. Here's an example of turning a
           Unison data type into a Json string:
           
               @source{User.toJson}
           
           Turning a Unison datatype into a Json object typically takes the
           form of a pattern match on the data type, where the fields of the
           data type are translated into Json using constructors like
           {Json.object} or {Json.text}.
           
           Here's an example of turning a Json object into a Unison data type:
           
               @source{User.fromJson}
           
           We represent Json deserialization with the {type Decoder} ability.
           You can inspect keys with the {object.at} function and decode them
           into the appropriate type with functions like {Decoder.text} or
           {Decoder.int}.
           
           {{
           docCallout
             (Some {{ 📚 }})
             {{
             **Instructions**
             
             Update your service to expect and produce the following JSON data
             blobs. You can supply stub values for the JSON responses for now.
             
             When you're ready, `update` your codebase and run your solution.
             
             ``` ucm
             cloud-start/main> run submit.ex3_microblog.pt2
             ```
             }} }}
    
    ## Part 3: Implementing the storage layer and connecting to the web-service
    
       We've written the Http layer of the web-app; what remains is to
       implement the storage layer and the basic logic for the microblogging
       site. We'll give you some pointers and teach you how to interact with
       the database, but so long as the POST's and GET's to your service return
       the expected results, the design of the schema and the service
       implementation is up to you.
       
       {{
       docCallout
         (Some {{ 📚 }})
         {{
         If you haven't read our
         [tutorial for how to design a database schema using BTree](https://www.unison.cloud/docs/tutorials/schema-modeling/),
         you should check that out before starting this exercise.
         }} }}
       
       ### Schema design best practices and tips
       
           Because we've started with the API layer, we already know the
           queries we'll be making. Now we can work backwards to design the
           database schema. You should write a few types that your database
           will store and retrieve:
           
           ``` unison
           type db.UserRow =
           type db.PostRow =
           type db.FollowingRow =
           [...]
           ```
           
           **Questions you might consider in this process:**
           
           * How much data normalization is preferable for your app? Should
             your keys be randomly generated ID's which reference the data in
             another table, or should an entire data type be stored directly in
             the table?
           * How can you ensure the uniqueness of a given key in your BTree
             table? Random id? Timestamps? Etc?
             __For the purpose of this exercise, you can assume that a user's
             handle is unique.__
           * Are secondary sorts and filters ok to do in memory, or should you
             store the data in a way that makes these operations more
             efficient?
           * What database operations will require keeping multiple tables in
             sync? Cloud databases support transactions via the
             {type Transaction} ability, but they have size constraints and too
             many transactions can lock down your tables.
           
           Many of the tables will likely be BTree's—sorted key-value tables
           that support tuple key types and querying by ranges. As you're
           designing your schema consider leveraging both of those features.
           For example, if we needed to get a user's most recent posts, rather
           than storing all the user's posts in a list, we could store the
           posts in a BTree keyed by the User __and__ the timestamp of the
           post. This way, we can query the table via the User prefix, to get
           all the posts in a sorted order:
           
           ``` unison
           userPostsTable: BTree (UserHandle, OffsetDateTime) PostRow
           userPostsTable = Btree.named database "userPosts" Universal.ordering
           
           getUserPosts =
             rangeClosed.prefix userPostsTable BTree.prefixOrdering targetUser targetUser
               |> Stream.toList
           ```
           
           {{
           docCallout
             (Some {{ 📝 }})
             {{
             Once you've thought about the set of tables needed to support the
             app, update your deploy function to create the {type Database} and
             tables.
             
             Feeling stuck? Check out the example schema in {type AppStorage}.
             
             When you're finished the deploy function should do the following:
             
             * Create a database for your application with
               @inlineSignature{Database.named}
             * Assign the database to your service environment with
               @inlineSignature{Database.assign}
             * Create each of the tables that house your Posts, Users, and
               Follower relationships with @inlineSignature{OrderedTable.named}
             * Deploy the http service, providing the necessary storage
               entities to the routes.
             
             ``` ucm
             cloud-start/main> edit ex3_microblog.deploy
             ```
             }} }}
       
       ### Transactions and other abilities in database interactions
       
           Once you've settled on your data types and schema, you can get
           started writing database interactions, let's look at an example
           which creates a user in the database:
           
           {{ docSource [docSourceElement (docEmbedTermLink do createuser) []]
           }}
           
           Cloud services don't have access to arbitrary IO, so generating
           timestamps or random ID's will require using the {type Remote}
           ability. We're using {now!} and {Remote.randomBytes} instead of IO.
           
           The {{ docLink (docEmbedTermLink do createuser) }} function is also
           using the {type Transaction} ability to perform multiple operations
           that should fail or succeed together. Most functions defined for
           updating records in a BTree have a transactional variant, suffixed
           with `.tx`.
           
           Because we're __writing__ to a BTree, the transaction also requires
           the {type Random} ability. Depending on what abilities your combined
           database operations require, run the transaction in one of the
           following:
           
               @signatures{transact, transact.random}
           
           {{
           docCallout
             (Some {{ 📝 }})
             {{
             **Instructions**
             
             Write the remaining database functions for the microblogging site
             and call them inside your earlier service route functions.
             
             Your service routes should do the following:
             
             * They should run the necessary database operations to create,
               read, update, and delete data.
             * They should translate the types returned from the database layer
               into the types expected by the API layer.
             * They should represent various errors from the database layer in
               terms of http status codes.
             
             We won't test for __all__ of the possible workflows in your app,
             but we will check if your service can create a new user, have that
             user create a post, and then retrieve that post by its id. We'll
             also check if your app allows a user to folllow another user, so
             that they can see a microblog feed of interesting posts.
             
             When you're ready, `update` your codebase and submit your
             solution.
             
             ``` ucm
             cloud-start/main> run submit.ex3_microblog.roundTrip
             ```
             }} }}
  }}

exercises.ex3_microblog.doc.expectedRoutes : Doc
exercises.ex3_microblog.doc.expectedRoutes =
  {{
  **User Routes**
  
  For the purpose of these routes, you can assume the user's handle looks like
  `@userName`. Don't worry about encoding the `@` symbol in the URL.
  
  * `POST /api/user/:handle` - Creates a new user
  * `GET /api/user/:handle/posts` - Returns all posts of a user by their
    handle, ordered by time
  
  **Post Routes**
  
  * `POST /api/posts` - Creates a new post
  * `GET /api/posts/:id` - Returns a post by its ID
  
  **Follower Routes**
  
  * `POST /api/follow/:handle` - Follows a user by their handle
  
  **Feed Routes**
  
  * `GET /api/feed/:handle` - Returns all posts of the people the user
    (identified by their handle) is following. Ordered by time.
  }}

exercises.ex3_microblog.doc.JsonSchema : Doc
exercises.ex3_microblog.doc.JsonSchema =
  {{
  # User endpoints
  
    **POST /api/user/:handle**
    
    Creates a new user.
    
    Request Body:
    
    ``` json
    {
      "userHandle" : "@bob",
      "name" : "Bob Bob",
      "avatar" : "https://example.com/avatar.jpg"
    }
    ```
    
    Where the "avatar" field is optional.
    
    Response Body:
    
    ``` json
    {
      "userId" : "SomeTextUserId"
    }
    ```
    
    **GET /api/user/:handle/posts**
    
    Returns all posts of a user by their handle
    
    The response body from the GET request should look like:
    
    ``` json
    [
      {
        "body" : "Blog Text",
        "name" : "Bob Bob",
        "userHandle" : "@bob",
        "timestamp" : "2021-01-01T00:00:00Z"
      }
    ]
    ```
    
    Where the "avatar" field is optional.
  
  # Post endpoints
  
    **POST /api/posts**
    
    Creates a new post.
    
    Expects a request body with the following form:
    
    ``` json
    {
      "body" : "Blog Text",
      "userId" : "SomeTextUserId"
    }
    ```
    
    The response JSON should look like:
    
    ``` json
    {
      "postId" : "SomeTextPostId"
    }
    ```
    
    **GET /api/posts/:id**
    
    Returns a post by its ID.
    
    The response JSON look like:
    
    ``` json
    {
      "body" : "Text",
      "name" : "Bob Bob",
      "userHandle" : "@bob",
      "timestamp" : "2021-01-01T00:00:00Z"
    }
    ```
  
  # Follower endpoints
  
    **POST /api/follow/:handle**
    
    Should contain a JSON request body with the following:
    
    ``` json
    {
      "follower" : "SomeTextFollowingId",
      "target" : "SomeTextFollowingId"
    }
    ```
    
    The response JSON should look like:
    
    ``` json
    {
      "followingId" : "SomeTextFollowingId"
    }
    ```
  
  # User "feed" endpoint
  
    **GET /api/feed/:handle**
    
    Returns all posts of the users that the given handle is following.
    
    The response should be a Json array:
    
    ``` json
    [
      {
        "body" : "Blog Text",
        "name" : "Bob Bob",
        "userHandle" : "@bob",
        "timestamp" : "2021-01-01T00:00:00Z"
      }
    ]
    ```
  }}

exercises.ex4_oauth.deploy : '{IO, Exception} URI
exercises.ex4_oauth.deploy =
  do
    Cloud.run do
      use exercises env
      database = Database.named "todo-auth-service-db"
      todoTable : OrderedTable (ex4_oauth.UserId, Text) TodoItem
      todoTable = OrderedTable.named database "todo-table" Universal.ordering
      Database.assign database env()
      serviceHash =
        deployHttp
          env()
          (Route.run (exercises.ex4_oauth.todoService todoTable database))
      name = ServiceName.named "todo-service"
      ServiceName.assign name serviceHash

exercises.ex4_oauth.doc : Doc
exercises.ex4_oauth.doc =
  {{
  # Add Auth to an HTTP Todo app
  
    In this exercise, you'll add authentication logic to an existing HTTP
    application.
    
    The todo app in this exercise is already set up with endpoints to create
    and update todos, however, it lacks a working user model. Currently,
    everyone can see and modify everyone else's todos! Let's add OAuth2 (with
    authentication provided by OpenID connect) to the app so that each user can
    only see and modify their own todos.
    
    {{ docCallout
      (Some {{ 🍎 }}) {{
      **What you'll learn**
      
      * A wee bit about OAuth 🤏
      * How to incorporate the `Auth` ability in HTTP service logic
      * The conventions and configuration options for the `Auth` ability
      * Securely storing user sessions with the `Auth` ability
      * An example walk-through for configuring an identity provider
      }} }}
    
    The wonderful
    [Auth library](https://share.unison-lang.org/@chrispenner/auth) ecosystem
    provides authentication support for the Cloud. The libraries you need are
    already installed in the cloud-start project, but if you were starting from
    scratch, you should `lib.install` the following:
    
    * [The `Routes` library](https://share.unison-lang.org/@unison/routes) -
      For writing HTTP service endpoints
    * [The `Auth` library](https://share.unison-lang.org/@chrispenner/auth) - A
      simple, Routes-library-friendly interface for authentication
    * [The `OAuth2` library](https://share.unison-lang.org/@alvaroc1/oauth2) -
      Contains helper functions for configuring Google, Github, etc.
    * [The `JWT` library](https://share.unison-lang.org/@alvaroc1/jwt) - For
      decoding JSON Web Tokens
    
    ## Why we need OAuth and the `Auth` ability
    
       Currently, the todo app has the following routes:
       
       * PUT `/todo` - Creates a new todo item
       * GET `/todos` - Lists all the todos
       * GET `/todo/:todoId` - Gets a specific todo item
       * DELETE `/todo/:todoId` - Deletes the todo item
       
       It also has a home page at "/" which provides a (very ugly 👹) form for
       administering todos.
       
       The todo app is backed by a simple Cloud database which stores the items
       keyed by a stub `UserId` text value. We do **not** want to have to
       create and maintain a "User table" that maps the `UserId` to usernames
       and passwords, so we'll rely on OAuth to avoid the security pitfalls of
       credential management.
       
       {{
       docCallout
         (Some {{ 📚 }})
         {{
         📚 OAuth2 is a security standard where a user allows an application
         granular access to their data via another "authorization service."
         With OAuth in place, the client application does not need to store
         user credentials and instead relies on a back-and-forth exchange of
         tokens for verification. OAuth is an
         ___authorization protocol__, meaning it describes what resources a
         user has access to, not user identity, but it can also be been
         extended to handle__authentication___ with OpenID Connect.
         }} }}
       
       OAuth can be…
       [complex](https://developer.okta.com/blog/2017/06/21/what-the-heck-is-oauth).
       😵‍💫 Fortunately, the `Auth` ability abstracts away much of it for us!
       
           @source{type Auth}
       
       Let's break down the `Auth` ability in terms of how you'll use it in an
       app:
       
       * The `session` type parameter can be any type that your application
         uses to represent a logged-in user. This type becomes a cookie that
         the user's browser stores upon sign-in and sends back with each
         request.
       * `requireSession : {Auth session} session` - Initiates a user
         session—this function starts the auth process if a user hasn't logged
         in already or returns the active session if they have.
       * `getSession : {Auth session} (Optional session)` - Returns the `Some`
         session if the user is logged in, or `Optional.None` if not.
       
       The `Auth` ability defines a __simple interface__ for use in your
       service logic, but it requires a handler that specifies details like
       what platform the user should sign in with. You'll need to register your
       app with an external OAuth provider and configure it to match. The
       subsequent parts of this exercise break down that process.
       
       [Part 1: Configuring the Auth ability]({ex4_oauth.doc.pt1})
  }}

exercises.ex4_oauth.doc.pt1 : Doc
exercises.ex4_oauth.doc.pt1 =
  {{
  # Part 1: Configuring the Auth ability
  
    To use the {type Auth} ability we'll first need an instance of the
    {type AuthConfig} type. This type establishes the contract between the auth
    provider and the application.
    
    We'll use the `defaultCloud` helper function to construct an `AuthConfig`
    value with some Cloud-specific defaults and security benefits.
    
        @signature{defaultCloud}
    
    {{
    docCallout
      (Some {{ 📓 }})
      {{
      **Instructions**
      
      In the {{ (docLink (docEmbedTermLink do exercises.ex4_oauth.deploy)) }}
      function, start creating the {type AuthConfig} value, these stub values
      are fine for now. We'll be filling in the following arguments one at a
      time:
      
      ``` unison
      hmacKey : HMACKey
      hmacKey = todo "HMACKey"
      oauthClient : Oauth2Client IdToken
      oauthClient = todo "oauthClient"
      oauthScopes : Optional Text
      oauthScopes = todo "scopes"
      onSuccess : TokenResponse IdToken ->{Exception, Http, Log} ex5_oauth.UserId
      onSuccess = todo "successCallback"
      jsonDecoder : '{Decoder} ex5_oauth.UserId
      jsonDecoder = todo "jsonDecoder"
      jsonEncoder : : ex5_oauth.UserId -> Json
      jsonEncoder = todo "jsonEncoder"
      
      authConfig: AuthConfig {Http, Exception, Log} IdToken ex5_oauth.UserId
      authConfig = defaultCloud
        hmacKey oauthClient oauthScopes onSuccess jsonDecoder jsonEncoder
      ```
      }} }}
    
    ## Session cookie security with HMAC
    
       When a user logs in, the Auth library creates a cookie that contains
       information about the user's session. This cookie is signed with an
       {type HMACKey} to prevent tampering.
       
       The `defaultCloud` function takes care of the signing and verification
       process when it writes the session cookie to the browser, so you just
       need to provide an {type HMACKey} value and transform it into
       {type Bytes}.
       
       Some important security reminders when dealing with cookies:
       
       **Don't commit your secret keys to your codebase!**
       
       The {type HMACKey} should __not__ be committed to your codebase as a
       literal value or stored in regular Cloud databases. Instead, you should
       store secret values in an environment variable on the command line. You
       can also load it into the Cloud's secure {type Environment.Config}
       storage.
       
       **It's important to sign cookies in the Cloud!**
       
       If you do not sign your cookies, bad actors could write cookies to the
       browser in an attempt to impersonate the user. Signing and verifying the
       cookie ensures that authentication will fail if the cookie has been
       tampered with.
       
       {{
       docCallout
         (Some {{ 📚 }})
         {{
         **Instructions**
         
         Create an environment variable for your {type HMACKey} and use it to
         implement the `hmacKey` argument to the `defaultCloud` function.
         
         The `IO.getEnv` function reads an environment variable as a `Text`
         value.
         
         ``` unison
         hmacKey : HMACKey
         hmacKey = HMACKey (Text.toUtf8 (IO.getEnv "HMAC_KEY"))
         ```
         }} }}
       
       Let's continue on to implement the `oauthClient` and `oauthScopes`
       fields. They need to match values that we'll obtain from a third-party
       auth provider.
       
       [Part 2: Configuring an auth provider]({ex4_oauth.doc.pt2})
  }}

exercises.ex4_oauth.doc.pt2 : Doc
exercises.ex4_oauth.doc.pt2 =
  {{
  # Part 2: Configuring an auth provider
  
    This step uses Google Cloud Platform as an auth provider as an example.
    We'll configure the consent screen, create an OAuth2 client, and set up the
    scopes that our app will request from Google. You can follow a similar
    process with other providers like GitHub, Facebook, or Twitter.
    
    Head to the
    [Google Cloud Platform Console](https://console.cloud.google.com/). The
    Google Cloud service that we'll want is the "APIs and Services" product.
    Once there, head to the "Credentials" section.
    
    ## Configure the consent screen
    
       If you've never created an OAuth client on Google Cloud before, you'll
       need to set up a consent screen. This is the page that the user will see
       when they sign in to our Todo app and give it permission to access their
       Google account.
       
       Google will prompt you to select "Internal" or "External" for the user
       type. For this exercise, select "External" to enable your application to
       reach anyone with a Google email. We will deploy our "External"
       application in "Testing" mode so we won't need to verify it.
       
       Next, Google's consent form will ask for a few pieces of information to
       display. The "home page" value should look like
       `https://<yourHandle>.unison-services.cloud/s/todo-service/`. For now,
       feel free to enter "https://www.unison.cloud/privacy-policy/" and
       "https://www.unison.cloud/terms-of-service/" as the values for your
       privacy policy and terms of service. If you wanted to submit your app
       for verification, these would need to be real pages associated with your
       app's domain.
       
       ### Selecting OAuth Scopes
       
           Scopes describe the kinds of user data our todo app is asking to use
           on behalf of the user. For example, we might request read/write
           access to the user's calendar if we wanted our todo app to be able
           to schedule tasks.
           
           [There are many options to choose from,](https://developers.google.com/identity/protocols/oauth2/scopes)
           but for the purpose of this exercise, we only need to request the
           "openid" scope from Google. The
           [OpenID](https://openid.net/developers/how-connect-works/) scope
           verifies the user's identity but provides no other user information.
           Picking this scope ensures that the auth provider will return a
           value in the `TokenResponse` that contains a field called `sub`
           which represents a unique identifier for the authenticated user.
           
           {{
           docCallout
             (Some {{ 📓 }})
             {{
             **Instructions**
             
             "openid" is **already included** in the list of scopes provided by
             the `defaultCloud` config helper, so our `oauthScopes` field can
             be left as `Optional.None`.
             
             Fill that out now in the `ex4_oauth.deploy` function.
             
             ``` unison
             oauthScopes = Optional.None
             ```
             }} }}
           
           If you were to select more scopes for this consent screen, they
           should be added to the the "oauthScopes" field in a
           **space-delimited string.**
           
           Common scope requests include "email" and "profile" values. Here's
           what it would look like to request email, profile, and calendar
           management scopes:
           
           ``` unison
           oauthScopes = Some "email profile https://www.googleapis.com/auth/admin.directory.resource.calendar"
           ```
           
           Finally, Google will ask you to create some "Test Users" for the
           app. Add your own email address to test the todo app's OAuth flow.
    
    ## Create the Google OAuth2 Client
    
       Select "Create Credentials" and then "OAuth Client ID". You'll be
       prompted to select the application type. For this exercise, select "Web
       Application" and give your client a name.
       
       Your authorized javascript origins should look something like
       `https://<shareHandle>.unison-services.cloud`.
       
       The "Authorized redirect URI" is where Google will send the user after
       they've successfully logged in. Auth library provides an
       "oauth/redirect" endpoint for this purpose, so this value should follow
       the pattern:
       
       ``` raw
       https://<handle>.unison-services.cloud/s/todo-service/oauth/redirect
       ```
       
       Click "Create Client" to see the values for your client id and secret.
       You'll need them to configure your `defaultCloud` function.
       
       {{
       docCallout
         (Some {{ 📓 }})
         {{
         **Instructions**
         
         Save the client id and secret to environment variables. Next, change
         the `ex4_oauth.deploy` function to read the client id and secret from
         your environment variables and pass them to the
         `google : ClientId -> ClientSecret -> Oauth2Client IdToken` helper
         function from the
         [OAuth2](https://share.unison-lang.org/@alvaroc1/oauth2) library.
         
         The first three values for your constructing your `AuthConfig` are
         done! 🎉 Your code should look something like this:
         
         ``` unison
         hmacKey : HMACKey
         hmacKey = HMACKey (Text.toUtf8 (IO.getEnv "HMAC_KEY"))
         clientId = getEnv "GOOGLE_CLIENT_ID"
         clientSecret = getEnv "GOOGLE_CLIENT_SECRET"
         oauthClient : Oauth2Client IdToken
         oauthClient = google (ClientId clientId) (ClientSecret clientSecret)
         oauthScopes : Optional Text
         oauthScopes = None
         ```
         }} }}
       
       [Part 3: Define your Session type]({ex4_oauth.doc.pt3})
  }}

exercises.ex4_oauth.doc.pt3 : Doc
exercises.ex4_oauth.doc.pt3 =
  {{
  # Part 3: Define your session type
  
    The final three fields to implement for the `defaultCloud` function relate
    to handling the response from the identity provider and creating the
    `session` type that parameterizes the `Auth` ability. Once the user
    successfully signs in, the auth provider sends the app a response
    containing a token representing the user's identity.
    
    Your task is to tell the app how to transform this token response into the
    `session` type in the `onSuccess` callback function.
    
    ``` unison
    [...]
    onSuccess : TokenResponse IdToken ->{Exception, Http, Log} ex4_oauth.UserId
    onSuccess = todo "successCallback"
    decodeSession : '{Decoder} ex4_oauth.UserId
    decodeSession = todo "decodeSession"
    encodeSession : : ex4_oauth.UserId -> Json
    encodeSession = todo "encodeSession"
    ```
    
    We've decided that the "session" type is a {type ex4_oauth.UserId}: a
    simple wrapper around a {type Text} id value, but if our model of an
    "signed in user" needed more information, such as the user's email, we
    could also extract that information from the `TokenResponse`.
    
    The JSON encoder and decoder functions are used by the {type Auth} library
    when saving the `session` type as a cookie in the browser.
    
    {{
    docCallout
      (Some {{ 📓 }})
      {{
      **Instructions**
      
      Implement the `onSuccess` callback function. Its argument,
      `TokenResponse IdToken`, is a wrapper around a text value representing a
      [JWT](https://jwt.io/introduction).
      
      The `onSuccess` function should do the following:
      
      * Decode the JWT text into a `JWT` type with the
        {alvaroc1_jwt_0_0_1.decode} function
      * Extract the `sub` value from it with {Jwt.sub}. (Remember that value
        from our scopes configuration step? 😉) This is the unique user id for
        the identity provider
      * Use the `sub` value to create an instance of the `ex4_oauth.UserId`
        type
      
      Finally, use the
      [JSON library](https://share.unison-lang.org/@unison/json) to write the
      `encodeSession` and `decodeSession` functions. They should encode and
      decode the `ex4_oauth.UserId` into a json object which looks like this:
      
      ``` json
      {
        "user_id": "unique-user-id-as-string"
      }
      ```
      
      At this point, your {defaultCloud} function should have all its arguments
      implemented. You've made your {type AuthConfig} type! The hard part is
      done! 🚀
      }} }}
    
    [Part 4: Use the Auth ability in your service]({pt4})
  }}

exercises.ex4_oauth.doc.pt4 : Doc
exercises.ex4_oauth.doc.pt4 =
  use oauth2 handler
  {{
  # Use the Auth ability in your service
  
    With the {type AuthConfig} created, we are set up to __use__ the
    {type Auth} ability in the service to ensure that the appropriate todos are
    served to each user.
    
    The {type Auth} library provides a handler called {handler} for use with
    any {type Routes} based HTTP service. It also appends the following routes
    to the service:
    
    * /login - Redirects the user to the identity provider's login page
    * /logout - Logs the user out and redirects them to the home page
    * /oauth/redirect - A callback used for completing the OAuth2 flow
    
    {{
    docCallout
      (Some {{ 📓 }})
      {{
      **Instructions**
      
      {routes.todoService} defines the todo app's current endpoints. Change the
      {exercises.ex4_oauth.deploy} function to pass {routes.todoService} to the
      {handler} function before the routes are given as an argument to
      {Route.run}.
      
      Save the scratch file and `update` your codebase.
      }} }}
    
    On to the {routes.todoService} function proper! `view` it in the UCM to see
    how the current {type ex4_oauth.UserId} works:
    
    ``` unison
    exercises.ex4_oauth.todoService :
      -> BTree (ex4_oauth.UserId, Text) TodoItem
      -> Database
      -> '{Route, Exception, State, Remote, Log} ()
    exercises.ex4_oauth.todoService html todoTable db =
      _ = "Oh no, we need a real UserId!"
      userIdSession = ex4_oauth.UserId.UserId "stubValue"
      [...]
    ```
    
    We'll be adding calls to `getSession` for endpoints where a user should be
    signed in to access todos. Let's reiterate the "business logic" of the
    todo-app in simple `Auth` ability terms:
    
    * If a user issues a request to add, delete, edit, or view todos, check if
      they're signed in with `getSession`. If the value from `getSession` is
      `Optional.None`, the service returns a 401 response.
    * If the user is able to authenticate, the `Auth` functions return a
      `UserId` as the session type. The `UserId` is then used for database
      lookups.
    
    {{
    docCallout
      (Some {{ 📓 }})
      {{
      📓 **Instructions**
      
      ``` ucm
        cloud-start/main> edit ex4_oauth.todoService
      ```
      
      Change the {exercises.ex4_oauth.todoService} function to get the
      authenticated user's {type ex4_oauth.UserId} from the {type Auth} ability
      or return a 401 Unauthorized response if the user is not authenticated.
      No changes to the database schema or query logic are needed for this
      exercise!
      
      Save the scratch file and `update` your codebase. Test the login flow by
      running the `deploy` function in the UCM.
      
      ``` ucm
      cloud-start/main> run ex4_oauth.deploy
      ```
      
      Remember to sign in at the "/login" route of your service! It's another
      freebie from the Auth ecosystem.
      
      When you're ready, submit your solution for validation.
      
      ``` ucm
      cloud-start/main> run submit.ex4_oauth.roundtrip
      ```
      
      Congratulations! You've added authentication to a Cloud service! 🥳
      }} }}
  }}

exercises.ex4_oauth.todoService :
  OrderedTable (ex4_oauth.UserId, Text) TodoItem
  -> Database
  -> '{Route, Exception, unison_cloud_19_0_0.Storage, Remote, Log} ()
exercises.ex4_oauth.todoService todoTable db =
  use Parser / s
  use Route <|> noCapture
  use Text ++
  use TodoItem toJson
  _ = "Oh no, we need a real UserId!"
  userIdSession = ex4_oauth.UserId.UserId "stubValue"
  home : '{Route} ()
  home = do
    noCapture GET Parser.root
    ok.html todoService.html
  getTodoItem : '{Route, Exception, Remote} ()
  getTodoItem = do
    todoId = route GET (s "todo" / Parser.text)
    todoKey = (userIdSession, todoId)
    match catch do OrderedTable.read todoTable todoKey with
      Right todoItem -> ok.json (toJson todoItem)
      Left _         -> notFound.text ("todo item not found " ++ todoId)
  getTodoItems : '{Route, Exception, Remote, Log} ()
  getTodoItems =
    do
      name = noCapture GET (s "todos")
      records =
        rangeClosed.prefix
          todoTable OrderedTable.prefixOrdering userIdSession userIdSession
          |> Stream.toList
      jsonRecords = Json.array (List.map (r -> at2 r |> toJson) records)
      info.json "records" jsonRecords
      ok.json jsonRecords
  putTodoItem : '{Route, Exception, Remote} ()
  putTodoItem = do
    name = noCapture PUT (s "todo")
    todoItem : {Route, Exception} TodoItem
    todoItem = decodeJson TodoItem.fromJson
    todoId = TodoItem.id todoItem
    todoKey = (userIdSession, todoId)
    match catch do randomly do BTree.write todoTable todoKey todoItem with
      Left e  -> badRequest.text ("failed to write todo item " ++ todoId)
      Right _ -> ok.text ("created todo item " ++ todoId)
  deleteTodoItem : '{Route, Exception, Remote} ()
  deleteTodoItem = do
    id = route DELETE (s "todo" / Parser.text)
    todoKey = (userIdSession, id)
    match catch do OrderedTable.delete todoTable todoKey with
      Left _  -> badRequest.text ("todo item failed to be  found " ++ id)
      Right _ -> ok.text ("deleted todo item " ++ id)
  home <|> getTodoItem <|> putTodoItem <|> deleteTodoItem <|> getTodoItems

exercises.ex4_oauth.todoService.html : Text
exercises.ex4_oauth.todoService.html =
  """
  <!doctype html>
  <html lang="en">
    <head>
      <meta charset="UTF-8" />
      <meta name="viewport" content="width=device-width, initial-scale=1.0" />
      <title>Todo List</title>
      <link rel="preconnect" href="https://fonts.googleapis.com" />
      <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
      <link
        href="https://fonts.googleapis.com/css2?family=Inter:wght@100..900&display=swap"
        rel="stylesheet"
      />
      <style>
        :root {
          --sz-0: 1px;
          --sz-1: 0.125rem;
          --sz-2: 0.25rem;
          --sz-3: 0.5rem;
          --sz-4: 0.625rem;
          --sz-5: 0.75rem;
          --sz-6: 0.875rem;
          --sz-7: 1rem;
          --sz-8: 1.25rem;
          --sz-9: 1.5rem;
          --sz-10: 2rem;
          --sz-11: 3rem;
          --sz-12: 3.5rem;
          --sz-13: 4rem;
  
          --color-green: #52d188;
          --color-blue: #5595f4;
          --color-background: #fff;
          --color-container: #f1f3f5;
          --color-primary: #18181c;
          --color-primary-action: var(--color-blue);
          --color-primary-action-text: #fff;
          --color-subdued: #818286;
          --color-very-subdued: #bdbfc6;
          --color-border: #d1d5dc;
        }
  
        html {
          font-size: 16px;
        }
  
        body {
          font-family: "Inter", sans-serif;
          font-size: var(--sz-7);
          color: var(--color-primary);
          background: var(--color-background);
        }
  
        main {
          width: 42rem;
          margin: auto;
          margin-top: var(--sz-13);
        }
  
        input[type="text"] {
          padding: var(--sz-2) var(--sz-3);
        }
  
        button {
          border: 0;
          color: var(--color-primary-action-text);
          background: var(--color-primary-action);
          font-weight: bold;
          font-size: var(--sz-6);
          padding: var(--sz-2) var(--sz-3);
          border-radius: var(--sz-2);
        }
  
        h1 {
          font-size: var(--sz-10);
          font-weight: 900;
        }
  
        h2 {
          font-size: var(--sz-8);
        }
  
        form {
          display: flex;
          flex-direction: row;
          align-items: center;
          gap: var(--sz-6);
          padding: var(--sz-7);
          background: var(--color-container);
          border-radius: var(--sz-2);
          line-height: 1;
        }
  
        form label {
          display: flex;
          flex-direction: row;
          align-items: center;
          gap: var(--sz-1);
        }
  
        .todo-item {
          display: flex;
          flex-direction: row;
          justify-content: space-between;
          padding: var(--sz-3);
          border-bottom: 1px solid var(--color-border);
        }
  
        .completed span {
          text-decoration: line-through;
          color: var(--color-green);
        }
  
        .todo-item input[type="checkbox"] {
          margin-right: var(--sz-3);
        }
      </style>
      <script>
        window.addEventListener("load", () => {
          console.log('Window has fully loaded');
  
          const addForm = document.getElementById("add-form");
          const addEntryInput = document.getElementById("add-entry");
          const addCompletedInput = document.getElementById("add-completed");
          const currentUrl = `${location.protocol}//${location.host}${location.pathname}`;
  
          async function addTodo(entry, completed) {
            try {
              const todosUrl = `${currentUrl}todo`;
              const todoId = Date.now().toString();
              const response = await fetch(todosUrl, {
                method: "PUT",
                credentials: "include", // Ensures cookies are included for auth
                headers: {
                  "Content-Type": "application/json"
                },
                body: JSON.stringify({
                  id: todoId,
                  entry: entry,
                  completed: completed
                })
              });
  
              if (!response.ok) {
                throw new Error("Network response was not ok");
              }
  
              fetchTodos();
            } catch (error) {
              console.error("Error adding todo:", error);
            }
          }
  
          // Event listener for adding todo submission
          addForm.addEventListener("submit", (event) => {
            event.preventDefault();
            const entry = addEntryInput.value;
            const completed = addCompletedInput.checked;
  
            addTodo(entry, completed);
          });
  
          // Function to fetch all todos from the API
          async function fetchTodos() {
            try {
              const todosUrl = `${currentUrl}todos`;
  
              const response = await fetch(todosUrl, {
                method: "GET",
                credentials: "include",
                headers: {
                  "Content-Type": "application/json"
                }
              });
  
              if (!response.ok) {
                throw new Error("Network response was not ok");
              }
              const todos = await response.json();
              displayTodos(todos);
            } catch (error) {
              console.error("Error fetching todos:", error);
            }
          }
  
          function displayTodos(todos) {
            let todoContainer = document.getElementById("todo-container");
            todoContainer.innerHTML = "";
  
            todos.forEach(todo => {
              let todoItem = document.createElement("div");
              todoItem.className = "todo-item";
              if (todo.completed) {
                todoItem.classList.add("completed");
              }
  
              let checkbox = document.createElement("input");
              checkbox.type = "checkbox";
              checkbox.checked = todo.completed;
              checkbox.addEventListener("change", () => {
                todoItem.classList.toggle("completed");
                editTodo(todo, checkbox.checked);
              });
  
              let text = document.createElement("span");
              text.textContent = todo.entry;
  
              let deleteButton = document.createElement("button");
              deleteButton.textContent = "Delete";
              deleteButton.addEventListener("click", (event) =>
                deleteTodo(todo.id, event)
              );
  
              todoItem.appendChild(checkbox);
              todoItem.appendChild(text);
              todoItem.appendChild(deleteButton);
              todoContainer.appendChild(todoItem);
            });
          }
  
          async function editTodo(todo, isCompleted){
            try {
              const editTodosUrl = `${currentUrl}todo/${todo.id}`;
              const response = await fetch(editTodosUrl, {
                method: "PUT",
                credentials: "include",
                headers: {
                  "Content-Type": "application/json"
                },
                body: JSON.stringify({
                  id: todo.id,
                  entry: todo.entry,
                  completed: isCompleted
                })
              });
  
              if (!response.ok) {
                throw new Error("Network response was not ok");
              }
            } catch (error) {
              console.error("Error editing todo:", error);
            }
          };
  
          async function deleteTodo(todoId, event) {
            event.preventDefault();
  
            try {
              const deleteTodosUrl = `${currentUrl}todo/${todoId}`;
  
              const response = await fetch(deleteTodosUrl, {
                method: "DELETE",
                credentials: "include",
                headers: {
                  "Content-Type": "application/json"
                }
              });
  
              await response;
  
              if (!response.ok) {
                throw new Error("Network response was not ok");
              }
  
              fetchTodos();
            } catch (error) {
              console.error("Error deleting todo:", error);
            }
          }
  
          // Fetch and display todos on page load
          fetchTodos();
        }, { once: true });
      </script>
    </head>
    <body>
      <main>
        <h1>Todo</h1>
        <form id="add-form" class="add-form">
          <input type="text" id="add-entry" placeholder="New todo" required />
          <label>
            <input type="checkbox" id="add-completed" />
            Completed?
          </label>
          <button type="submit">Add</button>
        </form>
        <div id="todo-container"></div>
      </main>
    </body>
  </html>
  """

exercises.ex5_webSockets.aboutWebsockets.summary : Doc
exercises.ex5_webSockets.aboutWebsockets.summary =
  {{
  WebSockets are a communication protocol that enables two-way communication
  between a client and server. Unlike HTTP, which follows a request-response
  model, WebSocket connections between the client and server are
  **persistent**, eliminating the need for repeated HTTP requests. WebSockets
  allow for low-latency communication, making it ideal for real-time
  applications such as chat apps, online gaming, and financial trading
  platforms.
  }}

exercises.ex5_webSockets.chatHandlerService :
  Cell (Set unison_cloud_19_0_0.websockets.WebSocket)
  -> HttpRequest
  -> Either
    HttpResponse
    (unison_cloud_19_0_0.websockets.WebSocket
    ->{Exception, Remote, WebSockets} ())
exercises.ex5_webSockets.chatHandlerService cell = cases
  HttpRequest.HttpRequest _ _ (URI _ _ (Path [username]) _ _) _ _ ->
    Right (webSocketChatHandler cell username)
  _ -> Left HttpResponse.badRequest

exercises.ex5_webSockets.deploy : '{IO, Exception} URI
exercises.ex5_webSockets.deploy = do
  Cloud.run do
    use exercises env
    database = Database.named "cloudExerciseDB"
    Database.assign database env()
    cell = Cell.named database "WebSocketConnections" Set.empty
    sh = deployHttpWebSocket env() (_ -> Right (webSocketStateHandler cell))
    sn = ServiceName.named "web-socket-echo"
    ServiceName.assign sn sh

exercises.ex5_webSockets.doc : Doc
exercises.ex5_webSockets.doc =
  {{
  # 🧦 WebSockets Chat App
  
    In this exercise we'll be building a simple, CLI-based chat application
    using WebSockets. The application will allow users to send messages to a
    chat room and see messages from other users in real-time.
    
    {{ docCallout
      (Some {{ 📚 }}) {{
      **What you'll learn**
      
      * How to use the WebSockets API to build real-time applications
      * How to call and deploy a WebSocket service in Unison Cloud
      * How to use the {type Cell} type to manage state
      * How to integrate a Cloud service with the command line
      }} }}
    
    ## Getting Started
    
       {{ doc.summary }}
       
       {{
       docCallout
         (Some {{ 🍎 }})
         {{
         [More about the WebSocket protocol](aboutWebSockets)
         }} }}
       
       {{ ex5_webSockets.doc.pt1 }}
       
       {{ ex5_webSockets.doc.pt2 }}
  }}

exercises.ex5_webSockets.doc.aboutWebSockets : Doc
exercises.ex5_webSockets.doc.aboutWebSockets =
  {{
  # 🧐 What are WebSockets?
  
    {{ doc.summary }}
    
    ## WebSocket Protocol
    
       The WebSocket protocol uses a simple message-based frame format,
       allowing the transmission of text or binary data between client and
       server. The WebSocket protocol starts with an HTTP upgrade handshake,
       and once the connection is established, it switches to the WebSocket
       protocol. Here's what that looks like:
       
       ``` mermaid
       sequenceDiagram
         participant Client
         participant Server
         Client->>Server: http GET request
         Note over Client,Server: headers include:`Upgrade:websocket` and `Sec-Websocket-Key`
         Note over Server: Examines upgrade header
         Server->>Client: Responds with HTTP 101 Switching prototcols code
         loop Client and server can send messages back and forth
             Client->>Server: Ping!
             Server->>Client: Pong!
         end
         Client->>Server: Initiates "close frame" request
         Server->>Client: Acknowledges "close frame" request
         Note over Client,Server: Connection Closed
       ```
       
       [More about the WebSocket API on the web](https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API)
  }}

exercises.ex5_webSockets.doc.pt1 : Doc
exercises.ex5_webSockets.doc.pt1 =
  use ex5_webSockets webSocketHandler
  {{
  # Part 1: Implement a (stateless) WebSockets service handler
  
    Unison WebSockets services take the basic form:
    
    {{ docSignature [docEmbedSignatureLink do webSocketHandler] }}
    
    This means given a
    [`WebSocket`]({type unison_cloud_19_0_0.websockets.WebSocket}), which
    identifies a unique connection to a client, the service can send and
    receive messages to the client using the {type WebSockets} ability.
    
    The core functions you'll use when describing back-and-forth WebSocket
    interactions are:
    
    * {WebSockets.receive}: which reads a message from the client
    * {WebSockets.send}: which sends a message to the client
    * {WebSockets.close}: which closes the connection to the client
    
    The [`Message`]({type websockets.Message}) that is passed between the
    client and server can contain {type Text} or {type Bytes} values.
    
    ``` unison
    textMessage = TextMessage "hello world"
    bytesMessage = BinaryMessage (toUtf8 "hello world")
    ```
    
    {{
    docCallout
      (Some {{ 📝 }})
      {{
      Implement the {{ (docLink (docEmbedTermLink do webSocketHandler)) }}
      function as a simple echo service that sends back the message it receives
      from the client indefinately.
      
      ``` ucm
      cloud-start/main> edit exercises.ex3_webSockets.webSocketHandler
      ```
      
      Save your file and run `update` in the UCM.
      }} }}
    
    Once you've implemented the logic for WebSocket interaction, deploy it to
    the Cloud using the {deployHttpWebSocket} function.
    
        @signature{deployHttpWebSocket}
    
    This function takes an {type Environment} where the service will be
    deployed and a second argument which is a **function** from an Http request
    to either an Http response or a WebSocket handler.
    
    ``` unison
    (HttpRequest -> Either HttpResponse (websockets.WebSocket ->{Remote, WebSockets} ()))
    ```
    
    We represent the response as an {type Either} because an Http request to a
    service could initiate a regular HttpResponse or a WebSocket connection,
    depending upon what path is requested. Perhaps requests to the path "/chat"
    start WebSocket interactions but other requests to "/userInfo" are regular
    GET requests.
    
    Create a URI for your service with the @inlineSignature{ServiceName.named}
    function and link the name to the service hash returned from the
    {deployHttpWebSocket} function using @inlineSignature{ServiceName.assign}.
    
    {{
    docCallout
      (Some {{ 📝 }})
      {{
      Deploy the service to the cloud with the {{
      (docSignatureInline (docEmbedSignatureLink do ex5_webSockets.deploy)) }}
      service that sends back the message it receives from the client. For now,
      any incoming {type HttpRequest} to the service should start a WebSocket
      connection.
      
      ``` ucm
      cloud-start/main> edit exercises.webSockets.webSocketHandler
      ```
      
      Save your file and run `update` in the UCM.
      
      Once you've completed the implementation, run the following command to
      submit your solution:
      
      ``` ucm
      cloud-start/main> submit exercises.submit.webSocketService
      ```
      }} }}
  }}

exercises.ex5_webSockets.doc.pt2 : Doc
exercises.ex5_webSockets.doc.pt2 =
  {{
  # Part 2: Adding state to the service
  
    Now that you have a basic WebSocket service, let's keep a the current state
    of the users who have connected to the service. This logic will be useful
    for any WebSocket service that needs to broadcast to a group of clients at
    once.
    
    The {type Cell} type is a simple Cloud storage primitive that holds a
    single value. We'll use this to store set of connected clients. When a new
    user connects to the chat service, we'll update the {type Cell} with the
    new user's WebSocket connection and when a user disconnects, we'll remove
    their connection from the {type Cell}.
    
    Implement the {{ docLink (docEmbedTermLink do webSocketStateHandler) }}
    function so that it echos the message it receives from the client to all
    the service's connected clients.
    
    The message should also be echoed back to the connecting client itself.
    After all, your user will want to see their own messages!
    
    ## Finalizers and WebSockets
    
       The {addFinalizer} function runs
       
       When a WebSocket connection is closed, we should remove the connection
       from the set of connected clients being held in state. Use the
       {addFinalizer} function to remove the WebSocket connection from the
       service state.
       
       {{
       docCallout
         (Some {{ 📝 }})
         {{
         **Instructions**
         
         ``` ucm
         cloud-start/main> edit exercises.webSockets.webSocketStateHandler
         ```
         
         Save your file and run `update` in the UCM.
         
         Once you've completed the implementation, `edit` the {{
         (docLink (docEmbedTermLink do ex5_webSockets.deploy)) }} function to
         use your new stateful WebSocket handler, save and `update` the change,
         and finally run the following command to submit your solution:
         
         ``` ucm
         cloud-start/main> run submit.ex3_webSockets.pt2
         ```
         }} }}
  }}

exercises.ex5_webSockets.doc.pt3 : Doc
exercises.ex5_webSockets.doc.pt3 =
  {{
  # Part 3: Adding HTTP routing to the WebSocket service
  
    
  }}

exercises.ex5_webSockets.webSocketChatHandler :
  Cell (Set unison_cloud_19_0_0.websockets.WebSocket)
  -> Text
  -> unison_cloud_19_0_0.websockets.WebSocket
  ->{Exception, Remote, WebSockets} ()
exercises.ex5_webSockets.webSocketChatHandler cell username ws =
  use Cell modify
  use Text ++
  addFinalizer do unsafeRun! do modify cell (s -> (Set.delete ws s, ()))
  modify cell (s -> (Set.insert ws s, ()))
  loop =
    do
      match WebSockets.receive ws with
        TextMessage msg ->
          recipients = Cell.read cell
          flipped.deprecated
            (Set.toList recipients)
            (r ->
              WebSockets.send r (TextMessage ("<" ++ username ++ "> " ++ msg)))
        _ -> ()
  forever loop

exercises.ex5_webSockets.webSocketHandler :
  unison_cloud_19_0_0.websockets.WebSocket ->{Exception, Remote, WebSockets} ()
exercises.ex5_webSockets.webSocketHandler ws = forever do
  msg = WebSockets.receive ws
  WebSockets.send ws msg

exercises.ex5_webSockets.webSocketHandler.doc : Doc
exercises.ex5_webSockets.webSocketHandler.doc =
  {{ This is what the user implements first, for simplicity's sake }}

exercises.ex5_webSockets.webSocketHttpHandler :
  HttpRequest
  -> Either
    HttpResponse
    (unison_cloud_19_0_0.websockets.WebSocket
    ->{Exception, Remote, WebSockets} ())
exercises.ex5_webSockets.webSocketHttpHandler _ =
  Right ex5_webSockets.webSocketHandler

exercises.ex5_webSockets.webSocketStateHandler :
  Cell (Set unison_cloud_19_0_0.websockets.WebSocket)
  -> unison_cloud_19_0_0.websockets.WebSocket
  ->{Exception, Remote, WebSockets} ()
exercises.ex5_webSockets.webSocketStateHandler cell ws =
  use Cell modify
  addFinalizer do unsafeRun! do modify cell (s -> (Set.delete ws s, ()))
  modify cell (s -> (Set.insert ws s, ()))
  loop = do
    msg = WebSockets.receive ws
    recipients = Cell.read cell
    flipped.deprecated (Set.toList recipients) (r -> WebSockets.send r msg)
  forever loop

exercises.README : Doc
exercises.README =
  {{
  # 🌤️ Cloud Exercises
  
    Welcome to the Cloud Exercises! This set of exercises is designed to help
    you learn about Unison and Unison Cloud while building real applications
    and services.
    
    {{
    docCallout
      (Some {{ 📚 }})
      {{
      The docs and instructions are located in the cloud website:
      
      https://www.unison.cloud/exercises/
      
      Where possible, each exercise has a matching {type Doc} instruction set
      that you can view in the UCM with `dispay`.
      
      ``` ucm
      cloud-start/main> display exercises.ex1_quickstart.doc
      ```
      }} }}
  
  # An example challenge:
  
    {{ ex2_nativeService.doc }}
  
  # What should you see upon submitting code?
  
    {{ ch1 }}
  }}

exercises.README.ch1 : Doc
exercises.README.ch1 =
  Paragraph
    [ Image
        (Paragraph [Word "sample", Word "challenge"])
        (Word
          "data:image/png;base64,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WEXOmdJizU0sC4PxnZiFi60YzQLwOVMi5mpHAJN80DX+008/2UVjGAlEhQCfH1HBzExIgARikAA9mjHYKCwSCZAACZAACZAACeQGAmGZdZ4bQLAOJEACJEACJEACJEAC4SVAQzO8PKmNBEiABEiABEiABEjgPAEamrwVSIAESIAESIAESIAEIkKAhmZEsFIpCZAACZAACZAACZAADU3eAyRAAiRAAiRAAiRAAhEhQEMzIliplARIgARIgARIgARIgIYm7wESIAESIAESIAESIIGIEKChGRGsVEoCJEACJEACJEACJEBDk/cACZAACZAACZAACZBARAjQ0IwIViolARIgARIgARIgARKgocl7gARIgARIgARIgARIICIEaGhGBCuVkgAJkAAJkAAJkAAJ0NDkPUACJEACJEACJEACJBARAjQ0I4KVSkmABEiABEiABEiABGho8h4gARIgARIgARIgARKICAEamhHBSqUkQAIkQAIkQAIkQAI0NHkPkAAJkAAJkAAJkAAJRIQADc2IYKVSEiABEiABEiABEiABGpq8B0iABEiABEiABEiABCJCgIZmRLBSKQmQAAmQAAmQAAmQQEK4EJxtnCJycX7JX7JgllQmHz0rsilZCq4JW1GylD8jkwAJkAAJkAAJkAAJRIZAWKy7k7ekSu3OF0vr2q2leP5ikub1qtLiZSce8Xg8ciL5hKzcvFK2fPWHJM6jg9WOGMNIgARIgARIgARI4EIiELKhefbSFKnQpaq0vaS1FI0vLMmpZ7SJ6QlCQZmXck79JaWc0TFKJBaXdk0uk9Nxp+Tw7t1S8NuQixQkZ14mARIgARIgARIgARKIJoGQrbrUpnGSWK6IbE3aImeS043HYBWAkZms/hLTEqVhfH0pFFdIpdsuB+IOKB1F5cAlyqP5bbDUvB4qgdatW8utt94qr7/+uqxfvz5UdUxPAiRAAiRAAiRAArYEQjY0pYTIoZT9cuzEIfGm2XWXeyRV/Z1NTpKHKw6Vh2sMlsOpR+WWjb1k05kNkiD5BboCSceOHeWuu+6SIkWKSFxcnHhV1/z+/ftlxIgRcuTIkUBJcv21AQMGSLly5eTJJ590XVdwrFmzplx++eURNTRvueUW6dq1q9x9992uy8aIJEACJEACJEACuY9AyIamNy1VTp07KoLhlXZ2pgpOTTkstQteKv2q3yVx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YJ28gaEaDz74oP58O5XP6LM78vkR/Plkxy0cYdjNLdDQCNP+TveXUzjK+MYbb/gmeuIz/PPPP8uTTz6pi+8mvV098V2BzzMm1RiB4We2qHXS73//B/r+sbv/TZ7Bno/++k18wxfv7fSH4/Nl8uSRBHKCQNgMTVN4LEkEw8VNt4VJY47wtmBJHetYSBNmPaLrGt2h/ouAmzjBwqEfv9yzMhHC6PQ/YvD9999/Ly+99JIvKJz6fUrDeOKWr12W8HLAsPNfN9UuTbjC0K4YThFsLCo8bfghgB8go0eP1uWEoWkE6WGkIjyQhMon1PZ3ql+o+gPVOSvX0JMAxphBbJbOsqYPR/n4/AjP88naLrFyDoMJK334rxARavlgaGKNTnhI0UWf3ee70+ff6f5HPUJ5PjrpD8fnK1TWTE8C2SEQdkMzO4W4ENLAKwtP5vbt27UnFt3B2FXGug7chVCPvFLGQIZmXqk76xl7BPj8iFybGEMTi7NTSIAEYo9AvOoSHh17xYq9EuGXOJaFwfhOdPliK0azAHzslZYlwmQDdI3/9NNPhEECOU6Az4/INQGeyZhMGmwJrsjlTM0kQAJuCNCj6YYS45AACZAACZAACZAACWSZQFhmnWc5VyYgARIgARIgARIgARLI9QRoaOb6JmYFSYAESIAESIAESCBnCNDQzBnuzJUESIAESIAESIAEcj0BGpq5volZQRIgARIgARIgARLIGQI0NHOGO3MlARIgARIgARIggVxPgIZmrm9iVpAESIAESIAESIAEcoYADc2c4c5cSYAESIAESIAESCDXE6ChmeubmBUkARIgARIgARIggZwhQEMzZ7gzVxIgARIgARIgARLI9QRoaOb6JmYFSYAESIAESIAESCBnCNDQzBnuzJUESIAESIAESIAEcj0BGpq5volZQRIgARIgARIgARLIGQI0NHOGO3MlARIgARIgARIggVxPgIZmrm9iVpAESIAESIAESIAEcoYADc2c4c5cSYAESIAESIAESCDXE6ChmeubmBUkARIgARIgARIggZwhQEMzZ7gzVxIgARIgARIgARLI9QRoaOb6JmYFSYAESIAESIAESCBnCNDQzBnuzJUESIAESIAESIAEcj0BGpq5volZQRIgARIgARIgARLIGQJhMzR7FCokfdUrq4I0PQoXzmoyxicBEiABEiABEiABEohx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")
        Optional.None
    ]

exercises.solutions.ex1_quickstart.deploy : '{IO, Exception} URI
exercises.solutions.ex1_quickstart.deploy = Cloud.main do
  serviceHash = deployHttp exercises.env() ex1_quickstart.helloWorld.logic
  serviceName = ServiceName.named "hello-world"
  ServiceName.assign serviceName serviceHash

exercises.solutions.ex2_nativeService.callService : '{IO, Exception} Nat
exercises.solutions.ex2_nativeService.callService = Cloud.main do
  serviceHash = solutions.ex2_nativeService.deploy()
  Cloud.submit exercises.env() do Services.call serviceHash 5

exercises.solutions.ex2_nativeService.deploy :
  '{IO, Exception} ServiceHash Nat Nat
exercises.solutions.ex2_nativeService.deploy =
  use Nat >=
  threshold = sqrt (Float.fromNat maxNat) |> Float.ceiling |> Float.toNat
  Cloud.main do
    Cloud.deploy
      exercises.env()
      (n ->
        (if Optional.exists (t -> n >= t) threshold then
          Exception.raise ex2_nativeService.failure
        else Nat.pow n 2))

exercises.solutions.ex3_microblog.api :
  AppStorage
  -> HttpRequest
  ->{Exception, unison_cloud_19_0_0.Storage, Remote, Random} HttpResponse
exercises.solutions.ex3_microblog.api storage =
  use Route <|>
  Route.run
    (solutions.ex3_microblog.api.createPost storage
      <|> solutions.ex3_microblog.api.getPostById storage
      <|> getUserPosts storage
      <|> createUser storage
      <|> api.followUser storage
      <|> getFeed storage)

exercises.solutions.ex3_microblog.api.createPost :
  AppStorage
  -> '{Route, Exception, unison_cloud_19_0_0.Storage, Remote, Random} ()
exercises.solutions.ex3_microblog.api.createPost storage =
  do
    use Parser / s
    Route.noCapture POST (s "api" / s "posts")
    let
      (CreatePost body userHandle) = decodeJson CreatePost.fromJson
      (v2.PostRow.PostRow postId _ _ _) =
        db.createPost storage (UserHandle userHandle) body
      ok.json (PostId.toJson postId)

exercises.solutions.ex3_microblog.api.createUser :
  AppStorage
  -> '{Route, Exception, unison_cloud_19_0_0.Storage, Remote, Random} ()
exercises.solutions.ex3_microblog.api.createUser storage =
  do
    use Parser / s
    userHandleText = route POST (s "api" / s "user" / Parser.text)
    newUser = decodeJson User.fromJson
    avatarURI = Optional.flatMap parseOptional (User.avatar newUser)
    userName' = userName newUser
    userHandle = UserHandle userHandleText
    BTree.write
      (userHandleToUser storage)
      userHandle
      (v2.UserRow.UserRow userHandle userName' avatarURI)
    ok.json (UserId.toJson <| client.UserId.UserId userHandleText)

exercises.solutions.ex3_microblog.api.followUser :
  AppStorage
  -> '{Route, Exception, unison_cloud_19_0_0.Storage, Remote, Random} ()
exercises.solutions.ex3_microblog.api.followUser storage =
  do
    use Parser / s
    userHandle = route POST (s "api" / s "follow" / Parser.text)
    let
      (follower, target) = decodeJson FollowRequest.fromJson
      (v2.FollowingRow.FollowingRow id _ _ _) =
        db.followUser storage (UserHandle follower) (UserHandle target)
      ok.json (FollowingId.toJson id)

exercises.solutions.ex3_microblog.api.getFeed :
  AppStorage -> '{Route, Exception, unison_cloud_19_0_0.Storage, Remote} ()
exercises.solutions.ex3_microblog.api.getFeed storage =
  do
    use Parser / s
    userHandle = route GET (s "api" / s "feed" / Parser.text)
    posts : [v2.PostRow]
    posts = getFeedPosts storage (UserHandle userHandle)
    postClient =
      List.map
        (cases
          v2.PostRow.PostRow _ createdAt body uhandle ->
            (v2.UserRow.UserRow (UserHandle uh) name _) =
              OrderedTable.read (userHandleToUser storage) uhandle
            Post body name uh (OffsetDateTime.toText createdAt))
        posts
    postsJson = Posts.toJson postClient
    ok.json postsJson

exercises.solutions.ex3_microblog.api.getPostById :
  AppStorage -> '{Route, Exception, unison_cloud_19_0_0.Storage, Remote} ()
exercises.solutions.ex3_microblog.api.getPostById storage =
  do
    use OrderedTable.read tx
    use Parser / s
    postUID = UID (Text.toUtf8 (route GET (s "api" / s "posts" / Parser.text)))
    post = 
      transact (AppStorage.database storage) do
        (v2.PostRow.PostRow _ createdAt body userHandle) =
          tx (AppStorage.postsTable storage) (v2.PostId.PostId postUID)
        (v2.UserRow.UserRow (UserHandle userHandleAsText) userName avatar) =
          tx (userHandleToUser storage) userHandle
        timeTxt = OffsetDateTime.toText createdAt
        Post.toJson (Post body userName userHandleAsText timeTxt)
    ok.json post

exercises.solutions.ex3_microblog.api.getUserPosts :
  AppStorage -> '{Route, Exception, unison_cloud_19_0_0.Storage} ()
exercises.solutions.ex3_microblog.api.getUserPosts storage =
  do
    use Parser / s
    userHandle = route GET (s "api" / s "user" / Parser.text / s "posts")
    clientPosts = 
      transact (AppStorage.database storage) do
        posts = getPostsByUserHandle storage (UserHandle userHandle)
        let
          (v2.UserRow.UserRow _ userName _) =
            OrderedTable.read.tx
              (userHandleToUser storage) (UserHandle userHandle)
          List.map
            (cases
              v2.PostRow.PostRow _ createdAt body _ ->
                Post body userName userHandle (OffsetDateTime.toText createdAt))
            posts
    ok.json (Posts.toJson clientPosts)

exercises.solutions.ex3_microblog.client.CreatePost.fromJson :
  '{Decoder} CreatePost
exercises.solutions.ex3_microblog.client.CreatePost.fromJson = do
  use Decoder text
  use object at!
  body = at! "body" text
  userId = at! "userId" text
  CreatePost body userId

exercises.solutions.ex3_microblog.client.FollowingId.toJson :
  v2.FollowingId ->{Exception} Json
exercises.solutions.ex3_microblog.client.FollowingId.toJson = cases
  v2.FollowingId.FollowingId (UID bytes) ->
    Json.object [("followingId", Json.text (fromUtf8 bytes))]

exercises.solutions.ex3_microblog.client.FollowRequest.fromJson :
  '{Decoder} (Text, Text)
exercises.solutions.ex3_microblog.client.FollowRequest.fromJson = do
  use Decoder text
  use object at!
  follower = at! "follower" text
  target = at! "target" text
  (follower, target)

exercises.solutions.ex3_microblog.client.FollowRequest.fromJson.doc : Doc
exercises.solutions.ex3_microblog.client.FollowRequest.fromJson.doc =
  {{
  ```
  """
  {
  "follower": "123uuidUserId123",
  "target": "123uuidUserId123"
  }
  """
  ```
  }}

exercises.solutions.ex3_microblog.client.Post.body : Post -> Text
exercises.solutions.ex3_microblog.client.Post.body = cases
  Post body _ _ _ -> body

exercises.solutions.ex3_microblog.client.Post.body.modify :
  (Text ->{g} Text) -> Post ->{g} Post
exercises.solutions.ex3_microblog.client.Post.body.modify f = cases
  Post body name userHandle timestamp ->
    Post (f body) name userHandle timestamp

exercises.solutions.ex3_microblog.client.Post.body.set : Text -> Post -> Post
exercises.solutions.ex3_microblog.client.Post.body.set body1 = cases
  Post _ name userHandle timestamp -> Post body1 name userHandle timestamp

exercises.solutions.ex3_microblog.client.Post.doc : Doc
exercises.solutions.ex3_microblog.client.Post.doc =
  {{
  Client side representation of a Post
  
  `` Post body name userHandle timeStamp ``
  
  Corresponds to the following Json structure:
  
  ```
  """
    {
      "body": "Text",
      "name": "Bob Bob",
      "userHandle": "@bob",
      "timestamp": "2021-01-01T00:00:00Z"
    }
  """
  ```
  }}

exercises.solutions.ex3_microblog.client.Post.name : Post -> Text
exercises.solutions.ex3_microblog.client.Post.name = cases
  Post _ name _ _ -> name

exercises.solutions.ex3_microblog.client.Post.name.modify :
  (Text ->{g} Text) -> Post ->{g} Post
exercises.solutions.ex3_microblog.client.Post.name.modify f = cases
  Post body name userHandle timestamp ->
    Post body (f name) userHandle timestamp

exercises.solutions.ex3_microblog.client.Post.name.set : Text -> Post -> Post
exercises.solutions.ex3_microblog.client.Post.name.set name1 = cases
  Post body _ userHandle timestamp -> Post body name1 userHandle timestamp

exercises.solutions.ex3_microblog.client.Post.timestamp : Post -> Text
exercises.solutions.ex3_microblog.client.Post.timestamp = cases
  Post _ _ _ timestamp -> timestamp

exercises.solutions.ex3_microblog.client.Post.timestamp.modify :
  (Text ->{g} Text) -> Post ->{g} Post
exercises.solutions.ex3_microblog.client.Post.timestamp.modify f = cases
  Post body name userHandle timestamp ->
    Post body name userHandle (f timestamp)

exercises.solutions.ex3_microblog.client.Post.timestamp.set :
  Text -> Post -> Post
exercises.solutions.ex3_microblog.client.Post.timestamp.set timestamp1 = cases
  Post body name userHandle _ -> Post body name userHandle timestamp1

exercises.solutions.ex3_microblog.client.Post.toJson : Post -> Json
exercises.solutions.ex3_microblog.client.Post.toJson = cases
  Post body userName userHandle timeStamp ->
    Json.object
      [ ("body", Json.text body)
      , ("name", Json.text userName)
      , ("userHandle", Json.text userHandle)
      , ("timestamp", Json.text timeStamp)
      ]

exercises.solutions.ex3_microblog.client.Post.userHandle : Post -> Text
exercises.solutions.ex3_microblog.client.Post.userHandle = cases
  Post _ _ userHandle _ -> userHandle

exercises.solutions.ex3_microblog.client.Post.userHandle.modify :
  (Text ->{g} Text) -> Post ->{g} Post
exercises.solutions.ex3_microblog.client.Post.userHandle.modify f = cases
  Post body name userHandle timestamp ->
    Post body name (f userHandle) timestamp

exercises.solutions.ex3_microblog.client.Post.userHandle.set :
  Text -> Post -> Post
exercises.solutions.ex3_microblog.client.Post.userHandle.set userHandle1 = cases
  Post body name _ timestamp -> Post body name userHandle1 timestamp

exercises.solutions.ex3_microblog.client.PostId.toJson :
  v2.PostId ->{Exception} Json
exercises.solutions.ex3_microblog.client.PostId.toJson = cases
  v2.PostId.PostId (UID bytes) ->
    Json.object [("postId", Json.text (fromUtf8 bytes))]

exercises.solutions.ex3_microblog.client.Posts.toJson : [Post] -> Json
exercises.solutions.ex3_microblog.client.Posts.toJson list =
  List.map Post.toJson list |> Json.array

exercises.solutions.ex3_microblog.client.UserId.toJson : client.UserId -> Json
exercises.solutions.ex3_microblog.client.UserId.toJson = cases
  client.UserId.UserId id -> Json.object [("userId", Json.text id)]

exercises.solutions.ex3_microblog.db.createPost :
  AppStorage
  -> UserHandle
  -> Text
  ->{Exception, unison_cloud_19_0_0.Storage, Remote, Random} v2.PostRow
exercises.solutions.ex3_microblog.db.createPost storage userHandle body =
  use BTree.write tx
  postId = v2.PostId.PostId UID.random()
  timeStamp = instantToOffsetDateTime()
  postTable = AppStorage.postsTable storage
  userPostsTable = AppStorage.userPostsTable storage
  transact.random (AppStorage.database storage) do
    postRow = v2.PostRow.PostRow postId timeStamp body userHandle
    tx postTable postId postRow
    tx userPostsTable (userHandle, timeStamp) postRow
    postRow

exercises.solutions.ex3_microblog.db.followUser :
  AppStorage
  -> UserHandle
  -> UserHandle
  ->{Exception, unison_cloud_19_0_0.Storage, Remote, Random} v2.FollowingRow
exercises.solutions.ex3_microblog.db.followUser storage follower target =
  followingTable = AppStorage.followingTable storage
  followingId = v2.FollowingId.FollowingId UID.random()
  timeStamp = atUTC now!
  followingRow =
    v2.FollowingRow.FollowingRow followingId follower target timeStamp
  BTree.write followingTable (follower, target) followingRow
  followingRow

exercises.solutions.ex3_microblog.db.getFeedPosts :
  AppStorage -> UserHandle ->{Remote} [v2.PostRow]
exercises.solutions.ex3_microblog.db.getFeedPosts storage followerHandle =
  use OrderedTable prefixOrdering
  use Stream map
  use rangeClosed prefix
  use v2 PostRow
  followerTable : OrderedTable (UserHandle, UserHandle) v2.FollowingRow
  followerTable = followingTable storage
  targetUsers : '{Remote, Stream UserHandle} ()
  targetUsers =
    prefix followerTable prefixOrdering followerHandle followerHandle
      |> map at2
      |> map v2.FollowingRow.target
  userPosts : OrderedTable (UserHandle, OffsetDateTime) PostRow
  userPosts = AppStorage.userPostsTable storage
  posts : '{Remote, Stream PostRow} ()
  posts =
    Stream.flatMap
      (uid -> prefix userPosts prefixOrdering uid uid ()) targetUsers
      |> map at2
  Stream.toList posts

exercises.solutions.ex3_microblog.db.getPostsByUserHandle :
  AppStorage -> UserHandle ->{Transaction, Exception} [v2.PostRow]
exercises.solutions.ex3_microblog.db.getPostsByUserHandle storage userHandle =
  userPostsTable = AppStorage.userPostsTable storage
  resultStream =
    rangeClosed.prefix.tx
      userPostsTable OrderedTable.prefixOrdering userHandle userHandle
  Stream.map at2 resultStream |> Stream.toList

exercises.solutions.ex3_microblog.deploy : '{IO, Exception} URI
exercises.solutions.ex3_microblog.deploy = Cloud.main do
  storage = createAppStorage()
  hash = deployHttp exercises.env() (ex3_microblog.api storage)
  serviceName = ServiceName.named "microblog"
  ServiceName.assign serviceName hash

exercises.solutions.ex3_microblog.instantToOffsetDateTime :
  '{Remote} OffsetDateTime
exercises.solutions.ex3_microblog.instantToOffsetDateTime = do
  instantNow = now!
  Instant.atOffset instantNow UTC

exercises.solutions.ex4_oauth.deploy : '{IO, Exception} URI
exercises.solutions.ex4_oauth.deploy =
  do
    use Optional None
    use ex4_oauth UserId.UserId
    use exercises env
    googleClientId = getEnv "GOOGLE_CLIENT_ID"
    googleClientSecret = getEnv "GOOGLE_CLIENT_SECRET"
    oauthClient =
      google (ClientId googleClientId) (ClientSecret googleClientSecret)
    hmacKey = HMACKey (getEnv "HMAC_KEY" |> Text.toUtf8)
    successCallback :
      TokenResponse IdToken ->{Exception, Http, Log} ex4_oauth.UserId
    successCallback tokenResponse =
      info "Successfully authenticated user" []
      let
        (IdToken jwtText) = idToken tokenResponse
        jwt = alvaroc1_jwt_0_0_1.decode jwtText
        match Jwt.sub jwt with
          None     ->
            warn "No sub in JWT" []
            raiseGeneric "No sub in JWT" jwt
          Some sub ->
            info "User authenticated and decoded" []
            UserId.UserId sub
    encodeUserId : ex4_oauth.UserId -> Json
    encodeUserId = cases UserId.UserId uid -> Json.text uid
    decodeUserId : '{Decoder} ex4_oauth.UserId
    decodeUserId = do UserId.UserId Decoder.text()
    additionalScopes = None
    authConfig : AuthConfig {Http, Exception, Log} IdToken ex4_oauth.UserId
    authConfig =
      defaultCloud
        hmacKey
        oauthClient
        additionalScopes
        successCallback
        decodeUserId
        encodeUserId
    Cloud.run do
      database = Database.named "todo-auth-service-db"
      todoTable : OrderedTable (ex4_oauth.UserId, Text) TodoItem
      todoTable = OrderedTable.named database "todo-table" Universal.ordering
      Database.assign database env()
      serviceHash =
        deployHttp
          env()
          (Route.run do
            oauth2.handler
              authConfig (solutions.ex4_oauth.todoService todoTable database))
      name = ServiceName.named "todo-service"
      ServiceName.assign name serviceHash

exercises.solutions.ex4_oauth.getSessionOr401 :
  (ex4_oauth.UserId ->{g} ()) ->{g, Route, Auth ex4_oauth.UserId} ()
exercises.solutions.ex4_oauth.getSessionOr401 continue = match getSession with
  Optional.None -> unauthorized (Text.toUtf8 "Unauthorized")
  Some session  -> continue session

exercises.solutions.ex4_oauth.todoService :
  OrderedTable (ex4_oauth.UserId, Text) TodoItem
  -> Database
  -> '{Route,
  Exception,
  unison_cloud_19_0_0.Storage,
  Remote,
  Log,
  Auth ex4_oauth.UserId} ()
exercises.solutions.ex4_oauth.todoService todoTable db =
  use Parser / s
  use Route <|> noCapture
  use Text ++
  use TodoItem toJson
  home : '{Route, Auth ex4_oauth.UserId} ()
  home =
    do
      noCapture GET Parser.root
      match getSession with
        Optional.None ->
          ok.text "Welcome to the todo app! Consider logging in!"
        Some (ex4_oauth.UserId.UserId uid) -> ok.html todoService.html
  getTodoItem : '{Route, Exception, Remote, Log, Auth ex4_oauth.UserId} ()
  getTodoItem = do
    todoId = route GET (s "todo" / Parser.text)
    getSessionOr401 cases
      userIdSession ->
        todoKey = (userIdSession, todoId)
        match catch do OrderedTable.read todoTable todoKey with
          Right todoItem ->
            jsonTodoItem = toJson todoItem
            info.json "GET todo item" jsonTodoItem
            ok.json jsonTodoItem
          Left _         -> notFound.text ("todo item not found " ++ todoId)
  getTodoItems : '{Route, Exception, Remote, Log, Auth ex4_oauth.UserId} ()
  getTodoItems =
    do
      name = noCapture GET (s "todos")
      getSessionOr401 cases
        userIdSession ->
          records =
            rangeClosed.prefix
              todoTable OrderedTable.prefixOrdering userIdSession userIdSession
              |> Stream.toList
          jsonRecords = Json.array (List.map (r -> at2 r |> toJson) records)
          info.json "GET todoItems" jsonRecords
          ok.json jsonRecords
  putTodoItem : '{Route, Exception, Remote, Log, Auth ex4_oauth.UserId} ()
  putTodoItem = do
    name = noCapture PUT (s "todo")
    getSessionOr401 cases
      userIdSession ->
        todoItem : {Route, Exception} TodoItem
        todoItem = decodeJson TodoItem.fromJson
        todoId = TodoItem.id todoItem
        todoKey = (userIdSession, todoId)
        match catch do randomly do BTree.write todoTable todoKey todoItem with
          Left e  -> badRequest.text ("failed to write todo item " ++ todoId)
          Right _ ->
            info.json "PUT todo item" (toJson todoItem)
            ok.text ("created todo item " ++ todoId)
  deleteTodoItem : '{Route, Exception, Remote, Log, Auth ex4_oauth.UserId} ()
  deleteTodoItem = do
    id = route DELETE (s "todo" / Parser.text)
    getSessionOr401 cases
      userIdSession ->
        todoKey = (userIdSession, id)
        match catch do OrderedTable.delete todoTable todoKey with
          Left _  -> badRequest.text ("todo item failed to be  found " ++ id)
          Right _ ->
            info "DELETE" [("todoId", id)]
            ok.text ("deleted todo item " ++ id)
  home <|> getTodoItem <|> putTodoItem <|> deleteTodoItem <|> getTodoItems

exercises.submit.ex1_quickstart : '{IO, Exception} ()
exercises.submit.ex1_quickstart =
  do
    (results, progress) =
      exercise
        (Track.Number.Number 1)
        (Exercise.Number.Number 1 (Part 1))
        "Quickstart Http Service Deployment"
        do
        use URI /
        baseURI = exercises.ex1_quickstart.deploy() / "Alice"
        request = HttpRequest.get baseURI
        response = callHttpService request
        expectHttpBodyString
          request 200 "Alice" "the service should echo back the input"
    print (req -> HttpRequest.uri req |> URI.toText) print.HttpResponse results
    printLine track1_title
    printProgress progress

exercises.submit.ex2_nativeService : '{IO, Exception} ()
exercises.submit.ex2_nativeService =
  do
    (results1, _) =
      exercise
        (Track.Number.Number 1)
        (Exercise.Number.Number 2 (Part 1))
        "Square Service Exercise"
        do
        serviceHash = exercises.ex2_nativeService.deploy()
        validator.expect serviceHash 3 9 "3 squared is 9"
        expectTimed
          serviceHash
          3
          9
          (Remote.Duration.seconds 1)
          "Square service should take less than 1 second to run"
    use Nat toText
    print toText toText results1
    let
      (results2, _) =
        exercise
          (Track.Number.Number 1)
          (Exercise.Number.Number 2 (Part 2))
          "Square Service Exercise - Error practice"
          do
          serviceHash = exercises.ex2_nativeService.deploy()
          threshold =
            sqrt (Float.fromNat maxNat)
              |> Float.ceiling
              |> Float.toNat
              |> getOrBug "whoops"
          expectFailure
            serviceHash
            threshold
            "cannot be squared"
            "Service should raise an error when trying to square a number above this threshold"
          expectFailure
            serviceHash
            maxNat
            "cannot be squared"
            "Service should raise an error when trying to square a number that would cause a Nat overflow"
      print toText toText results2
    let
      (results3, trackProgress) =
        exercise
          (Track.Number.Number 1)
          (Exercise.Number.Number 2 (Part 3))
          "Square Service Exercise - Call a native service"
          do
          result = exercises.ex2_nativeService.callService()
          expectValue 25 result "5 squared is 25"
      print toText toText results3
      printLine track1_title
      printProgress trackProgress

exercises.submit.ex3_microblog.bobFollowsAlice :
  URI
  -> Text
  -> Text
  ->{Cloud, Stream (models.Result HttpRequest HttpResponse)} Either
    Failure Text
exercises.submit.ex3_microblog.bobFollowsAlice baseUri follower target =
  use Text ++
  use URI /
  followBody =
    Text.toUtf8
      ("{\n  \"follower\": \""
        ++ follower
        ++ "\", \"target\": \""
        ++ target
        ++ "\"}")
  decodeHttpResponse
    (HttpRequest.post (baseUri / "api" / "follow" / "@alice") (Body followBody))
    FollowingId.fromJson
    "calling POST /api/follow/ to follow a user"

exercises.submit.ex3_microblog.createPostForUser :
  URI
  -> Text
  -> Text
  ->{Cloud, Stream (models.Result HttpRequest HttpResponse)} Either
    Failure Text
exercises.submit.ex3_microblog.createPostForUser baseUri userIdString postText =
  use Text ++
  use URI /
  postBody : Bytes
  postBody =
    Text.toUtf8
      ("          {\n           \"body\" : \""
        ++ postText
        ++ "\",\n           \"userId\": \""
        ++ userIdString
        ++ "\"}")
  postIdString : Either Failure Text
  postIdString =
    decodeHttpResponse
      (HttpRequest.post (baseUri / "api" / "posts") (Body postBody))
      PostId.fromJson
      "calling POST /api/posts to create a blogPost"
  postIdString

exercises.submit.ex3_microblog.createSampleUserAlice :
  URI
  ->{Cloud, Stream (models.Result HttpRequest HttpResponse)} Either
    Failure Text
exercises.submit.ex3_microblog.createSampleUserAlice baseUri =
  use URI /
  createUserBody =
    Text.toUtf8
      "{\n  \"userHandle\" : \"@alice\",\n  \"name\" : \"Alice Alice\",\n  \"avatar\" : \"https://example.com/avatar.jpg\"\n}"
  userIdStringE : Either Failure Text
  userIdStringE =
    decodeHttpResponse
      (HttpRequest.post
        (baseUri / "api" / "user" / "@alice") (Body createUserBody))
      UserId.fromJson
      "calling POST /api/user/@alice to create a user"
  userIdStringE

exercises.submit.ex3_microblog.createSampleUserBob :
  URI
  ->{Cloud, Stream (models.Result HttpRequest HttpResponse)} Either
    Failure Text
exercises.submit.ex3_microblog.createSampleUserBob baseUri =
  use URI /
  createUserBody =
    Text.toUtf8
      "{\n  \"userHandle\" : \"@bob\", \"name\" : \"Bob Bob\",\n  \"avatar\" : \"https://example.com/avatar.jpg\"\n}"
  userIdStringE : Either Failure Text
  userIdStringE =
    decodeHttpResponse
      (HttpRequest.post
        (baseUri / "api" / "user" / "@bob") (Body createUserBody))
      UserId.fromJson
      "calling POST /api/user/@bob"
  userIdStringE

exercises.submit.ex3_microblog.FollowingId.fromJson : Body ->{Exception} Text
exercises.submit.ex3_microblog.FollowingId.fromJson = cases
  Body responseBody ->
    bodyText = fromUtf8 responseBody
    Decoder.run (object.at "followingId" Decoder.text) bodyText

exercises.submit.ex3_microblog.getPostById :
  URI -> Text ->{Cloud, Stream (models.Result HttpRequest HttpResponse)} ()
exercises.submit.ex3_microblog.getPostById baseUri postIdString =
  use URI /
  expectedJson = 
    unsafeRun! do
      Json.fromText
        "{\n  \"body\" : \"This is a blog post\",\n  \"userName\" : \"Bob Bob\",\n  \"userHandle\" : \"@bob\"\n}"
  expectJson
    (HttpRequest.get (baseUri / "api" / "posts" / postIdString))
    200
    isSubset
    expectedJson
    "User and post creation round-trip"

exercises.submit.ex3_microblog.getUserFeed :
  URI -> Text ->{Cloud, Stream (models.Result HttpRequest HttpResponse)} ()
exercises.submit.ex3_microblog.getUserFeed baseUri feedUserHandle =
  use URI /
  expectedAlicePost = 
    unsafeRun! do
      Json.fromText
        "{\n  \"body\" : \"Alice wrote a new blog\",\n  \"userName\" : \"Alice Alice\",\n  \"userHandle\" : \"@alice\"\n}"
  expectJson
    (HttpRequest.get (baseUri / "api" / "feed" / feedUserHandle))
    200
    Array.contains
    expectedAlicePost
    "Calling GET /api/feed/:handle to get the posts of the people the user is following"

exercises.submit.ex3_microblog.PostId.fromJson : Body ->{Exception} Text
exercises.submit.ex3_microblog.PostId.fromJson = cases
  Body responseBody ->
    bodyText = fromUtf8 responseBody
    go : '{Decoder} Text
    go = object.at "postId" Decoder.text
    Decoder.run go bodyText

exercises.submit.ex3_microblog.pt1 : '{IO, Exception} ()
exercises.submit.ex3_microblog.pt1 =
  do
    (results, trackProgress) =
      exercise
        (Track.Number.Number 1)
        (Exercise.Number.Number 3 (Part 1))
        "Microblog Web Service"
        do
        use Bytes empty
        use HttpRequest get post
        use URI /
        baseUri = exercises.ex3_microblog.deploy()
        _ = "User routes tests"
        expectHttpCode
          (post (baseUri / "api" / "user" / "@picasso") (Body empty))
          200
          "POST /api/user/:handle"
        expectHttpCode
          (get (baseUri / "api" / "user" / "@picasso" / "posts"))
          200
          "GET /api/user/:handle/posts"
        _ = "Post routes tests "
        expectHttpCode
          (post (baseUri / "api" / "posts") (Body empty)) 200 "POST /api/posts"
        expectHttpCode
          (get (baseUri / "api" / "posts" / "abc123")) 200 "GET /api/posts/:id"
        _ = "Follower routes tests"
        expectHttpCode
          (post (baseUri / "api" / "follow" / "@picasso") (Body empty))
          200
          "POST /api/follow/:handle"
        expectHttpCode
          (get (baseUri / "api" / "feed" / "@picasso"))
          200
          "GET /api/feed/:handle"
    print print.HttpRequest print.HttpResponse results
    printLine track1_title
    printProgress trackProgress

exercises.submit.ex3_microblog.pt2 : '{IO, Exception} ()
exercises.submit.ex3_microblog.pt2 =
  do
    use HttpRequest get post
    use Text toUtf8
    use URI /
    track = Track.Number.Number 1
    num = Exercise.Number.Number 3 (Part 2)
    title = "Microblog Web Service—JSON serialization and deserialization"
    let
      (results, trackProgress) =
        exercise track num title do
          baseUri = exercises.ex3_microblog.deploy()
          _ = "User routes tests"
          userPostBody =
            toUtf8
              "{\n  \"userHandle\" : \"@kirby\",\n  \"name\" : \"Kirby Kirby\",\n  \"avatar\" : \"https://example.com/avatar.jpg\"\n}"
          expectHttpJsonKeys
            (post (baseUri / "api" / "user" / "@kirby") (Body userPostBody))
            200
            ["userId"]
            "POST /api/user/:handle"
          expectHttpJsonKeys
            (get (baseUri / "api" / "user" / "@picasso" / "posts"))
            200
            ["body", "name", "userHandle", "timestamp"]
            "GET /api/user/:handle/posts"
          _ = "Post routes tests"
          postBody =
            "  {\n    \"body\": \"This is a blog post\",\n    \"userId\": \"123uuidUserId123\"\n  }"
              |> toUtf8
          expectHttpJsonKeys
            (post (baseUri / "api" / "posts") (Body postBody))
            200
            ["postId"]
            "POST /api/posts"
          expectedGETPostsKeys = ["name", "userHandle", "timestamp", "body"]
          expectHttpJsonKeys
            (get (baseUri / "api" / "posts" / "abc123"))
            200
            expectedGETPostsKeys
            "GET /api/posts/:id"
          _ = "Follower routes tests"
          followBody =
            "  {\"follower\": \"123uuidUserId123\", \"target\": \"123uuidUserId123\"}"
              |> toUtf8
          expectHttpJsonKeys
            (post (baseUri / "api" / "follow" / "@picasso") (Body followBody))
            200
            ["followingId"]
            "POST /api/follow/:handle"
          _ = "Feed routes"
          expectHttpJsonKeys
            (get (baseUri / "api" / "feed" / "@picasso"))
            200
            expectedGETPostsKeys
            "GET /api/feed"
      print print.HttpRequest print.HttpResponse results
      printLine track1_title
      printProgress trackProgress

exercises.submit.ex3_microblog.roundTrip : '{IO, Exception} ()
exercises.submit.ex3_microblog.roundTrip =
  do
    use Either flatMapRight mapRight
    use print HttpRequest HttpResponse
    use unison_base_3_23_1 ignore
    track = Track.Number.Number 1
    baseUri = exercises.ex3_microblog.deploy()
    num3 = Exercise.Number.Number 3 (Part 3)
    title = "Microblog Web Service—create and get a post by ID"
    let
      (results, _) =
        exercise track num3 title do
          _ = "Roundtrip post creation - a new post can be retrieved by its ID"
          _ = "A new post, is associated with its user profile page"
          userIdString = createSampleUserBob baseUri
          postIdString =
            flatMapRight
              (id -> createPostForUser baseUri id "Bobs cool new blog post")
              userIdString
          ignore
            <| mapRight (r -> ex3_microblog.getPostById baseUri r) postIdString
      print HttpRequest HttpResponse results
      num4 = Exercise.Number.Number 3 (Part 4)
      usersProfile = "Microblog Web Service—Follow a user and see their posts"
      let
        (results2, trackProgress) =
          exercise track num4 usersProfile do
            bobId = createSampleUserBob baseUri
            aliceId = createSampleUserAlice baseUri
            _ = "Bob follows Alice"
            followerId =
              tupleRight bobId aliceId
                |> mapRight (uncurry (bobFollowsAlice baseUri))
            _ = "Alice creates a post"
            postIdString =
              flatMapRight
                (id -> createPostForUser baseUri id "Alice wrote a new blog")
                aliceId
            _ = "Bob can read Alice's blog posts"
            ignore (getUserFeed baseUri "@bob")
        print HttpRequest HttpResponse results2
        printLine track1_title
        printProgress trackProgress

exercises.submit.ex3_microblog.UserId.fromJson : Body ->{Exception} Text
exercises.submit.ex3_microblog.UserId.fromJson = cases
  Body responseBody ->
    bodyText = fromUtf8 responseBody
    Decoder.run (object.at "userId" Decoder.text) bodyText

exercises.submit.ex4_oauth.roundTrip : '{IO, Exception} ()
exercises.submit.ex4_oauth.roundTrip =
  do
    use HttpRequest addHeader get put
    use Text toUtf8
    use URI /
    use print HttpRequest HttpResponse
    track = Track.Number.Number 1
    baseUri = exercises.ex4_oauth.deploy()
    num4pt1 = Exercise.Number.Number 4 (Part 1)
    title = "Todo App with OAuth-prevent todo CRUD"
    let
      (results, _) =
        exercise track num4pt1 title do
          body =
            toUtf8
              "{\"entry\": \"Buy milk\", \"id\": \"abc123\", \"completed\": false}"
          expectHttpCode
            (put (baseUri / "todo") (Body body))
            401
            "Unauthorized user should not PUT a todo"
          expectHttpCode
            (get (baseUri / "todo" / "abc123"))
            401
            "Unauthorized user should not GET a todo"
          expectHttpCode
            (get (baseUri / "todos"))
            401
            "Unauthorized user should not GET all todos"
          expectHttpCode
            (HttpRequest.delete (baseUri / "todo" / "abc123"))
            401
            "Unauthorized user should not DELETE a todo"
      print HttpRequest HttpResponse results
      num4pt2 = Exercise.Number.Number 4 (Part 2)
      usersProfile = "Todo App with OAuth—check cookie signing"
      let
        (results2, trackProgress) =
          exercise track num4pt2 usersProfile do
            body =
              toUtf8
                "{\"entry\": \"Buy milk\", \"id\": \"abc123\", \"completed\": false}"
            request = put (baseUri / "todo") (Body body)
            jwtBad =
              "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.9pK1D-rDOpbR22W99l7DU5lsBLvLZ9R-uJ-aTxItW5U"
            reqWithHeaders =
              addHeader "Authorization" jwtBad request
                |> addHeader
                  "Cookie" "session=IAmDefinitelyARealSessionCookie;"
            expectHttpCode
              (put (baseUri / "todo") (Body body))
              401
              "invalid JWT should not PUT a todo"
        print HttpRequest HttpResponse results2
        printLine track1_title
        printProgress trackProgress

exercises.submit.ex5_webSockets.pt1 : '{IO, Exception} ()
exercises.submit.ex5_webSockets.pt1 =
  do
    (results, trackProgress) =
      exercise
        (Track.Number.Number 1)
        (Exercise.Number.Number 3 (Part 1))
        "WebSockets Echo Exercise"
        do
        callWebSocketService
          ex5_webSockets.deploy()
          (expectWebSocketEcho
            "the websockets service should echo back the input")
    print toDebugText toDebugText results
    printLine track1_title
    printProgress trackProgress

exercises.submit.ex5_webSockets.pt2 : '{IO, Exception} ()
exercises.submit.ex5_webSockets.pt2 =
  do
    (resultsPt2, progress) =
      exercise
        (Track.Number.Number 1)
        (Exercise.Number.Number 3 (Part 2))
        "WebSockets Echo Exercise - echo to all connected clients"
        do
        use Exception raise
        use Optional None
        use Promise new
        use Reporting Expected
        use Result Error
        use concurrent kill sleepMicroseconds
        use concurrent.Promise read write
        use fork impl
        use unison_base_3_23_1 ignore
        wsURI = ex5_webSockets.deploy()
        readPromise = new()
        sendPromise = new()
        sendClient : Text -> '{IO} ()
        sendClient msg =
          do
            handle
              catch do
                callWebSocketService
                  wsURI (ws -> WebSocket.send ws (TextMessage msg))
            with cases
              { raise (Failure _ t _) -> _ } ->
                ignore (write sendPromise (Some (Error t (Expected msg))))
              { _ } -> ignore (write sendPromise None)
        receiveClient : Text -> '{IO} ()
        receiveClient expected =
          do
            handle
              callWebSocketService
                wsURI
                (ws ->
                  let
                    res =
                      handle WebSocket.receive ws
                      with cases
                        { Abort.abort -> _ } ->
                          Error "Remote WebSocket hung up" (Expected expected)
                        { raise (Failure _ t _) -> _ } ->
                          Error t (Expected expected)
                        { a } ->
                          match a with
                            TextMessage txt ->
                              if txt === expected then
                                Correct
                                  "The message was successfully broadcast"
                                  (InputOutput (Some expected) (Some expected))
                              else
                                Incorrect
                                  "Resulting message did not match"
                                  (InputOutputExpected expected txt expected)
                            _ ->
                              Error
                                "Expected TextMessage get BinaryMessage"
                                (Expected expected)
                    ignore (write readPromise res))
            with cases
              { raise (Failure _ t _) -> _ } ->
                ignore (write readPromise (Error t (Expected expected)))
              { a } -> ()
        expected = "xyzzy"
        timeout : ThreadId -> ThreadId -> '{IO} ()
        timeout sendingThread receivingThread =
          do
            unsafeRun! do sleepMicroseconds 500000
            unsafeRun! do kill sendingThread
            unsafeRun! do kill receivingThread
            unsafeRun! do
              ignore
                (write
                  readPromise
                  (Error "Timeout waiting for message" (Expected expected)))
        receiveThread = impl (receiveClient expected)
        sleepMicroseconds 500000
        sendThread = impl (sendClient expected)
        timeoutThread = impl (timeout sendThread receiveThread)
        match read sendPromise with
          Some e -> emit e
          None   ->
            result = read readPromise
            unsafeRun! do kill timeoutThread
            emit result
    print toDebugText toDebugText resultsPt2
    printLine track1_title
    printProgress progress

exercises.submit.track1_title : Text
exercises.submit.track1_title = "⛅️ Cloud Basics Track"

metadata.licenses.cc0 : LicenseType
metadata.licenses.cc0 = LicenseType types.cc0.text

metadata.licenses.cc0.doc : Doc
metadata.licenses.cc0.doc =
  {{
  The
  [Creative Commons CC0 license](https://creativecommons.org/publicdomain/zero/1.0/).
  Here's the summary, copied verbatim from the website:
  
  {{
  docCallout
    Optional.None
    {{
    The person who associated a work with this deed has dedicated the work to
    the public domain by waiving all of his or her rights to the work worldwide
    under copyright law, including all related and neighboring rights, to the
    extent allowed by law.
    
    You can copy, modify, distribute and perform the work, even for commercial
    purposes, all without asking permission. See Other Information below.
    
    **Other information**
    
    * In no way are the patent or trademark rights of any person affected by
      CC0, nor are the rights that other persons may have in the work or in how
      the work is used, such as publicity or privacy rights.
    * Unless expressly stated otherwise, the person who associated a work with
      this deed makes no warranties about the work, and disclaims liability for
      all uses of the work, to the fullest extent permitted by applicable law.
    * When using or citing the work, you should not imply endorsement by the
      author or the affirmer.
    }} }}
  
  See the full license text for details.
  }}

metadata.licenses.types.cc0.text : Doc
metadata.licenses.types.cc0.text =
  {{
  **Statement of Purpose**
  
  The laws of most jurisdictions throughout the world automatically confer
  exclusive Copyright and Related Rights (defined below) upon the creator and
  subsequent owner(s) (each and all, an "owner") of an original work of
  authorship and/or a database (each, a "Work").
  
  Certain owners wish to permanently relinquish those rights to a Work for the
  purpose of contributing to a commons of creative, cultural and scientific
  works ("Commons") that the public can reliably and without fear of later
  claims of infringement build upon, modify, incorporate in other works, reuse
  and redistribute as freely as possible in any form whatsoever and for any
  purposes, including without limitation commercial purposes. These owners may
  contribute to the Commons to promote the ideal of a free culture and the
  further production of creative, cultural and scientific works, or to gain
  reputation or greater distribution for their Work in part through the use and
  efforts of others.
  
  For these and/or other purposes and motivations, and without any expectation
  of additional consideration or compensation, the person associating CC0 with
  a Work (the "Affirmer"), to the extent that he or she is an owner of
  Copyright and Related Rights in the Work, voluntarily elects to apply CC0 to
  the Work and publicly distribute the Work under its terms, with knowledge of
  his or her Copyright and Related Rights in the Work and the meaning and
  intended legal effect of CC0 on those rights.
  
  **1. Copyright and Related Rights.** A Work made available under CC0 may be
  protected by copyright and related or neighboring rights ("Copyright and
  Related Rights"). Copyright and Related Rights include, but are not limited
  to, the following:
  
  1. the right to reproduce, adapt, distribute, perform, display, communicate,
     and translate a Work;
  2. moral rights retained by the original author(s) and/or performer(s);
  3. publicity and privacy rights pertaining to a person's image or likeness
     depicted in a Work;
  4. rights protecting against unfair competition in regards to a Work, subject
     to the limitations in paragraph 4(a), below;
  5. rights protecting the extraction, dissemination, use and reuse of data in
     a Work;
  6. database rights (such as those arising under Directive 96/9/EC of the
     European Parliament and of the Council of 11 March 1996 on the legal
     protection of databases, and under any national implementation thereof,
     including any amended or successor version of such directive); and
  7. other similar, equivalent or corresponding rights throughout the world
     based on applicable law or treaty, and any national implementations
     thereof.
  
  **2. Waiver.** To the greatest extent permitted by, but not in contravention
  of, applicable law, Affirmer hereby overtly, fully, permanently, irrevocably
  and unconditionally waives, abandons, and surrenders all of Affirmer's
  Copyright and Related Rights and associated claims and causes of action,
  whether now known or unknown (including existing as well as future claims and
  causes of action), in the Work (i) in all territories worldwide, (ii) for the
  maximum duration provided by applicable law or treaty (including future time
  extensions), (iii) in any current or future medium and for any number of
  copies, and (iv) for any purpose whatsoever, including without limitation
  commercial, advertising or promotional purposes (the "Waiver"). Affirmer
  makes the Waiver for the benefit of each member of the public at large and to
  the detriment of Affirmer's heirs and successors, fully intending that such
  Waiver shall not be subject to revocation, rescission, cancellation,
  termination, or any other legal or equitable action to disrupt the quiet
  enjoyment of the Work by the public as contemplated by Affirmer's express
  Statement of Purpose.
  
  **3. Public License Fallback.** Should any part of the Waiver for any reason
  be judged legally invalid or ineffective under applicable law, then the
  Waiver shall be preserved to the maximum extent permitted taking into account
  Affirmer's express Statement of Purpose. In addition, to the extent the
  Waiver is so judged Affirmer hereby grants to each affected person a
  royalty-free, non transferable, non sublicensable, non exclusive, irrevocable
  and unconditional license to exercise Affirmer's Copyright and Related Rights
  in the Work (i) in all territories worldwide, (ii) for the maximum duration
  provided by applicable law or treaty (including future time extensions),
  (iii) in any current or future medium and for any number of copies, and (iv)
  for any purpose whatsoever, including without limitation commercial,
  advertising or promotional purposes (the "License"). The License shall be
  deemed effective as of the date CC0 was applied by Affirmer to the Work.
  Should any part of the License for any reason be judged legally invalid or
  ineffective under applicable law, such partial invalidity or ineffectiveness
  shall not invalidate the remainder of the License, and in such case Affirmer
  hereby affirms that he or she will not (i) exercise any of his or her
  remaining Copyright and Related Rights in the Work or (ii) assert any
  associated claims and causes of action with respect to the Work, in either
  case contrary to Affirmer's express Statement of Purpose.
  
  **4. Limitations and Disclaimers.**
  
  1. No trademark or patent rights held by Affirmer are waived, abandoned,
     surrendered, licensed or otherwise affected by this document.
  2. Affirmer offers the Work as-is and makes no representations or warranties
     of any kind concerning the Work, express, implied, statutory or otherwise,
     including without limitation warranties of title, merchantability, fitness
     for a particular purpose, non infringement, or the absence of latent or
     other defects, accuracy, or the present or absence of errors, whether or
     not discoverable, all to the greatest extent permissible under applicable
     law.
  3. Affirmer disclaims responsibility for clearing rights of other persons
     that may apply to the Work or any use thereof, including without
     limitation any person's Copyright and Related Rights in the Work. Further,
     Affirmer disclaims responsibility for obtaining any necessary consents,
     permissions or other rights required for any use of the Work.
  4. Affirmer understands and acknowledges that Creative Commons is not a party
     to this document and has no duty or obligation with respect to this CC0 or
     use of the Work.
  }}

README : Doc
README =
  {{
  # ⛅️ Welcome to the Unison Cloud Starter Project
  
    This is a template project with sample applications and learning modules to
    get you started building and deploying services on
    [Unison Cloud](https://unison.cloud).
    
    {{
    docCallout
      (Some {{ ✅ }})
      {{
      **Prerequisites**
      
      * You have the Unison codebase manager, `ucm`
        [installed](https://www.unison-lang.org/docs/quickstart/#installation-options)
        on your machine
        * Version M5f or higher will work. If you aren't sure, type `version`
          in `ucm` or `ucm version` on the command line.
      * You have a Unison account on
        [Unison Share](https://share.unison-lang.org)
      * You have signed up for Unison Cloud at
        [unison.cloud](https://unison.cloud)
      }} }}
    
    ## 🪩 Deploying sample applications
    
       You can use this project as a template and deploy any of the sample
       services in the `example` namespace service using the following commands
       in the `ucm` console:
       
       ``` ucm
       .> project.create-empty
       amusing-giraffe/main> pull @unison/cloud-start/releases/latest
       amusing-giraffe/main> run examples.helloWorld.deploy
       ```
       
       This will pull all the needed dependencies into a fresh project, and run
       the following "hello world" service:
       
       {{
       docSource
         [ docSourceElement
             (docEmbedTermLink do ex1_quickstart.helloWorld.logic) []
         , docSourceElement (docEmbedTermLink do helloWorld.deploy) []
         ] }}
       
       ### Sample applications include:
       
           * [HelloWorld app]({helloWorld.deploy}) - A simple "hello world"
             HTTP service
           * [Counter app]({counter.deploy}) - A simple stateful counter HTTP
             service
           * [Todo app]({todoApp.deploy}) - An HTTP todo app using the Cloud's
             database layer for persistent storage
           * [Unison-Native app]({multiService.deploy}) - An example of a
             backend with multiple Unison-native services that call each other
             and a single HTTP edge service
           * [Chat app]({chat.deploy}) - A WebSockets chat application
           * [AuthDemo app]({authDemo.deploy}) - An HTTP service that uses
             OAuth2 (OIDC) for authentication
           * [ServePage app]({servePage.deploy}) - An HTTP service that serves
             a simple HTML page with CSS and JS from Blob storage
    
    ## 🍏 Learning about Unison Cloud
    
       This project includes a series of exercises to complete to help you
       learn about Unison Cloud. They come with a friendly test-suite so you
       can see if what you're doing works. You'll find them in the `exercises`
       namespace.
       
       {{
       docCallout
         (Some {{ 📓 }})
         {{
         [Our Cloud learning module page includes explanations of Cloud
         concepts and instructions for how to run them.](https://www.unison.cloud/learn/)
         }} }}
       
       To run a specific exercise, you'll typically `edit` a stub function and
       then submit it for deployment and testing on the Cloud:
       
       ``` ucm
       amusing-giraffe/main> edit exercises.ex1_quickstart.deploy
       amusing-giraffe/main> run exercises.submit.ex1_quickstart
       ```
    
    ## What dependencies are included?
    
       In addition to [the base library](/@unison/base), this template project
       includes:
       
       * The [Unison Cloud client](/@unison/cloud), for interacting with Unison
         Cloud
       * The [Routes library](/@unison/routes), for nicely defining HTTP
         endpoints
       * [JSON encoding and decoding](/@unison/json)
       * The [HTTP library](/@unison/http), which includes the basic types when
         working with the HTTP protocol and the {type Http} ability for issuing
         HTTP client requests.
       * The [Auth](/@chrispenner/auth) library, for handling authentication
       
       {{
       docAside
         {{
         All example code is licensed
         {{ (docLink (docEmbedTermLink do licenses.cc0)) }}. Do whatever you
         like with it!
         }} }}
  }}

ReleaseNotes : Doc
ReleaseNotes =
  {{
  * Upgrades Cloud from 18.6.4 to 19.0.0
  * Upgrades Base from 3.22.0 to 3.23.1
  }}
````

## Code style conventions

At the top-level of this project are two namespaces, `exercises` and `examples`. Users of this library are typically working in one of the two top-level namespaces at a time, so it is uncommon to mix them when programming.
