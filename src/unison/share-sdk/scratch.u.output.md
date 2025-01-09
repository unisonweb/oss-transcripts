# Share-sdk

This is a high-level HTTP server library for Unison. It contains utilities for writing http and websocket endpoints.

## Library contents list

``` ucm
@unison/share-sdk/main> pull.without-history @unison/share-sdk/releases/2.7.0

  Downloaded 26859 entities.

  ✅

  Successfully updated @unison/share-sdk/main from
  @unison/share-sdk/releases/2.7.0.

@unison/share-sdk/main> find

  1.   type BranchRef
  2.   BranchRef.BranchRef : Text -> BranchRef
  3.   BranchRef.ReleaseBranchRef : Text -> BranchRef
  4.   BranchRef.toAPIPath : BranchRef -> Path
  5.   BranchRef.toSharePath : BranchRef -> Path
  6.   type EmbedKatex
  7.   EmbedKatex.asBlock : EmbedKatex -> EmbedKatex
  8.   EmbedKatex.asInline : EmbedKatex -> EmbedKatex
  9.   EmbedKatex.display : EmbedKatex -> KatexDisplay
  10.  EmbedKatex.display.modify : (KatexDisplay
                                   ->{g} KatexDisplay)
                                   -> EmbedKatex
                                   ->{g} EmbedKatex
  11.  EmbedKatex.display.set : KatexDisplay
                                -> EmbedKatex
                                -> EmbedKatex
  12.  EmbedKatex.EmbedKatex : Text
                               -> KatexDisplay
                               -> EmbedKatex
  13.  EmbedKatex.katex : Text -> EmbedKatex
  14.  type EmbedKatex.KatexDisplay
  15.  EmbedKatex.KatexDisplay.Block : KatexDisplay
  16.  EmbedKatex.KatexDisplay.Inline : KatexDisplay
  17.  EmbedKatex.markup : EmbedKatex -> Text
  18.  EmbedKatex.markup.modify : (Text ->{g} Text)
                                  -> EmbedKatex
                                  ->{g} EmbedKatex
  19.  EmbedKatex.markup.set : Text -> EmbedKatex -> EmbedKatex
  20.  EmbedKatex.toHtml : EmbedKatex -> Html
  21.  EmbedKatex.withDisplay : KatexDisplay
                                -> EmbedKatex
                                -> EmbedKatex
  22.  type EmbedMermaid
  23.  EmbedMermaid.diagram : EmbedMermaid -> Text
  24.  EmbedMermaid.diagram.modify : (Text ->{g} Text)
                                     -> EmbedMermaid
                                     ->{g} EmbedMermaid
  25.  EmbedMermaid.diagram.set : Text
                                  -> EmbedMermaid
                                  -> EmbedMermaid
  26.  EmbedMermaid.EmbedMermaid : Text -> Theme -> EmbedMermaid
  27.  EmbedMermaid.mermaid : Text -> EmbedMermaid
  28.  type EmbedMermaid.Theme
  29.  EmbedMermaid.theme : EmbedMermaid -> Theme
  30.  EmbedMermaid.theme.modify : (Theme ->{g} Theme)
                                   -> EmbedMermaid
                                   ->{g} EmbedMermaid
  31.  EmbedMermaid.Theme.Predefined : Text -> Theme
  32.  EmbedMermaid.theme.set : Theme
                                -> EmbedMermaid
                                -> EmbedMermaid
  33.  EmbedMermaid.toHtml : EmbedMermaid -> Html
  34.  EmbedMermaid.withTheme : Text
                                -> EmbedMermaid
                                -> EmbedMermaid
  35.  EmbedMermaid.withTheme_ : Theme
                                 -> EmbedMermaid
                                 -> EmbedMermaid
  36.  type EmbedSvg
  37.  EmbedSvg.markup : EmbedSvg -> Text
  38.  EmbedSvg.markup.modify : (Text ->{g} Text)
                                -> EmbedSvg
                                ->{g} EmbedSvg
  39.  EmbedSvg.markup.set : Text -> EmbedSvg -> EmbedSvg
  40.  EmbedSvg.svg : Text -> EmbedSvg
  41.  EmbedSvg.Svg : Text -> EmbedSvg
  42.  EmbedSvg.toHtml : EmbedSvg -> Html
  43.  type FoldToggle
  44.  FoldToggle.close : FoldToggle -> FoldToggle
  45.  FoldToggle.disabled : FoldToggle
  46.  FoldToggle.foldToggle : FoldToggle
  47.  FoldToggle.FoldToggle : Toggleable
                               -> Position
                               -> FoldToggle
  48.  FoldToggle.isClosed : Boolean -> FoldToggle -> FoldToggle
  49.  FoldToggle.isDisabled : Boolean
                               -> FoldToggle
                               -> FoldToggle
  50.  FoldToggle.isOpen : Boolean -> FoldToggle -> FoldToggle
  51.  FoldToggle.open : FoldToggle -> FoldToggle
  52.  type FoldToggle.Position
  53.  FoldToggle.position : FoldToggle -> Position
  54.  FoldToggle.Position.Closed : Position
  55.  FoldToggle.position.modify : (Position ->{g} Position)
                                    -> FoldToggle
                                    ->{g} FoldToggle
  56.  FoldToggle.Position.Opened : Position
  57.  FoldToggle.position.set : Position
                                 -> FoldToggle
                                 -> FoldToggle
  58.  type FoldToggle.Toggleable
  59.  FoldToggle.toggleable : FoldToggle -> Toggleable
  60.  FoldToggle.Toggleable.Disabled : Toggleable
  61.  FoldToggle.toggleable.modify : (Toggleable
                                      ->{g} Toggleable)
                                      -> FoldToggle
                                      ->{g} FoldToggle
  62.  FoldToggle.toggleable.set : Toggleable
                                   -> FoldToggle
                                   -> FoldToggle
  63.  FoldToggle.Toggleable.Toggleable : Toggleable
  64.  FoldToggle.toHtml : FoldToggle -> Html
  65.  FoldToggle.toHtml.doc : Doc
  66.  FoldToggle.withPosition : Position
                                 -> FoldToggle
                                 -> FoldToggle
  67.  FoldToggle.withToggleable : Toggleable
                                   -> FoldToggle
                                   -> FoldToggle
  68.  type FQN
  69.  FQN.decode : '{Decoder} FQN
  70.  FQN.decodeFromParent : FQN -> '{Decoder} FQN
  71.  FQN.FQN : List.Nonempty Text -> FQN
  72.  FQN.fromList : [Text] -> FQN
  73.  FQN.fromParent : FQN -> Text -> FQN
  74.  FQN.fromText : Text -> FQN
  75.  FQN.fromText.doc : Doc
  76.  FQN.segments : FQN -> List.Nonempty Text
  77.  FQN.toText : FQN -> Text
  78.  FQN.toText.doc : Doc
  79.  type Hash
  80.  Hash.apiPrefix : Text
  81.  Hash.decode : '{Decoder} Hash
  82.  Hash.fromText : Text ->{Exception} Hash
  83.  Hash.fromText_ : Text ->{Exception} Hash
  84.  Hash.Hash : InternalHash -> Hash
  85.  Hash.isAbilityConstructorHash : Hash -> Boolean
  86.  Hash.isAbilityConstructorHash.doc : Doc
  87.  Hash.isAssumedBuiltin : Hash -> Boolean
  88.  Hash.isAssumedBuiltin_ : Text -> Text -> Boolean
  89.  Hash.isAssumedBuiltin_.doc : Doc
  90.  Hash.isDataConstructorHash : Hash -> Boolean
  91.  Hash.isDataConstructorHash.doc : Doc
  92.  Hash.isList : Hash -> Boolean
  93.  Hash.isRawHash : Text -> Boolean
  94.  Hash.isTuple : Hash -> Boolean
  95.  Hash.prefix : Text
  96.  Hash.stripHashPrefix : Text -> Text
  97.  Hash.stripHashPrefix.doc : Doc
  98.  Hash.toApiUrlText : Hash -> Text
  99.  Hash.toShortText : Hash -> Text
  100. Hash.toShortText_ : Text -> Hash -> Text
  101. Hash.toShortText_.doc : Doc
  102. Hash.toText : Hash -> Text
  103. Hash.toText_ : Text
                      -> (Text ->{g} Text)
                      -> Hash
                      ->{g} Text
  104. Hash.toUnescapedApiUrlText : Hash -> Text
  105. Hash.toUnescapedApiUrlText.doc : Doc
  106. Hash.toUnprefixedShortText : Hash -> Text
  107. Hash.toUnprefixedText : Hash -> Text
  108. Hash.toUrlText : Hash -> Text
  109. Hash.tryFromText : Text -> Optional Hash
  110. Hash.tryFromText_ : Text -> Optional Hash
  111. Hash.urlPrefix : Text
  112. type HashQualified
  113. HashQualified.doc : Doc
  114. HashQualified.fromText : Text -> HashQualified
  115. HashQualified.HashOnly : Hash -> HashQualified
  116. HashQualified.HashQualified : FQN
                                     -> Hash
                                     -> HashQualified
  117. HashQualified.isRawHashQualified : Text -> Boolean
  118. HashQualified.NameOnly : FQN -> HashQualified
  119. HashQualified.toSharePath : HashQualified -> Path
  120. HashQualified.toSharePath.doc : Doc
  121. HashQualified.tryFromText_ : (Text ->{g} FQN)
                                    -> Text
                                    -> Text
                                    ->{g} Optional HashQualified
  122. type Icon
  123. Icon.arrowDown : Icon
  124. Icon.arrowEscapeBox : Icon
  125. Icon.arrowLeft : Icon
  126. Icon.arrowLeftUp : Icon
  127. Icon.arrowRight : Icon
  128. Icon.arrowsFromLine : Icon
  129. Icon.arrowsToLine : Icon
  130. Icon.arrowUp : Icon
  131. Icon.caretDown : Icon
  132. Icon.caretLeft : Icon
  133. Icon.caretRight : Icon
  134. Icon.caretUp : Icon
  135. Icon.Icon : Text -> [Attribute] -> [Svg] -> Icon
  136. Icon.toHtml : Icon -> Html
  137. Icon.unisonMark : Icon
  138. Icon.withAttributes : [Attribute] -> Icon -> Icon
  139. Icon.withClass : Text -> Icon -> Icon
  140. Icon.withClassList : [(Text, Boolean)] -> Icon -> Icon
  141. type InternalHash
  142. InternalHash.constructorSuffix : InternalHash
                                        -> Optional Text
  143. InternalHash.constructorSuffix.modify : (Optional Text
                                               ->{g} Optional
                                                 Text)
                                               -> InternalHash
                                               ->{g} InternalHash
  144. InternalHash.constructorSuffix.set : Optional Text
                                            -> InternalHash
                                            -> InternalHash
  145. InternalHash.hash : InternalHash -> Text
  146. InternalHash.hash.modify : (Text ->{g} Text)
                                  -> InternalHash
                                  ->{g} InternalHash
  147. InternalHash.hash.set : Text
                               -> InternalHash
                               -> InternalHash
  148. InternalHash.InternalHash : Text
                                   -> Boolean
                                   -> Optional Text
                                   -> InternalHash
  149. InternalHash.isAssumedBuiltin : InternalHash -> Boolean
  150. InternalHash.isAssumedBuiltin.modify : (Boolean
                                              ->{g} Boolean)
                                              -> InternalHash
                                              ->{g} InternalHash
  151. InternalHash.isAssumedBuiltin.set : Boolean
                                           -> InternalHash
                                           -> InternalHash
  152. type NamespacePath
  153. NamespacePath.NamespacePath : [Text] -> NamespacePath
  154. NamespacePath.toApiText : NamespacePath -> Text
  155. NamespacePath.toAPIText.doc : Doc
  156. NamespacePath.toList : NamespacePath -> [Text]
  157. NamespacePath.toPath : NamespacePath -> Path
  158. type ProjectRef
  159. ProjectRef.doc : Doc
  160. ProjectRef.fromText : Text ->{Exception} ProjectRef
  161. ProjectRef.fromText.doc : Doc
  162. ProjectRef.projectRef : Text
                               -> Text
                               ->{Exception} ProjectRef
  163. ProjectRef.ProjectRef : Text -> Text -> ProjectRef
  164. ProjectRef.projectRef.doc : Doc
  165. type ProjectRef.ProjectSlug
  166. ProjectRef.projectSlug : ProjectRef -> Text
  167. ProjectRef.ProjectSlug.fromText : Text
                                         ->{Exception} ProjectSlug
  168. ProjectRef.ProjectSlug.fromText.doc : Doc
  169. ProjectRef.ProjectSlug.isValidProjectSlug : Text
                                                   -> Boolean
  170. ProjectRef.ProjectSlug.isValidProjectSlug.doc : Doc
  171. ProjectRef.ProjectSlug.isValidProjectSlug.tests.aDashAreValid : [Result]
  172. ProjectRef.ProjectSlug.isValidProjectSlug.tests.anUnderscoreAreValid : [Result]
  173. ProjectRef.ProjectSlug.isValidProjectSlug.tests.codeIsInvalid : [Result]
  174. ProjectRef.ProjectSlug.isValidProjectSlug.tests.dashesAreValid : [Result]
  175. ProjectRef.ProjectSlug.isValidProjectSlug.tests.lettersAreValid : [Result]
  176. ProjectRef.ProjectSlug.isValidProjectSlug.tests.nonAlphanumIsInvalid : [Result]
  177. ProjectRef.ProjectSlug.isValidProjectSlug.tests.numbersAreValid : [Result]
  178. ProjectRef.ProjectSlug.isValidProjectSlug.tests.pIsInvalid : [Result]
  179. ProjectRef.ProjectSlug.isValidProjectSlug.tests.underscoresAreValid : [Result]
  180. ProjectRef.ProjectSlug.ProjectRef.ProjectSlug : Text
                                                       -> ProjectSlug
  181. ProjectRef.ProjectSlug.toText : ProjectSlug -> Text
  182. ProjectRef.ProjectSlug.toText.doc : Doc
  183. ProjectRef.ProjectSlug.tryFromText : Text
                                            -> Optional
                                              ProjectSlug
  184. ProjectRef.ProjectSlug.tryFromText.doc : Doc
  185. ProjectRef.toSharePath : ProjectRef -> Path
  186. ProjectRef.userHandle : ProjectRef -> Text
  187. README : Doc
  188. type Reference
  189. Reference.AbilityConstructorReference : HashQualified
                                               -> Reference
  190. Reference.DataConstructorReference : HashQualified
                                            -> Reference
  191. Reference.fromText : (HashQualified ->{g} Reference)
                            -> Text
                            ->{g} Reference
  192. Reference.TermReference : HashQualified -> Reference
  193. Reference.toShareURI : ProjectRef
                              -> BranchRef
                              -> Reference
                              -> URI
  194. Reference.TypeReference : HashQualified -> Reference
  195. share.apiHost : Text
  196. share.fetchDoc : ProjectRef
                        -> BranchRef
                        -> NamespacePath
                        ->{Exception, Http} [ShareDoc]
  197. share.fetchTerm : ProjectRef
                         -> BranchRef
                         -> NamespacePath
                         ->{Exception, Http} [Term]
  198. share.fetchType : ProjectRef
                         -> BranchRef
                         -> NamespacePath
                         ->{Exception, Http} [Type.Type]
  199. share.shareHost : Text
  200. type ShareDefinitionSlug
  201. ShareDefinitionSlug.fqn : ShareDefinitionSlug -> FQN
  202. ShareDefinitionSlug.fqn.modify : (FQN ->{g} FQN)
                                        -> ShareDefinitionSlug
                                        ->{g} ShareDefinitionSlug
  203. ShareDefinitionSlug.fqn.set : FQN
                                     -> ShareDefinitionSlug
                                     -> ShareDefinitionSlug
  204. ShareDefinitionSlug.projectRef : ShareDefinitionSlug
                                        -> ProjectRef
  205. ShareDefinitionSlug.projectRef.modify : (ProjectRef
                                               ->{g} ProjectRef)
                                               -> ShareDefinitionSlug
                                               ->{g} ShareDefinitionSlug
  206. ShareDefinitionSlug.projectRef.set : ProjectRef
                                            -> ShareDefinitionSlug
                                            -> ShareDefinitionSlug
  207. ShareDefinitionSlug.ShareDefinitionSlug : ProjectRef
                                                 -> FQN
                                                 -> ShareDefinitionSlug
  208. type ShareDoc
  209. ShareDoc.Anchor : Text -> ShareDoc -> ShareDoc
  210. ShareDoc.Aside : ShareDoc -> ShareDoc
  211. ShareDoc.Blankline : ShareDoc
  212. ShareDoc.Blockquote : ShareDoc -> ShareDoc
  213. ShareDoc.Bold : ShareDoc -> ShareDoc
  214. ShareDoc.BulletedList : [ShareDoc] -> ShareDoc
  215. ShareDoc.Callout : Optional ShareDoc
                          -> ShareDoc
                          -> ShareDoc
  216. ShareDoc.Code : ShareDoc -> ShareDoc
  217. ShareDoc.CodeBlock : Text -> ShareDoc -> ShareDoc
  218. ShareDoc.Column : [ShareDoc] -> ShareDoc
  219. ShareDoc.decode : '{Decoder} ShareDoc
  220. type ShareDoc.EmbeddedSource
  221. ShareDoc.EmbeddedSource.ShareDoc.Builtin : Syntax
                                                  -> EmbeddedSource
  222. ShareDoc.EmbeddedSource.ShareDoc.EmbeddedSource : Syntax
                                                         -> Syntax
                                                         -> EmbeddedSource
  223. ShareDoc.Folded : FoldedDoc -> ShareDoc
  224. ShareDoc.Folded.toHtml : [Attribute] -> IsFolded -> Html
  225. type ShareDoc.FoldedDoc
  226. ShareDoc.FoldedDoc.details : FoldedDoc -> ShareDoc
  227. ShareDoc.FoldedDoc.details.modify : (ShareDoc
                                           ->{g} ShareDoc)
                                           -> FoldedDoc
                                           ->{g} FoldedDoc
  228. ShareDoc.FoldedDoc.details.set : ShareDoc
                                        -> FoldedDoc
                                        -> FoldedDoc
  229. ShareDoc.FoldedDoc.FoldedDoc : FoldId
                                      -> Boolean
                                      -> ShareDoc
                                      -> ShareDoc
                                      -> FoldedDoc
  230. ShareDoc.FoldedDoc.foldId : FoldedDoc -> FoldId
  231. ShareDoc.FoldedDoc.foldId.modify : (FoldId ->{g} FoldId)
                                          -> FoldedDoc
                                          ->{g} FoldedDoc
  232. ShareDoc.FoldedDoc.foldId.set : FoldId
                                       -> FoldedDoc
                                       -> FoldedDoc
  233. ShareDoc.FoldedDoc.isFolded : FoldedDoc -> Boolean
  234. ShareDoc.FoldedDoc.isFolded.modify : (Boolean
                                            ->{g} Boolean)
                                            -> FoldedDoc
                                            ->{g} FoldedDoc
  235. ShareDoc.FoldedDoc.isFolded.set : Boolean
                                         -> FoldedDoc
                                         -> FoldedDoc
  236. ShareDoc.FoldedDoc.summary : FoldedDoc -> ShareDoc
  237. ShareDoc.FoldedDoc.summary.modify : (ShareDoc
                                           ->{g} ShareDoc)
                                           -> FoldedDoc
                                           ->{g} FoldedDoc
  238. ShareDoc.FoldedDoc.summary.set : ShareDoc
                                        -> FoldedDoc
                                        -> FoldedDoc
  239. type ShareDoc.FoldedSource
  240. ShareDoc.FoldedSource.FoldedSource : FoldId
                                            -> Boolean
                                            -> EmbeddedSource
                                            -> FoldedSource
  241. ShareDoc.FoldedSource.foldId : FoldedSource -> FoldId
  242. ShareDoc.FoldedSource.foldId.modify : (FoldId
                                             ->{g} FoldId)
                                             -> FoldedSource
                                             ->{g} FoldedSource
  243. ShareDoc.FoldedSource.foldId.set : FoldId
                                          -> FoldedSource
                                          -> FoldedSource
  244. ShareDoc.FoldedSource.isFolded : FoldedSource -> Boolean
  245. ShareDoc.FoldedSource.isFolded.modify : (Boolean
                                               ->{g} Boolean)
                                               -> FoldedSource
                                               ->{g} FoldedSource
  246. ShareDoc.FoldedSource.isFolded.set : Boolean
                                            -> FoldedSource
                                            -> FoldedSource
  247. ShareDoc.FoldedSource.source : FoldedSource
                                      -> EmbeddedSource
  248. ShareDoc.FoldedSource.source.modify : (EmbeddedSource
                                             ->{g} EmbeddedSource)
                                             -> FoldedSource
                                             ->{g} FoldedSource
  249. ShareDoc.FoldedSource.source.set : EmbeddedSource
                                          -> FoldedSource
                                          -> FoldedSource
  250. type ShareDoc.FoldId
  251. ShareDoc.FoldId.ShareDoc.FoldId : Text -> FoldId
  252. ShareDoc.Group : ShareDoc -> ShareDoc
  253. ShareDoc.Image : ShareDoc
                        -> ShareDoc
                        -> Optional ShareDoc
                        -> ShareDoc
  254. type ShareDoc.IsFolded
  255. ShareDoc.IsFolded.Disabled : Html -> IsFolded
  256. ShareDoc.IsFolded.IsFolded : [Html]
                                    -> FoldId
                                    -> Boolean
                                    -> IsFolded
  257. ShareDoc.Italic : ShareDoc -> ShareDoc
  258. ShareDoc.Join : [ShareDoc] -> ShareDoc
  259. ShareDoc.Linebreak : ShareDoc
  260. type ShareDoc.MediaSource
  261. ShareDoc.MediaSource.MediaSource : Text
                                          -> Optional Text
                                          -> ShareDoc.MediaSource
  262. ShareDoc.MediaSource.mediaSourceMimeType : ShareDoc.MediaSource
                                                  -> Optional
                                                    Text
  263. ShareDoc.MediaSource.mediaSourceMimeType.modify : (Optional
                                                           Text
                                                         ->{g} Optional
                                                           Text)
                                                         -> ShareDoc.MediaSource
                                                         ->{g} ShareDoc.MediaSource
  264. ShareDoc.MediaSource.mediaSourceMimeType.set : Optional
                                                        Text
                                                      -> ShareDoc.MediaSource
                                                      -> ShareDoc.MediaSource
  265. ShareDoc.MediaSource.mediaSourceUrl : ShareDoc.MediaSource
                                             -> Text
  266. ShareDoc.MediaSource.mediaSourceUrl.modify : (Text
                                                    ->{g} Text)
                                                    -> ShareDoc.MediaSource
                                                    ->{g} ShareDoc.MediaSource
  267. ShareDoc.MediaSource.mediaSourceUrl.set : Text
                                                 -> ShareDoc.MediaSource
                                                 -> ShareDoc.MediaSource
  268. ShareDoc.mergeWords : Text -> [ShareDoc] -> [ShareDoc]
  269. ShareDoc.mergeWords.doc : Doc
  270. ShareDoc.NamedLink : ShareDoc -> ShareDoc -> ShareDoc
  271. type ShareDoc.NamedLinkHref
  272. ShareDoc.NamedLinkHref.Href : Text -> NamedLinkHref
  273. ShareDoc.NamedLinkHref.InvalidHref : NamedLinkHref
  274. ShareDoc.NamedLinkHref.ReferenceHref : Reference
                                              -> NamedLinkHref
  275. ShareDoc.normalizeHref : NamedLinkHref
                                -> ShareDoc
                                -> NamedLinkHref
  276. ShareDoc.NumberedList : Nat -> [ShareDoc] -> ShareDoc
  277. ShareDoc.Section : ShareDoc -> [ShareDoc] -> ShareDoc
  278. ShareDoc.SectionBreak : ShareDoc
  279. ShareDoc.Span : [ShareDoc] -> ShareDoc
  280. ShareDoc.Special : ShareDoc.SpecialForm -> ShareDoc
  281. type ShareDoc.SpecialForm
  282. ShareDoc.SpecialForm.decode : '{Decoder} ShareDoc.SpecialForm
  283. ShareDoc.SpecialForm.Embed : Syntax
                                    -> ShareDoc.SpecialForm
  284. ShareDoc.SpecialForm.EmbedInline : Syntax
                                          -> ShareDoc.SpecialForm
  285. ShareDoc.SpecialForm.Eval : Syntax
                                   -> Syntax
                                   -> ShareDoc.SpecialForm
  286. ShareDoc.SpecialForm.EvalInline : Syntax
                                         -> Syntax
                                         -> ShareDoc.SpecialForm
  287. ShareDoc.SpecialForm.Example : Syntax
                                      -> ShareDoc.SpecialForm
  288. ShareDoc.SpecialForm.ExampleBlock : Syntax
                                           -> ShareDoc.SpecialForm
  289. ShareDoc.SpecialForm.FrontMatter : Map Text [Text]
                                          -> ShareDoc.SpecialForm
  290. ShareDoc.SpecialForm.LaTeXInline : Text
                                          -> ShareDoc.SpecialForm
  291. ShareDoc.SpecialForm.Link : Syntax
                                   -> ShareDoc.SpecialForm
  292. ShareDoc.SpecialForm.Signature : [TermSignature]
                                        -> ShareDoc.SpecialForm
  293. ShareDoc.SpecialForm.SignatureInline : TermSignature
                                              -> ShareDoc.SpecialForm
  294. ShareDoc.SpecialForm.Source : [FoldedSource]
                                     -> ShareDoc.SpecialForm
  295. ShareDoc.SpecialForm.Svg : Text -> ShareDoc.SpecialForm
  296. ShareDoc.SpecialForm.Video : [ShareDoc.MediaSource]
                                    -> Map Text Text
                                    -> ShareDoc.SpecialForm
  297. ShareDoc.Strikethrough : ShareDoc -> ShareDoc
  298. ShareDoc.Style : Text -> ShareDoc -> ShareDoc
  299. ShareDoc.Table : [[ShareDoc]] -> ShareDoc
  300. ShareDoc.toHtml : Linked -> ShareDoc -> Html
  301. ShareDoc.Tooltip : ShareDoc -> ShareDoc -> ShareDoc
  302. ShareDoc.toText : Text -> ShareDoc -> Text
  303. ShareDoc.toText.doc : Doc
  304. ShareDoc.UntitledSection : [ShareDoc] -> ShareDoc
  305. ShareDoc.Word : Text -> ShareDoc
  306. type Source
  307. Source.codeToHtml : ViewConfig -> Html -> Html
  308. Source.isBuiltin : Source -> Boolean
  309. Source.syntaxToHtml : ViewConfig -> Syntax -> Html
  310. Source.Term : FQN -> TermSource -> Source
  311. Source.toHtml : ViewConfig -> Source -> Html
  312. Source.Type : TypeSource -> Source
  313. type Source.ViewConfig
  314. Source.ViewConfig.Monochrome : ViewConfig
  315. Source.ViewConfig.Plain : ViewConfig
  316. Source.ViewConfig.Rich : Linked -> ViewConfig
  317. Source.ViewConfig.toClassName : ViewConfig -> Text
  318. Source.ViewConfig.toSyntaxLinked : ViewConfig -> Linked
  319. type Syntax
  320. Syntax.decode : '{Decoder} Syntax
  321. Syntax.foldLeft : (b ->{g1} SyntaxSegment ->{g} b)
                         -> b
                         -> Syntax
                         ->{g, g1} b
  322. Syntax.fromList : [SyntaxSegment] ->{Abort} Syntax
  323. type Syntax.Linked
  324. Syntax.Linked.Linked : (Reference -> Text) -> Linked
  325. Syntax.Linked.NotLinked : Linked
  326. Syntax.numLines : Syntax -> Nat
  327. Syntax.segments : Syntax -> List.Nonempty SyntaxSegment
  328. Syntax.Syntax : List.Nonempty SyntaxSegment -> Syntax
  329. type Syntax.SyntaxSegment
  330. Syntax.SyntaxSegment.decode : '{Decoder} SyntaxSegment
  331. Syntax.SyntaxSegment.reference : SyntaxSegment
                                        -> Optional Reference
  332. type Syntax.SyntaxSegment.SeqOp
  333. Syntax.SyntaxSegment.SeqOp.Concat : SeqOp
  334. Syntax.SyntaxSegment.SeqOp.Cons : SeqOp
  335. Syntax.SyntaxSegment.SeqOp.Snoc : SeqOp
  336. Syntax.SyntaxSegment.SyntaxSegment : SyntaxType
                                            -> Text
                                            -> SyntaxSegment
  337. type Syntax.SyntaxSegment.SyntaxType
  338. Syntax.SyntaxSegment.SyntaxType.AbilityBraces : SyntaxType
  339. Syntax.SyntaxSegment.SyntaxType.AbilityConstructorReference : Hash
                                                                     -> Optional
                                                                       FQN
                                                                     -> SyntaxType
  340. Syntax.SyntaxSegment.SyntaxType.BindingEquals : SyntaxType
  341. Syntax.SyntaxSegment.SyntaxType.Blank : SyntaxType
  342. Syntax.SyntaxSegment.SyntaxType.BooleanLiteral : SyntaxType
  343. Syntax.SyntaxSegment.SyntaxType.BytesLiteral : SyntaxType
  344. Syntax.SyntaxSegment.SyntaxType.CharLiteral : SyntaxType
  345. Syntax.SyntaxSegment.SyntaxType.ControlKeyword : SyntaxType
  346. Syntax.SyntaxSegment.SyntaxType.DataConstructorReference : Hash
                                                                  -> Optional
                                                                    FQN
                                                                  -> SyntaxType
  347. Syntax.SyntaxSegment.SyntaxType.DataTypeKeyword : SyntaxType
  348. Syntax.SyntaxSegment.SyntaxType.DataTypeModifier : SyntaxType
  349. Syntax.SyntaxSegment.SyntaxType.DataTypeParams : SyntaxType
  350. Syntax.SyntaxSegment.SyntaxType.decodeOp : '{Decoder} SyntaxType
  351. Syntax.SyntaxSegment.SyntaxType.DelayForceChar : SyntaxType
  352. Syntax.SyntaxSegment.SyntaxType.DelimiterChar : SyntaxType
  353. Syntax.SyntaxSegment.SyntaxType.DocDelimiter : SyntaxType
  354. Syntax.SyntaxSegment.SyntaxType.DocKeyword : SyntaxType
  355. Syntax.SyntaxSegment.SyntaxType.fromText : Text
                                                  -> SyntaxType
  356. Syntax.SyntaxSegment.SyntaxType.HashQualifier : Text
                                                       -> SyntaxType
  357. Syntax.SyntaxSegment.SyntaxType.LinkKeyword : SyntaxType
  358. Syntax.SyntaxSegment.SyntaxType.NumericLiteral : SyntaxType
  359. Syntax.SyntaxSegment.SyntaxType.Op : SeqOp -> SyntaxType
  360. Syntax.SyntaxSegment.SyntaxType.Parenthesis : SyntaxType
  361. Syntax.SyntaxSegment.SyntaxType.TermReference : Hash
                                                       -> Optional
                                                         FQN
                                                       -> SyntaxType
  362. Syntax.SyntaxSegment.SyntaxType.TextLiteral : SyntaxType
  363. Syntax.SyntaxSegment.SyntaxType.toClassName : SyntaxType
                                                     -> Text
  364. Syntax.SyntaxSegment.SyntaxType.TypeAscriptionColon : SyntaxType
  365. Syntax.SyntaxSegment.SyntaxType.TypeOperator : SyntaxType
  366. Syntax.SyntaxSegment.SyntaxType.TypeReference : Hash
                                                       -> Optional
                                                         FQN
                                                       -> SyntaxType
  367. Syntax.SyntaxSegment.SyntaxType.Unit : SyntaxType
  368. Syntax.SyntaxSegment.SyntaxType.UseKeyword : SyntaxType
  369. Syntax.SyntaxSegment.SyntaxType.UsePrefix : SyntaxType
  370. Syntax.SyntaxSegment.SyntaxType.UseSuffix : SyntaxType
  371. Syntax.SyntaxSegment.SyntaxType.Var : SyntaxType
  372. Syntax.SyntaxSegment.toHtml : Linked
                                     -> SyntaxSegment
                                     -> Html
  373. Syntax.toHtml : Linked -> Syntax -> Html
  374. Syntax.tryFromList : [SyntaxSegment] -> Optional Syntax
  375. Syntax.viewFQN : FQN -> Html
  376. type Syntax.Width
  377. Syntax.Width.Width : Int -> Width
  378. type Term
  379. Term.decode : Hash -> '{Decoder} Term
  380. Term.Term : Hash -> TermCategory -> TermSource -> Term
  381. type Term.TermCategory
  382. Term.TermCategory.DocTerm : TermCategory
  383. Term.TermCategory.PlainTerm : TermCategory
  384. Term.TermCategory.TestTerm : TermCategory
  385. type Term.TermSignature
  386. Term.TermSignature.TermSignature : Syntax
                                          -> TermSignature
  387. Term.TermSignature.toHtml : ViewConfig
                                   -> TermSignature
                                   -> Html
  388. Term.TermSignature.toNamedHtml : ViewConfig
                                        -> FQN
                                        -> TermSignature
                                        -> Html
  389. Term.TermSignature.toNamedHtml_ : ViewConfig
                                         -> FQN
                                         -> TermSignature
                                         -> Html
  390. type Term.TermSource
  391. Term.TermSource.Builtin : TermSignature -> TermSource
  392. Term.TermSource.numLines : TermSource -> Nat
  393. Term.TermSource.numSignatureLines : TermSource -> Nat
  394. Term.TermSource.Source : TermSignature
                                -> Syntax
                                -> TermSource
  395. Term.TermSource.toHtml : ViewConfig
                                -> FQN
                                -> TermSource
                                -> Html
  396. tests.docToHtml : '{IO, Exception} [Text]
  397. tests.termToHtml : '{IO, Exception} [Text]
  398. Type.decode : Hash -> '{Decoder} Type.Type
  399. type Type.Type
  400. Type.Type.Type : Hash
                        -> TypeCategory
                        -> TypeSource
                        -> Type.Type
  401. type Type.TypeCategory
  402. Type.TypeCategory.AbilityType : TypeCategory
  403. Type.TypeCategory.DataType : TypeCategory
  404. type Type.TypeSource
  405. Type.TypeSource.Builtin : TypeSource
  406. Type.TypeSource.numLines : TypeSource -> Nat
  407. Type.TypeSource.Source : Syntax -> TypeSource
  408. Type.TypeSource.toHtml : ViewConfig -> TypeSource -> Html
  409. up.html.Attribute.classList : [(Text, Boolean)]
                                     -> Attribute
  410. up.http.HttpResponse.Body.toText : Body
                                          ->{Exception} Text
  411. up.http.HttpResponse.bodyText : HttpResponse
                                       ->{Exception} Text
  412. up.HttpResponse.ensureSuccess : HttpResponse
                                       ->{Exception} HttpResponse
  413. up.svg.toHtml : Svg -> Html
  414. type UserHandle
  415. UserHandle.fromText : Text ->{Exception} UserHandle
  416. UserHandle.fromText.doc : Doc
  417. UserHandle.isValidHandle : Text -> Boolean
  418. UserHandle.isValidHandle.doc : Doc
  419. UserHandle.isValidHandle.tests.consecutiveDashesAreInvalid : [Result]
  420. UserHandle.isValidHandle.tests.consecutiveDashesAreInvalid2 : [Result]
  421. UserHandle.isValidHandle.tests.dashPrefixIsInvalid : [Result]
  422. UserHandle.isValidHandle.tests.nonAlphanumIsInvalid : [Result]
  423. UserHandle.isValidHandle.tests.numbersAreValid : [Result]
  424. UserHandle.isValidHandle.tests.prefixedIsValid : [Result]
  425. UserHandle.isValidHandle.tests.singleDashesAreValid : [Result]
  426. UserHandle.isValidHandle.tests.unprefixedIsValid : [Result]
  427. UserHandle.toText : UserHandle -> Text
  428. UserHandle.toText.doc : Doc
  429. UserHandle.toUnprefixedText : UserHandle -> Text
  430. UserHandle.toUnprefixedText.doc : Doc
  431. UserHandle.tryFromText : Text -> Optional UserHandle
  432. UserHandle.tryFromText.doc : Doc
  433. UserHandle.UserHandle : Text -> UserHandle
```

## Code examples

``` ucm
@unison/share-sdk/main> edit 1-5000

  ☝️

  I added 286 definitions to the top of scratch.u

  You can edit them there, then run `update` to replace the
  definitions currently in this namespace.
```
