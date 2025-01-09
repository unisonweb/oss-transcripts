# Website

The source code for the Unison programming language website. Contains documentation and learning materials for Unison.

## Library contents list

``` ucm
@unison/website/main> pull.without-history @unison/website/main

  Downloaded 49046 entities.

  ✅

  Successfully updated @unison/website/main from
  @unison/website/main.

@unison/website/main> find

  1.   articles.distributedDatasets.additionalTopics : Doc
  2.   articles.distributedDatasets.coreIdea : Doc
  3.   articles.distributedDatasets.coreIdea.eager.Tree.map : (a
                                                              ->{Remote} b)
                                                              -> lib.Tree
                                                                a
                                                              ->{Remote} lib.Tree
                                                                b
  4.   structural type articles.distributedDatasets.coreIdea.SimpleTree a
  5.   articles.distributedDatasets.coreIdea.SimpleTree.SimpleTree.Empty : SimpleTree
                                                                             a
  6.   articles.distributedDatasets.coreIdea.SimpleTree.SimpleTree.One : a
                                                                         -> SimpleTree
                                                                           a
  7.   articles.distributedDatasets.coreIdea.SimpleTree.SimpleTree.Two : SimpleTree
                                                                           a
                                                                         -> SimpleTree
                                                                           a
                                                                         -> SimpleTree
                                                                           a
  8.   articles.distributedDatasets.coreIdea.stub.Tree.map : (a
                                                             ->{Remote} b)
                                                             -> lib.Tree
                                                               a
                                                             ->{Remote} lib.Tree
                                                               b
  9.   articles.distributedDatasets.ex1 : Seq k Nat
                                          ->{Remote} Nat
  10.  articles.distributedDatasets.exercises.ex1 : Doc
  11.  articles.distributedDatasets.exercises.ex1.Tree.reverse : lib.Tree
                                                                   a
                                                                 -> lib.Tree
                                                                   a
  12.  articles.distributedDatasets.exercises.ex1a : Doc
  13.  articles.distributedDatasets.exercises.ex2 : Doc
  14.  articles.distributedDatasets.exercises.ex3 : Doc
  15.  articles.distributedDatasets.exercises.ex3.Tree.fromList : [a]
                                                                  -> lib.Tree
                                                                    a
  16.  articles.distributedDatasets.exercises.ex3a : Doc
  17.  articles.distributedDatasets.exercises.ex4 : Doc
  18.  articles.distributedDatasets.exercises.ex5 : Doc
  19.  articles.distributedDatasets.exercises.ex6 : Doc
  20.  articles.distributedDatasets.exercises.ex7 : Doc
  21.  articles.distributedDatasets.exercises.ex8 : Doc
  22.  articles.distributedDatasets.exercises.make : Doc
                                                     -> Doc
                                                     -> Doc
                                                     -> Doc
  23.  articles.distributedDatasets.glossary.fusion : Doc
  24.  articles.distributedDatasets.incrementalEvaluation : Doc
  25.  articles.distributedDatasets.incrementalEvaluation.answers.Tree.memo : Location
                                                                                {Scratch}
                                                                              -> lib.Tree
                                                                                a
                                                                              -> lib.Tree
                                                                                a
  26.  articles.distributedDatasets.incrementalEvaluation.memo1.Tree.reduce : Location
                                                                                {Scratch,
                                                                                g}
                                                                              -> a
                                                                              -> (a
                                                                              -> '{Remote} a
                                                                              ->{Remote} a)
                                                                              -> lib.Tree
                                                                                a
                                                                              ->{Remote} a
  27.  articles.distributedDatasets.index : Doc
  28.  articles.distributedDatasets.index.tutorial : Doc
  29.  articles.distributedDatasets.reductions : Doc
  30.  articles.distributedDatasets.reductions.lazy.Tree.reduce : a
                                                                  -> (a
                                                                  -> Remote.Value
                                                                    a
                                                                  ->{Remote} a)
                                                                  -> lib.Tree
                                                                    a
                                                                  ->{Remote} a
  31.  articles.distributedDatasets.reductions.parallel.Tree.reduce : a
                                                                      -> (a
                                                                      ->{Remote} a
                                                                      ->{Remote} a)
                                                                      -> lib.Tree
                                                                        a
                                                                      ->{Remote} a
  32.  articles.distributedDatasets.reductions.sequential.Tree.reduce : a
                                                                        -> (a
                                                                        ->{Remote} a
                                                                        ->{Remote} a)
                                                                        -> lib.Tree
                                                                          a
                                                                        ->{Remote} a
  33.  articles.distributedDatasets.reductions.withFlatmap.Tree.reduce : zero
                                                                         -> (zero
                                                                         ->{Remote} zero
                                                                         ->{Remote} zero)
                                                                         -> lib.Tree
                                                                           zero
                                                                         ->{Remote} zero
  34.  articles.distributedDatasets.reductions.withMap.Tree.reduce : a
                                                                     -> (a
                                                                     ->{Remote} a
                                                                     ->{Remote} a)
                                                                     -> lib.Tree
                                                                       a
                                                                     ->{Remote} a
  35.  articles.distributedDatasets.src.Tree.fromList : [a]
                                                        -> lib.Tree
                                                          a
  36.  articles.distributedDatasets.src.Tree.map : (a
                                                   ->{Remote} b)
                                                   -> lib.Tree a
                                                   -> lib.Tree b
  37.  articles.distributedDatasets.src.Tree.memo : Location
                                                      {Scratch}
                                                    -> lib.Tree
                                                      a
                                                    -> lib.Tree
                                                      a
  38.  articles.distributedDatasets.src.Tree.reduce : a
                                                      -> (a
                                                      ->{g} 'a
                                                      ->{Remote} a)
                                                      -> lib.Tree
                                                        a
                                                      ->{Remote} a
  39.  articles.distributedDatasets.src.Tree.reverse : lib.Tree
                                                         a
                                                       -> lib.Tree
                                                         a
  40.  articles.distributedDatasets.src.Tree.take : Nat
                                                    -> lib.Tree
                                                      a
                                                    ->{Remote} [a]
  41.  articles.distributedDatasets._authors : Doc
  42.  articles.distributedDatasets._sidebar : Doc
  43.  articles.distributedDatasets._summary : Doc
  44.  articles.distributedDatasets._title : Doc
  45.  blog.adventOfCode2022.index : Doc
  46.  blog.adventOfCodeALookBack.index : Doc
  47.  blog.adventOfCodeHighlights2022.index : Doc
  48.  blog.adventOfCodeHighlights2022._day1 : Doc
  49.  blog.adventOfCodeHighlights2022._day10 : Doc
  50.  blog.adventOfCodeHighlights2022._day11 : Doc
  51.  blog.adventOfCodeHighlights2022._day12 : Doc
  52.  blog.adventOfCodeHighlights2022._day13 : Doc
  53.  blog.adventOfCodeHighlights2022._day14 : Doc
  54.  blog.adventOfCodeHighlights2022._day15 : Doc
  55.  blog.adventOfCodeHighlights2022._day17 : Doc
  56.  blog.adventOfCodeHighlights2022._day18 : Doc
  57.  blog.adventOfCodeHighlights2022._day2 : Doc
  58.  blog.adventOfCodeHighlights2022._day3 : Doc
  59.  blog.adventOfCodeHighlights2022._day4 : Doc
  60.  blog.adventOfCodeHighlights2022._day5 : Doc
  61.  blog.adventOfCodeHighlights2022._day6 : Doc
  62.  blog.adventOfCodeHighlights2022._day7 : Doc
  63.  blog.adventOfCodeHighlights2022._day8 : Doc
  64.  blog.adventOfCodeHighlights2022._day9 : Doc
  65.  blog.adventOfCodeHighlights2022._foldDoc : Doc
                                                  -> Doc
                                                  -> Doc
  66.  blog.adventOfCodeTooling2022.index : Doc
  67.  blog.aocInUnison2023.index : Doc
  68.  blog.april_2020Update.index : Doc
  69.  blog.autocomplete.index : Doc
  70.  blog.batchStorageApi.index : Doc
  71.  blog.benefitCorpReport.index : Doc
  72.  blog.birthdayKata.index : Doc
  73.  blog.blogEngine.index : Doc
  74.  blog.cloudLearningKickoff.index : Doc
  75.  blog.cloudTeaser.index : Doc
  76.  blog.cloudTeaser.setConfig : Text ->{IO, Exception} Text
  77.  blog.cloudTeaser.simpleStorage : Database
                                        -> Table Text Nat
                                        -> '{Exception,
                                        Cloud,
                                        cloud.Storage} ()
  78.  blog.contributingToUnison.index : Doc
  79.  blog.decLibraryUpdates2022.index : Doc
  80.  blog.developerProductivityReallyMatters.index : Doc
  81.  blog.dutchUnisonMeetup.index : Doc
  82.  blog.experienceReportUnisonInProduction.index : Doc
  83.  blog.heatherMiller.index : Doc
  84.  blog.heresWhatsBeenHappeningWithUnison.index : Doc
  85.  blog.howToRefactorACodebaseWithoutEverBreakingIt.index : Doc
  86.  blog.introducingContributions.index : Doc
  87.  blog.itsTimeToRethinkCloudPricing.index : Doc
  88.  structural ability blog.jitAnnounce.Control r
  89.  blog.jitAnnounce.Control.control : ((a ->{Control r} r)
                                          -> r)
                                          ->{Control r} a
  90.  blog.jitAnnounce.index : Doc
  91.  blog.jitAnnounce.prompt : '{e, Control r} r ->{e} r
  92.  blog.jitAnnounce.reset : '{e, Shift r} r ->{e} r
  93.  structural ability blog.jitAnnounce.Shift r
  94.  blog.jitAnnounce.Shift.shift : ((a -> r) -> r)
                                      ->{Shift r} a
  95.  blog.jitAnnounce._aside1 : Doc
  96.  blog.jitAnnounce._aside1desc : Doc
  97.  blog.jitAnnounce._aside2 : Doc
  98.  blog.jitAnnounce._aside2desc : Doc
  99.  blog.latexDocSupport.index : Doc
  100. blog.latexDocSupport.index._arrows : Doc
  101. blog.latexDocSupport.index._composition : Doc
  102. blog.latexDocSupport.index._ex1 : Doc
  103. blog.latexDocSupport.index._ex2 : Doc
  104. blog.latexDocSupport.index._ex3 : Doc
  105. blog.latexDocSupport.index._labeledArrows : Doc
  106. blog.latexDocSupport.index._mermaid1 : Doc
  107. blog.latexDocSupport.index._quantifiers : Doc
  108. blog.latexDocSupport.index._vertical : Doc
  109. blog.longUpdateMergeProcess.index : Doc
  110. blog.m2Release.index : Doc
  111. blog.m4Codehosting.index : Doc
  112. blog.m4hRelease.index : Doc
  113. blog.march2023LibraryUpdates.index : Doc
  114. blog.march2023LibraryUpdates.index._multiLine : Text
  115. blog.march_2019Update.index : Doc
  116. blog.march_2020Update.index : Doc
  117. blog.newUpdateProcess.index : Doc
  118. blog.newYearsUpdate2019.index : Doc
  119. blog.ourSeedFunding.index : Doc
  120. blog.peopleAreWritingLibraries.index : Doc
  121. blog.preConferenceSyntaxGuide.index : Doc
  122. blog.projectBasedUcmCommands.index : Doc
  123. blog.projectsAreHere.index : Doc
  124. blog.projectsIncoming.index : Doc
  125. blog.reducingChurn.index : Doc
  126. blog.roadmap.index : Doc
  127. blog.shareSearchImprovements.index : Doc
  128. blog.stackTracesM4d.index : Doc
  129. blog.summer2023Highlights.index : Doc
  130. blog.summer2023Highlights._byeRoute : '{Route} ()
  131. blog.summer2023Highlights._hiRoute : '{Route} ()
  132. blog.summer2023Highlights._main : '{IO, Exception} ()
  133. blog.typeBasedSearch.index : Doc
  134. blog.ucm0523.index : Doc
  135. blog.ucm0525.index : Doc
  136. blog.ucm0526.index : Doc
  137. blog.ucm0527.index : Doc
  138. blog.ucm0528.index : Doc
  139. blog.unisonServicesPreview.index : Doc
  140. blog.unisonShareIsOpenSource.index : Doc
  141. blog.unison_2021YearInReview.index : Doc
  142. blog.visualizingRemote.index : Doc
  143. blog.visualizingRemote.index._blockingReduce : '{Remote} Nat
  144. blog.visualizingRemote.index._multipleLocations : '{Remote} Nat
  145. blog.visualizingRemote.index._simpleReduce : '{Remote} Nat
  146. blog.vscodeStartup.index : Doc
  147. blog.whereUnisonIsHeaded.index : Doc
  148. blog.wrapUp2022.index : Doc
  149. blog.writeupOfOurFirstUnisonMeetup.index : Doc
  150. blog._getPosts : Soup ->{Throw XMLError} [(Text, Text)]
  151. docs.atAGlance : Doc
  152. docs.atAGlance.distributed : Seq k Nat ->{Remote} Nat
  153. docs.atAGlance.distributedEx : Seq k Nat ->{Remote} Nat
  154. docs.atAGlance.streamList : '[Nat]
  155. docs.atAGlance._nav : Doc
  156. docs.contributeDocs : Doc
  157. docs.delayGreet : 'Text
  158. docs.divBy : Nat -> Nat ->{Stream Nat} Nat
  159. docs.escapeQuoteLiteral : Doc
  160. docs.exercises.controlFlow : Doc
  161. docs.exercises.controlFlow.ex1 : Doc
  162. docs.exercises.controlFlow.ex2 : Doc
  163. docs.exercises.controlFlow.ex2.answers.drawShape : Shape
                                                          -> Char
                                                          -> [[Char]]
  164. structural type docs.exercises.controlFlow.ex2.answers.Shape
  165. docs.exercises.controlFlow.ex2.answers.Shape.Rectangle : Nat
                                                                -> Nat
                                                                -> Shape
  166. docs.exercises.controlFlow.ex2.answers.Shape.Square : Nat
                                                             -> Shape
  167. docs.exercises.controlFlow.ex2.draw : [[Char]]
                                             -> '{IO} ()
  168. docs.exercises.controlFlow.ex2.testDraw1 : '{IO} ()
  169. docs.exercises.controlFlow.ex2.testDraw2 : '{IO} ()
  170. docs.exercises.controlFlow.ex3 : Doc
  171. docs.exercises.controlFlow.ex3.answerCases.matchTwo : Nat
                                                             -> Nat
                                                             -> Text
  172. docs.exercises.controlFlow.ex4 : Doc
  173. docs.exercises.controlFlow.ex4.answer.myText : Text
                                                      -> Text
  174. docs.exercises.controlFlow.ex4.myText : Text -> Text
  175. docs.exercises.controlFlow.ex4.test1 : [test.Result]
  176. docs.exercises.controlFlow.ex4.test2 : [test.Result]
  177. docs.exercises.controlFlow.ex4.test3 : [test.Result]
  178. docs.exercises.controlFlow.ex4.test4 : [test.Result]
  179. docs.exercises.controlFlow.ex4.test5 : [test.Result]
  180. docs.exercises.controlFlow.ex4.test6 : [test.Result]
  181. docs.exercises.valuesFunctions : Doc
  182. docs.exercises.valuesFunctions.ex1 : Doc
  183. docs.exercises.valuesFunctions.ex2 : Doc
  184. docs.exercises.valuesFunctions.ex3 : Doc
  185. docs.exercises.valuesFunctions.ex3.hints.h1 : Doc
  186. docs.exercises.valuesFunctions.ex3.hints.h2 : Doc
  187. docs.exercises.valuesFunctions.ex4 : Doc
  188. docs.exercises.valuesFunctions.ex4.factorial : Nat -> Nat
  189. docs.exercises.valuesFunctions.ex4.hints.h1 : Doc
  190. docs.exercises.valuesFunctions.ex5 : Doc
  191. docs.exercises.valuesFunctions.ex5.answers.a1 : Doc
  192. docs.exercises.valuesFunctions.ex5.answers.removeEveryOther : [a]
                                                                     -> [a]
  193. docs.exercises.valuesFunctions.ex5.hints.h1 : Doc
  194. docs.exercises.valuesFunctions.ex5.hints.h2 : Doc
  195. docs.exercises.valuesFunctions.ex5.tests.t1 : [test.Result]
  196. docs.exercises.valuesFunctions.ex5.tests.t2 : [test.Result]
  197. docs.exercises.valuesFunctions.ex5.tests.t3 : [test.Result]
  198. docs.fundamentals.abilities.abilityExercises.Stream.pipe : '{Stream
                                                                    a} ()
                                                                  -> '{Ask
                                                                    a,
                                                                  Stream
                                                                    b} r
                                                                  -> '{Stream
                                                                    b} ()
  199. docs.fundamentals.abilities.errorHandling : Doc
  200. docs.fundamentals.abilities.errorHandling.divBy : Nat
                                                         -> Nat
                                                         ->{Abort} Nat
  201. docs.fundamentals.abilities.errorHandling.divByException : Nat
                                                                  -> Nat
                                                                  ->{Exception} Nat
  202. docs.fundamentals.abilities.errorHandling.divByOptional : Nat
                                                                 -> Nat
                                                                 -> Optional
                                                                   Nat
  203. docs.fundamentals.abilities.errorHandling.divByThrow : Nat
                                                              -> Nat
                                                              ->{Throw
                                                                Text} Nat
  204. docs.fundamentals.abilities.errorHandling.myFunction : Nat
                                                              -> Nat
                                                              ->{Abort} Nat
  205. docs.fundamentals.abilities.exercises.ex1 : Doc
  206. docs.fundamentals.abilities.exercises.ex2 : Doc
  207. docs.fundamentals.abilities.exercises.ex2.answers.averageOfRange : Nat
                                                                          ->{Store
                                                                            [Nat]} Float
  208. docs.fundamentals.abilities.exercises.ex2.answers.handleAverageOfRange : Float
  209. docs.fundamentals.abilities.exercises.ex3 : Doc
  210. docs.fundamentals.abilities.exercises.ex3.answers.handleAverageOfRange : Float
  211. docs.fundamentals.abilities.exercises.ex4 : Doc
  212. docs.fundamentals.abilities.faqs : Doc
  213. docs.fundamentals.abilities.forMonadicallyInclined : Doc
  214. docs.fundamentals.abilities.forMonadicallyInclined.final : '{IO,
                                                                  Exception} ()
  215. docs.fundamentals.abilities.forMonadicallyInclined.refExample1 : '{IO} Text
  216. docs.fundamentals.abilities.forMonadicallyInclined.refExample2 : '{IO} Text
  217. docs.fundamentals.abilities.forMonadicallyInclined.refExample3 : '{IO} Text
  218. docs.fundamentals.abilities.forMonadicallyInclined.safeDiv1 : Nat
                                                                     -> Nat
                                                                     ->{Exception} Nat
  219. docs.fundamentals.abilities.forMonadicallyInclined.safeDiv2 : '{IO,
                                                                     Exception} Nat
  220. docs.fundamentals.abilities.forMonadicallyInclined.safeDiv3 : '{IO,
                                                                     Exception,
                                                                     Store
                                                                       Text} Nat
  221. docs.fundamentals.abilities.forMonadicallyInclined.safeDiv4 : '{IO,
                                                                     Exception,
                                                                     Store
                                                                       Text} Nat
  222. docs.fundamentals.abilities.index : Doc
  223. docs.fundamentals.abilities.index._nav : Doc
  224. docs.fundamentals.abilities.usingAbilitiesPt1 : Doc
  225. ability docs.fundamentals.abilities.usingAbilitiesPt1.Cache k v
  226. docs.fundamentals.abilities.usingAbilitiesPt1.Cache.Cache.get : k
                                                                       ->{IO,
                                                                       Exception,
                                                                       Cache} v
  227. docs.fundamentals.abilities.usingAbilitiesPt1.Cache.Cache.put : k
                                                                       -> v
                                                                       ->{IO,
                                                                       Exception,
                                                                       Cache} ()
  228. docs.fundamentals.abilities.usingAbilitiesPt1.effectfulPredicate.stopIfTrue : (a
                                                                                     ->{g} Boolean)
                                                                                     -> a
                                                                                     ->{g,
                                                                                     Abort} a
  229. docs.fundamentals.abilities.usingAbilitiesPt1.greet : '{IO,
                                                             Exception} ()
  230. docs.fundamentals.abilities.usingAbilitiesPt1.nonEmptyName : Text
                                                                    -> Text
  231. docs.fundamentals.abilities.usingAbilitiesPt1.stopIfTrue : (a
                                                                  -> Boolean)
                                                                  -> a
                                                                  ->{Abort} a
  232. docs.fundamentals.abilities.usingAbilitiesPt1.store.getAfterStore : '{g,
                                                                           Store
                                                                             a} b
                                                                           ->{g,
                                                                           Store
                                                                             a} a
  233. docs.fundamentals.abilities.usingAbilitiesPt1.store.nonEmptyName : Text
                                                                          -> Text
  234. docs.fundamentals.abilities.usingAbilitiesPt1.store.stopIfTrue : (a
                                                                        -> Boolean)
                                                                        -> a
                                                                        ->{Abort,
                                                                        Store
                                                                          a} a
  235. docs.fundamentals.abilities.usingAbilitiesPt1._nav : Doc
  236. docs.fundamentals.abilities.usingAbilitiesPt2 : Doc
  237. docs.fundamentals.abilities.usingAbilitiesPt2.nameGreet : '{IO,
                                                                 Exception} ()
  238. docs.fundamentals.abilities.usingAbilitiesPt2._nav : Doc
  239. docs.fundamentals.abilities.usingAbilitiesTut : Doc
  240. type docs.fundamentals.abilities.usingAbilitiesTut.Animal
  241. docs.fundamentals.abilities.usingAbilitiesTut.Animal.Bird : Animal
  242. docs.fundamentals.abilities.usingAbilitiesTut.Animal.Squirrel : Animal
  243. docs.fundamentals.abilities.usingAbilitiesTut.animals : [Animal]
  244. type docs.fundamentals.abilities.usingAbilitiesTut.BirdFeeder
  245. docs.fundamentals.abilities.usingAbilitiesTut.BirdFeeder.BirdFeeder : Nat
                                                                             -> BirdFeeder
  246. docs.fundamentals.abilities.usingAbilitiesTut.dispenseFood1 : Animal
                                                                     -> BirdFeeder
                                                                     -> BirdFeeder
  247. type docs.fundamentals.abilities.usingAbilitiesTut.Message
  248. docs.fundamentals.abilities.usingAbilitiesTut.Message.TextMessage : Text
                                                                           -> usingAbilitiesTut.Message
  249. docs.fundamentals.abilities.writingAbilities : Doc
  250. docs.fundamentals.abilities.writingAbilities.constantStore : b
                                                                    -> '{g,
                                                                    KVStore
                                                                      a
                                                                      b} r
                                                                    ->{g} r
  251. docs.fundamentals.abilities.writingAbilities.discard : r
                                                              -> '{g,
                                                              KVStore
                                                                a
                                                                b} r
                                                              ->{g} r
  252. docs.fundamentals.abilities.writingAbilities.inMemory : '{g,
                                                               KVStore
                                                                 a
                                                                 b} r
                                                               ->{g} r
  253. docs.fundamentals.abilities.writingAbilities.inMemory.impl : Map
                                                                      a
                                                                      b
                                                                    -> Request
                                                                      {KVStore
                                                                        a
                                                                        b,
                                                                      g}
                                                                      r
                                                                    ->{g} r
  254. docs.fundamentals.abilities.writingAbilities.inMemoryWithMap : '{g,
                                                                      KVStore
                                                                        a
                                                                        b} r
                                                                      ->{g} ( r,
                                                                        Map
                                                                        a
                                                                        b)
  255. ability docs.fundamentals.abilities.writingAbilities.KVStore a b
  256. docs.fundamentals.abilities.writingAbilities.KVStore.get : a
                                                                  ->{KVStore
                                                                    a
                                                                    b} Optional
                                                                    b
  257. docs.fundamentals.abilities.writingAbilities.KVStore.put : a
                                                                  -> b
                                                                  ->{KVStore
                                                                    a
                                                                    b} ()
  258. docs.fundamentals.abilities.writingAbilities.myProgram : '{KVStore
                                                                  Nat
                                                                  Nat} Text
  259. docs.fundamentals.abilities.writingAbilities._nav : Doc
  260. docs.fundamentals.abilities._handlerDefinition : Doc
  261. docs.fundamentals.controlFlow.aside.dataAccess : Doc
  262. docs.fundamentals.controlFlow.aside.exhaustivityChecking : Doc
  263. type docs.fundamentals.controlFlow.Color
  264. docs.fundamentals.controlFlow.Color.RGB : Nat
                                                 -> Nat
                                                 -> Nat
                                                 -> controlFlow.Color
  265. docs.fundamentals.controlFlow.exceptionHandling : Doc
  266. docs.fundamentals.controlFlow.exceptionHandling.bug : Doc
  267. docs.fundamentals.controlFlow.exceptionHandling.either : Doc
  268. docs.fundamentals.controlFlow.exceptionHandling.either.naming : Doc
  269. docs.fundamentals.controlFlow.exceptionHandling.failure : Doc
  270. docs.fundamentals.controlFlow.exceptionHandling.failure.example1 : Failure
  271. type docs.fundamentals.controlFlow.exceptionHandling.failure.example1.DatabaseError
  272. docs.fundamentals.controlFlow.exceptionHandling.failure.example1.DatabaseError.DuplicateValuesForUniqueColumn : DatabaseError
  273. docs.fundamentals.controlFlow.exceptionHandling.failure.example1.DatabaseError.NonNullConstraintViolated : DatabaseError
  274. docs.fundamentals.controlFlow.exceptionHandling.failure.example1.DatabaseError.NumericValueOutOfRange : DatabaseError
  275. type docs.fundamentals.controlFlow.exceptionHandling.failure.example1.User
  276. docs.fundamentals.controlFlow.exceptionHandling.failure.example1.User.User : Text
                                                                                    -> User
  277. docs.fundamentals.controlFlow.exceptionHandling.failure.genericFailure : Failure
  278. docs.fundamentals.controlFlow.exceptionHandling.opt1 : Doc
  279. docs.fundamentals.controlFlow.exceptionHandling.optional : Doc
  280. type docs.fundamentals.controlFlow.exceptionHandling.optional.Cake
  281. docs.fundamentals.controlFlow.exceptionHandling.optional.Cake.Cake : Text
                                                                            -> Cake
  282. docs.fundamentals.controlFlow.exceptionHandling.optional.cakeFactory : [Ingredient]
                                                                              -> Optional
                                                                                Cake
  283. type docs.fundamentals.controlFlow.exceptionHandling.optional.Ingredient
  284. docs.fundamentals.controlFlow.exceptionHandling.optional.Ingredient.Egg : Ingredient
  285. docs.fundamentals.controlFlow.exceptionHandling.optional.Ingredient.Flour : Ingredient
  286. docs.fundamentals.controlFlow.exceptionHandling.optional.Ingredient.Kale : Ingredient
  287. docs.fundamentals.controlFlow.exceptionHandling.optional.Ingredient.Sugar : Ingredient
  288. docs.fundamentals.controlFlow.exceptionHandling._nav : Doc
  289. docs.fundamentals.controlFlow.functionalLooping : Doc
  290. docs.fundamentals.controlFlow.functionalLooping.fold.myTotal : [Nat]
                                                                      -> Nat
  291. docs.fundamentals.controlFlow.functionalLooping.recursive.myTotal : [Nat]
                                                                           -> Nat
  292. docs.fundamentals.controlFlow.functionalLooping.tailRecursive.myTotal : [Nat]
                                                                               -> Nat
  293. docs.fundamentals.controlFlow.functionalLooping._nav : Doc
  294. docs.fundamentals.controlFlow.ifThenAndElse : Doc
  295. docs.fundamentals.controlFlow.ifThenAndElse._nav : Doc
  296. docs.fundamentals.controlFlow.looping : Doc
  297. docs.fundamentals.controlFlow.patternMatching : Doc
  298. docs.fundamentals.controlFlow.patternMatching.listPatterns : Doc
  299. type docs.fundamentals.controlFlow.patternMatching.Lunch
  300. docs.fundamentals.controlFlow.patternMatching.Lunch.Mystery : Text
                                                                     -> Boolean
                                                                     -> Lunch
  301. docs.fundamentals.controlFlow.patternMatching.Lunch.Salad : Text
                                                                   -> Lunch
  302. docs.fundamentals.controlFlow.patternMatching.Lunch.Soup : Text
                                                                  -> Lunch
  303. type docs.fundamentals.controlFlow.patternMatching.Utensil
  304. docs.fundamentals.controlFlow.patternMatching.Utensil.Fork : Utensil
  305. docs.fundamentals.controlFlow.patternMatching.Utensil.Knife : Utensil
  306. docs.fundamentals.controlFlow.patternMatching.Utensil.Spoon : Utensil
  307. docs.fundamentals.controlFlow.patternMatching._nav : Doc
  308. docs.fundamentals.controlFlow.patternMatching2 : Doc
  309. docs.fundamentals.controlFlow.patternMatching2._nav : Doc
  310. docs.fundamentals.controlFlow.tailCallSumm : Doc
  311. docs.fundamentals.controlFlow._asPatterns : Doc
  312. type docs.fundamentals.controlFlow._asPatterns.Hydra
  313. docs.fundamentals.controlFlow._asPatterns.Hydra.Heads : Nat
                                                               -> Nat
                                                               -> Nat
                                                               -> Nat
                                                               -> Nat
                                                               -> Hydra
  314. docs.fundamentals.controlFlow._asPatterns.slayHydra : Nat
                                                             -> Hydra
                                                             -> Optional
                                                               Hydra
  315. docs.fundamentals.controlFlow._casesSyntax : Doc
  316. docs.fundamentals.controlFlow._casesSyntax.myMatch : Nat
                                                            -> Text
  317. docs.fundamentals.controlFlow._casesSyntax.twoCases : Nat
                                                             -> Nat
                                                             -> Text
  318. docs.fundamentals.controlFlow._datatypesEither : Doc
  319. docs.fundamentals.controlFlow._dataTypesPatternMatching : Doc
  320. docs.fundamentals.controlFlow._dataTypesPatternMatching.placeSetting : Lunch
                                                                              -> [Utensil]
  321. docs.fundamentals.controlFlow._ifElseBlocks._nav : Doc
  322. docs.fundamentals.controlFlow._ifElseBlocksSum : Doc
  323. docs.fundamentals.controlFlow._literalPatternMatching : Doc
  324. docs.fundamentals.controlFlow._summaryLoopingConstructs : Doc
  325. docs.fundamentals.controlFlow._typeParamConvention : Doc
  326. docs.fundamentals.controlFlow._typeParamConventionGotcha : Doc
  327. docs.fundamentals.controlFlow._variablesGuards : Doc
  328. docs.fundamentals.controlFlow._vsOopConstructors : Doc
  329. docs.fundamentals.dataTypes.recordTypes : Doc
  330. docs.fundamentals.dataTypes.recordTypes._nav : Doc
  331. docs.fundamentals.dataTypes.uniqueAndStructuralTypes : Doc
  332. type docs.fundamentals.dataTypes.uniqueAndStructuralTypes.Genre
  333. docs.fundamentals.dataTypes.uniqueAndStructuralTypes.Genre.Biography : Genre
  334. docs.fundamentals.dataTypes.uniqueAndStructuralTypes.Genre.CookBooks : Genre
  335. docs.fundamentals.dataTypes.uniqueAndStructuralTypes.Genre.Fiction : Genre
  336. docs.fundamentals.dataTypes.uniqueAndStructuralTypes.Genre.Poetry : Genre
  337. docs.fundamentals.dataTypes.uniqueAndStructuralTypes.Genre.Science : Genre
  338. structural type docs.fundamentals.dataTypes.uniqueAndStructuralTypes.Weekday
  339. docs.fundamentals.dataTypes.uniqueAndStructuralTypes.Weekday.Fri : Weekday
  340. docs.fundamentals.dataTypes.uniqueAndStructuralTypes.Weekday.Mon : Weekday
  341. docs.fundamentals.dataTypes.uniqueAndStructuralTypes.Weekday.Thurs : Weekday
  342. docs.fundamentals.dataTypes.uniqueAndStructuralTypes.Weekday.Tues : Weekday
  343. docs.fundamentals.dataTypes.uniqueAndStructuralTypes.Weekday.Wed : Weekday
  344. docs.fundamentals.dataTypes.uniqueAndStructuralTypes._nav : Doc
  345. structural type docs.fundamentals.dataTypes._recordTypes.DaysOfWeek
  346. docs.fundamentals.dataTypes._recordTypes.DaysOfWeek.Fri : DaysOfWeek
  347. docs.fundamentals.dataTypes._recordTypes.DaysOfWeek.Mon : DaysOfWeek
  348. docs.fundamentals.dataTypes._recordTypes.DaysOfWeek.Sat : DaysOfWeek
  349. docs.fundamentals.dataTypes._recordTypes.DaysOfWeek.Sun : DaysOfWeek
  350. docs.fundamentals.dataTypes._recordTypes.DaysOfWeek.Thurs : DaysOfWeek
  351. docs.fundamentals.dataTypes._recordTypes.DaysOfWeek.Tues : DaysOfWeek
  352. docs.fundamentals.dataTypes._recordTypes.DaysOfWeek.Wed : DaysOfWeek
  353. structural type docs.fundamentals.dataTypes._recordTypes.Volunteer
  354. docs.fundamentals.dataTypes._recordTypes.Volunteer.age : Volunteer
                                                                -> Nat
  355. docs.fundamentals.dataTypes._recordTypes.Volunteer.age.modify : (Nat
                                                                       ->{g} Nat)
                                                                       -> Volunteer
                                                                       ->{g} Volunteer
  356. docs.fundamentals.dataTypes._recordTypes.Volunteer.age.set : Nat
                                                                    -> Volunteer
                                                                    -> Volunteer
  357. docs.fundamentals.dataTypes._recordTypes.Volunteer.daysAvailable : Volunteer
                                                                          -> Set
                                                                            DaysOfWeek
  358. docs.fundamentals.dataTypes._recordTypes.Volunteer.daysAvailable.modify : (Set
                                                                                   DaysOfWeek
                                                                                 ->{g} Set
                                                                                   DaysOfWeek)
                                                                                 -> Volunteer
                                                                                 ->{g} Volunteer
  359. docs.fundamentals.dataTypes._recordTypes.Volunteer.daysAvailable.set : Set
                                                                                DaysOfWeek
                                                                              -> Volunteer
                                                                              -> Volunteer
  360. docs.fundamentals.dataTypes._recordTypes.Volunteer.desiredStartDate : Volunteer
                                                                             -> Text
  361. docs.fundamentals.dataTypes._recordTypes.Volunteer.desiredStartDate.modify : (Text
                                                                                    ->{g} Text)
                                                                                    -> Volunteer
                                                                                    ->{g} Volunteer
  362. docs.fundamentals.dataTypes._recordTypes.Volunteer.desiredStartDate.set : Text
                                                                                 -> Volunteer
                                                                                 -> Volunteer
  363. docs.fundamentals.dataTypes._recordTypes.Volunteer.endDate : Volunteer
                                                                    -> Optional
                                                                      Text
  364. docs.fundamentals.dataTypes._recordTypes.Volunteer.endDate.modify : (Optional
                                                                             Text
                                                                           ->{g} Optional
                                                                             Text)
                                                                           -> Volunteer
                                                                           ->{g} Volunteer
  365. docs.fundamentals.dataTypes._recordTypes.Volunteer.endDate.set : Optional
                                                                          Text
                                                                        -> Volunteer
                                                                        -> Volunteer
  366. docs.fundamentals.dataTypes._recordTypes.Volunteer.example : Volunteer
  367. docs.fundamentals.dataTypes._recordTypes.Volunteer.example.avail : Set
                                                                            DaysOfWeek
  368. docs.fundamentals.dataTypes._recordTypes.Volunteer.preferredName : Volunteer
                                                                          -> Text
  369. docs.fundamentals.dataTypes._recordTypes.Volunteer.preferredName.modify : (Text
                                                                                 ->{g} Text)
                                                                                 -> Volunteer
                                                                                 ->{g} Volunteer
  370. docs.fundamentals.dataTypes._recordTypes.Volunteer.preferredName.set : Text
                                                                              -> Volunteer
                                                                              -> Volunteer
  371. docs.fundamentals.dataTypes._recordTypes.Volunteer.Volunteer : Text
                                                                      -> Nat
                                                                      -> Text
                                                                      -> Optional
                                                                        Text
                                                                      -> Set
                                                                        DaysOfWeek
                                                                      -> Volunteer
  372. docs.fundamentals.dataTypes._uniqueAndStructuralTypes.bookExample : struct.Author
  373. docs.fundamentals.dataTypes._uniqueAndStructuralTypes.bookFinder : struct.Author
                                                                          -> [( struct.Author,
                                                                            struct.Author)]
                                                                          -> Optional
                                                                            struct.Author
  374. structural type docs.fundamentals.dataTypes._uniqueAndStructuralTypes.struct.Author
  375. docs.fundamentals.dataTypes._uniqueAndStructuralTypes.struct.Author.struct.Author.Author : Text
                                                                                                  -> Nat
                                                                                                  -> Set
                                                                                                    Genre
                                                                                                  -> struct.Author
  376. docs.fundamentals.dataTypes._uniqueAndStructuralTypes.struct.authorExample : struct.Author
  377. structural type docs.fundamentals.dataTypes._uniqueAndStructuralTypes.struct.Book
  378. docs.fundamentals.dataTypes._uniqueAndStructuralTypes.struct.Book.Book : Text
                                                                                -> Nat
                                                                                -> Set
                                                                                  Genre
                                                                                -> struct.Author
  379. type docs.fundamentals.dataTypes._uniqueAndStructuralTypes.uniqueVersion.Author
  380. docs.fundamentals.dataTypes._uniqueAndStructuralTypes.uniqueVersion.Author.uniqueVersion.Author.Author : Text
                                                                                                                -> Nat
                                                                                                                -> uniqueVersion.Author
  381. type docs.fundamentals.dataTypes._uniqueAndStructuralTypes.uniqueVersion.Book
  382. docs.fundamentals.dataTypes._uniqueAndStructuralTypes.uniqueVersion.Book.Book : Text
                                                                                       -> Nat
                                                                                       -> uniqueVersion.Book
  383. docs.fundamentals.valuesAndFunctions.commonCollectionTypes : Doc
  384. docs.fundamentals.valuesAndFunctions.commonCollectionTypes._nav : Doc
  385. docs.fundamentals.valuesAndFunctions.definingOperators : Doc
  386. docs.fundamentals.valuesAndFunctions.definingOperators.^ : Nat
                                                                  -> Nat
                                                                  -> Nat
  387. docs.fundamentals.valuesAndFunctions.definingOperators._nav : Doc
  388. docs.fundamentals.valuesAndFunctions.delayedComputations : Doc
  389. docs.fundamentals.valuesAndFunctions.delayedComputations.coinflip : Boolean
                                                                           -> Text
  390. docs.fundamentals.valuesAndFunctions.delayedComputations.longText : 'Text
  391. docs.fundamentals.valuesAndFunctions.delayedComputations.tldr : Doc
  392. docs.fundamentals.valuesAndFunctions.delayedComputations._nav : Doc
  393. docs.fundamentals.valuesAndFunctions.functionApplicationOperators : Doc
  394. docs.fundamentals.valuesAndFunctions.functionApplicationOperators.andThenEx : Boolean
  395. docs.fundamentals.valuesAndFunctions.functionApplicationOperators.andThenMultiEx : Boolean
  396. docs.fundamentals.valuesAndFunctions.functionApplicationOperators.composeEx : Nat
                                                                                     -> Boolean
  397. docs.fundamentals.valuesAndFunctions.functionApplicationOperators.composeMultiEx : Text
                                                                                          -> Boolean
  398. docs.fundamentals.valuesAndFunctions.functionApplicationOperators.pipeBackwardsEx : Optional
                                                                                             Nat
  399. docs.fundamentals.valuesAndFunctions.functionApplicationOperators.pipeBackwardsEx.wrap : Nat
                                                                                                -> Optional
                                                                                                  Nat
  400. docs.fundamentals.valuesAndFunctions.functionApplicationOperators.pipeEx : Boolean
  401. docs.fundamentals.valuesAndFunctions.functionApplicationOperators.pipeRightEx : Optional
                                                                                         Nat
  402. docs.fundamentals.valuesAndFunctions.functionApplicationOperators._nav : Doc
  403. docs.fundamentals.valuesAndFunctions.functions : Doc
  404. docs.fundamentals.valuesAndFunctions.functions.addNums : Nat
                                                                -> Nat
                                                                -> Nat
  405. docs.fundamentals.valuesAndFunctions.functions.addOne : Nat
                                                               -> Nat
  406. docs.fundamentals.valuesAndFunctions.functions._nav : Doc
  407. docs.fundamentals.valuesAndFunctions.oldFunctionsContent : Doc
  408. docs.fundamentals.valuesAndFunctions.readingTypeSignatures : Doc
  409. docs.fundamentals.valuesAndFunctions.readingTypeSignatures._nav : Doc
  410. docs.fundamentals.valuesAndFunctions.terms : Doc
  411. docs.fundamentals.valuesAndFunctions.terms._nav : Doc
  412. docs.fundamentals.valuesAndFunctions._blockSyntax : Doc
  413. docs.fundamentals.valuesAndFunctions._higherOrderFunctions : Doc
  414. docs.fundamentals.valuesAndFunctions._lambdaSyntax : Doc
  415. docs.fundamentals.valuesAndFunctions._polymorphismLinkAside : Doc
  416. docs.fundamentals.valuesAndFunctions._summary : Doc
  417. docs.fundamentals.valuesAndFunctions._termsFunctionsSummary : Doc
  418. docs.fundamentals.valuesAndFunctions._tupleDecomposition : Doc
  419. docs.fundamentals.valuesAndFunctions._tupleDecomposition.getBytesSize : ( Text,
                                                                                 Bytes,
                                                                                 Text)
                                                                               -> Nat
  420. docs.glance.bankTransfers : '{IO, Exception} ()
  421. docs.glance.delayGreet : 'Text
  422. docs.glance.double : Nat -> Nat
  423. docs.glance.exampleGet : '{IO, Exception} HttpResponse
  424. docs.glance.getRandomElem : [a] ->{Abort, Random} a
  425. docs.glance.greet : Text -> Text
  426. docs.glance.incrementTVar : TVar Nat ->{STM} ()
  427. type docs.glance.LivingThings
  428. docs.glance.LivingThings.Animal : LivingThings
  429. docs.glance.LivingThings.Fungi : LivingThings
  430. docs.glance.LivingThings.Monera : LivingThings
  431. docs.glance.LivingThings.Plant : LivingThings
  432. docs.glance.LivingThings.Protists : LivingThings
  433. docs.glance.nonZero : Nat ->{Exception} Nat
  434. type docs.glance.Pet
  435. docs.glance.Pet.age : Pet -> Nat
  436. docs.glance.Pet.age.modify : (Nat ->{g} Nat)
                                    -> Pet
                                    ->{g} Pet
  437. docs.glance.Pet.age.set : Nat -> Pet -> Pet
  438. docs.glance.Pet.foodPreferences : Pet -> [Text]
  439. docs.glance.Pet.foodPreferences.modify : ([Text]
                                                ->{g} [Text])
                                                -> Pet
                                                ->{g} Pet
  440. docs.glance.Pet.foodPreferences.set : [Text]
                                             -> Pet
                                             -> Pet
  441. docs.glance.Pet.glance.Pet : Nat -> Text -> [Text] -> Pet
  442. docs.glance.Pet.species : Pet -> Text
  443. docs.glance.Pet.species.modify : (Text ->{g} Text)
                                        -> Pet
                                        ->{g} Pet
  444. docs.glance.Pet.species.set : Text -> Pet -> Pet
  445. docs.glance.queueExample : '{IO, Exception} ()
  446. docs.glance.readFile : '{IO, Exception} ()
  447. docs.glance.runIncrement : '{IO, Exception} ()
  448. docs.glance.transfer : Int
                              -> TVar Int
                              -> TVar Int
                              ->{STM} ()
  449. structural type docs.glance.Tree a
  450. docs.glance.Tree.Empty : glance.Tree a
  451. docs.glance.Tree.Node : a
                               -> glance.Tree a
                               -> glance.Tree a
                               -> glance.Tree a
  452. docs.glossary.abilityDeclaration : Doc
  453. docs.glossary.abilityRequirement : Doc
  454. docs.glossary.absolutePath : Doc
  455. docs.glossary.arity : Doc
  456. docs.glossary.associativity : Doc
  457. docs.glossary.branch : Doc
  458. docs.glossary.callStack : Doc
  459. docs.glossary.continuation : Doc
  460. docs.glossary.contributorBranch : Doc
  461. docs.glossary.controlFlow : Doc
  462. docs.glossary.curried : Doc
  463. docs.glossary.dataConstructor : Doc
  464. docs.glossary.declarative : Doc
  465. docs.glossary.deterministic : Doc
  466. docs.glossary.eager : Doc
  467. docs.glossary.expression : Doc
  468. docs.glossary.functionApplication : Doc
  469. docs.glossary.fusion : Doc
  470. docs.glossary.gitUrls : Doc
  471. docs.glossary.higherOrderFunction : Doc
  472. docs.glossary.imperative : Doc
  473. docs.glossary.lambda : Doc
  474. docs.glossary.lexicalScope : Doc
  475. docs.glossary.literal : Doc
  476. docs.glossary.operators : Doc
  477. docs.glossary.predicate : Doc
  478. docs.glossary.project : Doc
  479. docs.glossary.referentialTransparency : Doc
  480. docs.glossary.remoteMapping : Doc
  481. docs.glossary.requestConstructors : Doc
  482. docs.glossary.tailCallPosition : Doc
  483. docs.glossary.thunk : Doc
  484. docs.glossary.ucm : Doc
  485. docs.glossary.useClause : Doc
  486. docs.glossary.watchExpression : Doc
  487. docs.glossary._namespace : Doc
  488. docs.greet : Text -> Text
  489. docs.howCanUnisonHelp : Doc
  490. docs.index : Doc
  491. docs.installInstructions : Doc
  492. docs.labs.wordle.docs.breakdown : Doc
  493. docs.labs.wordle.docs.challenges : Doc
  494. docs.labs.wordle.docs.codebaseSetup : Doc
  495. docs.labs.wordle.docs.colorizeResult : Doc
  496. docs.labs.wordle.docs.coreLogic : Doc
  497. docs.labs.wordle.docs.gameLoop : Doc
  498. docs.labs.wordle.docs.gameLoop.fileTest : '{IO,
                                                 Exception} ()
  499. docs.labs.wordle.docs.hard : Doc
  500. docs.labs.wordle.docs.intro : Doc
  501. docs.labs.wordle.docs.validation : Doc
  502. docs.labs.wordle.solutions.basic.countLetters : [Char]
                                                       -> Map
                                                         Char
                                                         Nat
  503. docs.labs.wordle.solutions.basic.gameLoop : Nat
                                                   -> basic.Target
                                                   -> [[basic.Result]]
                                                   ->{IO,
                                                   Exception,
                                                   Ask
                                                     (Set Text)} ()
  504. docs.labs.wordle.solutions.basic.getUserInput : '{IO,
                                                       Exception,
                                                       Ask
                                                         (Set
                                                           Text)} basic.Guess
  505. type docs.labs.wordle.solutions.basic.Guess
  506. docs.labs.wordle.solutions.basic.Guess.fromText : Text
                                                         -> basic.Guess
  507. docs.labs.wordle.solutions.basic.Guess.Guess : [( Char,
                                                        Nat)]
                                                      -> basic.Guess
  508. docs.labs.wordle.solutions.basic.Guess.score : basic.Guess
                                                      -> basic.Target
                                                      -> [basic.Result]
  509. docs.labs.wordle.solutions.basic.inLocation : (Char, Nat)
                                                     -> basic.Target
                                                     -> Boolean
  510. docs.labs.wordle.solutions.basic.isVictory : [basic.Result]
                                                    -> Boolean
  511. docs.labs.wordle.solutions.basic.loadDict : FilePath
                                                   -> '{IO,
                                                   Exception} Set
                                                     Text
  512. docs.labs.wordle.solutions.basic.loadDictBuiltin : '{IO,
                                                          Exception} Optional
                                                            (Set
                                                              Text)
  513. docs.labs.wordle.solutions.basic.loadDictBuiltin.doc : Doc
  514. docs.labs.wordle.solutions.basic.main : '{IO, Exception} ()
  515. docs.labs.wordle.solutions.basic.overrideLookup : Text
                                                         -> '{IO,
                                                         Exception} Boolean
  516. docs.labs.wordle.solutions.basic.readFile : FilePath
                                                   -> '{IO,
                                                   Exception} Text
  517. docs.labs.wordle.solutions.basic.renderChar : basic.Result
                                                     -> Text
  518. docs.labs.wordle.solutions.basic.renderGuesses : [[basic.Result]]
                                                        -> Text
  519. docs.labs.wordle.solutions.basic.renderRow : [basic.Result]
                                                    -> Text
  520. docs.labs.wordle.solutions.basic.renderTest : '{IO,
                                                     Exception} ()
  521. type docs.labs.wordle.solutions.basic.Result
  522. docs.labs.wordle.solutions.basic.Result.Exists : Char
                                                        -> basic.Result
  523. docs.labs.wordle.solutions.basic.Result.InPlace : Char
                                                         -> basic.Result
  524. docs.labs.wordle.solutions.basic.Result.NotFound : Char
                                                          -> basic.Result
  525. type docs.labs.wordle.solutions.basic.Target
  526. docs.labs.wordle.solutions.basic.Target.fromText : Text
                                                          -> basic.Target
  527. docs.labs.wordle.solutions.basic.Target.Target : Map
                                                          Char
                                                          Nat
                                                        -> Set
                                                          ( Char,
                                                            Nat)
                                                        -> basic.Target
  528. docs.labs.wordle.solutions.basic.Text.normalize : Text
                                                         -> Text
  529. docs.labs.wordle.solutions.basic.tmp.writeDictFile : '{IO,
                                                            Exception} ()
  530. docs.labs.wordle.solutions.basic.tmp.writeFile : FilePath
                                                        -> Text
                                                        ->{IO,
                                                        Exception} ()
  531. docs.labs.wordle.solutions.basic.yesNo : '{IO, Exception} Boolean
  532. docs.labs.wordle.solutions.stubs.characterResult : ( Char,
                                                            Nat)
                                                          -> stubs.Target
                                                          -> stubs.Result
  533. docs.labs.wordle.solutions.stubs.gameLoop : Nat
                                                   -> stubs.Target
                                                   -> [[stubs.Result]]
                                                   ->{IO,
                                                   Exception,
                                                   Ask
                                                     (Set Text)} ()
  534. docs.labs.wordle.solutions.stubs.getUserInput : '{IO,
                                                       Exception,
                                                       Ask
                                                         (Set
                                                           Text)} stubs.Guess
  535. type docs.labs.wordle.solutions.stubs.Guess
  536. docs.labs.wordle.solutions.stubs.Guess.doc : Doc
  537. docs.labs.wordle.solutions.stubs.Guess.fromText : Text
                                                         -> stubs.Guess
  538. docs.labs.wordle.solutions.stubs.Guess.Guess : TODO
                                                      -> stubs.Guess
  539. docs.labs.wordle.solutions.stubs.Guess.score : stubs.Guess
                                                      -> stubs.Target
                                                      -> [stubs.Result]
  540. docs.labs.wordle.solutions.stubs.guesser : Set Text
                                                  -> stubs.Guess
  541. docs.labs.wordle.solutions.stubs.inLocation : (Char, Nat)
                                                     -> stubs.Target
                                                     -> Boolean
  542. docs.labs.wordle.solutions.stubs.isVictory : [stubs.Result]
                                                    -> Boolean
  543. docs.labs.wordle.solutions.stubs.loadDict : FilePath
                                                   -> '{IO,
                                                   Exception} Set
                                                     Text
  544. docs.labs.wordle.solutions.stubs.loadDictBuiltin : '{IO,
                                                          Exception} Optional
                                                            (Set
                                                              Text)
  545. docs.labs.wordle.solutions.stubs.main : '{IO, Exception} ()
  546. docs.labs.wordle.solutions.stubs.overrideLookup : Text
                                                         -> '{IO,
                                                         Exception} Boolean
  547. docs.labs.wordle.solutions.stubs.readFile : FilePath
                                                   -> '{IO,
                                                   Exception} Text
  548. docs.labs.wordle.solutions.stubs.refine : Set Text
                                                 -> stubs.Guess
                                                 -> stubs.Target
                                                 -> Set Text
  549. docs.labs.wordle.solutions.stubs.renderChar : stubs.Result
                                                     -> Text
  550. docs.labs.wordle.solutions.stubs.renderGuesses : [[stubs.Result]]
                                                        -> Text
  551. docs.labs.wordle.solutions.stubs.renderRow : [stubs.Result]
                                                    -> Text
  552. docs.labs.wordle.solutions.stubs.renderTest : '{IO,
                                                     Exception} ()
  553. type docs.labs.wordle.solutions.stubs.Result
  554. docs.labs.wordle.solutions.stubs.Result.doc : Doc
  555. docs.labs.wordle.solutions.stubs.Result.Exists : TODO
                                                        -> stubs.Result
  556. docs.labs.wordle.solutions.stubs.Result.InPlace : TODO
                                                         -> stubs.Result
  557. docs.labs.wordle.solutions.stubs.Result.NotFound : TODO
                                                          -> stubs.Result
  558. docs.labs.wordle.solutions.stubs.solve : Set Text
                                                -> stubs.Target
                                                -> [stubs.Guess]
  559. type docs.labs.wordle.solutions.stubs.Target
  560. docs.labs.wordle.solutions.stubs.Target.doc : Doc
  561. docs.labs.wordle.solutions.stubs.Target.fromText : Text
                                                          -> stubs.Target
  562. docs.labs.wordle.solutions.stubs.Target.Target : TODO
                                                        -> stubs.Target
  563. type docs.labs.wordle.solutions.stubs.TODO
  564. docs.labs.wordle.solutions.stubs.TODO.TODO : TODO
  565. docs.labs.wordle.solutions.stubs.yesNo : '{IO, Exception} Boolean
  566. type docs.labs.wordle.utils.Callout
  567. docs.labs.wordle.utils.Callout.body : Callout -> Doc
  568. docs.labs.wordle.utils.Callout.body.modify : (Doc
                                                    ->{g} Doc)
                                                    -> Callout
                                                    ->{g} Callout
  569. docs.labs.wordle.utils.Callout.body.set : Doc
                                                 -> Callout
                                                 -> Callout
  570. docs.labs.wordle.utils.Callout.Callout : Doc
                                                -> Doc
                                                -> Doc
                                                -> Callout
  571. docs.labs.wordle.utils.Callout.emoji : Callout -> Doc
  572. docs.labs.wordle.utils.Callout.emoji.modify : (Doc
                                                     ->{g} Doc)
                                                     -> Callout
                                                     ->{g} Callout
  573. docs.labs.wordle.utils.Callout.emoji.set : Doc
                                                  -> Callout
                                                  -> Callout
  574. docs.labs.wordle.utils.Callout.title : Callout -> Doc
  575. docs.labs.wordle.utils.Callout.title.modify : (Doc
                                                     ->{g} Doc)
                                                     -> Callout
                                                     ->{g} Callout
  576. docs.labs.wordle.utils.Callout.title.set : Doc
                                                  -> Callout
                                                  -> Callout
  577. docs.labs.wordle.utils.emojis.answer : Doc
  578. docs.labs.wordle.utils.emojis.getStarted : Doc
  579. docs.labs.wordle.utils.emojis.hint : Doc
  580. docs.labs.wordle.utils.emojis.learnMore : Doc
  581. docs.labs.wordle.utils.emojis.next : Doc
  582. docs.labs.wordle.utils.emojis.video : Doc
  583. docs.labs.wordle.utils.foldedCallout : Callout -> Doc
  584. docs.labs.wordle.utils.TODO : Doc
  585. docs.languageReference.abilitiesAndAbilityHandlers : Doc
  586. docs.languageReference.abilitiesInFunctionTypes : Doc
  587. docs.languageReference.abilityDeclaration : Doc
  588. docs.languageReference.abilityHandlers : Doc
  589. docs.languageReference.abilityInference : Doc
  590. docs.languageReference.abilityPatterns : Doc
  591. docs.languageReference.absolutelyQualifiedIdentifiers : Doc
  592. docs.languageReference.asPatterns : Doc
  593. docs.languageReference.basicLexicalForms : Doc
  594. docs.languageReference.blankPatterns : Doc
  595. docs.languageReference.blocks.syntacticalPrecedence : Doc
  596. docs.languageReference.blocksAndStatements : Doc
  597. docs.languageReference.booleanConjunctionDisjunction : Doc
  598. docs.languageReference.booleanExpressions : Doc
  599. docs.languageReference.builtInTypeConstructors : Doc
  600. docs.languageReference.builtInTypes : Doc
  601. docs.languageReference.comments : Doc
  602. docs.languageReference.conditionalExpressions : Doc
  603. docs.languageReference.constructorPatterns : Doc
  604. docs.languageReference.delayedComputations : Doc
  605. docs.languageReference.delayedComputations.program : '{IO,
                                                            Exception} ()
  606. docs.languageReference.delayedComputations.syntacticPrecedence : Doc
  607. docs.languageReference.delayedComputations.syntacticPrecedence.x : Nat
  608. docs.languageReference.destructuringBinds : Doc
  609. docs.languageReference.destructuringBinds.addBox : Box
                                                            Nat
                                                          -> Box
                                                            Nat
                                                          -> Nat
  610. docs.languageReference.destructuringBinds.addTwo : ( Nat,
                                                            Nat)
                                                          -> Nat
  611. type docs.languageReference.destructuringBinds.Box a
  612. docs.languageReference.destructuringBinds.Box.Box : a
                                                           -> Box
                                                             a
  613. docs.languageReference.documentationLiterals : Doc
  614. docs.languageReference.escapeSequences : Doc
  615. docs.languageReference.expressions : Doc
  616. docs.languageReference.functionApplication : Doc
  617. docs.languageReference.functionTypes : Doc
  618. docs.languageReference.guardPatterns : Doc
  619. docs.languageReference.hashes : Doc
  620. docs.languageReference.hashQualifiedIdentifiers : Doc
  621. docs.languageReference.identifiers : Doc
  622. docs.languageReference.kindsOfTypes : Doc
  623. docs.languageReference.lexicalSyntaxOfBlocks : Doc
  624. docs.languageReference.listPatterns : Doc
  625. docs.languageReference.literalHashReferences : Doc
  626. docs.languageReference.literalPatterns : Doc
  627. docs.languageReference.literals : Doc
  628. docs.languageReference.matchExpression : Nat
  629. docs.languageReference.matchExpressionsAndPatternMatching : Doc
  630. docs.languageReference.nameResolutionAndTheEnvironment : Doc
  631. docs.languageReference.namespaceDeclaration : Doc
  632. docs.languageReference.namespaceQualifiedIdentifiers : Doc
  633. docs.languageReference.operatorDefinitions : Doc
  634. docs.languageReference.parenthesizedExpressions : Doc
  635. docs.languageReference.patternMatchingOnAbilityConstructors : Doc
  636. docs.languageReference.polymorphicTypes : Doc
  637. docs.languageReference.recordType : Doc
  638. structural type docs.languageReference.recordType.examples.Point1
  639. docs.languageReference.recordType.examples.Point1.Point2 : Nat
                                                                  -> Nat
                                                                  -> Point1
  640. type docs.languageReference.recordType.examples.Point2
  641. docs.languageReference.recordType.examples.Point2.languageReference.recordTypes.examples.Point : Nat
                                                                                                        -> Nat
                                                                                                        -> Point2
  642. docs.languageReference.recordType.examples.Point2.x : Point2
                                                             -> Nat
  643. docs.languageReference.recordType.examples.Point2.x.modify : (Nat
                                                                    ->{g} Nat)
                                                                    -> Point2
                                                                    ->{g} Point2
  644. docs.languageReference.recordType.examples.Point2.x.set : Nat
                                                                 -> Point2
                                                                 -> Point2
  645. docs.languageReference.recordType.examples.Point2.y : Point2
                                                             -> Nat
  646. docs.languageReference.recordType.examples.Point2.y.modify : (Nat
                                                                    ->{g} Nat)
                                                                    -> Point2
                                                                    ->{g} Point2
  647. docs.languageReference.recordType.examples.Point2.y.set : Nat
                                                                 -> Point2
                                                                 -> Point2
  648. docs.languageReference.reservedWords : Doc
  649. docs.languageReference.scopedTypeVariables : Doc
  650. docs.languageReference.shortHashes : Doc
  651. docs.languageReference.structuralTypes : Doc
  652. docs.languageReference.syntacticPrecedenceOperatorsPrefixFunctionApplication : Doc
  653. docs.languageReference.termDeclarations : Doc
  654. docs.languageReference.termDefinition : Doc
  655. docs.languageReference.termDefinition.sumUpTo : Nat
                                                       -> Nat
  656. docs.languageReference.theTypecheckingRuleForAbilities : Doc
  657. docs.languageReference.topLevelDeclaration : Doc
  658. docs.languageReference.tuplePatterns : Doc
  659. docs.languageReference.tupleTypes : Doc
  660. docs.languageReference.typeAnnotations : Doc
  661. docs.languageReference.typeApplication : Doc
  662. docs.languageReference.typeConstructors : Doc
  663. docs.languageReference.types : Doc
  664. docs.languageReference.typeSignatures : Doc
  665. docs.languageReference.typeVariables : Doc
  666. docs.languageReference.uniqueTypes : Doc
  667. type docs.languageReference.uniqueTypes.Direction
  668. docs.languageReference.uniqueTypes.Direction.East : uniqueTypes.Direction
  669. docs.languageReference.uniqueTypes.Direction.North : uniqueTypes.Direction
  670. docs.languageReference.uniqueTypes.Direction.South : uniqueTypes.Direction
  671. docs.languageReference.uniqueTypes.Direction.West : uniqueTypes.Direction
  672. type docs.languageReference.uniqueTypes.Suit
  673. docs.languageReference.uniqueTypes.Suit.Clubs : Suit
  674. docs.languageReference.uniqueTypes.Suit.Diamonds : Suit
  675. docs.languageReference.uniqueTypes.Suit.Hearts : Suit
  676. docs.languageReference.uniqueTypes.Suit.Spades : Suit
  677. docs.languageReference.unit : Doc
  678. docs.languageReference.useClauses : Doc
  679. docs.languageReference.userDefinedAbilities : Doc
  680. docs.languageReference.userDefinedDataTypes : Doc
  681. type docs.languageReference.userDefinedDataTypes.UserId
  682. docs.languageReference.userDefinedDataTypes.UserId.Email : Text
                                                                  -> UserId
  683. docs.languageReference.userDefinedDataTypes.UserId.Phone : Nat
                                                                  -> UserId
  684. docs.languageReference.userDefinedTypes : Doc
  685. docs.languageReference.variablePatterns : Doc
  686. docs.languageReference._sidebar : Doc
  687. docs.languageReference._suffixedBasedNameResolution : Doc
  688. docs.languageReference._typeDirectedNameResolution : Doc
  689. docs.projects : Doc
  690. docs.quickstart : Doc
  691. docs.quickstart._nav : Doc
  692. docs.theBigIdea : Doc
  693. docs.theBigIdea._nav : Doc
  694. docs.todo.TODO : Doc
  695. docs.tooling.authorLicense : Doc
  696. docs.tooling.codebaseOrganization : Doc
  697. docs.tooling.localCodebaseUI : Doc
  698. docs.tooling.localCodebaseUI._nav : Doc
  699. docs.tooling.projectFAQs : Doc
  700. docs.tooling.projectsCodebaseOrganization : Doc
  701. docs.tooling.projectsCodebaseOrganization._nav : Doc
  702. docs.tooling.projectsLibraryMigration : Doc
  703. docs.tooling.projectSyntax : Doc
  704. docs.tooling.projectWorkflows : Doc
  705. docs.tooling.projectWorkflows.cloneBranch : Doc
  706. docs.tooling.projectWorkflows.cloneLib : Doc
  707. docs.tooling.projectWorkflows.createBranches : Doc
  708. docs.tooling.projectWorkflows.createFromLibrary : Doc
  709. docs.tooling.projectWorkflows.createNewProject : Doc
  710. docs.tooling.projectWorkflows.createProjectFromNamespace : Doc
  711. docs.tooling.projectWorkflows.creatingPrs : Doc
  712. docs.tooling.projectWorkflows.delete : Doc
  713. docs.tooling.projectWorkflows.deletingRemoteBranches : Doc
  714. docs.tooling.projectWorkflows.installDependency : Doc
  715. docs.tooling.projectWorkflows.libraryReleases : Doc
  716. docs.tooling.projectWorkflows.listProjects : Doc
  717. docs.tooling.projectWorkflows.merge : Doc
  718. docs.tooling.projectWorkflows.pull : Doc
  719. docs.tooling.projectWorkflows.push : Doc
  720. docs.tooling.projectWorkflows.renameProject : Doc
  721. docs.tooling.projectWorkflows.reviewingPrs : Doc
  722. docs.tooling.projectWorkflows.switchProjectsBranches : Doc
  723. docs.tooling.projectWorkflows.viewBranches : Doc
  724. docs.tooling.transcripts : Doc
  725. docs.tooling.unisonShare : Doc
  726. docs.tooling.unisonShare._nav : Doc
  727. docs.tour : Doc
  728. docs.tour.bigTechnicalIdea._hashCollisionNote : Doc
  729. docs.tour.square : Nat -> Nat
  730. docs.tour._bigTechnicalIdea : Doc
  731. docs.tour._nav : Doc
  732. docs.tour._scratchFiles : Doc
  733. docs.ucmCommands.add : Doc
  734. docs.ucmCommands.add._cmd : Doc
  735. docs.ucmCommands.addPreview : Doc
  736. docs.ucmCommands.addRun : Doc
  737. docs.ucmCommands.aliaz.many : Doc
  738. docs.ucmCommands.aliaz.term : Doc
  739. docs.ucmCommands.aliaz.term._cmd : Doc
  740. docs.ucmCommands.aliaz.typez : Doc
  741. docs.ucmCommands.api : Doc
  742. docs.ucmCommands.auth.login : Doc
  743. docs.ucmCommands.back : Doc
  744. docs.ucmCommands.branch : Doc
  745. docs.ucmCommands.branchEmpty : Doc
  746. docs.ucmCommands.branches : Doc
  747. docs.ucmCommands.builtins.merge : Doc
  748. docs.ucmCommands.cd : Doc
  749. docs.ucmCommands.cd._cmd : Doc
  750. docs.ucmCommands.clear : Doc
  751. docs.ucmCommands.clone : Doc
  752. docs.ucmCommands.codebaseCreate : Doc
  753. docs.ucmCommands.codebaseCreate._cmd : Doc
  754. docs.ucmCommands.compile : Doc
  755. docs.ucmCommands.create.author : Doc
  756. docs.ucmCommands.create.author._cmd : Doc
  757. docs.ucmCommands.debug.clearCache : Doc
  758. docs.ucmCommands.debugDocToMarkdown : Doc
  759. docs.ucmCommands.del : Doc
  760. docs.ucmCommands.del.namespc : Doc
  761. docs.ucmCommands.del.namespc.force : Doc
  762. docs.ucmCommands.del.patch : Doc
  763. docs.ucmCommands.delBranch : Doc
  764. docs.ucmCommands.dependencies : Doc
  765. docs.ucmCommands.dependents : Doc
  766. docs.ucmCommands.display : Doc
  767. docs.ucmCommands.display.to : Doc
  768. docs.ucmCommands.docs : Doc
  769. docs.ucmCommands.docs._cmd : Doc
  770. docs.ucmCommands.edit : Doc
  771. docs.ucmCommands.editNamespace : Doc
  772. docs.ucmCommands.editNew : Doc
  773. docs.ucmCommands.find : Doc
  774. docs.ucmCommands.find.all : Doc
  775. docs.ucmCommands.find.verbose : Doc
  776. docs.ucmCommands.find._cmd : Doc
  777. docs.ucmCommands.findIn : Doc
  778. docs.ucmCommands.fork : Doc
  779. docs.ucmCommands.gist : Doc
  780. docs.ucmCommands.global.reflog : Doc
  781. docs.ucmCommands.help : Doc
  782. docs.ucmCommands.helpTopics : Doc
  783. docs.ucmCommands.history : Doc
  784. docs.ucmCommands.index : Doc
  785. docs.ucmCommands.ioTest : Doc
  786. docs.ucmCommands.ioTestAll : Doc
  787. docs.ucmCommands.learn._cmd : Doc
  788. docs.ucmCommands.libInstall : Doc
  789. docs.ucmCommands.load : Doc
  790. docs.ucmCommands.ls : Doc
  791. docs.ucmCommands.ls._cmd : Doc
  792. docs.ucmCommands.merge : Doc
  793. docs.ucmCommands.mergeCommit : Doc
  794. docs.ucmCommands.move : Doc
  795. docs.ucmCommands.move.namespace_ : Doc
  796. docs.ucmCommands.move.term : Doc
  797. docs.ucmCommands.move.term._cmd : Doc
  798. docs.ucmCommands.move.typez : Doc
  799. docs.ucmCommands.move.typez._cmd : Doc
  800. docs.ucmCommands.project.reflog : Doc
  801. docs.ucmCommands.projectCreate : Doc
  802. docs.ucmCommands.projectRename : Doc
  803. docs.ucmCommands.projects : Doc
  804. docs.ucmCommands.pull : Doc
  805. docs.ucmCommands.pull._cmd : Doc
  806. docs.ucmCommands.pullWithoutHistory : Doc
  807. docs.ucmCommands.push : Doc
  808. docs.ucmCommands.push._cmd : Doc
  809. docs.ucmCommands.quit : Doc
  810. docs.ucmCommands.reflog : Doc
  811. docs.ucmCommands.reflog._cmd : Doc
  812. docs.ucmCommands.reset : Doc
  813. docs.ucmCommands.resetRoot : Doc
  814. docs.ucmCommands.resetRoot._cmd : Doc
  815. docs.ucmCommands.run : Doc
  816. docs.ucmCommands.run.compiled : Doc
  817. docs.ucmCommands.runNative : Doc
  818. docs.ucmCommands.switch : Doc
  819. docs.ucmCommands.test : Doc
  820. docs.ucmCommands.testAll : Doc
  821. docs.ucmCommands.textFind : Doc
  822. docs.ucmCommands.textFindAll : Doc
  823. docs.ucmCommands.todoUCM : Doc
  824. docs.ucmCommands.toHtml : Doc
  825. docs.ucmCommands.ui : Doc
  826. docs.ucmCommands.undo : Doc
  827. docs.ucmCommands.undo._cmd : Doc
  828. docs.ucmCommands.unsafeForcePush : Doc
  829. docs.ucmCommands.update : Doc
  830. docs.ucmCommands.upgrade : Doc
  831. docs.ucmCommands.upgradeCommit : Doc
  832. docs.ucmCommands.version : Doc
  833. docs.ucmCommands.view : Doc
  834. docs.ucmCommands.view._cmd : Doc
  835. docs.ucmCommands._make : Doc -> Doc -> Doc -> Doc
  836. docs.ucmCommands._sidebar : Doc
  837. docs.usageTopics.bibliography : Doc
  838. docs.usageTopics.docker : Doc
  839. docs.usageTopics.documentation : Doc
  840. docs.usageTopics.documentation._mermaid1 : Doc
  841. docs.usageTopics.editorSetup : Doc
  842. docs.usageTopics.generalFaqs : Doc
  843. docs.usageTopics.resettingCodebaseState : Doc
  844. docs.usageTopics.runningPrograms : Doc
  845. docs.usageTopics.runningPrograms.myMain : '{IO,
                                                 Exception} ()
  846. docs.usageTopics.testing : Doc
  847. docs.usageTopics.workflowHowTos.resolveConflictsProjects : Doc
  848. docs.usageTopics.workflowHowTos.resolveConflictsUpdateOld : Doc
  849. docs.usageTopics.workflowHowTos.updateCode : Doc
  850. docs.usageTopics.workflowHowTos.updateDependency : Doc
  851. docs.usageTopics.workflowHowTos.updateDependencyLibInstall : Doc
  852. docs.usageTopics.workflowHowTos.updateDependencyNamespaces : Doc
  853. docs.usageTopics.workflowHowTos.updateProjectDependency : Doc
  854. docs.utils.emojis.answer : Doc
  855. docs.utils.emojis.exercise : Doc
  856. docs.utils.emojis.headsUp : Doc
  857. docs.utils.emojis.hint : Doc
  858. docs.utils.emojis.important : Doc
  859. docs.utils.emojis.index : Doc
  860. docs.utils.emojis.learnMore : Doc
  861. docs.utils.emojis.placeholder : Doc
  862. docs.utils.emojis.reminder : Doc
  863. docs.utils.emojis.style : Doc
  864. docs.utils.emojis.suggested : Doc
  865. docs.utils.navStyleTag : Text
  866. docs.utils.navStyleTag.doc : Doc
  867. docs.whatProblemsDoesUnisonSolve : Doc
  868. docs._sidebar : Doc
  869. metadata.authors.bbarker : metadata.Author
  870. metadata.authors.bbarker.guid : GUID
  871. metadata.authors.h22roscoe : metadata.Author
  872. metadata.authors.h22roscoe.guid : GUID
  873. metadata.copyrightHolders.bbarker : CopyrightHolder
  874. metadata.copyrightHolders.h22roscoe : CopyrightHolder
  875. pages.community.codeOfConduct : Doc
  876. pages.community.evaluatingIncidents : Doc
  877. pages.community.index : Doc
  878. pages.home.examples.distributedEx : Seq k Nat
                                           ->{Remote} Nat
  879. pages.home.examples.helloWorld : '{IO, Exception} ()
  880. pages.home.examples.httpEx : '{IO, Exception} HttpResponse
  881. pages.home._examples : Doc
  882. pages.jobs.index : Doc
  883. pages.talks.index : Doc
  884. pages.unisonComputing.index : Doc
  885. README : Doc
  886. square.tests.ex1 : [test.Result]
```

## Code examples

``` ucm
@unison/website/main> edit 1-14000

  ☝️

  I added 784 definitions to the top of scratch.u

  You can edit them there, then run `update` to replace the
  definitions currently in this namespace.
```
