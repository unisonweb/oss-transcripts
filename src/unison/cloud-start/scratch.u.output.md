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

## Code style conventions

At the top-level of this project are two namespaces, `exercises` and `examples`. Users of this library are typically working in one of the two top-level namespaces at a time, so it is uncommon to mix them when programming. Terms which include the `admin` namespace are unlikely to be called directly by users.
