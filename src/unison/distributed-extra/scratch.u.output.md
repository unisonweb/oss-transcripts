# Distributed-extra

This library is a playground for expressing distributed data types via the Remote ability.

## Library contents list

``` ucm
@unison/distributed-extra/main> pull.without-history @unison/distributed-extra/releases/0.1.0

  Downloaded 18049 entities.

  ✅

  Successfully updated @unison/distributed-extra/main from
  @unison/distributed-extra/releases/0.1.0.

@unison/distributed-extra/main> find

  1.   type attributes.Defer
  2.   type attributes.Memo
  3.   structural type Binary d a
  4.   Binary.One : a -> Binary d a
  5.   Binary.root : Binary d a -> a
  6.   Binary.toView : (∀ x. d x -> distributed_6_0_0.Value x)
                       -> Binary d a
                       -> Binary distributed_6_0_0.Value a
  7.   Binary.Two : a
                    -> d (Binary d a)
                    -> d (Binary d a)
                    -> Binary d a
  8.   structural type Buffer d a
  9.   Buffer.arity : Buffer d a -> Nat
  10.  Buffer.at! : Nat -> Buffer d a ->{Abort, Storage d} a
  11.  Buffer.Buffer : Nat
                       -> Nat
                       -> [a]
                       -> d (Buffer d (d [a]))
                       -> [a]
                       -> Buffer d a
  12.  Buffer.cons : a -> Buffer d a ->{Storage d} Buffer d a
  13.  Buffer.empty : Nat -> Buffer d a
  14.  Buffer.Empty : Nat -> Buffer d a
  15.  Buffer.findSorted : (a ->{g, Abort, Storage d} Ordering)
                           -> Buffer d a
                           ->{g, Storage d} Optional a
  16.  Buffer.findSorted.tests : [Result]
  17.  Buffer.findSorted! : (a ->{g, Abort, Storage d} Ordering)
                            -> Buffer d a
                            ->{g, Abort, Storage d} a
  18.  Buffer.first : Buffer d a ->{Storage d} Optional a
  19.  Buffer.foldLeft : (b -> a ->{g, Storage d} b)
                         -> b
                         -> Buffer d a
                         ->{g, Storage d} b
  20.  Buffer.foldRight : (a -> b ->{g, Storage d} b)
                          -> b
                          -> Buffer d a
                          ->{g, Storage d} b
  21.  Buffer.fromList : Nat -> [a] ->{Storage d} Buffer d a
  22.  Buffer.last : Buffer d a ->{Storage d} Optional a
  23.  Buffer.map : (a -> b)
                    -> Buffer distributed_6_0_0.Value a
                    -> Buffer distributed_6_0_0.Value b
  24.  Buffer.memoFold : Location {Scratch, g}
                         -> (a ->{Remote, Scratch} b)
                         -> b
                         -> (b -> b ->{Remote, Scratch} b)
                         -> Buffer distributed_6_0_0.Value a
                         ->{Remote} b
  25.  Buffer.memoFoldSequential : Location {Scratch, g}
                                   -> b
                                   -> (b
                                   -> a
                                   ->{Remote, Scratch} b)
                                   -> Buffer
                                     distributed_6_0_0.Value a
                                   ->{Remote} b
  26.  Buffer.size : Buffer d a -> Nat
  27.  Buffer.snoc : a -> Buffer d a ->{Storage d} Buffer d a
  28.  Buffer.snocs : [a] -> Buffer d a ->{Storage d} Buffer d a
  29.  Buffer.tests.test1 : [Result]
  30.  Buffer.toList : Buffer d a ->{Storage d} [a]
  31.  Buffer.toList.doc : Doc
  32.  Buffer.toList.tests : [Result]
  33.  Buffer.toView : (∀ x. d x -> distributed_6_0_0.Value x)
                       -> Buffer d a
                       -> Buffer distributed_6_0_0.Value a
  34.  Buffer.uncons : Buffer d a
                       ->{Storage d} Optional (a, Buffer d a)
  35.  Buffer.uncons.doc : Doc
  36.  Buffer.unsnoc : Buffer d a
                       ->{Storage d} Optional (Buffer d a, a)
  37.  Buffer.unsnoc.doc : Doc
  38.  type Chain d a
  39.  Chain.<= : Chain d a -> Chain d a ->{Storage d} Boolean
  40.  Chain.at : Nat -> Chain d a ->{Storage d} Optional a
  41.  Chain.at! : Nat -> Chain d a ->{Abort, Storage d} a
  42.  Chain.atHash! : Nat
                       -> Chain d a
                       ->{Abort, Storage d} (a, Hash, Hash)
  43.  Chain.cons : a -> Chain d a ->{Storage d} Chain d a
  44.  Chain.Cons : Nat
                    -> Binary d (a, Hash, Hash)
                    -> Chain d a
                    -> Chain d a
  45.  Chain.cons' : (∀ x. x -> Hash)
                     -> (a, Hash)
                     -> Chain d a
                     ->{Storage d} Chain d a
  46.  Chain.consMany : [a] -> Chain d a ->{Storage d} Chain d a
  47.  Chain.defaultHash : a -> Hash
  48.  Chain.drop : Nat -> Chain d a ->{Storage d} Chain d a
  49.  Chain.drop1 : Chain d a ->{Storage d} Chain d a
  50.  Chain.empty : Chain d a
  51.  Chain.Empty : Chain d a
  52.  Chain.equal : Chain d1 a1 -> Chain d a -> Boolean
  53.  Chain.foldSequential : b
                              -> (a -> b ->{Remote} b)
                              -> Chain distributed_6_0_0.Value a
                              ->{Remote} b
  54.  Chain.fromList : [a] ->{Storage d} Chain d a
  55.  Chain.hash : Chain d a -> Hash
  56.  Chain.hash.parent : Chain d a -> Hash
  57.  Chain.head : Chain d a -> Optional a
  58.  Chain.head! : Chain d a ->{Abort} a
  59.  Chain.head' : Chain d a -> Optional (a, Hash, Hash)
  60.  Chain.join : Chain d a
                    -> Chain d a
                    ->{Storage d} Chain d a
  61.  Chain.join.doc.implementationNotes : Doc
  62.  Chain.joins : [Chain d a] ->{Storage d} Chain d a
  63.  Chain.lca : Chain d a
                   -> Chain d a
                   ->{Storage d} Chain d a
  64.  Chain.lteq : Chain d a -> Chain d a ->{Storage d} Boolean
  65.  Chain.map : (i -> o)
                   -> Chain distributed_6_0_0.Value i
                   -> Chain distributed_6_0_0.Value o
  66.  Chain.memoFold : Location {Scratch, g}
                        -> (a ->{Remote, Scratch} b)
                        -> b
                        -> (b -> b ->{Remote, Scratch} b)
                        -> Chain distributed_6_0_0.Value a
                        ->{Remote} b
  67.  Chain.memoFoldSequential : Location {Scratch, g}
                                  -> b
                                  -> (b
                                  -> a
                                  ->{Remote, Scratch} b)
                                  -> Chain
                                    distributed_6_0_0.Value a
                                  ->{Remote} b
  68.  Chain.one : a ->{Storage d} Chain d a
  69.  Chain.size : Chain d a -> Nat
  70.  Chain.takeEnd : Nat -> Chain d a ->{Storage d} Chain d a
  71.  Chain.takeList : Nat
                        -> Chain d a
                        ->{Storage d} [(a, Hash, Hash)]
  72.  Chain.toList : Chain d a ->{Storage d} [a]
  73.  Chain.toSeq : Nat
                     -> Chain distributed_6_0_0.Value a
                     -> Seq k a
  74.  Chain.toView : (∀ x. d x -> distributed_6_0_0.Value x)
                      -> Chain d a
                      -> Chain distributed_6_0_0.Value a
  75.  Chain.trees : Chain d a
                     -> [(Nat, Binary d (a, Hash, Hash))]
  76.  Chain.uncons : Chain d a
                      ->{Storage d} Optional (a, Chain d a)
  77.  type Clock
  78.  Clock.Clock : Set Bytes -> Set Bytes -> Clock
  79.  Clock.head : Clock -> Set Bytes
  80.  Clock.head.modify : (Set Bytes ->{g} Set Bytes)
                           -> Clock
                           ->{g} Clock
  81.  Clock.head.normalized : Clock -> Set Bytes
  82.  Clock.head.set : Set Bytes -> Clock -> Clock
  83.  Clock.history : Clock -> Set Bytes
  84.  Clock.history.modify : (Set Bytes ->{g} Set Bytes)
                              -> Clock
                              ->{g} Clock
  85.  Clock.history.set : Set Bytes -> Clock -> Clock
  86.  Clock.join : Clock -> Clock -> Clock
  87.  Clock.lteq : Clock -> Clock -> Boolean
  88.  Clock.tick : a -> Clock -> Clock
  89.  Clock.tick' : ((a, Set Bytes) ->{g1} Bytes)
                     -> a
                     -> Clock
                     ->{g1} Clock
  90.  type Dataset d a
  91.  Dataset.contains : a -> Dataset d a ->{Storage d} Boolean
  92.  Dataset.D : Hash
                   -> Nat
                   -> a
                   -> a
                   -> d (Dataset d a)
                   -> Dataset d a
  93.  Dataset.empty : Dataset d a
  94.  Dataset.Empty : Dataset d a
  95.  Dataset.findBy : (a ->{g} Ordering)
                        -> Dataset d a
                        ->{g, Storage d} Optional a
  96.  Dataset.fromList : [a] ->{Storage d} Dataset d a
  97.  Dataset.halve : Dataset d a
                       ->{Storage d} (Dataset d a, Dataset d a)
  98.  Dataset.hash : Dataset d a -> Hash
  99.  Dataset.impl.minmaxBy : (a ->{g} a ->{g1} Ordering)
                               -> Dataset d a
                               -> Dataset d a
                               ->{g, g1, Abort} ( a,
                                 Dataset d a,
                                 a,
                                 a,
                                 Dataset d a,
                                 a)
  100. Dataset.impl.saveIfDeep : Dataset d a
                                 ->{Storage d} Dataset d a
  101. Dataset.insert : a
                        -> Dataset d a
                        ->{Storage d} Dataset d a
  102. Dataset.insertBy : (a -> a ->{g} Ordering)
                          -> a
                          -> Dataset d a
                          ->{g, Storage d} Dataset d a
  103. Dataset.isEmpty : Dataset d a -> Boolean
  104. Dataset.Leaf : a -> Dataset d a
  105. Dataset.range : Dataset d a ->{Abort} (a, a)
  106. Dataset.save : Dataset d a ->{Storage d} Dataset d a
  107. Dataset.size : Dataset d a -> Nat
  108. Dataset.tests.consistencyWithSet : [Result]
  109. Dataset.toList : Dataset d a ->{Storage d} [a]
  110. Dataset.union : Dataset d a
                       -> Dataset d a
                       ->{Storage d} Dataset d a
  111. Dataset.Union : Nat
                       -> Nat
                       -> a
                       -> a
                       -> Dataset d a
                       -> Dataset d a
                       -> Dataset d a
  112. Dataset.unionBy : (a -> a ->{g} Ordering)
                         -> Dataset d a
                         -> Dataset d a
                         ->{g, Storage d} Dataset d a
  113. Dataset.unsavedDepth : Dataset d a -> Nat
  114. type DVar a
  115. DVar.clear : DVar a -> DVar a
  116. DVar.DVar : Nat -> TrimClock -> Set a -> DVar a
  117. DVar.empty : DVar a
  118. DVar.gc : Nat -> DVar a -> DVar a
  119. DVar.join : DVar a -> DVar a -> DVar a
  120. DVar.lastNonce : DVar a -> Nat
  121. DVar.lastNonce.modify : (Nat ->{g} Nat)
                               -> DVar a
                               ->{g} DVar a
  122. DVar.lastNonce.set : Nat -> DVar a -> DVar a
  123. DVar.meet : DVar a -> DVar a -> DVar a
  124. DVar.new : a -> DVar a
  125. DVar.set : a -> DVar a -> DVar a
  126. DVar.time : DVar a -> TrimClock
  127. DVar.time.modify : (TrimClock ->{g} TrimClock)
                          -> DVar a
                          ->{g} DVar a
  128. DVar.time.set : TrimClock -> DVar a -> DVar a
  129. DVar.values : DVar a -> Set a
  130. DVar.values.modify : (Set a1 ->{g} Set a)
                            -> DVar a1
                            ->{g} DVar a
  131. DVar.values.set : Set a -> DVar a1 -> DVar a
  132. type Ebt a
  133. Ebt.debug.depth : Ebt a ->{Scratch} Nat
  134. Ebt.doc : Doc
  135. Ebt.empty : Ebt a
  136. Ebt.Empty : Ebt a
  137. Ebt.empty.doc : Doc
  138. Ebt.insert : Hashed a -> a -> Ebt a ->{Scratch} Ebt a
  139. Ebt.insert.doc : Doc
  140. Ebt.insert! : Hashed a
                     -> a
                     -> Ebt a
                     ->{Abort, Scratch} Ebt a
  141. Ebt.lookup : Hashed a -> Ebt a ->{Scratch} Optional a
  142. Ebt.lookup.doc : Doc
  143. Ebt.lookup! : Hashed a -> Ebt a ->{Abort, Scratch} a
  144. Ebt.One : Hashed a -> a -> Ebt a
  145. Ebt.replaceIf : (a -> a ->{g, Abort} Boolean)
                       -> Hashed a
                       -> a
                       -> Ebt a
                       ->{g, Scratch} Ebt a
  146. Ebt.replaceIf.doc : Doc
  147. Ebt.replaceIf! : (a -> a ->{g, Abort} Boolean)
                        -> Hashed a
                        -> a
                        -> Ebt a
                        ->{g, Abort, Scratch} Ebt a
  148. Ebt.Split : Optional a -> [Hashed (Ebt a)] -> Ebt a
  149. Ebt.tests.ex1 : [Result]
  150. ability Fold e
  151. Fold.doc : Doc
  152. Fold.docs.example : '{Remote,
                           Storage distributed_6_0_0.Value} r
                           -> Either Failure r
  153. Fold.fold : (e ->{Remote, Scratch} r)
                   -> r
                   -> (r -> r ->{Remote, Scratch} r)
                   ->{Fold e} distributed_6_0_0.Value r
  154. Fold.foldSequential : r
                             -> (r -> e ->{Remote, Scratch} r)
                             ->{Fold e} distributed_6_0_0.Value
                               r
  155. Fold.fork : '{Remote, Scratch, Fold e} r
                   ->{Fold e} distributed_6_0_0.Value r
  156. Fold.journal.run : Journal distributed_6_0_0.Value e
                          -> '{Remote, Fold e} r
                          ->{Remote} r
  157. Fold.list.run : [e] -> '{Remote, Fold e} r ->{Remote} r
  158. type Fold.View a b
  159. Fold.view : '{Fold e} View e e
  160. Fold.View.doc : Doc
  161. Fold.View.filter : (b ->{Remote} Boolean)
                          -> View a b
                          -> View a b
  162. Fold.View.filterMap : (b ->{Remote} Optional c)
                             -> View a b
                             -> View a c
  163. Fold.View.map : (b ->{Remote} c) -> View a b -> View a c
  164. Fold.View.run : View a b -> '{Fold b} r ->{Fold a} r
  165. Fold.View.View : (∀ r. '{Fold b} r ->{Fold a} r)
                        -> View a b
  166. Fold.zoom : (e0 ->{Remote, Scratch} Optional e)
                   -> '{Fold e} r
                   -> '{Fold e0} r
  167. Fold.zoom! : (e0 ->{Abort, Remote, Scratch} e)
                    -> '{Fold e} r
                    -> '{Fold e0} r
  168. structural type Index k m a
  169. Index.empty : m -> Index k m a
  170. Index.Index : distributed_6_0_0.Value
                       (m, Two Mode a (Index k m a))
                     -> Index k m a
  171. Index.map : (a ->{Exception, Remote} b)
                   -> Index k m a
                   -> Index Defer m b
  172. Index.memo : Location {Scratch, g}
                    -> Index k m a
                    -> Index Memo m a
  173. Index.metric : Index Memo m a ->{Remote} m
  174. Index.one : m -> a -> Index k m a
  175. Index.search : (m ->{Remote} Boolean)
                      -> Index Memo m a
                      -> Seq Memo a
  176. Index.toSeq : Index k m a -> Seq k a
  177. Index.two : Mode
                   -> m
                   -> Index k m a
                   -> Index k m a
                   -> Index k m a
  178. Index.unwrap : Index k m a
                      -> distributed_6_0_0.Value
                        (m, Two Mode a (Index k m a))
  179. Index.unwrap! : Index k m a
                       ->{Remote} (m, Two Mode a (Index k m a))
  180. type Journal d a
  181. Journal.add : a -> Journal d a ->{Storage d} Journal d a
  182. Journal.add.doc : Doc
  183. Journal.adds : [a]
                      -> Journal d a
                      ->{Storage d} Journal d a
  184. Journal.adds.doc : Doc
  185. Journal.buffer : Journal d a -> Buffer d a
  186. Journal.buffer.modify : (Buffer d a ->{g} Buffer d a)
                               -> Journal d a
                               ->{g} Journal d a
  187. Journal.buffer.set : Buffer d a
                            -> Journal d a
                            -> Journal d a
  188. Journal.commit : Journal d a ->{Storage d} Journal d a
  189. Journal.commit.doc : Doc
  190. Journal.commitEvery : Nat
                             -> Journal d a
                             ->{Storage d} Journal d a
  191. Journal.commitEvery.doc : Doc
  192. Journal.committed : Journal d a
                           -> d (Chain d (Buffer d a))
  193. Journal.committed.modify : (d (Chain d (Buffer d a))
                                  ->{g} d (Chain d (Buffer d a)))
                                  -> Journal d a
                                  ->{g} Journal d a
  194. Journal.committed.set : d (Chain d (Buffer d a))
                               -> Journal d a
                               -> Journal d a
  195. Journal.doc : Doc
  196. Journal.empty : Nat ->{Storage d} Journal d a
  197. Journal.empty.doc : Doc
  198. Journal.equal : Journal d a
                       -> Journal d a
                       ->{Storage d} Boolean
  199. Journal.fromList : [a] ->{Storage d} Journal d a
  200. Journal.join : Journal d a
                      -> Journal d a
                      ->{Storage d} Journal d a
  201. Journal.join.doc : Doc
  202. Journal.joinChain : Journal d a
                           -> Chain d (Buffer d a)
                           ->{Storage d} Journal d a
  203. Journal.Journal : Buffer d a
                         -> d (Chain d (Buffer d a))
                         -> Journal d a
  204. Journal.lteq : Journal d a
                      -> Journal d a
                      ->{Storage d} Boolean
  205. Journal.memoFold : Location {Scratch, g}
                          -> (a ->{Remote, Scratch} b)
                          -> b
                          -> (b -> b ->{Remote, Scratch} b)
                          -> Journal distributed_6_0_0.Value a
                          ->{Remote} b
  206. Journal.memoFoldSequential : Location {Scratch, g}
                                    -> b
                                    -> (b
                                    -> a
                                    ->{Remote, Scratch} b)
                                    -> Journal
                                      distributed_6_0_0.Value a
                                    ->{Remote} b
  207. Journal.toList : Journal distributed_6_0_0.Value a
                        ->{Remote} [a]
  208. Journal.toList.doc : Doc
  209. Journal.toView : (∀ x. d x -> distributed_6_0_0.Value x)
                        -> Journal d a
                        -> Journal distributed_6_0_0.Value a
  210. type LwwMap k v
  211. LwwMap.delete : k -> v -> LwwMap k v -> LwwMap k v
  212. LwwMap.deleteWin.join : LwwMap k v
                               -> LwwMap k v
                               -> LwwMap k v
  213. LwwMap.empty : LwwMap k v
  214. LwwMap.insert : k -> v -> LwwMap k v -> LwwMap k v
  215. LwwMap.insertWin.join : LwwMap k v
                               -> LwwMap k v
                               -> LwwMap k v
  216. LwwMap.LwwMap : Map k (DVar v) -> LwwMap k v
  217. LwwMap.toList : LwwMap k v -> [(k, v)]
  218. type Mode
  219. Mode.append : Mode -> Mode -> Mode
  220. Mode.Parallel : Mode
  221. Mode.Sequential : Mode
  222. type Op g s
  223. Op.Op : s -> (s ->{g} s) -> Op g s
  224. Op.push : Op g s -> Op g1 s ->{g} Op {h, g} s
  225. type Range k
  226. Range.Empty : Range k
  227. Range.merge : Range k -> Range k -> Range k
  228. Range.Range : k -> k -> Range k
  229. Range.within : k -> Range k -> Boolean
  230. type Rbt a
  231. Rbt.adjust : Bytes
                    -> (Nat -> Optional a ->{g} Rbt a)
                    -> Rbt a
                    ->{g} Rbt a
  232. Rbt.adjust.doc : Doc
  233. Rbt.doc : Doc
  234. Rbt.empty : Rbt a
  235. Rbt.Empty : Rbt a
  236. Rbt.empty.doc : Doc
  237. Rbt.impl.emptyChildren : [Rbt a]
  238. Rbt.impl.errorMsg : Text
  239. Rbt.impl.seedFromPair : Bytes -> Bytes -> Nat
  240. Rbt.impl.split : Nat
                        -> Bytes
                        -> Rbt a
                        -> Bytes
                        -> Rbt a
                        -> Rbt a
  241. Rbt.insert : (a ->{g} Optional Bytes)
                    -> Bytes
                    -> a
                    -> Rbt a
                    ->{g} Rbt a
  242. Rbt.insert.doc : Doc
  243. Rbt.insertAtDepth : Nat
                           -> Bytes
                           -> a
                           -> Rbt a
                           ->{Random} Rbt a
  244. Rbt.insertAtDepth.doc : Doc
  245. Rbt.lookup : Bytes -> Rbt a -> Optional a
  246. Rbt.lookup.doc : Doc
  247. Rbt.one : a -> Rbt a
  248. Rbt.One : a -> Rbt a
  249. Rbt.one.doc : Doc
  250. Rbt.setDelete : Bytes -> Rbt Bytes -> Rbt Bytes
  251. Rbt.setDelete.doc : Doc
  252. Rbt.setDelete! : Bytes -> Rbt Bytes ->{Abort} Rbt Bytes
  253. Rbt.setDelete!.doc : Doc
  254. Rbt.setInsert : Bytes -> Rbt Bytes -> Rbt Bytes
  255. Rbt.setInsert.doc : Doc
  256. Rbt.Split : Nat -> Rbt a -> [Rbt a] -> Rbt a
  257. Rbt.toList : Rbt a -> [a]
  258. Rbt.toList.doc : Doc
  259. Rbt.toStream : Rbt a ->{Stream a} ()
  260. Rbt.toStream.doc : Doc
  261. README : Doc
  262. ReleaseNotes : Doc
  263. type Rope d a
  264. Rope.arity : Rope d a -> Nat
  265. Rope.arity.doc : Doc
  266. type Rope.Chunk a
  267. Rope.Chunk.Chunk : (a -> a -> Boolean)
                          -> (Nat -> a -> a)
                          -> (Nat -> a -> a)
                          -> (a -> Nat)
                          -> Chunk a
  268. Rope.Chunk.drop : Chunk a -> Nat -> a -> a
  269. Rope.Chunk.drop.modify : ((Nat -> a -> a)
                                ->{g} Nat
                                -> a
                                -> a)
                                -> Chunk a
                                ->{g} Chunk a
  270. Rope.Chunk.drop.set : (Nat -> a -> a)
                             -> Chunk a
                             -> Chunk a
  271. Rope.Chunk.flatMap : Chunk a
                            -> (a ->{g} [b])
                            -> a
                            ->{g} [b]
  272. Rope.Chunk.isEmpty : Chunk a -> a -> Boolean
  273. Rope.Chunk.map : Chunk a -> (a ->{g} b) -> a ->{g} [b]
  274. Rope.Chunk.select : Chunk a
                           -> a
                           -> [a]
                           -> Optional (List.Nonempty a)
  275. Rope.Chunk.size : Chunk a -> a -> Nat
  276. Rope.Chunk.size.modify : ((a -> Nat) ->{g} a -> Nat)
                                -> Chunk a
                                ->{g} Chunk a
  277. Rope.Chunk.size.set : (a -> Nat) -> Chunk a -> Chunk a
  278. Rope.Chunk.startsWith : Chunk a -> a -> a -> Boolean
  279. Rope.Chunk.startsWith.modify : ((a -> a -> Boolean)
                                      ->{g} a
                                      -> a
                                      -> Boolean)
                                      -> Chunk a
                                      ->{g} Chunk a
  280. Rope.Chunk.startsWith.set : (a -> a -> Boolean)
                                   -> Chunk a
                                   -> Chunk a
  281. Rope.Chunk.stripCommonPrefix : Chunk a
                                      -> List.Nonempty a
                                      -> (Nat, List.Nonempty a)
  282. Rope.Chunk.suffixes : Chunk a -> a -> [a]
  283. Rope.Chunk.take : Chunk a -> Nat -> a -> a
  284. Rope.Chunk.take.modify : ((Nat -> a -> a)
                                ->{g} Nat
                                -> a
                                -> a)
                                -> Chunk a
                                ->{g} Chunk a
  285. Rope.Chunk.take.set : (Nat -> a -> a)
                             -> Chunk a
                             -> Chunk a
  286. Rope.Chunk.Text : Chunk Text
  287. Rope.Chunk.uncons : Chunk a -> a -> Optional (a, a)
  288. Rope.cons : a -> Rope d a ->{Storage d} Rope d a
  289. Rope.cons.doc : Doc
  290. Rope.doc : Doc
  291. Rope.drop : Nat -> Rope d a ->{Storage d} Rope d a
  292. Rope.drop.doc : Doc
  293. Rope.empty : Nat -> Chunk a -> Rope d a
  294. Rope.empty.doc : Doc
  295. Rope.emptyText : Rope d Text
  296. Rope.emptyText.arity : Nat -> Rope d Text
  297. Rope.emptyText.arity.doc : Doc
  298. Rope.emptyText.doc : Doc
  299. Rope.fromText : Nat -> Text ->{Storage d} Rope d Text
  300. Rope.fromText.doc : Doc
  301. Rope.Rope : Chunk a -> Nat -> Buffer d a -> Rope d a
  302. Rope.size : Rope d a ->{Storage d} Nat
  303. Rope.size.doc : Doc
  304. Rope.snoc : a -> Rope d a ->{Storage d} Rope d a
  305. Rope.snoc.doc : Doc
  306. Rope.startsWith : Rope d a
                         -> Rope d a
                         ->{Storage d} Boolean
  307. Rope.startsWith.doc : Doc
  308. Rope.take : Nat -> Rope d a ->{Storage d} Rope d a
  309. Rope.take.doc : Doc
  310. Rope.tests.associativity : [Result]
  311. Rope.tests.construction : [Result]
  312. Rope.toText : Rope d Text ->{Storage d} Text
  313. Rope.toText.doc : Doc
  314. Rope.underlying : Rope d a -> Buffer d a
  315. Rope.underlying.doc : Doc
  316. type Semispace g m k v
  317. Semispace.active : Semispace g m k v -> m
  318. Semispace.active.doc : Doc
  319. Semispace.active.modify : (m ->{h1} m)
                                 -> Semispace g m k v
                                 ->{h1} Semispace g m k v
  320. Semispace.doc : Doc
  321. Semispace.empty : Semispace g m k v -> m
  322. Semispace.empty.doc : Doc
  323. Semispace.expiring : Semispace g m k v -> m
  324. Semispace.expiring.doc : Doc
  325. Semispace.fromMap : Map k v -> Semispace {} (Map k v) k v
  326. Semispace.fromMap.doc : Doc
  327. Semispace.fromRbt : Nat
                           -> Rbt v
                           -> Semispace {Random} (Rbt v) Bytes v
  328. Semispace.fromRbt.doc : Doc
  329. Semispace.gc : Semispace g m k v -> Semispace g m k v
  330. Semispace.gc.doc : Doc
  331. Semispace.insert : k
                          -> v
                          -> Semispace g m k v
                          ->{g} Semispace g m k v
  332. Semispace.insert.doc : Doc
  333. Semispace.insert.soft : k
                               -> v
                               -> Semispace g m k v
                               ->{g} Semispace g m k v
  334. Semispace.insert.soft.doc : Doc
  335. Semispace.lookup : k
                          -> Semispace g m k v
                          ->{g} Optional
                            (v, Optional (Semispace g m k v))
  336. Semispace.lookup.doc : Doc
  337. Semispace.Semispace : (k -> m ->{g} Optional v)
                             -> (k -> v -> m ->{g} m)
                             -> m
                             -> m
                             -> m
                             -> Semispace g m k v
  338. Semispace.tests.fromMap : [Result]
  339. Semispace.tests.fromRbt : [Result]
  340. Semispace.touch.all : [k]
                             -> Semispace g m k v
                             ->{g} Semispace g m k v
  341. type SemispaceCache a
  342. SemispaceCache.doc : Doc
  343. SemispaceCache.gc : SemispaceCache a ->{IO} ()
  344. SemispaceCache.gc.doc : Doc
  345. SemispaceCache.gcIfSizeExceeds : Nat
                                        -> SemispaceCache a
                                        ->{IO, Exception} ()
  346. SemispaceCache.gcIfSizeExceeds.doc : Doc
  347. SemispaceCache.gcIfSizeExceeds.stm : Nat
                                            -> SemispaceCache a
                                            ->{STM} ()
  348. SemispaceCache.insert : Bytes
                               -> a
                               -> SemispaceCache a
                               ->{IO, Exception} ()
  349. SemispaceCache.insert.doc : Doc
  350. SemispaceCache.lookup : Bytes
                               -> SemispaceCache a
                               ->{IO, Exception} Optional a
  351. SemispaceCache.lookup.doc : Doc
  352. SemispaceCache.new : '{IO, Exception} SemispaceCache a
  353. SemispaceCache.new.doc : Doc
  354. SemispaceCache.new.stm : '{STM} SemispaceCache a
  355. SemispaceCache.SemispaceCache : TVar Nat
                                       -> TVar (TMap a)
                                       -> TVar (TMap a)
                                       -> SemispaceCache a
  356. SemispaceCache.size : SemispaceCache a
                             ->{IO, Exception} Nat
  357. SemispaceCache.size.doc : Doc
  358. SemispaceCache.size.stm : SemispaceCache a ->{STM} Nat
  359. SemispaceCache.tests.ex1 : '{IO, Exception} [Result]
  360. structural type Seq k a
  361. Seq.accumulate : Location {g, Scratch}
                        -> (i -> t)
                        -> t
                        -> (t -> t -> t)
                        -> Seq k i
                        -> Index Memo t i
  362. Seq.accumulate' : Location {Scratch, g}
                         -> (a ->{Exception, Remote} m)
                         -> m
                         -> (Index Memo m a
                         -> Index Memo m a
                         ->{Exception, Remote} Index Memo m a)
                         -> Seq k a
                         -> Index Memo m a
  363. Seq.append : Mode -> Seq k a -> Seq k a -> Seq k a
  364. Seq.chunkedRange : Nat -> Nat -> Nat -> Seq Defer Nat
  365. Seq.chunkedRange.doc : Doc
  366. Seq.chunkedRangeAt : Location g
                            -> Nat
                            -> Nat
                            -> Nat
                            -> Seq Defer Nat
  367. Seq.chunkedRangeAt.doc : Doc
  368. Seq.distribute : Location g -> Seq k a -> Seq Defer a
  369. Seq.distribute.doc : Doc
  370. Seq.doc : Doc
  371. Seq.doc.snippets.totallyLazy : Doc
  372. Seq.empty : Seq k a
  373. Seq.filter : (a ->{Exception, Remote} Boolean)
                    -> Seq k a
                    -> Seq Defer a
  374. Seq.filter.doc : Doc
  375. Seq.flatMap : (a ->{Exception, Remote} Seq Defer b)
                     -> Seq k a
                     -> Seq Defer b
  376. Seq.fromChunkedList : Nat -> [a] -> Seq k a
  377. Seq.fromList : Mode -> [a] -> Seq k a
  378. Seq.fromList.doc : Doc
  379. Seq.fromListAt : Location g -> Nat -> [a] -> Seq k a
  380. Seq.fromListAt.doc : Doc
  381. Seq.isEmpty : Seq Memo a ->{Remote} Boolean
  382. Seq.map : (a ->{Exception, Remote} b)
                 -> Seq k a
                 -> Seq Defer b
  383. Seq.map.doc : Doc
  384. Seq.mapRandom : Nat
                       -> (a ->{Random} b)
                       -> Seq k a
                       -> Seq Defer b
  385. Seq.memo : Location {Scratch, g} -> Seq k a -> Seq memo a
  386. Seq.memo.cast : Seq k a -> Seq memo a
  387. Seq.memoReduce : Location {Scratch, g}
                        -> m
                        -> (m -> m ->{Remote} m)
                        -> Seq k m
                        ->{Remote} m
  388. Seq.memoTop : Location {g, Scratch} -> Seq k a -> Seq k a
  389. Seq.one : a -> Seq k a
  390. Seq.pack : Location {g, Scratch}
                  -> Nat
                  -> Seq k1 a
                  ->{Remote} Seq k a
  391. Seq.packAt : Location {g, Scratch}
                    -> Nat
                    -> Seq Memo x
                    -> Seq k1 a
                    ->{Remote} Seq k a
  392. Seq.range : Nat -> Nat -> Seq Defer Nat
  393. Seq.range.doc : Doc
  394. Seq.rangeAt : Location g
                     -> Nat
                     -> Nat
                     -> Nat
                     -> Seq k Nat
  395. Seq.rangeAt.doc : Doc
  396. Seq.reduce : m
                    -> (m -> m ->{Remote} m)
                    -> Seq k m
                    ->{Remote} m
  397. Seq.reduce.doc : Doc
  398. Seq.reduceBalanced : z
                            -> (z -> z -> z)
                            -> Seq k z
                            ->{Remote} z
  399. Seq.reduceSizeBalanced : (Nat, m)
                                -> ((Nat, m)
                                ->{Remote} (Nat, m)
                                ->{Remote} (Nat, m))
                                -> Seq k (Nat, m)
                                ->{Remote} (Nat, m)
  400. Seq.sample : Nat -> Nat -> Seq Memo a ->{Remote} [a]
  401. Seq.sample1 : Seq Memo a ->{Remote, Random} Optional a
  402. Seq.send : Location {Scratch, g}
                  -> Seq Memo x
                  -> Seq k1 a
                  -> Seq k a
  403. Seq.Seq : distributed_6_0_0.Value (Two Mode a (Seq k a))
                 -> Seq k a
  404. Seq.skewUnfold : s
                        -> (s
                        -> distributed_6_0_0.Value
                          ([a], Optional (s, s)))
                        -> Seq Defer a
  405. Seq.skewUnfoldAt : Location g
                          -> s
                          -> (s
                          ->{g, Remote} ([a], Optional (s, s)))
                          -> Seq Defer a
  406. Seq.sort : Location {Scratch, g}
                  -> Nat
                  -> (a -> a ->{Remote} Ordering)
                  -> Seq Memo a
                  ->{Remote} Seq k a
  407. Seq.toList : Seq k a ->{Remote} [a]
  408. Seq.toRAM : Seq k a ->{Remote} Seq k2 a
  409. Seq.unfold : s
                    -> (s
                    -> distributed_6_0_0.Value (Two Mode a s))
                    -> Seq Defer a
  410. Seq.unfold.doc : Doc
  411. Seq.unfold' : s
                     -> (s
                     -> distributed_6_0_0.Value (Two Mode a s))
                     -> Seq Defer a
  412. Seq.unfold'.doc : Doc
  413. Seq.unwrap : Seq k a
                    -> distributed_6_0_0.Value
                      (Two Mode a (Seq k a))
  414. Seq.unwrap! : Seq k a ->{Remote} Two Mode a (Seq k a)
  415. Seq.zipRandomNat : Nat -> Seq k a -> Seq Defer (a, Nat)
  416. type Stamp
  417. Stamp.doc : Doc
  418. type Stamp.Event
  419. Stamp.Event.Branch : Nat -> Event -> Event -> Event
  420. Stamp.Event.decrement : Event -> Nat -> Event
  421. Stamp.Event.increment : Event -> Nat -> Event
  422. Stamp.Event.maxEv : Event -> Nat
  423. Stamp.Event.minEv : Event -> Nat
  424. Stamp.Event.modify : Event -> (Nat ->{g} Nat) ->{g} Event
  425. Stamp.Event.normEv : Event -> Event
  426. Stamp.Event.StampEvent : Nat -> Event
  427. Stamp.fork : Stamp -> (Stamp, Stamp)
  428. Stamp.forks : Nat -> Stamp -> [Stamp]
  429. type Stamp.Id
  430. Stamp.Id.Branch : Stamp.Id -> Stamp.Id -> Stamp.Id
  431. Stamp.Id.no : Stamp.Id
  432. Stamp.Id.split : Stamp.Id -> (Stamp.Id, Stamp.Id)
  433. Stamp.Id.StampId : Boolean -> Stamp.Id
  434. Stamp.Id.yes : Stamp.Id
  435. Stamp.join : Stamp -> Stamp -> Stamp
  436. Stamp.lteq : Stamp -> Stamp -> Boolean
  437. Stamp.Stamp : Stamp.Id -> Event -> Stamp
  438. Stamp.tests : [Result]
  439. Stamp.tick : Stamp -> Stamp
  440. Stamp.zero : Stamp
  441. ability Storage d
  442. type Storage.RAM a
  443. Storage.ram : '{g, Storage RAM} a ->{g} a
  444. Storage.ram.handler : Request {Storage RAM} a -> a
  445. Storage.RAM.RAM : a -> RAM a
  446. Storage.ram.value : '{g, Storage distributed_6_0_0.Value} a
                           ->{g, Remote} a
  447. Storage.ram.value.doc : Doc
  448. Storage.restore : d a ->{Storage d} a
  449. Storage.save : a ->{Storage d} d a
  450. Storage.saveWith : (∀ x.
                            x
                            ->{Remote} distributed_6_0_0.Value x)
                          -> '{h,
                          Storage distributed_6_0_0.Value} a
                          ->{h, Remote} a
  451. Storage.saveWith.doc : Doc
  452. Storage.scratch : '{g, Scratch} r
                         -> '{g, Storage Hashed} r
                         ->{g, Scratch} r
  453. Storage.scratch.doc : Doc
  454. Storage.scratchAt : '{Remote} Location {Scratch, g}
                           -> '{h,
                           Storage distributed_6_0_0.Value} a
                           ->{h, Remote} a
  455. Storage.scratchAt.doc : Doc
  456. type StorageProvider
  457. StorageProvider.doc : Doc
  458. StorageProvider.forget : StorageProvider
                                -> k a
                                ->{Remote} distributed_6_0_0.Value
                                  ()
  459. StorageProvider.forgetHash : StorageProvider
                                    -> Hashed a
                                    ->{Remote} distributed_6_0_0.Value
                                      ()
  460. StorageProvider.hashKey : StorageProvider
                                 -> k a
                                 -> Hashed a
  461. StorageProvider.lookup : StorageProvider
                                -> k a
                                ->{Remote} distributed_6_0_0.Value
                                  (Optional a)
  462. StorageProvider.lookupHash : StorageProvider
                                    -> Hashed a
                                    ->{Remote} distributed_6_0_0.Value
                                      (Optional a)
  463. StorageProvider.save : StorageProvider
                              -> a
                              ->{Remote} distributed_6_0_0.Value
                                (Hashed a)
  464. StorageProvider.saveHashed : StorageProvider
                                    -> Hashed a
                                    -> a
                                    ->{Remote} distributed_6_0_0.Value
                                      (Hashed a)
  465. StorageProvider.saveKeyed : StorageProvider
                                   -> k a
                                   -> a
                                   ->{Remote} distributed_6_0_0.Value
                                     (Hashed a)
  466. StorageProvider.scratch : StorageProvider
  467. StorageProvider.scratch.doc : Doc
  468. StorageProvider.scratch' : HashAlgorithm
                                  -> StorageProvider
  469. StorageProvider.StorageProvider : (∀ k a. k a -> Hashed a)
                                         -> (∀ a.
                                           Hashed a
                                           ->{Remote} distributed_6_0_0.Value
                                             (Optional a))
                                         -> (∀ a.
                                           Hashed a
                                           ->{Remote} distributed_6_0_0.Value
                                             ())
                                         -> (∀ a.
                                           Hashed a
                                           -> a
                                           ->{Remote} distributed_6_0_0.Value
                                             (Hashed a))
                                         -> StorageProvider
  470. structural type structures.Id a
  471. structures.Id.Id : a -> structures.Id a
  472. structural type structures.Two m a r
  473. structures.Two.Empty : Two m a r
  474. structures.Two.map : (r1 ->{g} r2)
                            -> Two m a r1
                            ->{g} Two m a r2
  475. structures.Two.map.doc : Doc
  476. structures.Two.One : a -> Two m a r
  477. structures.Two.Two : m -> r -> r -> Two m a r
  478. type TrimClock
  479. TrimClock.<= : TrimClock -> TrimClock -> Boolean
  480. type TrimClock.Expiring
  481. TrimClock.Expiring.Active : Expiring
  482. TrimClock.Expiring.Expiring : Expiring
  483. TrimClock.Expiring.isActive : Expiring -> Boolean
  484. TrimClock.gc : Nat -> TrimClock -> TrimClock
  485. TrimClock.head : TrimClock -> Set Bytes
  486. TrimClock.head.normalized : TrimClock -> Set Bytes
  487. TrimClock.join : TrimClock -> TrimClock -> TrimClock
  488. TrimClock.nonce : TrimClock -> Nat
  489. TrimClock.nonce.modify : (Nat ->{g} Nat)
                                -> TrimClock
                                ->{g} TrimClock
  490. TrimClock.nonce.set : Nat -> TrimClock -> TrimClock
  491. TrimClock.origin : TrimClock
  492. TrimClock.refresh : TrimClock -> TrimClock
  493. TrimClock.seen : TrimClock -> Map Bytes (Nat, Expiring)
  494. TrimClock.seen.modify : (Map Bytes (Nat, Expiring)
                               ->{g} Map Bytes (Nat, Expiring))
                               -> TrimClock
                               ->{g} TrimClock
  495. TrimClock.seen.set : Map Bytes (Nat, Expiring)
                            -> TrimClock
                            -> TrimClock
  496. TrimClock.tick : a -> TrimClock -> TrimClock
  497. TrimClock.tick' : ((a, Set Bytes) ->{g1} Bytes)
                         -> a
                         -> TrimClock
                         ->{g1} TrimClock
  498. TrimClock.tip.modify : (Set Bytes ->{g} Set Bytes)
                              -> TrimClock
                              ->{g} TrimClock
  499. TrimClock.tip.set : Set Bytes -> TrimClock -> TrimClock
  500. TrimClock.TrimClock : Nat
                             -> Set Bytes
                             -> Map Bytes (Nat, Expiring)
                             -> TrimClock
  501. up.crypto.blake2b_256 : a -> Bytes
  502. up.crypto.blake2b_256.doc : Doc
  503. up.List.binarySearch : (a ->{g1} Ordering)
                              -> [a]
                              ->{g1} Either Nat (a, Nat)
  504. up.List.binarySearch.tests : [Result]
  505. up.List.dropEndWhile : (a ->{g} Boolean) -> [a] ->{g} [a]
  506. up.List.foldb : (a ->{e} b)
                       -> (b ->{e} b ->{e} b)
                       -> b
                       -> [a]
                       ->{e} b
  507. up.List.map_ : (a ->{g} b) -> [a] ->{g} ()
  508. up.Random.rng.fromCurrentTime : '{IO} (∀ a g.
                                         '{g, Random} a
                                         ->{g, IO} a)
  509. up.Random.rng.io : '{IO, Random} (∀ a g.
                            '{g, Random} a ->{g, IO} a)
  510. up.Random.rng.mix : RNG -> RNG -> RNG
  511. up.Random.rng.mix.tests.bytes : '{IO} [Result]
  512. up.Random.rng.mix.tests.nat : '{IO} [Result]
  513. up.Random.rng.scope : '{Random, Scope s} (∀ a b.
                               '{g, Random} a ->{g, Scope s} a)
  514. up.Set.normalize : Set a -> Set a
  515. up.Set.normalize.doc : Doc
  516. up.Tuple.compareAt1By : (a ->{g2} a ->{g1} Ordering)
                               -> Tuple a b
                               -> Tuple a b
                               ->{g1, g2} Ordering
  517. up.Tuple.compareAt1By.doc : Doc
  518. type VectorClock k
  519. VectorClock.<= : VectorClock k
                        -> VectorClock k
                        -> Boolean
  520. VectorClock.doc : Doc
  521. VectorClock.empty : VectorClock k
  522. VectorClock.expire : k -> VectorClock k -> VectorClock k
  523. VectorClock.isTickOf : VectorClock k
                              -> VectorClock k
                              -> Optional (VectorClock k)
  524. VectorClock.isTickOf.doc : Doc
  525. VectorClock.join : VectorClock k
                          -> VectorClock k
                          -> VectorClock k
  526. VectorClock.joins : [VectorClock k] -> VectorClock k
  527. VectorClock.joinsBy : (a ->{g} VectorClock k)
                             -> [a]
                             ->{g} VectorClock k
  528. VectorClock.lteq : VectorClock k
                          -> VectorClock k
                          -> Boolean
  529. VectorClock.remove : k -> VectorClock k -> VectorClock k
  530. VectorClock.tick : k -> VectorClock k -> VectorClock k
  531. VectorClock.tickBy : Nat
                            -> k
                            -> VectorClock k
                            -> VectorClock k
  532. VectorClock.tickCountOf : k -> VectorClock k -> Nat
  533. VectorClock.tickHere : VectorClock (Location {})
                              ->{Remote} VectorClock
                                (Location {})
  534. VectorClock.ticks : VectorClock k
                           -> Map k (Nat, Expiring)
  535. VectorClock.ticks.modify : (Map k1 (Nat, Expiring)
                                  ->{g} Map k (Nat, Expiring))
                                  -> VectorClock k1
                                  ->{g} VectorClock k
  536. VectorClock.ticks.set : Map k (Nat, Expiring)
                               -> VectorClock k1
                               -> VectorClock k
  537. VectorClock.unconsCausal : VectorClock k
                                  -> [(a, VectorClock k)]
                                  -> ( VectorClock k,
                                    [(a, VectorClock k)],
                                    [(a, VectorClock k)])
  538. VectorClock.unconsCausal.doc : Doc
  539. VectorClock.VectorClock : Map k (Nat, Expiring)
                                 -> VectorClock k
```
