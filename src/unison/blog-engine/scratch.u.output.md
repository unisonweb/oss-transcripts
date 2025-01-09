# Blog-engine

Write a blog or newsletter in the Unison Doc format and host it on Unison Cloud 🚀

## Library contents list

``` ucm
@unison/blog-engine/main> pull.without-history @unison/blog-engine/releases/2.1.2

  Downloaded 47094 entities.

  ✅

  Successfully updated @unison/blog-engine/main from
  @unison/blog-engine/releases/2.1.2.

@unison/blog-engine/main> find

  1.   type Blog
  2.   Blog.addSubscriber : Blog
                            -> MailAddress
                            ->{Exception, Cloud} ()
  3.   Blog.addSubscriber.doc : Doc
  4.   Blog.atomFeedRoute : Blog
                            -> '{Route, Exception, Remote} ()
  5.   Blog.atomFeedRoute.doc : Doc
  6.   Blog.basePath : '{Route, Exception} Path
  7.   Blog.basePath.doc : Doc
  8.   Blog.baseURI : '{Route, Exception} URI
  9.   Blog.baseURI.doc : Doc
  10.  Blog.Blog : ProjectRef
                   -> Text
                   -> Text
                   -> OrderedTable Instant Slug
                   -> OrderedTable Slug Post
                   -> OrderedTable Slug Html
                   -> OrderedTable Text Text
                   -> Environment
                   -> Slug
                   -> BlogTheme
                   -> Text
                   -> Optional EmailNotificationsConfig
                   -> Blog
  11.  Blog.blogTitle : Blog -> Text
  12.  Blog.blogTitle.modify : (Text ->{g} Text)
                               -> Blog
                               ->{g} Blog
  13.  Blog.blogTitle.set : Text -> Blog -> Blog
  14.  Blog.cloudEnvironment : Blog -> Environment
  15.  Blog.cloudEnvironment.modify : (Environment
                                      ->{g} Environment)
                                      -> Blog
                                      ->{g} Blog
  16.  Blog.cloudEnvironment.set : Environment -> Blog -> Blog
  17.  Blog.deploy : Blog ->{Exception, Cloud} URI
  18.  Blog.deploy.doc : Doc
  19.  Blog.description : Blog -> Text
  20.  Blog.description.modify : (Text ->{g} Text)
                                 -> Blog
                                 ->{g} Blog
  21.  Blog.description.set : Text -> Blog -> Blog
  22.  Blog.doc : Doc
  23.  Blog.emailNotificationsConfig : Blog
                                       -> Optional
                                         EmailNotificationsConfig
  24.  Blog.emailNotificationsConfig.modify : (Optional
                                                EmailNotificationsConfig
                                              ->{g} Optional
                                                EmailNotificationsConfig)
                                              -> Blog
                                              ->{g} Blog
  25.  Blog.emailNotificationsConfig.set : Optional
                                             EmailNotificationsConfig
                                           -> Blog
                                           -> Blog
  26.  Blog.fromCloudEnv : Environment
                           -> Database
                           -> Slug
                           -> ProjectRef
                           -> Text
                           ->{Random} Blog
  27.  Blog.fromCloudEnv.doc : Doc
  28.  Blog.getPost : Slug -> Blog ->{Remote} Optional Post
  29.  Blog.getPost.doc : Doc
  30.  Blog.getSendgridApiKey : '{Config} Optional Text
  31.  Blog.guid : Blog -> Text
  32.  Blog.guid.modify : (Text ->{g} Text) -> Blog ->{g} Blog
  33.  Blog.guid.set : Text -> Blog -> Blog
  34.  Blog.htmlMailPost : EmailNotificationsConfig
                           -> Blog
                           -> Post
                           ->{Remote} Mail
  35.  Blog.htmlPosts : Blog -> OrderedTable Slug Html
  36.  Blog.htmlPosts.modify : (OrderedTable Slug Html
                               ->{g} OrderedTable Slug Html)
                               -> Blog
                               ->{g} Blog
  37.  Blog.htmlPosts.set : OrderedTable Slug Html
                            -> Blog
                            -> Blog
  38.  Blog.isEmailNotificationEnabled : Blog ->{Config} Boolean
  39.  Blog.latestPostSlug : Blog ->{Remote} Optional Slug
  40.  Blog.latestPostSlug.doc : Doc
  41.  Blog.link_ : [Attribute] -> Text -> [Html] ->{Route} Html
  42.  Blog.link_.doc : Doc
  43.  Blog.listPosts : Blog ->{Remote} [Post]
  44.  Blog.listPosts.doc : Doc
  45.  Blog.listPostsCloud : Blog ->{IO, Exception} [Post]
  46.  Blog.listPostsCloud.doc : Doc
  47.  Blog.makeBlog : Environment
                       -> Database
                       -> Slug
                       -> ProjectRef
                       -> Text
                       -> Text
                       -> Blog
  48.  Blog.makePost : Blog
                       -> Text
                       -> Text
                       -> BlogAuthor
                       -> NamespacePath
                       ->{Exception, Remote} Post
  49.  Blog.makePost.doc : Doc
  50.  Blog.new : Text
                  -> Text
                  -> ProjectRef
                  ->{Exception, Cloud} Blog
  51.  Blog.personalizations : Blog ->{Remote} [Personalization]
  52.  Blog.personalizations.doc : Doc
  53.  Blog.post.doc : Doc
  54.  Blog.posts : Blog -> OrderedTable Slug Post
  55.  Blog.posts.modify : (OrderedTable Slug Post
                           ->{g} OrderedTable Slug Post)
                           -> Blog
                           ->{g} Blog
  56.  Blog.posts.set : OrderedTable Slug Post -> Blog -> Blog
  57.  Blog.postsByTime : Blog -> OrderedTable Instant Slug
  58.  Blog.postsByTime.modify : (OrderedTable Instant Slug
                                 ->{g} OrderedTable Instant Slug)
                                 -> Blog
                                 ->{g} Blog
  59.  Blog.postsByTime.set : OrderedTable Instant Slug
                              -> Blog
                              -> Blog
  60.  Blog.publishPost : Blog
                          -> Post
                          ->{Config,
                          Exception,
                          Storage,
                          Http,
                          Remote} ()
  61.  Blog.publishPost.doc : Doc
  62.  Blog.removeSubscriber : Blog
                               -> MailAddress
                               ->{Exception, Cloud} ()
  63.  Blog.removeSubscriber.doc : Doc
  64.  Blog.renderFrontPage : Blog -> Html
  65.  Blog.renderFrontPage.doc : Doc
  66.  Blog.routes.allPostsRoute : Blog
                                   -> '{Route,
                                   Config,
                                   Exception,
                                   Remote,
                                   Log} ()
  67.  Blog.routes.allPostsRoute.doc : Doc
  68.  Blog.routes.homeRoute : Blog
                               -> '{Route,
                               Config,
                               Exception,
                               Remote,
                               Log} ()
  69.  Blog.routes.homeRoute.doc : Doc
  70.  Blog.routes.notFoundRoute : Blog
                                   -> '{Route,
                                   Config,
                                   Exception,
                                   Remote,
                                   Log} ()
  71.  Blog.routes.postRoute : Blog
                               -> '{Route,
                               Config,
                               Exception,
                               Remote,
                               Log} ()
  72.  Blog.routes.postRoute.doc : Doc
  73.  Blog.routes.subscribeRoute : Blog
                                    -> '{Route,
                                    Config,
                                    Exception,
                                    Remote,
                                    Log} ()
  74.  Blog.rssFeedRoute : Blog
                           -> '{Route, Exception, Remote} ()
  75.  Blog.rssFeedRoute.doc : Doc
  76.  Blog.server : Blog
                     -> HttpRequest
                     ->{Config, Exception, Storage, Remote, Log} HttpResponse
  77.  Blog.server.doc : Doc
  78.  Blog.serviceName : Blog -> Slug
  79.  Blog.serviceName.modify : (Slug ->{g} Slug)
                                 -> Blog
                                 ->{g} Blog
  80.  Blog.serviceName.set : Slug -> Blog -> Blog
  81.  Blog.setSendgridApiKey : Blog
                                -> Text
                                ->{Exception, Cloud} ()
  82.  Blog.shareProjectRef : Blog -> ProjectRef
  83.  Blog.shareProjectRef.modify : (ProjectRef
                                     ->{g} ProjectRef)
                                     -> Blog
                                     ->{g} Blog
  84.  Blog.shareProjectRef.set : ProjectRef -> Blog -> Blog
  85.  Blog.subscribe : Blog -> Subscriber ->{Remote} ()
  86.  Blog.subscribers : Blog -> OrderedTable Text Text
  87.  Blog.subscribers.modify : (OrderedTable Text Text
                                 ->{g} OrderedTable Text Text)
                                 -> Blog
                                 ->{g} Blog
  88.  Blog.subscribers.set : OrderedTable Text Text
                              -> Blog
                              -> Blog
  89.  Blog.theme : Blog -> BlogTheme
  90.  Blog.theme.modify : (BlogTheme ->{g} BlogTheme)
                           -> Blog
                           ->{g} Blog
  91.  Blog.theme.set : BlogTheme -> Blog -> Blog
  92.  Blog.withDescription : Text -> Blog -> Blog
  93.  Blog.withDescription.doc : Doc
  94.  Blog.withEmailNotificationsConfig : EmailNotificationsConfig
                                           -> Blog
                                           -> Blog
  95.  Blog.withServiceName : Slug -> Blog -> Blog
  96.  Blog.withServiceName.doc : Doc
  97.  Blog.withTheme : BlogTheme -> Blog -> Blog
  98.  Blog.withTheme.doc : Doc
  99.  type BlogAuthor
  100. BlogAuthor.avatar : BlogAuthor -> Optional URI
  101. BlogAuthor.avatar.modify : (Optional URI
                                  ->{g} Optional URI)
                                  -> BlogAuthor
                                  ->{g} BlogAuthor
  102. BlogAuthor.avatar.set : Optional URI
                               -> BlogAuthor
                               -> BlogAuthor
  103. BlogAuthor.bio : BlogAuthor -> Text
  104. BlogAuthor.bio.modify : (Text ->{g} Text)
                               -> BlogAuthor
                               ->{g} BlogAuthor
  105. BlogAuthor.bio.set : Text -> BlogAuthor -> BlogAuthor
  106. BlogAuthor.BlogAuthor : Text
                               -> Text
                               -> Optional URI
                               -> Text
                               -> BlogAuthor
  107. BlogAuthor.doc : Doc
  108. BlogAuthor.email : BlogAuthor -> Text
  109. BlogAuthor.email.modify : (Text ->{g} Text)
                                 -> BlogAuthor
                                 ->{g} BlogAuthor
  110. BlogAuthor.email.set : Text -> BlogAuthor -> BlogAuthor
  111. BlogAuthor.name : BlogAuthor -> Text
  112. BlogAuthor.name.modify : (Text ->{g} Text)
                                -> BlogAuthor
                                ->{g} BlogAuthor
  113. BlogAuthor.name.set : Text -> BlogAuthor -> BlogAuthor
  114. type BlogContext
  115. BlogContext.basePath : BlogContext -> Path
  116. BlogContext.basePath.modify : (Path ->{g} Path)
                                     -> BlogContext
                                     ->{g} BlogContext
  117. BlogContext.basePath.set : Path
                                  -> BlogContext
                                  -> BlogContext
  118. BlogContext.blog : BlogContext -> Blog
  119. BlogContext.blog.modify : (Blog ->{g} Blog)
                                 -> BlogContext
                                 ->{g} BlogContext
  120. BlogContext.blog.set : Blog -> BlogContext -> BlogContext
  121. BlogContext.blogContext : Blog
                                 ->{Route,
                                 Config,
                                 Exception,
                                 Remote} BlogContext
  122. BlogContext.BlogContext : Blog
                                 -> Instant
                                 -> Path
                                 -> Boolean
                                 -> BlogContext
  123. BlogContext.isEmailNotificationEnabled : BlogContext
                                                -> Boolean
  124. BlogContext.isEmailNotificationEnabled.modify : (Boolean
                                                       ->{g} Boolean)
                                                       -> BlogContext
                                                       ->{g} BlogContext
  125. BlogContext.isEmailNotificationEnabled.set : Boolean
                                                    -> BlogContext
                                                    -> BlogContext
  126. BlogContext.now : BlogContext -> Instant
  127. BlogContext.now.modify : (Instant ->{g} Instant)
                                -> BlogContext
                                ->{g} BlogContext
  128. BlogContext.now.set : Instant
                             -> BlogContext
                             -> BlogContext
  129. ability BlogEnv
  130. BlogEnv.doc : Doc
  131. BlogEnv.post : Text
                      -> BlogAuthor
                      -> NamespacePath
                      ->{BlogEnv} Post
  132. BlogEnv.publish : Post ->{BlogEnv} ()
  133. BlogEnv.publishAll : [Post] ->{BlogEnv} ()
  134. BlogEnv.publishAll.doc : Doc
  135. BlogEnv.withBlog : Blog
                          -> '{Config,
                          Exception,
                          Storage,
                          Http,
                          Remote,
                          BlogEnv} a
                          ->{Exception, Cloud} a
  136. BlogEnv.withBlog.doc : Doc
  137. type BlogTheme
  138. type BlogTheme.BlogColors
  139. BlogTheme.BlogColors.background : BlogColors
                                         -> BlogTheme.Color
  140. BlogTheme.BlogColors.background.modify : (BlogTheme.Color
                                                ->{g} BlogTheme.Color)
                                                -> BlogColors
                                                ->{g} BlogColors
  141. BlogTheme.BlogColors.background.set : BlogTheme.Color
                                             -> BlogColors
                                             -> BlogColors
  142. BlogTheme.BlogColors.BlogColors : BlogTheme.Color
                                         -> BlogTheme.Color
                                         -> BlogTheme.Color
                                         -> BlogTheme.Color
                                         -> BlogTheme.Color
                                         -> BlogTheme.Color
                                         -> BlogTheme.Color
                                         -> BlogTheme.Color
                                         -> BlogTheme.Color
                                         -> BlogTheme.Color
                                         -> BlogTheme.Color
                                         -> BlogTheme.Color
                                         -> BlogTheme.Color
                                         -> BlogTheme.Color
                                         -> BlogTheme.Color
                                         -> BlogTheme.Color
                                         -> BlogTheme.Color
                                         -> BlogTheme.Color
                                         -> BlogTheme.Color
                                         -> BlogTheme.Color
                                         -> BlogTheme.Color
                                         -> BlogTheme.Color
                                         -> BlogTheme.Color
                                         -> BlogTheme.Color
                                         -> BlogTheme.Color
                                         -> BlogTheme.Color
                                         -> BlogColors
  143. BlogTheme.BlogColors.border : BlogColors
                                     -> BlogTheme.Color
  144. BlogTheme.BlogColors.border.modify : (BlogTheme.Color
                                            ->{g} BlogTheme.Color)
                                            -> BlogColors
                                            ->{g} BlogColors
  145. BlogTheme.BlogColors.border.set : BlogTheme.Color
                                         -> BlogColors
                                         -> BlogColors
  146. BlogTheme.BlogColors.borderEmphasized : BlogColors
                                               -> BlogTheme.Color
  147. BlogTheme.BlogColors.borderEmphasized.modify : (BlogTheme.Color
                                                      ->{g} BlogTheme.Color)
                                                      -> BlogColors
                                                      ->{g} BlogColors
  148. BlogTheme.BlogColors.borderEmphasized.set : BlogTheme.Color
                                                   -> BlogColors
                                                   -> BlogColors
  149. BlogTheme.BlogColors.borderSubdued : BlogColors
                                            -> BlogTheme.Color
  150. BlogTheme.BlogColors.borderSubdued.modify : (BlogTheme.Color
                                                   ->{g} BlogTheme.Color)
                                                   -> BlogColors
                                                   ->{g} BlogColors
  151. BlogTheme.BlogColors.borderSubdued.set : BlogTheme.Color
                                                -> BlogColors
                                                -> BlogColors
  152. BlogTheme.BlogColors.button : BlogColors
                                     -> BlogTheme.Color
  153. BlogTheme.BlogColors.button.modify : (BlogTheme.Color
                                            ->{g} BlogTheme.Color)
                                            -> BlogColors
                                            ->{g} BlogColors
  154. BlogTheme.BlogColors.button.set : BlogTheme.Color
                                         -> BlogColors
                                         -> BlogColors
  155. BlogTheme.BlogColors.buttonEmphasized : BlogColors
                                               -> BlogTheme.Color
  156. BlogTheme.BlogColors.buttonEmphasized.modify : (BlogTheme.Color
                                                      ->{g} BlogTheme.Color)
                                                      -> BlogColors
                                                      ->{g} BlogColors
  157. BlogTheme.BlogColors.buttonEmphasized.set : BlogTheme.Color
                                                   -> BlogColors
                                                   -> BlogColors
  158. BlogTheme.BlogColors.buttonText : BlogColors
                                         -> BlogTheme.Color
  159. BlogTheme.BlogColors.buttonText.modify : (BlogTheme.Color
                                                ->{g} BlogTheme.Color)
                                                -> BlogColors
                                                ->{g} BlogColors
  160. BlogTheme.BlogColors.buttonText.set : BlogTheme.Color
                                             -> BlogColors
                                             -> BlogColors
  161. BlogTheme.BlogColors.buttonTextEmphasized : BlogColors
                                                   -> BlogTheme.Color
  162. BlogTheme.BlogColors.buttonTextEmphasized.modify : (BlogTheme.Color
                                                          ->{g} BlogTheme.Color)
                                                          -> BlogColors
                                                          ->{g} BlogColors
  163. BlogTheme.BlogColors.buttonTextEmphasized.set : BlogTheme.Color
                                                       -> BlogColors
                                                       -> BlogColors
  164. BlogTheme.BlogColors.container : BlogColors
                                        -> BlogTheme.Color
  165. BlogTheme.BlogColors.container.modify : (BlogTheme.Color
                                               ->{g} BlogTheme.Color)
                                               -> BlogColors
                                               ->{g} BlogColors
  166. BlogTheme.BlogColors.container.set : BlogTheme.Color
                                            -> BlogColors
                                            -> BlogColors
  167. BlogTheme.BlogColors.containerSubdued : BlogColors
                                               -> BlogTheme.Color
  168. BlogTheme.BlogColors.containerSubdued.modify : (BlogTheme.Color
                                                      ->{g} BlogTheme.Color)
                                                      -> BlogColors
                                                      ->{g} BlogColors
  169. BlogTheme.BlogColors.containerSubdued.set : BlogTheme.Color
                                                   -> BlogColors
                                                   -> BlogColors
  170. BlogTheme.BlogColors.divider : BlogColors
                                      -> BlogTheme.Color
  171. BlogTheme.BlogColors.divider.modify : (BlogTheme.Color
                                             ->{g} BlogTheme.Color)
                                             -> BlogColors
                                             ->{g} BlogColors
  172. BlogTheme.BlogColors.divider.set : BlogTheme.Color
                                          -> BlogColors
                                          -> BlogColors
  173. BlogTheme.BlogColors.doc : Doc
  174. BlogTheme.BlogColors.element : BlogColors
                                      -> BlogTheme.Color
  175. BlogTheme.BlogColors.element.modify : (BlogTheme.Color
                                             ->{g} BlogTheme.Color)
                                             -> BlogColors
                                             ->{g} BlogColors
  176. BlogTheme.BlogColors.element.set : BlogTheme.Color
                                          -> BlogColors
                                          -> BlogColors
  177. BlogTheme.BlogColors.elementEmphasized : BlogColors
                                                -> BlogTheme.Color
  178. BlogTheme.BlogColors.elementEmphasized.modify : (BlogTheme.Color
                                                       ->{g} BlogTheme.Color)
                                                       -> BlogColors
                                                       ->{g} BlogColors
  179. BlogTheme.BlogColors.elementEmphasized.set : BlogTheme.Color
                                                    -> BlogColors
                                                    -> BlogColors
  180. BlogTheme.BlogColors.elementSubdued : BlogColors
                                             -> BlogTheme.Color
  181. BlogTheme.BlogColors.elementSubdued.modify : (BlogTheme.Color
                                                    ->{g} BlogTheme.Color)
                                                    -> BlogColors
                                                    ->{g} BlogColors
  182. BlogTheme.BlogColors.elementSubdued.set : BlogTheme.Color
                                                 -> BlogColors
                                                 -> BlogColors
  183. BlogTheme.BlogColors.focusBorder : BlogColors
                                          -> BlogTheme.Color
  184. BlogTheme.BlogColors.focusBorder.modify : (BlogTheme.Color
                                                 ->{g} BlogTheme.Color)
                                                 -> BlogColors
                                                 ->{g} BlogColors
  185. BlogTheme.BlogColors.focusBorder.set : BlogTheme.Color
                                              -> BlogColors
                                              -> BlogColors
  186. BlogTheme.BlogColors.focusOutline : BlogColors
                                           -> BlogTheme.Color
  187. BlogTheme.BlogColors.focusOutline.modify : (BlogTheme.Color
                                                  ->{g} BlogTheme.Color)
                                                  -> BlogColors
                                                  ->{g} BlogColors
  188. BlogTheme.BlogColors.focusOutline.set : BlogTheme.Color
                                               -> BlogColors
                                               -> BlogColors
  189. BlogTheme.BlogColors.icon : BlogColors -> BlogTheme.Color
  190. BlogTheme.BlogColors.icon.modify : (BlogTheme.Color
                                          ->{g} BlogTheme.Color)
                                          -> BlogColors
                                          ->{g} BlogColors
  191. BlogTheme.BlogColors.icon.set : BlogTheme.Color
                                       -> BlogColors
                                       -> BlogColors
  192. BlogTheme.BlogColors.iconEmphasized : BlogColors
                                             -> BlogTheme.Color
  193. BlogTheme.BlogColors.iconEmphasized.modify : (BlogTheme.Color
                                                    ->{g} BlogTheme.Color)
                                                    -> BlogColors
                                                    ->{g} BlogColors
  194. BlogTheme.BlogColors.iconEmphasized.set : BlogTheme.Color
                                                 -> BlogColors
                                                 -> BlogColors
  195. BlogTheme.BlogColors.iconSubdued : BlogColors
                                          -> BlogTheme.Color
  196. BlogTheme.BlogColors.iconSubdued.modify : (BlogTheme.Color
                                                 ->{g} BlogTheme.Color)
                                                 -> BlogColors
                                                 ->{g} BlogColors
  197. BlogTheme.BlogColors.iconSubdued.set : BlogTheme.Color
                                              -> BlogColors
                                              -> BlogColors
  198. BlogTheme.BlogColors.infoContainerSubdued : BlogColors
                                                   -> BlogTheme.Color
  199. BlogTheme.BlogColors.infoContainerSubdued.modify : (BlogTheme.Color
                                                          ->{g} BlogTheme.Color)
                                                          -> BlogColors
                                                          ->{g} BlogColors
  200. BlogTheme.BlogColors.infoContainerSubdued.set : BlogTheme.Color
                                                       -> BlogColors
                                                       -> BlogColors
  201. BlogTheme.BlogColors.interactive : BlogColors
                                          -> BlogTheme.Color
  202. BlogTheme.BlogColors.interactive.modify : (BlogTheme.Color
                                                 ->{g} BlogTheme.Color)
                                                 -> BlogColors
                                                 ->{g} BlogColors
  203. BlogTheme.BlogColors.interactive.set : BlogTheme.Color
                                              -> BlogColors
                                              -> BlogColors
  204. BlogTheme.BlogColors.interactiveHover : BlogColors
                                               -> BlogTheme.Color
  205. BlogTheme.BlogColors.interactiveHover.modify : (BlogTheme.Color
                                                      ->{g} BlogTheme.Color)
                                                      -> BlogColors
                                                      ->{g} BlogColors
  206. BlogTheme.BlogColors.interactiveHover.set : BlogTheme.Color
                                                   -> BlogColors
                                                   -> BlogColors
  207. BlogTheme.BlogColors.text : BlogColors -> BlogTheme.Color
  208. BlogTheme.BlogColors.text.modify : (BlogTheme.Color
                                          ->{g} BlogTheme.Color)
                                          -> BlogColors
                                          ->{g} BlogColors
  209. BlogTheme.BlogColors.text.set : BlogTheme.Color
                                       -> BlogColors
                                       -> BlogColors
  210. BlogTheme.BlogColors.textEmphasized : BlogColors
                                             -> BlogTheme.Color
  211. BlogTheme.BlogColors.textEmphasized.modify : (BlogTheme.Color
                                                    ->{g} BlogTheme.Color)
                                                    -> BlogColors
                                                    ->{g} BlogColors
  212. BlogTheme.BlogColors.textEmphasized.set : BlogTheme.Color
                                                 -> BlogColors
                                                 -> BlogColors
  213. BlogTheme.BlogColors.textSubdued : BlogColors
                                          -> BlogTheme.Color
  214. BlogTheme.BlogColors.textSubdued.modify : (BlogTheme.Color
                                                 ->{g} BlogTheme.Color)
                                                 -> BlogColors
                                                 ->{g} BlogColors
  215. BlogTheme.BlogColors.textSubdued.set : BlogTheme.Color
                                              -> BlogColors
                                              -> BlogColors
  216. BlogTheme.BlogColors.textVerySubdued : BlogColors
                                              -> BlogTheme.Color
  217. BlogTheme.BlogColors.textVerySubdued.modify : (BlogTheme.Color
                                                     ->{g} BlogTheme.Color)
                                                     -> BlogColors
                                                     ->{g} BlogColors
  218. BlogTheme.BlogColors.textVerySubdued.set : BlogTheme.Color
                                                  -> BlogColors
                                                  -> BlogColors
  219. BlogTheme.BlogTheme : Text
                             -> FontStack
                             -> FontStack
                             -> BlogColors
                             -> SyntaxColors
                             -> DocColors
                             -> BlogTheme
  220. type BlogTheme.Color
  221. BlogTheme.Color.Color : Text -> BlogTheme.Color
  222. BlogTheme.Color.doc : Doc
  223. BlogTheme.Color.toText : BlogTheme.Color -> Text
  224. BlogTheme.Color.toText.doc : Doc
  225. BlogTheme.colors : BlogTheme -> BlogColors
  226. BlogTheme.colors.modify : (BlogColors ->{g} BlogColors)
                                 -> BlogTheme
                                 ->{g} BlogTheme
  227. BlogTheme.colors.set : BlogColors
                              -> BlogTheme
                              -> BlogTheme
  228. BlogTheme.doc : Doc
  229. type BlogTheme.DocColors
  230. BlogTheme.docColors : BlogTheme -> DocColors
  231. BlogTheme.DocColors.aside : DocColors -> BlogTheme.Color
  232. BlogTheme.DocColors.aside.modify : (BlogTheme.Color
                                          ->{g} BlogTheme.Color)
                                          -> DocColors
                                          ->{g} DocColors
  233. BlogTheme.DocColors.aside.set : BlogTheme.Color
                                       -> DocColors
                                       -> DocColors
  234. BlogTheme.DocColors.asideSource : DocColors
                                         -> BlogTheme.Color
  235. BlogTheme.DocColors.asideSource.modify : (BlogTheme.Color
                                                ->{g} BlogTheme.Color)
                                                -> DocColors
                                                ->{g} DocColors
  236. BlogTheme.DocColors.asideSource.set : BlogTheme.Color
                                             -> DocColors
                                             -> DocColors
  237. BlogTheme.DocColors.background : DocColors
                                        -> BlogTheme.Color
  238. BlogTheme.DocColors.background.modify : (BlogTheme.Color
                                               ->{g} BlogTheme.Color)
                                               -> DocColors
                                               ->{g} DocColors
  239. BlogTheme.DocColors.background.set : BlogTheme.Color
                                            -> DocColors
                                            -> DocColors
  240. BlogTheme.DocColors.border : DocColors -> BlogTheme.Color
  241. BlogTheme.DocColors.border.modify : (BlogTheme.Color
                                           ->{g} BlogTheme.Color)
                                           -> DocColors
                                           ->{g} DocColors
  242. BlogTheme.DocColors.border.set : BlogTheme.Color
                                        -> DocColors
                                        -> DocColors
  243. BlogTheme.DocColors.callout : DocColors
                                     -> BlogTheme.Color
  244. BlogTheme.DocColors.callout.modify : (BlogTheme.Color
                                            ->{g} BlogTheme.Color)
                                            -> DocColors
                                            ->{g} DocColors
  245. BlogTheme.DocColors.callout.set : BlogTheme.Color
                                         -> DocColors
                                         -> DocColors
  246. BlogTheme.DocColors.calloutSource : DocColors
                                           -> BlogTheme.Color
  247. BlogTheme.DocColors.calloutSource.modify : (BlogTheme.Color
                                                  ->{g} BlogTheme.Color)
                                                  -> DocColors
                                                  ->{g} DocColors
  248. BlogTheme.DocColors.calloutSource.set : BlogTheme.Color
                                               -> DocColors
                                               -> DocColors
  249. BlogTheme.DocColors.divider : DocColors
                                     -> BlogTheme.Color
  250. BlogTheme.DocColors.divider.modify : (BlogTheme.Color
                                            ->{g} BlogTheme.Color)
                                            -> DocColors
                                            ->{g} DocColors
  251. BlogTheme.DocColors.divider.set : BlogTheme.Color
                                         -> DocColors
                                         -> DocColors
  252. BlogTheme.DocColors.doc : Doc
  253. BlogTheme.DocColors.DocColors : BlogTheme.Color
                                       -> BlogTheme.Color
                                       -> BlogTheme.Color
                                       -> BlogTheme.Color
                                       -> BlogTheme.Color
                                       -> BlogTheme.Color
                                       -> BlogTheme.Color
                                       -> BlogTheme.Color
                                       -> BlogTheme.Color
                                       -> BlogTheme.Color
                                       -> BlogTheme.Color
                                       -> BlogTheme.Color
                                       -> BlogTheme.Color
                                       -> DocColors
  254. BlogTheme.DocColors.evalIcon : DocColors
                                      -> BlogTheme.Color
  255. BlogTheme.DocColors.evalIcon.modify : (BlogTheme.Color
                                             ->{g} BlogTheme.Color)
                                             -> DocColors
                                             ->{g} DocColors
  256. BlogTheme.DocColors.evalIcon.set : BlogTheme.Color
                                          -> DocColors
                                          -> DocColors
  257. BlogTheme.DocColors.evalResult : DocColors
                                        -> BlogTheme.Color
  258. BlogTheme.DocColors.evalResult.modify : (BlogTheme.Color
                                               ->{g} BlogTheme.Color)
                                               -> DocColors
                                               ->{g} DocColors
  259. BlogTheme.DocColors.evalResult.set : BlogTheme.Color
                                            -> DocColors
                                            -> DocColors
  260. BlogTheme.docColors.modify : (DocColors ->{g} DocColors)
                                    -> BlogTheme
                                    ->{g} BlogTheme
  261. BlogTheme.docColors.set : DocColors
                                 -> BlogTheme
                                 -> BlogTheme
  262. BlogTheme.DocColors.source : DocColors -> BlogTheme.Color
  263. BlogTheme.DocColors.source.modify : (BlogTheme.Color
                                           ->{g} BlogTheme.Color)
                                           -> DocColors
                                           ->{g} DocColors
  264. BlogTheme.DocColors.source.set : BlogTheme.Color
                                        -> DocColors
                                        -> DocColors
  265. BlogTheme.DocColors.text : DocColors -> BlogTheme.Color
  266. BlogTheme.DocColors.text.modify : (BlogTheme.Color
                                         ->{g} BlogTheme.Color)
                                         -> DocColors
                                         ->{g} DocColors
  267. BlogTheme.DocColors.text.set : BlogTheme.Color
                                      -> DocColors
                                      -> DocColors
  268. BlogTheme.DocColors.textSubdued : DocColors
                                         -> BlogTheme.Color
  269. BlogTheme.DocColors.textSubdued.modify : (BlogTheme.Color
                                                ->{g} BlogTheme.Color)
                                                -> DocColors
                                                ->{g} DocColors
  270. BlogTheme.DocColors.textSubdued.set : BlogTheme.Color
                                             -> DocColors
                                             -> DocColors
  271. BlogTheme.DocColors.title : DocColors -> BlogTheme.Color
  272. BlogTheme.DocColors.title.modify : (BlogTheme.Color
                                          ->{g} BlogTheme.Color)
                                          -> DocColors
                                          ->{g} DocColors
  273. BlogTheme.DocColors.title.set : BlogTheme.Color
                                       -> DocColors
                                       -> DocColors
  274. BlogTheme.DocColors.toCSSRules : DocColors -> [Rule]
  275. BlogTheme.DocColors.toCSSRules.doc : Doc
  276. type BlogTheme.FontStack
  277. BlogTheme.FontStack.doc : Doc
  278. BlogTheme.FontStack.FontStack : [Text] -> FontStack
  279. BlogTheme.FontStack.toText : FontStack -> Text
  280. BlogTheme.FontStack.toText.doc : Doc
  281. BlogTheme.mainFont : BlogTheme -> FontStack
  282. BlogTheme.mainFont.modify : (FontStack ->{g} FontStack)
                                   -> BlogTheme
                                   ->{g} BlogTheme
  283. BlogTheme.mainFont.set : FontStack
                                -> BlogTheme
                                -> BlogTheme
  284. BlogTheme.monospaceFont : BlogTheme -> FontStack
  285. BlogTheme.monospaceFont.modify : (FontStack
                                        ->{g} FontStack)
                                        -> BlogTheme
                                        ->{g} BlogTheme
  286. BlogTheme.monospaceFont.set : FontStack
                                     -> BlogTheme
                                     -> BlogTheme
  287. BlogTheme.name : BlogTheme -> Text
  288. BlogTheme.name.modify : (Text ->{g} Text)
                               -> BlogTheme
                               ->{g} BlogTheme
  289. BlogTheme.name.set : Text -> BlogTheme -> BlogTheme
  290. type BlogTheme.SyntaxColors
  291. BlogTheme.syntaxColors : BlogTheme -> SyntaxColors
  292. BlogTheme.SyntaxColors.ability_ : SyntaxColors
                                         -> BlogTheme.Color
  293. BlogTheme.SyntaxColors.ability_.modify : (BlogTheme.Color
                                                ->{g} BlogTheme.Color)
                                                -> SyntaxColors
                                                ->{g} SyntaxColors
  294. BlogTheme.SyntaxColors.ability_.set : BlogTheme.Color
                                             -> SyntaxColors
                                             -> SyntaxColors
  295. BlogTheme.SyntaxColors.base : SyntaxColors
                                     -> BlogTheme.Color
  296. BlogTheme.SyntaxColors.base.modify : (BlogTheme.Color
                                            ->{g} BlogTheme.Color)
                                            -> SyntaxColors
                                            ->{g} SyntaxColors
  297. BlogTheme.SyntaxColors.base.set : BlogTheme.Color
                                         -> SyntaxColors
                                         -> SyntaxColors
  298. BlogTheme.SyntaxColors.constructor : SyntaxColors
                                            -> BlogTheme.Color
  299. BlogTheme.SyntaxColors.constructor.modify : (BlogTheme.Color
                                                   ->{g} BlogTheme.Color)
                                                   -> SyntaxColors
                                                   ->{g} SyntaxColors
  300. BlogTheme.SyntaxColors.constructor.set : BlogTheme.Color
                                                -> SyntaxColors
                                                -> SyntaxColors
  301. BlogTheme.SyntaxColors.constructorNamespace : SyntaxColors
                                                     -> BlogTheme.Color
  302. BlogTheme.SyntaxColors.constructorNamespace.modify : (BlogTheme.Color
                                                            ->{g} BlogTheme.Color)
                                                            -> SyntaxColors
                                                            ->{g} SyntaxColors
  303. BlogTheme.SyntaxColors.constructorNamespace.set : BlogTheme.Color
                                                         -> SyntaxColors
                                                         -> SyntaxColors
  304. BlogTheme.SyntaxColors.doc : Doc
  305. BlogTheme.SyntaxColors.keyword : SyntaxColors
                                        -> BlogTheme.Color
  306. BlogTheme.SyntaxColors.keyword.modify : (BlogTheme.Color
                                               ->{g} BlogTheme.Color)
                                               -> SyntaxColors
                                               ->{g} SyntaxColors
  307. BlogTheme.SyntaxColors.keyword.set : BlogTheme.Color
                                            -> SyntaxColors
                                            -> SyntaxColors
  308. BlogTheme.SyntaxColors.linkContainerHovered : SyntaxColors
                                                     -> BlogTheme.Color
  309. BlogTheme.SyntaxColors.linkContainerHovered.modify : (BlogTheme.Color
                                                            ->{g} BlogTheme.Color)
                                                            -> SyntaxColors
                                                            ->{g} SyntaxColors
  310. BlogTheme.SyntaxColors.linkContainerHovered.set : BlogTheme.Color
                                                         -> SyntaxColors
                                                         -> SyntaxColors
  311. BlogTheme.syntaxColors.modify : (SyntaxColors
                                       ->{g} SyntaxColors)
                                       -> BlogTheme
                                       ->{g} BlogTheme
  312. BlogTheme.SyntaxColors.monochromeBase : SyntaxColors
                                               -> BlogTheme.Color
  313. BlogTheme.SyntaxColors.monochromeBase.modify : (BlogTheme.Color
                                                      ->{g} BlogTheme.Color)
                                                      -> SyntaxColors
                                                      ->{g} SyntaxColors
  314. BlogTheme.SyntaxColors.monochromeBase.set : BlogTheme.Color
                                                   -> SyntaxColors
                                                   -> SyntaxColors
  315. BlogTheme.SyntaxColors.monochromeEmphasized : SyntaxColors
                                                     -> BlogTheme.Color
  316. BlogTheme.SyntaxColors.monochromeEmphasized.modify : (BlogTheme.Color
                                                            ->{g} BlogTheme.Color)
                                                            -> SyntaxColors
                                                            ->{g} SyntaxColors
  317. BlogTheme.SyntaxColors.monochromeEmphasized.set : BlogTheme.Color
                                                         -> SyntaxColors
                                                         -> SyntaxColors
  318. BlogTheme.SyntaxColors.monochromeSubdued : SyntaxColors
                                                  -> BlogTheme.Color
  319. BlogTheme.SyntaxColors.monochromeSubdued.modify : (BlogTheme.Color
                                                         ->{g} BlogTheme.Color)
                                                         -> SyntaxColors
                                                         ->{g} SyntaxColors
  320. BlogTheme.SyntaxColors.monochromeSubdued.set : BlogTheme.Color
                                                      -> SyntaxColors
                                                      -> SyntaxColors
  321. BlogTheme.SyntaxColors.operator : SyntaxColors
                                         -> BlogTheme.Color
  322. BlogTheme.SyntaxColors.operator.modify : (BlogTheme.Color
                                                ->{g} BlogTheme.Color)
                                                -> SyntaxColors
                                                ->{g} SyntaxColors
  323. BlogTheme.SyntaxColors.operator.set : BlogTheme.Color
                                             -> SyntaxColors
                                             -> SyntaxColors
  324. BlogTheme.SyntaxColors.plain : SyntaxColors
                                      -> BlogTheme.Color
  325. BlogTheme.SyntaxColors.plain.modify : (BlogTheme.Color
                                             ->{g} BlogTheme.Color)
                                             -> SyntaxColors
                                             ->{g} SyntaxColors
  326. BlogTheme.SyntaxColors.plain.set : BlogTheme.Color
                                          -> SyntaxColors
                                          -> SyntaxColors
  327. BlogTheme.syntaxColors.set : SyntaxColors
                                    -> BlogTheme
                                    -> BlogTheme
  328. BlogTheme.SyntaxColors.subdued : SyntaxColors
                                        -> BlogTheme.Color
  329. BlogTheme.SyntaxColors.subdued.modify : (BlogTheme.Color
                                               ->{g} BlogTheme.Color)
                                               -> SyntaxColors
                                               ->{g} SyntaxColors
  330. BlogTheme.SyntaxColors.subdued.set : BlogTheme.Color
                                            -> SyntaxColors
                                            -> SyntaxColors
  331. BlogTheme.SyntaxColors.SyntaxColors : BlogTheme.Color
                                             -> BlogTheme.Color
                                             -> BlogTheme.Color
                                             -> BlogTheme.Color
                                             -> BlogTheme.Color
                                             -> BlogTheme.Color
                                             -> BlogTheme.Color
                                             -> BlogTheme.Color
                                             -> BlogTheme.Color
                                             -> BlogTheme.Color
                                             -> BlogTheme.Color
                                             -> BlogTheme.Color
                                             -> BlogTheme.Color
                                             -> BlogTheme.Color
                                             -> BlogTheme.Color
                                             -> BlogTheme.Color
                                             -> BlogTheme.Color
                                             -> BlogTheme.Color
                                             -> SyntaxColors
  332. BlogTheme.SyntaxColors.term : SyntaxColors
                                     -> BlogTheme.Color
  333. BlogTheme.SyntaxColors.term.modify : (BlogTheme.Color
                                            ->{g} BlogTheme.Color)
                                            -> SyntaxColors
                                            ->{g} SyntaxColors
  334. BlogTheme.SyntaxColors.term.set : BlogTheme.Color
                                         -> SyntaxColors
                                         -> SyntaxColors
  335. BlogTheme.SyntaxColors.termNamespace : SyntaxColors
                                              -> BlogTheme.Color
  336. BlogTheme.SyntaxColors.termNamespace.modify : (BlogTheme.Color
                                                     ->{g} BlogTheme.Color)
                                                     -> SyntaxColors
                                                     ->{g} SyntaxColors
  337. BlogTheme.SyntaxColors.termNamespace.set : BlogTheme.Color
                                                  -> SyntaxColors
                                                  -> SyntaxColors
  338. BlogTheme.SyntaxColors.text : SyntaxColors
                                     -> BlogTheme.Color
  339. BlogTheme.SyntaxColors.text.modify : (BlogTheme.Color
                                            ->{g} BlogTheme.Color)
                                            -> SyntaxColors
                                            ->{g} SyntaxColors
  340. BlogTheme.SyntaxColors.text.set : BlogTheme.Color
                                         -> SyntaxColors
                                         -> SyntaxColors
  341. BlogTheme.SyntaxColors.toCSS : SyntaxColors -> CSS
  342. BlogTheme.SyntaxColors.toCSS.doc : Doc
  343. BlogTheme.SyntaxColors.toCSSRules : SyntaxColors
                                           -> [Rule]
  344. BlogTheme.SyntaxColors.toCSSRules.doc : Doc
  345. BlogTheme.SyntaxColors.typeNamespace : SyntaxColors
                                              -> BlogTheme.Color
  346. BlogTheme.SyntaxColors.typeNamespace.modify : (BlogTheme.Color
                                                     ->{g} BlogTheme.Color)
                                                     -> SyntaxColors
                                                     ->{g} SyntaxColors
  347. BlogTheme.SyntaxColors.typeNamespace.set : BlogTheme.Color
                                                  -> SyntaxColors
                                                  -> SyntaxColors
  348. BlogTheme.SyntaxColors.type_ : SyntaxColors
                                      -> BlogTheme.Color
  349. BlogTheme.SyntaxColors.type_.modify : (BlogTheme.Color
                                             ->{g} BlogTheme.Color)
                                             -> SyntaxColors
                                             ->{g} SyntaxColors
  350. BlogTheme.SyntaxColors.type_.set : BlogTheme.Color
                                          -> SyntaxColors
                                          -> SyntaxColors
  351. BlogTheme.SyntaxColors.verySubdued : SyntaxColors
                                            -> BlogTheme.Color
  352. BlogTheme.SyntaxColors.verySubdued.modify : (BlogTheme.Color
                                                   ->{g} BlogTheme.Color)
                                                   -> SyntaxColors
                                                   ->{g} SyntaxColors
  353. BlogTheme.SyntaxColors.verySubdued.set : BlogTheme.Color
                                                -> SyntaxColors
                                                -> SyntaxColors
  354. BlogTheme.toCSS : BlogTheme -> CSS
  355. BlogTheme.toCSS.doc : Doc
  356. BlogTheme.unisonLight : BlogTheme
  357. BlogTheme.unisonLight.doc : Doc
  358. type emails.EmailNotificationsConfig
  359. emails.EmailNotificationsConfig.baseURI : EmailNotificationsConfig
                                                 -> URI
  360. emails.EmailNotificationsConfig.baseURI.modify : (URI
                                                        ->{g} URI)
                                                        -> EmailNotificationsConfig
                                                        ->{g} EmailNotificationsConfig
  361. emails.EmailNotificationsConfig.baseURI.set : URI
                                                     -> EmailNotificationsConfig
                                                     -> EmailNotificationsConfig
  362. emails.EmailNotificationsConfig.doc : Doc
  363. emails.EmailNotificationsConfig.EmailNotificationsConfig : MailAddress
                                                                  -> URI
                                                                  -> EmailNotificationsConfig
  364. emails.EmailNotificationsConfig.senderEmail : EmailNotificationsConfig
                                                     -> MailAddress
  365. emails.EmailNotificationsConfig.senderEmail.modify : (MailAddress
                                                            ->{g} MailAddress)
                                                            -> EmailNotificationsConfig
                                                            ->{g} EmailNotificationsConfig
  366. emails.EmailNotificationsConfig.senderEmail.set : MailAddress
                                                         -> EmailNotificationsConfig
                                                         -> EmailNotificationsConfig
  367. type emails.NewPostEmailNotification
  368. emails.NewPostEmailNotification.blog : NewPostEmailNotification
                                              -> Blog
  369. emails.NewPostEmailNotification.blog.modify : (Blog
                                                     ->{g} Blog)
                                                     -> NewPostEmailNotification
                                                     ->{g} NewPostEmailNotification
  370. emails.NewPostEmailNotification.blog.set : Blog
                                                  -> NewPostEmailNotification
                                                  -> NewPostEmailNotification
  371. emails.NewPostEmailNotification.box : [Attribute]
                                             -> [Attribute]
                                             -> [Html]
                                             -> Html
  372. emails.NewPostEmailNotification.NewPostEmailNotification : Blog
                                                                  -> Post
                                                                  -> NewPostEmailNotification
  373. emails.NewPostEmailNotification.post : NewPostEmailNotification
                                              -> Post
  374. emails.NewPostEmailNotification.post.modify : (Post
                                                     ->{g} Post)
                                                     -> NewPostEmailNotification
                                                     ->{g} NewPostEmailNotification
  375. emails.NewPostEmailNotification.post.set : Post
                                                  -> NewPostEmailNotification
                                                  -> NewPostEmailNotification
  376. emails.NewPostEmailNotification.styles : Text
  377. emails.NewPostEmailNotification.subject : NewPostEmailNotification
                                                 -> Text
  378. emails.NewPostEmailNotification.toHtml : EmailNotificationsConfig
                                                -> NewPostEmailNotification
                                                -> Html
  379. emails.NewPostEmailNotification.toHtml.doc : Doc
  380. emails.NewPostEmailNotification.toHtmlMailContent : EmailNotificationsConfig
                                                           -> NewPostEmailNotification
                                                           -> MailContent
  381. type emails.Subscriber
  382. emails.Subscriber.decode : '{Decoder} Subscriber
  383. emails.Subscriber.email : Subscriber -> Text
  384. emails.Subscriber.email.modify : (Text ->{g} Text)
                                        -> Subscriber
                                        ->{g} Subscriber
  385. emails.Subscriber.email.set : Text
                                     -> Subscriber
                                     -> Subscriber
  386. emails.Subscriber.name : Subscriber -> Text
  387. emails.Subscriber.name.modify : (Text ->{g} Text)
                                       -> Subscriber
                                       ->{g} Subscriber
  388. emails.Subscriber.name.set : Text
                                    -> Subscriber
                                    -> Subscriber
  389. emails.Subscriber.Subscriber : Text -> Text -> Subscriber
  390. type Page
  391. type Page.ActiveNavItem
  392. Page.activeNavItem : Page -> ActiveNavItem
  393. Page.ActiveNavItem.AllPosts : ActiveNavItem
  394. Page.ActiveNavItem.doc : Doc
  395. Page.ActiveNavItem.LatestPost : ActiveNavItem
  396. Page.activeNavItem.modify : (ActiveNavItem
                                   ->{g} ActiveNavItem)
                                   -> Page
                                   ->{g} Page
  397. Page.ActiveNavItem.NoneActive : ActiveNavItem
  398. Page.activeNavItem.set : ActiveNavItem -> Page -> Page
  399. Page.allPostsPage : BlogContext
                           ->{Exception, Remote} Page
  400. Page.allPostsPage.allPostsCSS : CSS
  401. Page.allPostsPage.postLink : (Instant, Slug, Post)
                                    -> Html
  402. Page.atomFeedPage : URI -> Blog ->{Remote} Text
  403. Page.atomFeedPage.doc : Doc
  404. Page.authorToHtml : BlogAuthor -> Html
  405. Page.badrequestPage : Text -> Html
  406. Page.badrequestPage.doc : Doc
  407. Page.comma : Html
  408. Page.content : Page -> [Html]
  409. Page.content.modify : ([Html] ->{g} [Html])
                             -> Page
                             ->{g} Page
  410. Page.content.set : [Html] -> Page -> Page
  411. Page.css : Page -> [CSS]
  412. Page.css.docStyles : Text
  413. Page.css.docStyles.doc : Doc
  414. Page.css.highlightJsStyles : Text
  415. Page.css.mainStyles : BlogTheme -> CSS
  416. Page.css.mainStyles.doc : Doc
  417. Page.css.modify : ([CSS] ->{g} [CSS]) -> Page ->{g} Page
  418. Page.css.set : [CSS] -> Page -> Page
  419. Page.css.syntaxStyles : Text
  420. Page.css.syntaxStyles.doc : Doc
  421. Page.doc : Doc
  422. type Page.DocumentResult
  423. Page.DocumentResult.NotFound : Text -> DocumentResult
  424. Page.DocumentResult.Success : Text -> DocumentResult
  425. Page.empty : Page
  426. Page.empty.doc : Doc
  427. type Page.NavItem
  428. Page.NavItem.doc : Doc
  429. Page.NavItem.NavItem : Text -> Text -> NavItem
  430. Page.NavItem.text : NavItem -> Text
  431. Page.NavItem.text.modify : (Text ->{g} Text)
                                  -> NavItem
                                  ->{g} NavItem
  432. Page.NavItem.text.set : Text -> NavItem -> NavItem
  433. Page.NavItem.toHtml : Boolean -> NavItem -> Html
  434. Page.NavItem.toHtml.doc : Doc
  435. Page.NavItem.url : NavItem -> Text
  436. Page.NavItem.url.modify : (Text ->{g} Text)
                                 -> NavItem
                                 ->{g} NavItem
  437. Page.NavItem.url.set : Text -> NavItem -> NavItem
  438. type Page.NavItems
  439. Page.navItems : NavItems
  440. Page.NavItems.allPosts : NavItems -> NavItem
  441. Page.NavItems.allPosts.modify : (NavItem ->{g} NavItem)
                                       -> NavItems
                                       ->{g} NavItems
  442. Page.NavItems.allPosts.set : NavItem
                                    -> NavItems
                                    -> NavItems
  443. Page.NavItems.doc : Doc
  444. Page.navItems.doc : Doc
  445. Page.NavItems.latestPost : NavItems -> NavItem
  446. Page.NavItems.latestPost.modify : (NavItem ->{g} NavItem)
                                         -> NavItems
                                         ->{g} NavItems
  447. Page.NavItems.latestPost.set : NavItem
                                      -> NavItems
                                      -> NavItems
  448. Page.NavItems.NavItems : NavItem -> NavItem -> NavItems
  449. Page.notFoundPage : Text -> Page
  450. Page.notFoundPage.doc : Doc
  451. Page.Page : Text
                   -> ActiveNavItem
                   -> [Html]
                   -> [CSS]
                   -> Page
  452. Page.pageHeader : BlogContext -> Page -> Html
  453. Page.postPage : BlogContext
                       -> Slug
                       ->{Exception, Remote} DocumentResult
  454. Page.postPage.doc : Doc
  455. Page.postPage.metadataToHtml : Metadata -> Html
  456. Page.postPage.postCSS : CSS
  457. Page.postPage_ : BlogContext
                        -> Post
                        -> Html
                        ->{Exception} Page
  458. Page.rssFeedPage : URI -> Blog ->{Remote} Text
  459. Page.rssFeedPage.doc : Doc
  460. Page.scripts : [Html]
  461. Page.scripts.doc : Doc
  462. Page.sep : Html
  463. Page.title : Page -> Text
  464. Page.title.modify : (Text ->{g} Text) -> Page ->{g} Page
  465. Page.title.set : Text -> Page -> Page
  466. Page.toHtml : BlogContext -> Page ->{Exception} Html
  467. Page.toHtml.doc : Doc
  468. Page.toHtmlDocument : BlogContext
                             -> Page
                             ->{Exception} Text
  469. Page.toHtmlDocument.doc : Doc
  470. Page.withActiveNavItem : ActiveNavItem -> Page -> Page
  471. Page.withActiveNavItem.doc : Doc
  472. Page.withContent : [Html] -> Page -> Page
  473. Page.withContent.doc : Doc
  474. Page.withCSS : CSS -> Page -> Page
  475. Page.withCSS_ : [CSS] -> Page -> Page
  476. Page.withTitle : Text -> Page -> Page
  477. Page.withTitle.doc : Doc
  478. type Post
  479. Post.addAuthor : BlogAuthor -> Post -> Post
  480. Post.addAuthor.doc : Doc
  481. Post.addTag : Text -> Post -> Post
  482. Post.addTag.doc : Doc
  483. Post.cloudPublish : '{g, Exception, Cloud} Blog
                           -> Post
                           ->{g, Exception, Cloud} ()
  484. Post.cloudPublish.doc : Doc
  485. Post.doc : Doc
  486. Post.docPath : Post -> NamespacePath
  487. Post.docPath.modify : (NamespacePath ->{g} NamespacePath)
                             -> Post
                             ->{g} Post
  488. Post.docPath.set : NamespacePath -> Post -> Post
  489. Post.key : Post -> Instant
  490. Post.key.doc : Doc
  491. type Post.Metadata
  492. Post.metadata : Post -> Metadata
  493. Post.Metadata.authors : Metadata -> [BlogAuthor]
  494. Post.Metadata.authors.modify : ([BlogAuthor]
                                      ->{g} [BlogAuthor])
                                      -> Metadata
                                      ->{g} Metadata
  495. Post.Metadata.authors.set : [BlogAuthor]
                                   -> Metadata
                                   -> Metadata
  496. Post.Metadata.doc : Doc
  497. Post.Metadata.guid : Metadata -> Text
  498. Post.Metadata.guid.modify : (Text ->{g} Text)
                                   -> Metadata
                                   ->{g} Metadata
  499. Post.Metadata.guid.set : Text -> Metadata -> Metadata
  500. Post.Metadata.Metadata : Text
                                -> Text
                                -> [BlogAuthor]
                                -> OffsetDateTime
                                -> [Text]
                                -> Slug
                                -> Text
                                -> Metadata
  501. Post.metadata.modify : (Metadata ->{g} Metadata)
                              -> Post
                              ->{g} Post
  502. Post.Metadata.publishedAt : Metadata -> OffsetDateTime
  503. Post.Metadata.publishedAt.modify : (OffsetDateTime
                                          ->{g} OffsetDateTime)
                                          -> Metadata
                                          ->{g} Metadata
  504. Post.Metadata.publishedAt.set : OffsetDateTime
                                       -> Metadata
                                       -> Metadata
  505. Post.metadata.set : Metadata -> Post -> Post
  506. Post.Metadata.slug : Metadata -> Slug
  507. Post.Metadata.slug.modify : (Slug ->{g} Slug)
                                   -> Metadata
                                   ->{g} Metadata
  508. Post.Metadata.slug.set : Slug -> Metadata -> Metadata
  509. Post.Metadata.summary : Metadata -> Text
  510. Post.Metadata.summary.modify : (Text ->{g} Text)
                                      -> Metadata
                                      ->{g} Metadata
  511. Post.Metadata.summary.set : Text -> Metadata -> Metadata
  512. Post.Metadata.tags : Metadata -> [Text]
  513. Post.Metadata.tags.modify : ([Text] ->{g} [Text])
                                   -> Metadata
                                   ->{g} Metadata
  514. Post.Metadata.tags.set : [Text] -> Metadata -> Metadata
  515. Post.Metadata.title : Metadata -> Text
  516. Post.Metadata.title.modify : (Text ->{g} Text)
                                    -> Metadata
                                    ->{g} Metadata
  517. Post.Metadata.title.set : Text -> Metadata -> Metadata
  518. Post.new : Text
                  -> Text
                  -> BlogAuthor
                  -> OffsetDateTime
                  -> NamespacePath
                  ->{Exception, Random} Post
  519. Post.new.doc : Doc
  520. Post.Post : Metadata -> NamespacePath -> Post
  521. Post.publishedAt : Post -> OffsetDateTime
  522. Post.publishedAt.doc : Doc
  523. Post.slug : Post -> Slug
  524. Post.slug.doc : Doc
  525. Post.title : Post -> Text
  526. Post.title.doc : Doc
  527. Post.toAtom : URI -> Post ->{Remote} XMLNode
  528. Post.toAtom.doc : Doc
  529. Post.toRSS : URI -> Post -> XMLNode
  530. Post.toRSS.doc : Doc
  531. Post.unpublish : '{g} Blog
                        -> Slug
                        ->{g, Exception, Cloud} ()
  532. Post.unpublish.doc : Doc
  533. Post.withAuthors : [BlogAuthor] -> Post -> Post
  534. Post.withAuthors.doc : Doc
  535. Post.withPublishedAt : OffsetDateTime -> Post -> Post
  536. Post.withPublishedOn : LocalDate -> Post -> Post
  537. Post.withSlug : Slug -> Post -> Post
  538. Post.withSlug.doc : Doc
  539. Post.withSummary : Text -> Post -> Post
  540. Post.withSummary.doc : Doc
  541. Post.withTags : [Text] -> Post -> Post
  542. Post.withTags.doc : Doc
  543. Post.withTitle : Text -> Post -> Post
  544. Post.withTitle.doc : Doc
  545. README : Doc
  546. README.posts.helloWorld : Doc
  547. README.sampleAuthor : BlogAuthor
  548. README.sampleBlog : '{Exception, Cloud} Blog
  549. README.sampleBlog.build : '{IO, Exception, Cloud} ()
  550. README.sampleBlog.buildDeploy : '{IO, Exception} URI
  551. README.sampleBlog.deploy : '{IO, Exception, Cloud} URI
  552. ReleaseNotes : Doc
  553. type up.base.time.LocalDate.NamedMonth
  554. up.base.time.LocalDate.NamedMonth.Apr : NamedMonth
  555. up.base.time.LocalDate.NamedMonth.Aug : NamedMonth
  556. up.base.time.LocalDate.NamedMonth.Dec : NamedMonth
  557. up.base.time.LocalDate.NamedMonth.Feb : NamedMonth
  558. up.base.time.LocalDate.NamedMonth.Jan : NamedMonth
  559. up.base.time.LocalDate.NamedMonth.Jul : NamedMonth
  560. up.base.time.LocalDate.NamedMonth.Jun : NamedMonth
  561. up.base.time.LocalDate.NamedMonth.Mar : NamedMonth
  562. up.base.time.LocalDate.NamedMonth.May : NamedMonth
  563. up.base.time.LocalDate.NamedMonth.Nov : NamedMonth
  564. up.base.time.LocalDate.NamedMonth.Oct : NamedMonth
  565. up.base.time.LocalDate.NamedMonth.Sep : NamedMonth
  566. up.base.time.LocalDate.NamedMonth.toShortText : NamedMonth
                                                       -> Text
  567. up.base.time.LocalDate.NamedMonth.toText : NamedMonth
                                                  -> Text
  568. up.base.time.LocalDate.NamedMonth.tryFromNat : Nat
                                                      -> Optional
                                                        NamedMonth
  569. up.base.time.LocalDate.toNamedMonth : LocalDate
                                             -> NamedMonth
  570. up.base.time.LocalDate.toShortText : LocalDate -> Text
  571. up.HttpResponse.ensureSuccess : HttpResponse
                                       ->{Exception} HttpResponse
  572. up.uriParser.Parser.root : Parser a a
  573. up.uriParser.Parser.root.doc : Doc
```

## Code examples

``` ucm
@unison/blog-engine/main> edit 1-5000

  ☝️

  I added 536 definitions to the top of scratch.u

  You can edit them there, then run `update` to replace the
  definitions currently in this namespace.
```

```` unison :added-by-ucm scratch.u
type Blog
  = { shareProjectRef : ProjectRef,
      blogTitle : Text,
      description : Text,
      postsByTime : OrderedTable Instant Slug,
      posts : OrderedTable Slug Post,
      htmlPosts : OrderedTable Slug Html,
      subscribers : OrderedTable Text Text,
      cloudEnvironment : Environment,
      serviceName : Slug,
      theme : BlogTheme,
      guid : Text,
      emailNotificationsConfig : Optional EmailNotificationsConfig }

type BlogAuthor
  = { name : Text, bio : Text, avatar : Optional URI, email : Text }

type BlogContext
  = { blog : Blog,
      now : Instant,
      basePath : Path,
      isEmailNotificationEnabled : Boolean }

ability BlogEnv where
  post : Text -> BlogAuthor -> NamespacePath ->{BlogEnv} Post
  publish : Post ->{BlogEnv} ()

type BlogTheme
  = { name : Text,
      mainFont : FontStack,
      monospaceFont : FontStack,
      colors : BlogColors,
      syntaxColors : SyntaxColors,
      docColors : DocColors }

type BlogTheme.BlogColors
  = { background : BlogTheme.Color,
      text : BlogTheme.Color,
      textSubdued : BlogTheme.Color,
      textVerySubdued : BlogTheme.Color,
      textEmphasized : BlogTheme.Color,
      icon : BlogTheme.Color,
      iconSubdued : BlogTheme.Color,
      iconEmphasized : BlogTheme.Color,
      border : BlogTheme.Color,
      borderSubdued : BlogTheme.Color,
      borderEmphasized : BlogTheme.Color,
      divider : BlogTheme.Color,
      container : BlogTheme.Color,
      containerSubdued : BlogTheme.Color,
      interactive : BlogTheme.Color,
      interactiveHover : BlogTheme.Color,
      focusBorder : BlogTheme.Color,
      focusOutline : BlogTheme.Color,
      infoContainerSubdued : BlogTheme.Color,
      element : BlogTheme.Color,
      elementSubdued : BlogTheme.Color,
      elementEmphasized : BlogTheme.Color,
      button : BlogTheme.Color,
      buttonText : BlogTheme.Color,
      buttonEmphasized : BlogTheme.Color,
      buttonTextEmphasized : BlogTheme.Color }

type BlogTheme.Color
  = Color Text

type BlogTheme.DocColors
  = { background : BlogTheme.Color,
      title : BlogTheme.Color,
      text : BlogTheme.Color,
      textSubdued : BlogTheme.Color,
      aside : BlogTheme.Color,
      asideSource : BlogTheme.Color,
      callout : BlogTheme.Color,
      calloutSource : BlogTheme.Color,
      source : BlogTheme.Color,
      border : BlogTheme.Color,
      divider : BlogTheme.Color,
      evalResult : BlogTheme.Color,
      evalIcon : BlogTheme.Color }

type BlogTheme.FontStack
  = FontStack [Text]

type BlogTheme.SyntaxColors
  = { plain : BlogTheme.Color,
      base : BlogTheme.Color,
      verySubdued : BlogTheme.Color,
      subdued : BlogTheme.Color,
      keyword : BlogTheme.Color,
      operator : BlogTheme.Color,
      term : BlogTheme.Color,
      termNamespace : BlogTheme.Color,
      ability_ : BlogTheme.Color,
      type_ : BlogTheme.Color,
      typeNamespace : BlogTheme.Color,
      constructor : BlogTheme.Color,
      constructorNamespace : BlogTheme.Color,
      text : BlogTheme.Color,
      linkContainerHovered : BlogTheme.Color,
      monochromeSubdued : BlogTheme.Color,
      monochromeBase : BlogTheme.Color,
      monochromeEmphasized : BlogTheme.Color }

type emails.EmailNotificationsConfig
  = { senderEmail : MailAddress, baseURI : URI }

type emails.NewPostEmailNotification
  = { blog : Blog, post : Post }

type emails.Subscriber
  = { email : Text, name : Text }

type Page
  = { title : Text,
      activeNavItem : ActiveNavItem,
      content : [Html],
      css : [CSS] }

type Page.ActiveNavItem
  = NoneActive
  | LatestPost
  | AllPosts

type Page.DocumentResult
  = Success Text
  | NotFound Text

type Page.NavItem
  = { url : Text, text : Text }

type Page.NavItems
  = { latestPost : NavItem, allPosts : NavItem }

type Post
  = { metadata : Metadata, docPath : NamespacePath }

type Post.Metadata
  = { title : Text,
      summary : Text,
      authors : [BlogAuthor],
      publishedAt : OffsetDateTime,
      tags : [Text],
      slug : Slug,
      guid : Text }

type up.base.time.LocalDate.NamedMonth
  = Jan
  | Feb
  | Mar
  | Apr
  | May
  | Jun
  | Jul
  | Aug
  | Sep
  | Oct
  | Nov
  | Dec

Blog.addSubscriber : Blog -> MailAddress ->{Exception, Cloud} ()
Blog.addSubscriber blog = cases
  MailAddress email name ->
    Cloud.submit (cloudEnvironment blog) do
      randomly do
        transact.random (OrderedTable.database (subscribers blog)) do
          OrderedTable.write.tx (subscribers blog) email name

Blog.addSubscriber.doc : Doc
Blog.addSubscriber.doc =
  {{
  Adds an email subscriber to the blog. This will add the subscriber's email
  address and name to the {{ docLink (docEmbedTermLink do subscribers) }} field
  of the blog.
  }}

Blog.atomFeedRoute : Blog -> '{Route, Exception, Remote} ()
Blog.atomFeedRoute blog = do
  noCapture GET (Parser.s "atom.xml")
  baseURI = Blog.baseURI()
  respond.ok (Text.toUtf8 (atomFeedPage baseURI blog))

Blog.atomFeedRoute.doc : Doc
Blog.atomFeedRoute.doc =
  {{ A {type Route} that serves an Atom feed for the {type Blog}. }}

Blog.basePath : '{Route, Exception} Path
Blog.basePath =
  do
    use List head
    use request header
    host = head (header "Host")
    cloudBasePath = head (header "Unison-Cloud-Base-Path")
    match (host, cloudBasePath) with
      (Some h, Some p) ->
        if endsWith "unison-services.cloud" h then
          unison_base_3_21_0.IO.net.URI.Path.fromText p
        else Path []
      _ -> Path []

Blog.basePath.doc : Doc
Blog.basePath.doc =
  {{
  Returns the base path of the current request.
  
  This is used throughout the blog to construct URIs for links and redirects.
  }}

Blog.baseURI : '{Route, Exception} URI
Blog.baseURI = do
  host = List.head (request.header "Host")
  path = Blog.basePath()
  match host with
    Some h -> path |> fromPath |> withHost h
    _      -> fromPath path

Blog.baseURI.doc : Doc
Blog.baseURI.doc =
  {{
  Combines the Host and {{ docLink (docEmbedTermLink do Blog.basePath) }} to
  construct a full URL.
  }}

Blog.blogTitle : Blog -> Text
Blog.blogTitle = cases Blog.Blog _ blogTitle _ _ _ _ _ _ _ _ _ _ -> blogTitle

Blog.blogTitle.modify : (Text ->{g} Text) -> Blog ->{g} Blog
Blog.blogTitle.modify f = cases
  Blog.Blog
    shareProjectRef
    blogTitle
    description
    postsByTime
    posts
    htmlPosts
    subscribers
    cloudEnvironment
    serviceName
    theme
    guid
    emailNotificationsConfig ->
    Blog.Blog
      shareProjectRef
      (f blogTitle)
      description
      postsByTime
      posts
      htmlPosts
      subscribers
      cloudEnvironment
      serviceName
      theme
      guid
      emailNotificationsConfig

Blog.blogTitle.set : Text -> Blog -> Blog
Blog.blogTitle.set blogTitle1 = cases
  Blog.Blog
    shareProjectRef
    _
    description
    postsByTime
    posts
    htmlPosts
    subscribers
    cloudEnvironment
    serviceName
    theme
    guid
    emailNotificationsConfig ->
    Blog.Blog
      shareProjectRef
      blogTitle1
      description
      postsByTime
      posts
      htmlPosts
      subscribers
      cloudEnvironment
      serviceName
      theme
      guid
      emailNotificationsConfig

Blog.cloudEnvironment : Blog -> Environment
Blog.cloudEnvironment = cases
  Blog.Blog _ _ _ _ _ _ _ cloudEnvironment _ _ _ _ -> cloudEnvironment

Blog.cloudEnvironment.modify :
  (Environment ->{g} Environment) -> Blog ->{g} Blog
Blog.cloudEnvironment.modify f = cases
  Blog.Blog
    shareProjectRef
    blogTitle
    description
    postsByTime
    posts
    htmlPosts
    subscribers
    cloudEnvironment
    serviceName
    theme
    guid
    emailNotificationsConfig ->
    Blog.Blog
      shareProjectRef
      blogTitle
      description
      postsByTime
      posts
      htmlPosts
      subscribers
      (f cloudEnvironment)
      serviceName
      theme
      guid
      emailNotificationsConfig

Blog.cloudEnvironment.set : Environment -> Blog -> Blog
Blog.cloudEnvironment.set cloudEnvironment1 = cases
  Blog.Blog
    shareProjectRef
    blogTitle
    description
    postsByTime
    posts
    htmlPosts
    subscribers
    _
    serviceName
    theme
    guid
    emailNotificationsConfig ->
    Blog.Blog
      shareProjectRef
      blogTitle
      description
      postsByTime
      posts
      htmlPosts
      subscribers
      cloudEnvironment1
      serviceName
      theme
      guid
      emailNotificationsConfig

Blog.deploy : Blog ->{Exception, Cloud} URI
Blog.deploy blog =
  env = cloudEnvironment blog
  slug = Slug.toText (serviceName blog)
  name = ServiceName.named slug
  serviceHash = deployHttp env (Blog.server blog)
  ServiceName.assign name serviceHash

Blog.deploy.doc : Doc
Blog.deploy.doc =
  {{
  Deploys the {type Blog} to Unison Cloud. Returns the URI of the deployed
  blog.
  }}

Blog.description : Blog -> Text
Blog.description = cases
  Blog.Blog _ _ description _ _ _ _ _ _ _ _ _ -> description

Blog.description.modify : (Text ->{g} Text) -> Blog ->{g} Blog
Blog.description.modify f = cases
  Blog.Blog
    shareProjectRef
    blogTitle
    description
    postsByTime
    posts
    htmlPosts
    subscribers
    cloudEnvironment
    serviceName
    theme
    guid
    emailNotificationsConfig ->
    Blog.Blog
      shareProjectRef
      blogTitle
      (f description)
      postsByTime
      posts
      htmlPosts
      subscribers
      cloudEnvironment
      serviceName
      theme
      guid
      emailNotificationsConfig

Blog.description.set : Text -> Blog -> Blog
Blog.description.set description1 = cases
  Blog.Blog
    shareProjectRef
    blogTitle
    _
    postsByTime
    posts
    htmlPosts
    subscribers
    cloudEnvironment
    serviceName
    theme
    guid
    emailNotificationsConfig ->
    Blog.Blog
      shareProjectRef
      blogTitle
      description1
      postsByTime
      posts
      htmlPosts
      subscribers
      cloudEnvironment
      serviceName
      theme
      guid
      emailNotificationsConfig

Blog.doc : Doc
Blog.doc =
  {{
  A {type Blog} is fundamentally a collection of blog posts, along with some
  associated metadata and configuration. It's the main data structure that
  powers a blog, and it's the thing that you'll be interacting with most often
  when you're working with this library.
  
  The {type Blog} type is a record type, and it has the following fields:
  
  * {{ docLink (docEmbedTermLink do shareProjectRef) }} is a reference to the
    Unison Share project that hosts the {type Doc} values for the blog posts.
    This is used to fetch the content of the blog posts when they're being
    rendered.
  * {{ docLink (docEmbedTermLink do blogTitle) }} is the title of the blog.
  * {{ docLink (docEmbedTermLink do description) }} is a short description of
    the blog.
  * {{ docLink (docEmbedTermLink do postsByTime) }} is a {type OrderedTable}
    that maps from {type Instant} values to {type Slug} values. This is used to
    find the most recent blog posts.
  * {{ docLink (docEmbedTermLink do posts) }} is the main collection of blog
    posts. It's a {type OrderedTable} that maps from {type Slug} values to
    {type Post} values. The {type Slug} is the unique identifier for a blog
    post and also the URL path component for the post.
  * {{ docLink (docEmbedTermLink do htmlPosts) }} is a {type OrderedTable} that
    maps from {type Slug} values to {type Html} values. This is used to cache
    the rendered HTML for the blog posts, so that we don't have to re-render
    them every time we want to display them.
  * {{ docLink (docEmbedTermLink do subscribers) }} is a {type OrderedTable}
    that maps from email addresses to names. This is used to keep track of
    email subscribers to the blog.
  * {{ docLink (docEmbedTermLink do cloudEnvironment) }} is the Unison Cloud
    {type Environment} that the blog runs in. This is used to interact with the
    cloud services that the blog depends on.
  * {{ docLink (docEmbedTermLink do serviceName) }} is the name of the blog
    service as a {type Slug}. This is used to identify the blog service in the
    cloud environment.
  * {{ docLink (docEmbedTermLink do Blog.theme) }} is the {type BlogTheme} that
    the blog uses to render its HTML. This includes things like fonts, colors,
    and other styling information.
  * {{ docLink (docEmbedTermLink do Blog.guid) }} is a unique identifier for
    the blog.
  * {{ docLink (docEmbedTermLink do emailNotificationsConfig) }} is the
    {type Optional} {type EmailNotificationsConfig} the blog uses to send
    emails to subscribers.
  }}

Blog.emailNotificationsConfig : Blog -> Optional EmailNotificationsConfig
Blog.emailNotificationsConfig = cases
  Blog.Blog _ _ _ _ _ _ _ _ _ _ _ emailNotificationsConfig ->
    emailNotificationsConfig

Blog.emailNotificationsConfig.modify :
  (Optional EmailNotificationsConfig ->{g} Optional EmailNotificationsConfig)
  -> Blog
  ->{g} Blog
Blog.emailNotificationsConfig.modify f = cases
  Blog.Blog
    shareProjectRef
    blogTitle
    description
    postsByTime
    posts
    htmlPosts
    subscribers
    cloudEnvironment
    serviceName
    theme
    guid
    emailNotificationsConfig ->
    Blog.Blog
      shareProjectRef
      blogTitle
      description
      postsByTime
      posts
      htmlPosts
      subscribers
      cloudEnvironment
      serviceName
      theme
      guid
      (f emailNotificationsConfig)

Blog.emailNotificationsConfig.set :
  Optional EmailNotificationsConfig -> Blog -> Blog
Blog.emailNotificationsConfig.set emailNotificationsConfig1 = cases
  Blog.Blog
    shareProjectRef
    blogTitle
    description
    postsByTime
    posts
    htmlPosts
    subscribers
    cloudEnvironment
    serviceName
    theme
    guid
    _ ->
    Blog.Blog
      shareProjectRef
      blogTitle
      description
      postsByTime
      posts
      htmlPosts
      subscribers
      cloudEnvironment
      serviceName
      theme
      guid
      emailNotificationsConfig1

Blog.fromCloudEnv :
  Environment -> Database -> Slug -> ProjectRef -> Text ->{Random} Blog
Blog.fromCloudEnv env db serviceName projectRef title =
  makeBlog env db serviceName projectRef title (UUID.toText version4())

Blog.fromCloudEnv.doc : Doc
Blog.fromCloudEnv.doc =
  {{
  Creates a new {type Blog} with the given {type Environment}, {type Database},
  {type Slug}, {type ProjectRef}, and title.
  
  The {type Blog} is created with a default theme, and no description. Use e.g.
  {{ docLink (docEmbedTermLink do withDescription) }} and {{
  docLink (docEmbedTermLink do Blog.withTheme) }} to customize the blog.
  
  # Example
  
    {{ docExampleBlock 0 do
      env = Environment.named "example-blog"
      db = Database.named "example-blog"
      serviceSlug = Slug "example-blog"
      projectRef = ProjectRef "unison" "example-blog"
      blog = fromCloudEnv env db serviceSlug projectRef "Example Blog"
      () }}
  }}

Blog.getPost : Slug -> Blog ->{Remote} Optional Post
Blog.getPost slug blog = OrderedTable.tryRead (posts blog) slug

Blog.getPost.doc : Doc
Blog.getPost.doc =
  {{
  Get a {type Blog} from a {type Blog} by its {type Slug}. Returns {NoneActive}
  if the post does not exist.
  }}

Blog.getSendgridApiKey : '{Config} Optional Text
Blog.getSendgridApiKey = do Config.lookup "sendgrid_api_key"

Blog.guid : Blog -> Text
Blog.guid = cases Blog.Blog _ _ _ _ _ _ _ _ _ _ guid _ -> guid

Blog.guid.modify : (Text ->{g} Text) -> Blog ->{g} Blog
Blog.guid.modify f = cases
  Blog.Blog
    shareProjectRef
    blogTitle
    description
    postsByTime
    posts
    htmlPosts
    subscribers
    cloudEnvironment
    serviceName
    theme
    guid
    emailNotificationsConfig ->
    Blog.Blog
      shareProjectRef
      blogTitle
      description
      postsByTime
      posts
      htmlPosts
      subscribers
      cloudEnvironment
      serviceName
      theme
      (f guid)
      emailNotificationsConfig

Blog.guid.set : Text -> Blog -> Blog
Blog.guid.set guid1 = cases
  Blog.Blog
    shareProjectRef
    blogTitle
    description
    postsByTime
    posts
    htmlPosts
    subscribers
    cloudEnvironment
    serviceName
    theme
    _
    emailNotificationsConfig ->
    Blog.Blog
      shareProjectRef
      blogTitle
      description
      postsByTime
      posts
      htmlPosts
      subscribers
      cloudEnvironment
      serviceName
      theme
      guid1
      emailNotificationsConfig

Blog.htmlMailPost : EmailNotificationsConfig -> Blog -> Post ->{Remote} Mail
Blog.htmlMailPost config b p =
  notification = NewPostEmailNotification b p
  Mail.new
    (Blog.personalizations b)
    (senderEmail config)
    (NewPostEmailNotification.subject notification)
    [toHtmlMailContent config notification]

Blog.htmlPosts : Blog -> OrderedTable Slug Html
Blog.htmlPosts = cases Blog.Blog _ _ _ _ _ htmlPosts _ _ _ _ _ _ -> htmlPosts

Blog.htmlPosts.modify :
  (OrderedTable Slug Html ->{g} OrderedTable Slug Html) -> Blog ->{g} Blog
Blog.htmlPosts.modify f = cases
  Blog.Blog
    shareProjectRef
    blogTitle
    description
    postsByTime
    posts
    htmlPosts
    subscribers
    cloudEnvironment
    serviceName
    theme
    guid
    emailNotificationsConfig ->
    Blog.Blog
      shareProjectRef
      blogTitle
      description
      postsByTime
      posts
      (f htmlPosts)
      subscribers
      cloudEnvironment
      serviceName
      theme
      guid
      emailNotificationsConfig

Blog.htmlPosts.set : OrderedTable Slug Html -> Blog -> Blog
Blog.htmlPosts.set htmlPosts1 = cases
  Blog.Blog
    shareProjectRef
    blogTitle
    description
    postsByTime
    posts
    _
    subscribers
    cloudEnvironment
    serviceName
    theme
    guid
    emailNotificationsConfig ->
    Blog.Blog
      shareProjectRef
      blogTitle
      description
      postsByTime
      posts
      htmlPosts1
      subscribers
      cloudEnvironment
      serviceName
      theme
      guid
      emailNotificationsConfig

Blog.isEmailNotificationEnabled : Blog ->{Config} Boolean
Blog.isEmailNotificationEnabled blog =
  isSome (Optional.zip getSendgridApiKey() (emailNotificationsConfig blog))

Blog.latestPostSlug : Blog ->{Remote} Optional Slug
Blog.latestPostSlug blog =
  postsByTime blog |> OrderedTable.min |> Optional.map at2

Blog.latestPostSlug.doc : Doc
Blog.latestPostSlug.doc =
  {{ Returns the {type Slug} of the latest {type Post} in the {type Blog}. }}

Blog.link_ : [Attribute] -> Text -> [Html] ->{Route} Html
Blog.link_ attrs href_ children =
  use List ++
  a (attrs ++ [href href_]) children

Blog.link_.doc : Doc
Blog.link_.doc =
  {{
  A helper function for creating an HTML link with the given attributes, href,
  and children.
  }}

Blog.listPosts : Blog ->{Remote} [Post]
Blog.listPosts blog =
  OrderedTable.toStream (posts blog)
    |> unison_base_3_21_0.data.Stream.map at2
    |> toList!

Blog.listPosts.doc : Doc
Blog.listPosts.doc =
  {{
  Returns a list of all {type Post}s in the {type Blog}, as a {type Remote}
  action.
  }}

Blog.listPostsCloud : Blog ->{IO, Exception} [Post]
Blog.listPostsCloud blog =
  force (Cloud.main do Cloud.submit (cloudEnvironment blog) do listPosts blog)

Blog.listPostsCloud.doc : Doc
Blog.listPostsCloud.doc =
  {{
  Returns a list of all {type Post}s in the {type Blog} as an {type IO} action.
  }}

Blog.makeBlog :
  Environment -> Database -> Slug -> ProjectRef -> Text -> Text -> Blog
Blog.makeBlog env db serviceName projectRef title guid =
  use OrderedTable named
  use Slug toText
  use Text ++
  use Universal ordering
  slugByTime =
    toText serviceName ++ "_slug_by_time_A699F661-6DBA-468B-869A-781621E296DD"
  postBySlug =
    toText serviceName ++ "_posts_by_slug_A699F661-6DBA-468B-869A-781621E296DD"
  htmlBySlug =
    toText serviceName ++ "_html_by_slug_A699F661-6DBA-468B-869A-781621E296DD"
  subscribersByEmail =
    toText serviceName ++ "_subscribers_A699F661-6DBA-468B-869A-781621E296DD"
  postsByTime = named db slugByTime (flip ordering)
  posts = named db postBySlug ordering
  htmlPosts = named db htmlBySlug ordering
  subscribers = named db subscribersByEmail ordering
  Blog.Blog
    projectRef
    title
    ""
    postsByTime
    posts
    htmlPosts
    subscribers
    env
    serviceName
    unisonLight
    guid
    None

Blog.makePost :
  Blog
  -> Text
  -> Text
  -> BlogAuthor
  -> NamespacePath
  ->{Exception, Remote} Post
Blog.makePost blog title summary author path =
  slug = Slug.fromText title
  match getPost slug blog with
    None ->
      randomly do
        guid = UUID.toText version4()
        timestamp = now!
        Post
          (Metadata title summary [author] (atUTC timestamp) [] slug guid) path
    Some post ->
      post
        |> metadata.modify
             (Metadata.title.set title
               >> Metadata.summary.set summary
               >> authors.set [author])
        |> docPath.set path

Blog.makePost.doc : Doc
Blog.makePost.doc =
  {{
  Either create a new {type Post} in a {type Blog} with the given title,
  summary, {type BlogAuthor}, and {type NamespacePath} (for retrieving its
  {type Doc} from Unison Share), or retrieve an existing post with the same
  {type Slug}. The {type Slug} is determined by the title of the post. The
  title, summary, author, and Share namespace path are updated if the post
  already exists and the new values are different from the existing ones.
  }}

Blog.new : Text -> Text -> ProjectRef ->{Exception, Cloud} Blog
Blog.new slug title shareProject =
  use Text ++
  env = Environment.named slug
  db = Database.named slug
  Database.assign db env
  serviceSlug = Slug slug
  cell = Cell.named db (slug ++ "_blog_guid") None
  Cloud.submit env do match Cell.read cell with
    None      ->
      blog = randomly do fromCloudEnv env db serviceSlug shareProject title
      transact db do Cell.write.tx cell (Some (Blog.guid blog))
      blog
    Some guid -> makeBlog env db serviceSlug shareProject title guid

Blog.personalizations : Blog ->{Remote} [Personalization]
Blog.personalizations blog =
  OrderedTable.toStream (subscribers blog)
    |> (unison_base_3_21_0.data.Stream.map cases
         (email, name) ->
           Personalization.for
             (List.Nonempty.singleton (MailAddress email name)))
    |> toList!

Blog.personalizations.doc : Doc
Blog.personalizations.doc =
  {{
  Returns a list of {type Personalization}s for the email subscribers of the
  {type Blog}, for use in sending email updates.
  }}

Blog.posts : Blog -> OrderedTable Slug Post
Blog.posts = cases Blog.Blog _ _ _ _ posts _ _ _ _ _ _ _ -> posts

Blog.posts.modify :
  (OrderedTable Slug Post ->{g} OrderedTable Slug Post) -> Blog ->{g} Blog
Blog.posts.modify f = cases
  Blog.Blog
    shareProjectRef
    blogTitle
    description
    postsByTime
    posts
    htmlPosts
    subscribers
    cloudEnvironment
    serviceName
    theme
    guid
    emailNotificationsConfig ->
    Blog.Blog
      shareProjectRef
      blogTitle
      description
      postsByTime
      (f posts)
      htmlPosts
      subscribers
      cloudEnvironment
      serviceName
      theme
      guid
      emailNotificationsConfig

Blog.posts.set : OrderedTable Slug Post -> Blog -> Blog
Blog.posts.set posts1 = cases
  Blog.Blog
    shareProjectRef
    blogTitle
    description
    postsByTime
    _
    htmlPosts
    subscribers
    cloudEnvironment
    serviceName
    theme
    guid
    emailNotificationsConfig ->
    Blog.Blog
      shareProjectRef
      blogTitle
      description
      postsByTime
      posts1
      htmlPosts
      subscribers
      cloudEnvironment
      serviceName
      theme
      guid
      emailNotificationsConfig

Blog.postsByTime : Blog -> OrderedTable Instant Slug
Blog.postsByTime = cases
  Blog.Blog _ _ _ postsByTime _ _ _ _ _ _ _ _ -> postsByTime

Blog.postsByTime.modify :
  (OrderedTable Instant Slug ->{g} OrderedTable Instant Slug)
  -> Blog
  ->{g} Blog
Blog.postsByTime.modify f = cases
  Blog.Blog
    shareProjectRef
    blogTitle
    description
    postsByTime
    posts
    htmlPosts
    subscribers
    cloudEnvironment
    serviceName
    theme
    guid
    emailNotificationsConfig ->
    Blog.Blog
      shareProjectRef
      blogTitle
      description
      (f postsByTime)
      posts
      htmlPosts
      subscribers
      cloudEnvironment
      serviceName
      theme
      guid
      emailNotificationsConfig

Blog.postsByTime.set : OrderedTable Instant Slug -> Blog -> Blog
Blog.postsByTime.set postsByTime1 = cases
  Blog.Blog
    shareProjectRef
    blogTitle
    description
    _
    posts
    htmlPosts
    subscribers
    cloudEnvironment
    serviceName
    theme
    guid
    emailNotificationsConfig ->
    Blog.Blog
      shareProjectRef
      blogTitle
      description
      postsByTime1
      posts
      htmlPosts
      subscribers
      cloudEnvironment
      serviceName
      theme
      guid
      emailNotificationsConfig

Blog.publishPost : Blog -> Post ->{Config, Exception, Storage, Http, Remote} ()
Blog.publishPost b post =
  use OrderedTable.write tx
  branchRef = BranchRef "main"
  html =
    fetchDoc (shareProjectRef b) branchRef (docPath post)
      |> List.head
      |> toGenericExceptionWith
           "I didn't find a Doc on Share at this project, branch, and path"
           (shareProjectRef b, branchRef, docPath post)
      |> ShareDoc.toHtml
           (Linked
             (toShareURI (shareProjectRef b) branchRef
               >> unison_base_3_21_0.IO.net.URI.toText))
  randomly do
    transact.random (OrderedTable.database (posts b)) do
      slug = Metadata.slug (Post.metadata post)
      tx (postsByTime b) (Post.key post) slug
      tx (posts b) slug post
      tx (htmlPosts b) slug html
  match Optional.zip
    (Config.lookup "sendgrid_api_key") (emailNotificationsConfig b) with
    Some (apiKey, config) ->
      base_2_14_0.ignore
        (Mail.send (APIKey apiKey) (htmlMailPost config b post))
    _ -> ()

Blog.publishPost.doc : Doc
Blog.publishPost.doc =
  {{ Publishes the given {type Post} to the given {type Blog}. }}

Blog.removeSubscriber : Blog -> MailAddress ->{Exception, Cloud} ()
Blog.removeSubscriber blog = cases
  MailAddress email name ->
    Cloud.submit (cloudEnvironment blog) do
      randomly do
        transact.random (OrderedTable.database (subscribers blog)) do
          OrderedTable.delete.tx (subscribers blog) email

Blog.removeSubscriber.doc : Doc
Blog.removeSubscriber.doc =
  {{
  Removes the given {type MailAddress} from the email subscribers of the
  {type Blog}.
  
  This will remove any subscriber with the given email address, regardless of
  the name associated with the email address.
  }}

Blog.renderFrontPage : Blog -> Html
Blog.renderFrontPage blog = h1 [] [hojberg_html_2_6_0.text (blogTitle blog)]

Blog.renderFrontPage.doc : Doc
Blog.renderFrontPage.doc =
  {{ Renders the front page of the {type Blog} as an {type Html} element. }}

Blog.routes.allPostsRoute : Blog -> '{Route, Config, Exception, Remote, Log} ()
Blog.routes.allPostsRoute blog = do
  noCapture GET (Parser.s "posts")
  info "200 | GET /posts" []
  blogContext = BlogContext.blogContext blog
  ok.html (blogContext |> allPostsPage |> toHtmlDocument blogContext)

Blog.routes.allPostsRoute.doc : Doc
Blog.routes.allPostsRoute.doc =
  {{
  A {type Route} that serves a list of all {type Post}s in the {type Blog}, as
  a web page.
  }}

Blog.routes.homeRoute : Blog -> '{Route, Config, Exception, Remote, Log} ()
Blog.routes.homeRoute blog =
  do
    noCapture GET uriParser.Parser.root
    blogContext = BlogContext.blogContext blog
    match latestPostSlug blog with
      Some s ->
        info "200 | GET /" [("latestPostSlug", Slug.toText s)]
        match postPage blogContext s with
          Success p  -> ok.html p
          NotFound p -> notFound.html p
      None ->
        info "404 | GET /" [("latestPostSlug", "no posts found")]
        notFound.html
          (toHtmlDocument blogContext (notFoundPage "Post not found"))

Blog.routes.homeRoute.doc : Doc
Blog.routes.homeRoute.doc =
  {{ A {type Route} that serves the home page of the {type Blog}. }}

Blog.routes.notFoundRoute : Blog -> '{Route, Config, Exception, Remote, Log} ()
Blog.routes.notFoundRoute blog = do
  use Text ++
  path = route GET restAsText
  info ("404 | GET " ++ path) []
  message = "Couldn't find a page matching /" ++ path
  blogContext = BlogContext.blogContext blog
  notFound.html (toHtmlDocument blogContext (notFoundPage message))

Blog.routes.postRoute : Blog -> '{Route, Config, Exception, Remote, Log} ()
Blog.routes.postRoute blog = do
  use Parser /
  use Slug toText
  slug = Slug.fromText (route GET (Parser.s "posts" / Parser.text))
  blogContext = BlogContext.blogContext blog
  match postPage blogContext slug with
    Success p  ->
      info "200 | GET /post/:slug" [("slug", toText slug)]
      ok.html p
    NotFound p ->
      info "404 | GET /post/:slug" [("slug", toText slug)]
      notFound.html p

Blog.routes.postRoute.doc : Doc
Blog.routes.postRoute.doc =
  {{
  A {type Route} that serves a {type Post} with the given {type Slug} as a web
  page.
  }}

Blog.routes.subscribeRoute :
  Blog -> '{Route, Config, Exception, Remote, Log} ()
Blog.routes.subscribeRoute blog =
  do
    noCapture POST (Parser.s "subscribe")
    if Blog.isEmailNotificationEnabled blog then
      subscriber = decodeJson Subscriber.decode
      subscribe blog subscriber
      info "200 | POST /subscribe" []
      ok.text "subscribed"
    else
      info
        "404 | POST /subscribe"
        [ ( "subscription"
          , "Requires EmailNotificationConfig and sendgrid_api_key"
          )
        ]
      notFound.text "Subscription is not supported."

Blog.rssFeedRoute : Blog -> '{Route, Exception, Remote} ()
Blog.rssFeedRoute blog = do
  noCapture GET (Parser.s "rss")
  baseURI = Blog.baseURI()
  respond.ok (Text.toUtf8 (rssFeedPage baseURI blog))

Blog.rssFeedRoute.doc : Doc
Blog.rssFeedRoute.doc =
  {{ A {type Route} that serves an RSS feed for the {type Blog}. }}

Blog.server :
  Blog -> HttpRequest ->{Config, Exception, Storage, Remote, Log} HttpResponse
Blog.server blog =
  use Route <|>
  Route.run
    (postRoute blog
      <|> allPostsRoute blog
      <|> rssFeedRoute blog
      <|> atomFeedRoute blog
      <|> homeRoute blog
      <|> subscribeRoute blog
      <|> notFoundRoute blog)

Blog.server.doc : Doc
Blog.server.doc =
  {{
  A server for the {type Blog}, which serves the home page, individual
  {type Post}s, and feeds.
  }}

Blog.serviceName : Blog -> Slug
Blog.serviceName = cases
  Blog.Blog _ _ _ _ _ _ _ _ serviceName _ _ _ -> serviceName

Blog.serviceName.modify : (Slug ->{g} Slug) -> Blog ->{g} Blog
Blog.serviceName.modify f = cases
  Blog.Blog
    shareProjectRef
    blogTitle
    description
    postsByTime
    posts
    htmlPosts
    subscribers
    cloudEnvironment
    serviceName
    theme
    guid
    emailNotificationsConfig ->
    Blog.Blog
      shareProjectRef
      blogTitle
      description
      postsByTime
      posts
      htmlPosts
      subscribers
      cloudEnvironment
      (f serviceName)
      theme
      guid
      emailNotificationsConfig

Blog.serviceName.set : Slug -> Blog -> Blog
Blog.serviceName.set serviceName1 = cases
  Blog.Blog
    shareProjectRef
    blogTitle
    description
    postsByTime
    posts
    htmlPosts
    subscribers
    cloudEnvironment
    _
    theme
    guid
    emailNotificationsConfig ->
    Blog.Blog
      shareProjectRef
      blogTitle
      description
      postsByTime
      posts
      htmlPosts
      subscribers
      cloudEnvironment
      serviceName1
      theme
      guid
      emailNotificationsConfig

Blog.setSendgridApiKey : Blog -> Text ->{Exception, Cloud} ()
Blog.setSendgridApiKey blog value =
  env = cloudEnvironment blog
  setValue env "sendgrid_api_key" value

Blog.shareProjectRef : Blog -> ProjectRef
Blog.shareProjectRef = cases
  Blog.Blog shareProjectRef _ _ _ _ _ _ _ _ _ _ _ -> shareProjectRef

Blog.shareProjectRef.modify : (ProjectRef ->{g} ProjectRef) -> Blog ->{g} Blog
Blog.shareProjectRef.modify f = cases
  Blog.Blog
    shareProjectRef
    blogTitle
    description
    postsByTime
    posts
    htmlPosts
    subscribers
    cloudEnvironment
    serviceName
    theme
    guid
    emailNotificationsConfig ->
    Blog.Blog
      (f shareProjectRef)
      blogTitle
      description
      postsByTime
      posts
      htmlPosts
      subscribers
      cloudEnvironment
      serviceName
      theme
      guid
      emailNotificationsConfig

Blog.shareProjectRef.set : ProjectRef -> Blog -> Blog
Blog.shareProjectRef.set shareProjectRef1 = cases
  Blog.Blog
    _
    blogTitle
    description
    postsByTime
    posts
    htmlPosts
    subscribers
    cloudEnvironment
    serviceName
    theme
    guid
    emailNotificationsConfig ->
    Blog.Blog
      shareProjectRef1
      blogTitle
      description
      postsByTime
      posts
      htmlPosts
      subscribers
      cloudEnvironment
      serviceName
      theme
      guid
      emailNotificationsConfig

Blog.subscribe : Blog -> Subscriber ->{Remote} ()
Blog.subscribe blog subscriber =
  OrderedTable.write
    (subscribers blog)
    (Subscriber.email subscriber)
    (Subscriber.name subscriber)

Blog.subscribers : Blog -> OrderedTable Text Text
Blog.subscribers = cases
  Blog.Blog _ _ _ _ _ _ subscribers _ _ _ _ _ -> subscribers

Blog.subscribers.modify :
  (OrderedTable Text Text ->{g} OrderedTable Text Text) -> Blog ->{g} Blog
Blog.subscribers.modify f = cases
  Blog.Blog
    shareProjectRef
    blogTitle
    description
    postsByTime
    posts
    htmlPosts
    subscribers
    cloudEnvironment
    serviceName
    theme
    guid
    emailNotificationsConfig ->
    Blog.Blog
      shareProjectRef
      blogTitle
      description
      postsByTime
      posts
      htmlPosts
      (f subscribers)
      cloudEnvironment
      serviceName
      theme
      guid
      emailNotificationsConfig

Blog.subscribers.set : OrderedTable Text Text -> Blog -> Blog
Blog.subscribers.set subscribers1 = cases
  Blog.Blog
    shareProjectRef
    blogTitle
    description
    postsByTime
    posts
    htmlPosts
    _
    cloudEnvironment
    serviceName
    theme
    guid
    emailNotificationsConfig ->
    Blog.Blog
      shareProjectRef
      blogTitle
      description
      postsByTime
      posts
      htmlPosts
      subscribers1
      cloudEnvironment
      serviceName
      theme
      guid
      emailNotificationsConfig

Blog.theme : Blog -> BlogTheme
Blog.theme = cases Blog.Blog _ _ _ _ _ _ _ _ _ theme _ _ -> theme

Blog.theme.modify : (BlogTheme ->{g} BlogTheme) -> Blog ->{g} Blog
Blog.theme.modify f = cases
  Blog.Blog
    shareProjectRef
    blogTitle
    description
    postsByTime
    posts
    htmlPosts
    subscribers
    cloudEnvironment
    serviceName
    theme
    guid
    emailNotificationsConfig ->
    Blog.Blog
      shareProjectRef
      blogTitle
      description
      postsByTime
      posts
      htmlPosts
      subscribers
      cloudEnvironment
      serviceName
      (f theme)
      guid
      emailNotificationsConfig

Blog.theme.set : BlogTheme -> Blog -> Blog
Blog.theme.set theme1 = cases
  Blog.Blog
    shareProjectRef
    blogTitle
    description
    postsByTime
    posts
    htmlPosts
    subscribers
    cloudEnvironment
    serviceName
    _
    guid
    emailNotificationsConfig ->
    Blog.Blog
      shareProjectRef
      blogTitle
      description
      postsByTime
      posts
      htmlPosts
      subscribers
      cloudEnvironment
      serviceName
      theme1
      guid
      emailNotificationsConfig

Blog.withDescription : Text -> Blog -> Blog
Blog.withDescription = description.set

Blog.withDescription.doc : Doc
Blog.withDescription.doc = {{ Sets the description of the {type Blog}. }}

Blog.withEmailNotificationsConfig : EmailNotificationsConfig -> Blog -> Blog
Blog.withEmailNotificationsConfig config blog =
  emailNotificationsConfig.set (Some config) blog

Blog.withServiceName : Slug -> Blog -> Blog
Blog.withServiceName = serviceName.set

Blog.withServiceName.doc : Doc
Blog.withServiceName.doc = {{ Sets the {type Slug} of the {type Blog}. }}

Blog.withTheme : BlogTheme -> Blog -> Blog
Blog.withTheme = Blog.theme.set

Blog.withTheme.doc : Doc
Blog.withTheme.doc = {{ Sets the theme of the {type Blog}. }}

BlogAuthor.avatar : BlogAuthor -> Optional URI
BlogAuthor.avatar = cases BlogAuthor _ _ avatar _ -> avatar

BlogAuthor.avatar.modify :
  (Optional URI ->{g} Optional URI) -> BlogAuthor ->{g} BlogAuthor
BlogAuthor.avatar.modify f = cases
  BlogAuthor name bio avatar email -> BlogAuthor name bio (f avatar) email

BlogAuthor.avatar.set : Optional URI -> BlogAuthor -> BlogAuthor
BlogAuthor.avatar.set avatar1 = cases
  BlogAuthor name bio _ email -> BlogAuthor name bio avatar1 email

BlogAuthor.bio : BlogAuthor -> Text
BlogAuthor.bio = cases BlogAuthor _ bio _ _ -> bio

BlogAuthor.bio.modify : (Text ->{g} Text) -> BlogAuthor ->{g} BlogAuthor
BlogAuthor.bio.modify f = cases
  BlogAuthor name bio avatar email -> BlogAuthor name (f bio) avatar email

BlogAuthor.bio.set : Text -> BlogAuthor -> BlogAuthor
BlogAuthor.bio.set bio1 = cases
  BlogAuthor name _ avatar email -> BlogAuthor name bio1 avatar email

BlogAuthor.doc : Doc
BlogAuthor.doc =
  {{
  A {type BlogAuthor} is a record type that represents an author of a blog
  post. It has the following fields:
  
  * {{ docLink (docEmbedTermLink do BlogAuthor.name) }} is the name of the
    author.
  * {{ docLink (docEmbedTermLink do bio) }} is a short biography of the author.
  * {{ docLink (docEmbedTermLink do avatar) }} is an optional {type URI} that
    points to an image of the author.
  * {{ docLink (docEmbedTermLink do BlogAuthor.email) }} is the email address
    of the author.
  }}

BlogAuthor.email : BlogAuthor -> Text
BlogAuthor.email = cases BlogAuthor _ _ _ email -> email

BlogAuthor.email.modify : (Text ->{g} Text) -> BlogAuthor ->{g} BlogAuthor
BlogAuthor.email.modify f = cases
  BlogAuthor name bio avatar email -> BlogAuthor name bio avatar (f email)

BlogAuthor.email.set : Text -> BlogAuthor -> BlogAuthor
BlogAuthor.email.set email1 = cases
  BlogAuthor name bio avatar _ -> BlogAuthor name bio avatar email1

BlogAuthor.name : BlogAuthor -> Text
BlogAuthor.name = cases BlogAuthor name _ _ _ -> name

BlogAuthor.name.modify : (Text ->{g} Text) -> BlogAuthor ->{g} BlogAuthor
BlogAuthor.name.modify f = cases
  BlogAuthor name bio avatar email -> BlogAuthor (f name) bio avatar email

BlogAuthor.name.set : Text -> BlogAuthor -> BlogAuthor
BlogAuthor.name.set name1 = cases
  BlogAuthor _ bio avatar email -> BlogAuthor name1 bio avatar email

BlogContext.basePath : BlogContext -> Path
BlogContext.basePath = cases BlogContext _ _ basePath _ -> basePath

BlogContext.basePath.modify :
  (Path ->{g} Path) -> BlogContext ->{g} BlogContext
BlogContext.basePath.modify f = cases
  BlogContext blog now basePath isEmailNotificationEnabled ->
    BlogContext blog now (f basePath) isEmailNotificationEnabled

BlogContext.basePath.set : Path -> BlogContext -> BlogContext
BlogContext.basePath.set basePath1 = cases
  BlogContext blog now _ isEmailNotificationEnabled ->
    BlogContext blog now basePath1 isEmailNotificationEnabled

BlogContext.blog : BlogContext -> Blog
BlogContext.blog = cases BlogContext blog _ _ _ -> blog

BlogContext.blog.modify : (Blog ->{g} Blog) -> BlogContext ->{g} BlogContext
BlogContext.blog.modify f = cases
  BlogContext blog now basePath isEmailNotificationEnabled ->
    BlogContext (f blog) now basePath isEmailNotificationEnabled

BlogContext.blog.set : Blog -> BlogContext -> BlogContext
BlogContext.blog.set blog1 = cases
  BlogContext _ now basePath isEmailNotificationEnabled ->
    BlogContext blog1 now basePath isEmailNotificationEnabled

BlogContext.blogContext : Blog ->{Route, Config, Exception, Remote} BlogContext
BlogContext.blogContext blog =
  BlogContext blog now! Blog.basePath() (Blog.isEmailNotificationEnabled blog)

BlogContext.isEmailNotificationEnabled : BlogContext -> Boolean
BlogContext.isEmailNotificationEnabled = cases
  BlogContext _ _ _ isEmailNotificationEnabled -> isEmailNotificationEnabled

BlogContext.isEmailNotificationEnabled.modify :
  (Boolean ->{g} Boolean) -> BlogContext ->{g} BlogContext
BlogContext.isEmailNotificationEnabled.modify f = cases
  BlogContext blog now basePath isEmailNotificationEnabled ->
    BlogContext blog now basePath (f isEmailNotificationEnabled)

BlogContext.isEmailNotificationEnabled.set :
  Boolean -> BlogContext -> BlogContext
BlogContext.isEmailNotificationEnabled.set isEmailNotificationEnabled1 = cases
  BlogContext blog now basePath _ ->
    BlogContext blog now basePath isEmailNotificationEnabled1

BlogContext.now : BlogContext -> Instant
BlogContext.now = cases BlogContext _ now _ _ -> now

BlogContext.now.modify :
  (Instant ->{g} Instant) -> BlogContext ->{g} BlogContext
BlogContext.now.modify f = cases
  BlogContext blog now basePath isEmailNotificationEnabled ->
    BlogContext blog (f now) basePath isEmailNotificationEnabled

BlogContext.now.set : Instant -> BlogContext -> BlogContext
BlogContext.now.set now1 = cases
  BlogContext blog _ basePath isEmailNotificationEnabled ->
    BlogContext blog now1 basePath isEmailNotificationEnabled

BlogEnv.doc : Doc
BlogEnv.doc =
  {{
  The {type BlogEnv} ability makees it convenient to create and publish posts
  to a {type Blog}. It has operations for declaring and publishing posts, and
  for publishing all the posts in a list.
  
  # Operations
  
    * {publish} - Publish a post to a blog. This operation takes a {type Post}
      and publishes it to the blog, creating a new post if it does not already
      exist, or updating an existing post if it does.
    * {{ docLink (docEmbedTermLink do publishAll) }} - Publish all the posts in
      a list. This operation takes a list of {type Post}s and publishes them to
      the blog.
    * {BlogEnv.post} - Defines a post. This operation takes a title, summary,
      {type BlogAuthor}, and {type NamespacePath} (for retrieving its
      {type Doc} from Unison Share). If a post with the same {type Slug}
      already exists, it is retrieved and updated with the new values.
      Otherwise, a new post is created.
  
  # Example usage
  
    Here's an example of how to use the {type BlogEnv} ability to create and
    publish a post:
    
        @source{sampleBlog.build}
  }}

BlogEnv.publishAll : [Post] ->{BlogEnv} ()
BlogEnv.publishAll = unison_base_3_21_0.data.List.foreach publish

BlogEnv.publishAll.doc : Doc
BlogEnv.publishAll.doc = {{ Publish all the posts in a list. }}

BlogEnv.withBlog :
  Blog
  -> '{Config, Exception, Storage, Http, Remote, BlogEnv} a
  ->{Exception, Cloud} a
BlogEnv.withBlog blog p =
  h = cases
    { a } -> a
    { publish post -> resume } -> handle resume (publishPost blog post) with h
    { BlogEnv.post title author path -> resume } ->
      handle resume (makePost blog title "" author path) with h
  Cloud.submit (cloudEnvironment blog) do handle p() with h

BlogEnv.withBlog.doc : Doc
BlogEnv.withBlog.doc =
  {{
  Run a {type BlogEnv} computation in the context of a {type Blog}. This
  operation takes a {type Blog} and a computation, and provides the
  {type BlogEnv} ability to the computation, allowing it to create and publish
  posts to the blog.
  
  # Example usage
  
    Here's an example of how to use the {{
    docLink (docEmbedTermLink do withBlog) }} operation to create and publish a
    post:
    
        @source{sampleBlog.build}
  }}

BlogTheme.BlogColors.background : BlogColors -> BlogTheme.Color
BlogTheme.BlogColors.background = cases
  BlogColors background _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ ->
    background

BlogTheme.BlogColors.background.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> BlogColors ->{g} BlogColors
BlogTheme.BlogColors.background.modify f = cases
  BlogColors
    background
    text
    textSubdued
    textVerySubdued
    textEmphasized
    icon
    iconSubdued
    iconEmphasized
    border
    borderSubdued
    borderEmphasized
    divider
    container
    containerSubdued
    interactive
    interactiveHover
    focusBorder
    focusOutline
    infoContainerSubdued
    element
    elementSubdued
    elementEmphasized
    button
    buttonText
    buttonEmphasized
    buttonTextEmphsaized ->
    BlogColors
      (f background)
      text
      textSubdued
      textVerySubdued
      textEmphasized
      icon
      iconSubdued
      iconEmphasized
      border
      borderSubdued
      borderEmphasized
      divider
      container
      containerSubdued
      interactive
      interactiveHover
      focusBorder
      focusOutline
      infoContainerSubdued
      element
      elementSubdued
      elementEmphasized
      button
      buttonText
      buttonEmphasized
      buttonTextEmphsaized

BlogTheme.BlogColors.background.set :
  BlogTheme.Color -> BlogColors -> BlogColors
BlogTheme.BlogColors.background.set background1 = cases
  BlogColors
    _
    text
    textSubdued
    textVerySubdued
    textEmphasized
    icon
    iconSubdued
    iconEmphasized
    border
    borderSubdued
    borderEmphasized
    divider
    container
    containerSubdued
    interactive
    interactiveHover
    focusBorder
    focusOutline
    infoContainerSubdued
    element
    elementSubdued
    elementEmphasized
    button
    buttonText
    buttonEmphasized
    buttonTextEmphsaized ->
    BlogColors
      background1
      text
      textSubdued
      textVerySubdued
      textEmphasized
      icon
      iconSubdued
      iconEmphasized
      border
      borderSubdued
      borderEmphasized
      divider
      container
      containerSubdued
      interactive
      interactiveHover
      focusBorder
      focusOutline
      infoContainerSubdued
      element
      elementSubdued
      elementEmphasized
      button
      buttonText
      buttonEmphasized
      buttonTextEmphsaized

BlogTheme.BlogColors.border : BlogColors -> BlogTheme.Color
BlogTheme.BlogColors.border = cases
  BlogColors _ _ _ _ _ _ _ _ border _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ -> border

BlogTheme.BlogColors.border.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> BlogColors ->{g} BlogColors
BlogTheme.BlogColors.border.modify f = cases
  BlogColors
    background
    text
    textSubdued
    textVerySubdued
    textEmphasized
    icon
    iconSubdued
    iconEmphasized
    border
    borderSubdued
    borderEmphasized
    divider
    container
    containerSubdued
    interactive
    interactiveHover
    focusBorder
    focusOutline
    infoContainerSubdued
    element
    elementSubdued
    elementEmphasized
    button
    buttonText
    buttonEmphasized
    buttonTextEmphsaized ->
    BlogColors
      background
      text
      textSubdued
      textVerySubdued
      textEmphasized
      icon
      iconSubdued
      iconEmphasized
      (f border)
      borderSubdued
      borderEmphasized
      divider
      container
      containerSubdued
      interactive
      interactiveHover
      focusBorder
      focusOutline
      infoContainerSubdued
      element
      elementSubdued
      elementEmphasized
      button
      buttonText
      buttonEmphasized
      buttonTextEmphsaized

BlogTheme.BlogColors.border.set : BlogTheme.Color -> BlogColors -> BlogColors
BlogTheme.BlogColors.border.set border1 = cases
  BlogColors
    background
    text
    textSubdued
    textVerySubdued
    textEmphasized
    icon
    iconSubdued
    iconEmphasized
    _
    borderSubdued
    borderEmphasized
    divider
    container
    containerSubdued
    interactive
    interactiveHover
    focusBorder
    focusOutline
    infoContainerSubdued
    element
    elementSubdued
    elementEmphasized
    button
    buttonText
    buttonEmphasized
    buttonTextEmphsaized ->
    BlogColors
      background
      text
      textSubdued
      textVerySubdued
      textEmphasized
      icon
      iconSubdued
      iconEmphasized
      border1
      borderSubdued
      borderEmphasized
      divider
      container
      containerSubdued
      interactive
      interactiveHover
      focusBorder
      focusOutline
      infoContainerSubdued
      element
      elementSubdued
      elementEmphasized
      button
      buttonText
      buttonEmphasized
      buttonTextEmphsaized

BlogTheme.BlogColors.borderEmphasized : BlogColors -> BlogTheme.Color
BlogTheme.BlogColors.borderEmphasized = cases
  BlogColors _ _ _ _ _ _ _ _ _ _ borderEmphasized _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ ->
    borderEmphasized

BlogTheme.BlogColors.borderEmphasized.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> BlogColors ->{g} BlogColors
BlogTheme.BlogColors.borderEmphasized.modify f = cases
  BlogColors
    background
    text
    textSubdued
    textVerySubdued
    textEmphasized
    icon
    iconSubdued
    iconEmphasized
    border
    borderSubdued
    borderEmphasized
    divider
    container
    containerSubdued
    interactive
    interactiveHover
    focusBorder
    focusOutline
    infoContainerSubdued
    element
    elementSubdued
    elementEmphasized
    button
    buttonText
    buttonEmphasized
    buttonTextEmphsaized ->
    BlogColors
      background
      text
      textSubdued
      textVerySubdued
      textEmphasized
      icon
      iconSubdued
      iconEmphasized
      border
      borderSubdued
      (f borderEmphasized)
      divider
      container
      containerSubdued
      interactive
      interactiveHover
      focusBorder
      focusOutline
      infoContainerSubdued
      element
      elementSubdued
      elementEmphasized
      button
      buttonText
      buttonEmphasized
      buttonTextEmphsaized

BlogTheme.BlogColors.borderEmphasized.set :
  BlogTheme.Color -> BlogColors -> BlogColors
BlogTheme.BlogColors.borderEmphasized.set borderEmphasized1 = cases
  BlogColors
    background
    text
    textSubdued
    textVerySubdued
    textEmphasized
    icon
    iconSubdued
    iconEmphasized
    border
    borderSubdued
    _
    divider
    container
    containerSubdued
    interactive
    interactiveHover
    focusBorder
    focusOutline
    infoContainerSubdued
    element
    elementSubdued
    elementEmphasized
    button
    buttonText
    buttonEmphasized
    buttonTextEmphsaized ->
    BlogColors
      background
      text
      textSubdued
      textVerySubdued
      textEmphasized
      icon
      iconSubdued
      iconEmphasized
      border
      borderSubdued
      borderEmphasized1
      divider
      container
      containerSubdued
      interactive
      interactiveHover
      focusBorder
      focusOutline
      infoContainerSubdued
      element
      elementSubdued
      elementEmphasized
      button
      buttonText
      buttonEmphasized
      buttonTextEmphsaized

BlogTheme.BlogColors.borderSubdued : BlogColors -> BlogTheme.Color
BlogTheme.BlogColors.borderSubdued = cases
  BlogColors _ _ _ _ _ _ _ _ _ borderSubdued _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ ->
    borderSubdued

BlogTheme.BlogColors.borderSubdued.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> BlogColors ->{g} BlogColors
BlogTheme.BlogColors.borderSubdued.modify f = cases
  BlogColors
    background
    text
    textSubdued
    textVerySubdued
    textEmphasized
    icon
    iconSubdued
    iconEmphasized
    border
    borderSubdued
    borderEmphasized
    divider
    container
    containerSubdued
    interactive
    interactiveHover
    focusBorder
    focusOutline
    infoContainerSubdued
    element
    elementSubdued
    elementEmphasized
    button
    buttonText
    buttonEmphasized
    buttonTextEmphsaized ->
    BlogColors
      background
      text
      textSubdued
      textVerySubdued
      textEmphasized
      icon
      iconSubdued
      iconEmphasized
      border
      (f borderSubdued)
      borderEmphasized
      divider
      container
      containerSubdued
      interactive
      interactiveHover
      focusBorder
      focusOutline
      infoContainerSubdued
      element
      elementSubdued
      elementEmphasized
      button
      buttonText
      buttonEmphasized
      buttonTextEmphsaized

BlogTheme.BlogColors.borderSubdued.set :
  BlogTheme.Color -> BlogColors -> BlogColors
BlogTheme.BlogColors.borderSubdued.set borderSubdued1 = cases
  BlogColors
    background
    text
    textSubdued
    textVerySubdued
    textEmphasized
    icon
    iconSubdued
    iconEmphasized
    border
    _
    borderEmphasized
    divider
    container
    containerSubdued
    interactive
    interactiveHover
    focusBorder
    focusOutline
    infoContainerSubdued
    element
    elementSubdued
    elementEmphasized
    button
    buttonText
    buttonEmphasized
    buttonTextEmphsaized ->
    BlogColors
      background
      text
      textSubdued
      textVerySubdued
      textEmphasized
      icon
      iconSubdued
      iconEmphasized
      border
      borderSubdued1
      borderEmphasized
      divider
      container
      containerSubdued
      interactive
      interactiveHover
      focusBorder
      focusOutline
      infoContainerSubdued
      element
      elementSubdued
      elementEmphasized
      button
      buttonText
      buttonEmphasized
      buttonTextEmphsaized

BlogTheme.BlogColors.button : BlogColors -> BlogTheme.Color
BlogTheme.BlogColors.button = cases
  BlogColors _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ button _ _ _ -> button

BlogTheme.BlogColors.button.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> BlogColors ->{g} BlogColors
BlogTheme.BlogColors.button.modify f = cases
  BlogColors
    background
    text
    textSubdued
    textVerySubdued
    textEmphasized
    icon
    iconSubdued
    iconEmphasized
    border
    borderSubdued
    borderEmphasized
    divider
    container
    containerSubdued
    interactive
    interactiveHover
    focusBorder
    focusOutline
    infoContainerSubdued
    element
    elementSubdued
    elementEmphasized
    button
    buttonText
    buttonEmphasized
    buttonTextEmphsaized ->
    BlogColors
      background
      text
      textSubdued
      textVerySubdued
      textEmphasized
      icon
      iconSubdued
      iconEmphasized
      border
      borderSubdued
      borderEmphasized
      divider
      container
      containerSubdued
      interactive
      interactiveHover
      focusBorder
      focusOutline
      infoContainerSubdued
      element
      elementSubdued
      elementEmphasized
      (f button)
      buttonText
      buttonEmphasized
      buttonTextEmphsaized

BlogTheme.BlogColors.button.set : BlogTheme.Color -> BlogColors -> BlogColors
BlogTheme.BlogColors.button.set button1 = cases
  BlogColors
    background
    text
    textSubdued
    textVerySubdued
    textEmphasized
    icon
    iconSubdued
    iconEmphasized
    border
    borderSubdued
    borderEmphasized
    divider
    container
    containerSubdued
    interactive
    interactiveHover
    focusBorder
    focusOutline
    infoContainerSubdued
    element
    elementSubdued
    elementEmphasized
    _
    buttonText
    buttonEmphasized
    buttonTextEmphsaized ->
    BlogColors
      background
      text
      textSubdued
      textVerySubdued
      textEmphasized
      icon
      iconSubdued
      iconEmphasized
      border
      borderSubdued
      borderEmphasized
      divider
      container
      containerSubdued
      interactive
      interactiveHover
      focusBorder
      focusOutline
      infoContainerSubdued
      element
      elementSubdued
      elementEmphasized
      button1
      buttonText
      buttonEmphasized
      buttonTextEmphsaized

BlogTheme.BlogColors.buttonEmphasized : BlogColors -> BlogTheme.Color
BlogTheme.BlogColors.buttonEmphasized = cases
  BlogColors _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ buttonEmphasized _ ->
    buttonEmphasized

BlogTheme.BlogColors.buttonEmphasized.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> BlogColors ->{g} BlogColors
BlogTheme.BlogColors.buttonEmphasized.modify f = cases
  BlogColors
    background
    text
    textSubdued
    textVerySubdued
    textEmphasized
    icon
    iconSubdued
    iconEmphasized
    border
    borderSubdued
    borderEmphasized
    divider
    container
    containerSubdued
    interactive
    interactiveHover
    focusBorder
    focusOutline
    infoContainerSubdued
    element
    elementSubdued
    elementEmphasized
    button
    buttonText
    buttonEmphasized
    buttonTextEmphsaized ->
    BlogColors
      background
      text
      textSubdued
      textVerySubdued
      textEmphasized
      icon
      iconSubdued
      iconEmphasized
      border
      borderSubdued
      borderEmphasized
      divider
      container
      containerSubdued
      interactive
      interactiveHover
      focusBorder
      focusOutline
      infoContainerSubdued
      element
      elementSubdued
      elementEmphasized
      button
      buttonText
      (f buttonEmphasized)
      buttonTextEmphsaized

BlogTheme.BlogColors.buttonEmphasized.set :
  BlogTheme.Color -> BlogColors -> BlogColors
BlogTheme.BlogColors.buttonEmphasized.set buttonEmphasized1 = cases
  BlogColors
    background
    text
    textSubdued
    textVerySubdued
    textEmphasized
    icon
    iconSubdued
    iconEmphasized
    border
    borderSubdued
    borderEmphasized
    divider
    container
    containerSubdued
    interactive
    interactiveHover
    focusBorder
    focusOutline
    infoContainerSubdued
    element
    elementSubdued
    elementEmphasized
    button
    buttonText
    _
    buttonTextEmphsaized ->
    BlogColors
      background
      text
      textSubdued
      textVerySubdued
      textEmphasized
      icon
      iconSubdued
      iconEmphasized
      border
      borderSubdued
      borderEmphasized
      divider
      container
      containerSubdued
      interactive
      interactiveHover
      focusBorder
      focusOutline
      infoContainerSubdued
      element
      elementSubdued
      elementEmphasized
      button
      buttonText
      buttonEmphasized1
      buttonTextEmphsaized

BlogTheme.BlogColors.buttonText : BlogColors -> BlogTheme.Color
BlogTheme.BlogColors.buttonText = cases
  BlogColors _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ buttonText _ _ ->
    buttonText

BlogTheme.BlogColors.buttonText.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> BlogColors ->{g} BlogColors
BlogTheme.BlogColors.buttonText.modify f = cases
  BlogColors
    background
    text
    textSubdued
    textVerySubdued
    textEmphasized
    icon
    iconSubdued
    iconEmphasized
    border
    borderSubdued
    borderEmphasized
    divider
    container
    containerSubdued
    interactive
    interactiveHover
    focusBorder
    focusOutline
    infoContainerSubdued
    element
    elementSubdued
    elementEmphasized
    button
    buttonText
    buttonEmphasized
    buttonTextEmphsaized ->
    BlogColors
      background
      text
      textSubdued
      textVerySubdued
      textEmphasized
      icon
      iconSubdued
      iconEmphasized
      border
      borderSubdued
      borderEmphasized
      divider
      container
      containerSubdued
      interactive
      interactiveHover
      focusBorder
      focusOutline
      infoContainerSubdued
      element
      elementSubdued
      elementEmphasized
      button
      (f buttonText)
      buttonEmphasized
      buttonTextEmphsaized

BlogTheme.BlogColors.buttonText.set :
  BlogTheme.Color -> BlogColors -> BlogColors
BlogTheme.BlogColors.buttonText.set buttonText1 = cases
  BlogColors
    background
    text
    textSubdued
    textVerySubdued
    textEmphasized
    icon
    iconSubdued
    iconEmphasized
    border
    borderSubdued
    borderEmphasized
    divider
    container
    containerSubdued
    interactive
    interactiveHover
    focusBorder
    focusOutline
    infoContainerSubdued
    element
    elementSubdued
    elementEmphasized
    button
    _
    buttonEmphasized
    buttonTextEmphsaized ->
    BlogColors
      background
      text
      textSubdued
      textVerySubdued
      textEmphasized
      icon
      iconSubdued
      iconEmphasized
      border
      borderSubdued
      borderEmphasized
      divider
      container
      containerSubdued
      interactive
      interactiveHover
      focusBorder
      focusOutline
      infoContainerSubdued
      element
      elementSubdued
      elementEmphasized
      button
      buttonText1
      buttonEmphasized
      buttonTextEmphsaized

BlogTheme.BlogColors.buttonTextEmphasized : BlogColors -> BlogTheme.Color
BlogTheme.BlogColors.buttonTextEmphasized = cases
  BlogColors
    _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ buttonTextEmphsaized ->
    buttonTextEmphsaized

BlogTheme.BlogColors.buttonTextEmphasized.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> BlogColors ->{g} BlogColors
BlogTheme.BlogColors.buttonTextEmphasized.modify f = cases
  BlogColors
    background
    text
    textSubdued
    textVerySubdued
    textEmphasized
    icon
    iconSubdued
    iconEmphasized
    border
    borderSubdued
    borderEmphasized
    divider
    container
    containerSubdued
    interactive
    interactiveHover
    focusBorder
    focusOutline
    infoContainerSubdued
    element
    elementSubdued
    elementEmphasized
    button
    buttonText
    buttonEmphasized
    buttonTextEmphsaized ->
    BlogColors
      background
      text
      textSubdued
      textVerySubdued
      textEmphasized
      icon
      iconSubdued
      iconEmphasized
      border
      borderSubdued
      borderEmphasized
      divider
      container
      containerSubdued
      interactive
      interactiveHover
      focusBorder
      focusOutline
      infoContainerSubdued
      element
      elementSubdued
      elementEmphasized
      button
      buttonText
      buttonEmphasized
      (f buttonTextEmphsaized)

BlogTheme.BlogColors.buttonTextEmphasized.set :
  BlogTheme.Color -> BlogColors -> BlogColors
BlogTheme.BlogColors.buttonTextEmphasized.set buttonTextEmphsaized1 = cases
  BlogColors
    background
    text
    textSubdued
    textVerySubdued
    textEmphasized
    icon
    iconSubdued
    iconEmphasized
    border
    borderSubdued
    borderEmphasized
    divider
    container
    containerSubdued
    interactive
    interactiveHover
    focusBorder
    focusOutline
    infoContainerSubdued
    element
    elementSubdued
    elementEmphasized
    button
    buttonText
    buttonEmphasized
    _ ->
    BlogColors
      background
      text
      textSubdued
      textVerySubdued
      textEmphasized
      icon
      iconSubdued
      iconEmphasized
      border
      borderSubdued
      borderEmphasized
      divider
      container
      containerSubdued
      interactive
      interactiveHover
      focusBorder
      focusOutline
      infoContainerSubdued
      element
      elementSubdued
      elementEmphasized
      button
      buttonText
      buttonEmphasized
      buttonTextEmphsaized1

BlogTheme.BlogColors.container : BlogColors -> BlogTheme.Color
BlogTheme.BlogColors.container = cases
  BlogColors _ _ _ _ _ _ _ _ _ _ _ _ container _ _ _ _ _ _ _ _ _ _ _ _ _ ->
    container

BlogTheme.BlogColors.container.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> BlogColors ->{g} BlogColors
BlogTheme.BlogColors.container.modify f = cases
  BlogColors
    background
    text
    textSubdued
    textVerySubdued
    textEmphasized
    icon
    iconSubdued
    iconEmphasized
    border
    borderSubdued
    borderEmphasized
    divider
    container
    containerSubdued
    interactive
    interactiveHover
    focusBorder
    focusOutline
    infoContainerSubdued
    element
    elementSubdued
    elementEmphasized
    button
    buttonText
    buttonEmphasized
    buttonTextEmphsaized ->
    BlogColors
      background
      text
      textSubdued
      textVerySubdued
      textEmphasized
      icon
      iconSubdued
      iconEmphasized
      border
      borderSubdued
      borderEmphasized
      divider
      (f container)
      containerSubdued
      interactive
      interactiveHover
      focusBorder
      focusOutline
      infoContainerSubdued
      element
      elementSubdued
      elementEmphasized
      button
      buttonText
      buttonEmphasized
      buttonTextEmphsaized

BlogTheme.BlogColors.container.set :
  BlogTheme.Color -> BlogColors -> BlogColors
BlogTheme.BlogColors.container.set container1 = cases
  BlogColors
    background
    text
    textSubdued
    textVerySubdued
    textEmphasized
    icon
    iconSubdued
    iconEmphasized
    border
    borderSubdued
    borderEmphasized
    divider
    _
    containerSubdued
    interactive
    interactiveHover
    focusBorder
    focusOutline
    infoContainerSubdued
    element
    elementSubdued
    elementEmphasized
    button
    buttonText
    buttonEmphasized
    buttonTextEmphsaized ->
    BlogColors
      background
      text
      textSubdued
      textVerySubdued
      textEmphasized
      icon
      iconSubdued
      iconEmphasized
      border
      borderSubdued
      borderEmphasized
      divider
      container1
      containerSubdued
      interactive
      interactiveHover
      focusBorder
      focusOutline
      infoContainerSubdued
      element
      elementSubdued
      elementEmphasized
      button
      buttonText
      buttonEmphasized
      buttonTextEmphsaized

BlogTheme.BlogColors.containerSubdued : BlogColors -> BlogTheme.Color
BlogTheme.BlogColors.containerSubdued = cases
  BlogColors _ _ _ _ _ _ _ _ _ _ _ _ _ containerSubdued _ _ _ _ _ _ _ _ _ _ _ _ ->
    containerSubdued

BlogTheme.BlogColors.containerSubdued.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> BlogColors ->{g} BlogColors
BlogTheme.BlogColors.containerSubdued.modify f = cases
  BlogColors
    background
    text
    textSubdued
    textVerySubdued
    textEmphasized
    icon
    iconSubdued
    iconEmphasized
    border
    borderSubdued
    borderEmphasized
    divider
    container
    containerSubdued
    interactive
    interactiveHover
    focusBorder
    focusOutline
    infoContainerSubdued
    element
    elementSubdued
    elementEmphasized
    button
    buttonText
    buttonEmphasized
    buttonTextEmphsaized ->
    BlogColors
      background
      text
      textSubdued
      textVerySubdued
      textEmphasized
      icon
      iconSubdued
      iconEmphasized
      border
      borderSubdued
      borderEmphasized
      divider
      container
      (f containerSubdued)
      interactive
      interactiveHover
      focusBorder
      focusOutline
      infoContainerSubdued
      element
      elementSubdued
      elementEmphasized
      button
      buttonText
      buttonEmphasized
      buttonTextEmphsaized

BlogTheme.BlogColors.containerSubdued.set :
  BlogTheme.Color -> BlogColors -> BlogColors
BlogTheme.BlogColors.containerSubdued.set containerSubdued1 = cases
  BlogColors
    background
    text
    textSubdued
    textVerySubdued
    textEmphasized
    icon
    iconSubdued
    iconEmphasized
    border
    borderSubdued
    borderEmphasized
    divider
    container
    _
    interactive
    interactiveHover
    focusBorder
    focusOutline
    infoContainerSubdued
    element
    elementSubdued
    elementEmphasized
    button
    buttonText
    buttonEmphasized
    buttonTextEmphsaized ->
    BlogColors
      background
      text
      textSubdued
      textVerySubdued
      textEmphasized
      icon
      iconSubdued
      iconEmphasized
      border
      borderSubdued
      borderEmphasized
      divider
      container
      containerSubdued1
      interactive
      interactiveHover
      focusBorder
      focusOutline
      infoContainerSubdued
      element
      elementSubdued
      elementEmphasized
      button
      buttonText
      buttonEmphasized
      buttonTextEmphsaized

BlogTheme.BlogColors.divider : BlogColors -> BlogTheme.Color
BlogTheme.BlogColors.divider = cases
  BlogColors _ _ _ _ _ _ _ _ _ _ _ divider _ _ _ _ _ _ _ _ _ _ _ _ _ _ ->
    divider

BlogTheme.BlogColors.divider.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> BlogColors ->{g} BlogColors
BlogTheme.BlogColors.divider.modify f = cases
  BlogColors
    background
    text
    textSubdued
    textVerySubdued
    textEmphasized
    icon
    iconSubdued
    iconEmphasized
    border
    borderSubdued
    borderEmphasized
    divider
    container
    containerSubdued
    interactive
    interactiveHover
    focusBorder
    focusOutline
    infoContainerSubdued
    element
    elementSubdued
    elementEmphasized
    button
    buttonText
    buttonEmphasized
    buttonTextEmphsaized ->
    BlogColors
      background
      text
      textSubdued
      textVerySubdued
      textEmphasized
      icon
      iconSubdued
      iconEmphasized
      border
      borderSubdued
      borderEmphasized
      (f divider)
      container
      containerSubdued
      interactive
      interactiveHover
      focusBorder
      focusOutline
      infoContainerSubdued
      element
      elementSubdued
      elementEmphasized
      button
      buttonText
      buttonEmphasized
      buttonTextEmphsaized

BlogTheme.BlogColors.divider.set : BlogTheme.Color -> BlogColors -> BlogColors
BlogTheme.BlogColors.divider.set divider1 = cases
  BlogColors
    background
    text
    textSubdued
    textVerySubdued
    textEmphasized
    icon
    iconSubdued
    iconEmphasized
    border
    borderSubdued
    borderEmphasized
    _
    container
    containerSubdued
    interactive
    interactiveHover
    focusBorder
    focusOutline
    infoContainerSubdued
    element
    elementSubdued
    elementEmphasized
    button
    buttonText
    buttonEmphasized
    buttonTextEmphsaized ->
    BlogColors
      background
      text
      textSubdued
      textVerySubdued
      textEmphasized
      icon
      iconSubdued
      iconEmphasized
      border
      borderSubdued
      borderEmphasized
      divider1
      container
      containerSubdued
      interactive
      interactiveHover
      focusBorder
      focusOutline
      infoContainerSubdued
      element
      elementSubdued
      elementEmphasized
      button
      buttonText
      buttonEmphasized
      buttonTextEmphsaized

BlogTheme.BlogColors.doc : Doc
BlogTheme.BlogColors.doc =
  {{
  A {type BlogColors} is a type that contains the colors used by a blog. It has
  the following fields:
  
  * {{ docLink (docEmbedTermLink do BlogColors.background) }} is the background
    color of the blog.
  * {{ docLink (docEmbedTermLink do BlogColors.text) }} is the color of the
    main text.
  * {{ docLink (docEmbedTermLink do BlogColors.textSubdued) }} is a subdued
    version of the main text color.
  * {{ docLink (docEmbedTermLink do textEmphasized) }} is an version of the
    main text color that's used for emphasis.
  * {{ docLink (docEmbedTermLink do icon) }} is the color of icons used in the
    blog.
  * {{ docLink (docEmbedTermLink do iconSubdued) }} is a subdued version of the
    icon color.
  * {{ docLink (docEmbedTermLink do iconEmphasized) }} is an emphasized version
    of the icon color.
  * {{ docLink (docEmbedTermLink do BlogColors.border) }} is the color of
    borders used in the blog.
  * {{ docLink (docEmbedTermLink do borderSubdued) }} is a subdued version of
    the border color.
  * {{ docLink (docEmbedTermLink do borderEmphasized) }} is an emphasized
    version of the border color.
  * {{ docLink (docEmbedTermLink do container) }} is the color of containers
    used in the blog.
  * {{ docLink (docEmbedTermLink do BlogColors.interactive) }} is the color of
    interactive elements in the blog, such as links.
  * {{ docLink (docEmbedTermLink do interactiveHover) }} is the color of
    interactive elements when they're hovered over.
  * {{ docLink (docEmbedTermLink do focusBorder) }} is the color of the border
    of an element that has focus.
  * {{ docLink (docEmbedTermLink do focusOutline) }} is the color of the
    outline of an element that has focus.
  }}

BlogTheme.BlogColors.element : BlogColors -> BlogTheme.Color
BlogTheme.BlogColors.element = cases
  BlogColors _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ element _ _ _ _ _ _ ->
    element

BlogTheme.BlogColors.element.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> BlogColors ->{g} BlogColors
BlogTheme.BlogColors.element.modify f = cases
  BlogColors
    background
    text
    textSubdued
    textVerySubdued
    textEmphasized
    icon
    iconSubdued
    iconEmphasized
    border
    borderSubdued
    borderEmphasized
    divider
    container
    containerSubdued
    interactive
    interactiveHover
    focusBorder
    focusOutline
    infoContainerSubdued
    element
    elementSubdued
    elementEmphasized
    button
    buttonText
    buttonEmphasized
    buttonTextEmphsaized ->
    BlogColors
      background
      text
      textSubdued
      textVerySubdued
      textEmphasized
      icon
      iconSubdued
      iconEmphasized
      border
      borderSubdued
      borderEmphasized
      divider
      container
      containerSubdued
      interactive
      interactiveHover
      focusBorder
      focusOutline
      infoContainerSubdued
      (f element)
      elementSubdued
      elementEmphasized
      button
      buttonText
      buttonEmphasized
      buttonTextEmphsaized

BlogTheme.BlogColors.element.set : BlogTheme.Color -> BlogColors -> BlogColors
BlogTheme.BlogColors.element.set element1 = cases
  BlogColors
    background
    text
    textSubdued
    textVerySubdued
    textEmphasized
    icon
    iconSubdued
    iconEmphasized
    border
    borderSubdued
    borderEmphasized
    divider
    container
    containerSubdued
    interactive
    interactiveHover
    focusBorder
    focusOutline
    infoContainerSubdued
    _
    elementSubdued
    elementEmphasized
    button
    buttonText
    buttonEmphasized
    buttonTextEmphsaized ->
    BlogColors
      background
      text
      textSubdued
      textVerySubdued
      textEmphasized
      icon
      iconSubdued
      iconEmphasized
      border
      borderSubdued
      borderEmphasized
      divider
      container
      containerSubdued
      interactive
      interactiveHover
      focusBorder
      focusOutline
      infoContainerSubdued
      element1
      elementSubdued
      elementEmphasized
      button
      buttonText
      buttonEmphasized
      buttonTextEmphsaized

BlogTheme.BlogColors.elementEmphasized : BlogColors -> BlogTheme.Color
BlogTheme.BlogColors.elementEmphasized = cases
  BlogColors
    _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ elementEmphasized _ _ _ _ ->
    elementEmphasized

BlogTheme.BlogColors.elementEmphasized.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> BlogColors ->{g} BlogColors
BlogTheme.BlogColors.elementEmphasized.modify f = cases
  BlogColors
    background
    text
    textSubdued
    textVerySubdued
    textEmphasized
    icon
    iconSubdued
    iconEmphasized
    border
    borderSubdued
    borderEmphasized
    divider
    container
    containerSubdued
    interactive
    interactiveHover
    focusBorder
    focusOutline
    infoContainerSubdued
    element
    elementSubdued
    elementEmphasized
    button
    buttonText
    buttonEmphasized
    buttonTextEmphsaized ->
    BlogColors
      background
      text
      textSubdued
      textVerySubdued
      textEmphasized
      icon
      iconSubdued
      iconEmphasized
      border
      borderSubdued
      borderEmphasized
      divider
      container
      containerSubdued
      interactive
      interactiveHover
      focusBorder
      focusOutline
      infoContainerSubdued
      element
      elementSubdued
      (f elementEmphasized)
      button
      buttonText
      buttonEmphasized
      buttonTextEmphsaized

BlogTheme.BlogColors.elementEmphasized.set :
  BlogTheme.Color -> BlogColors -> BlogColors
BlogTheme.BlogColors.elementEmphasized.set elementEmphasized1 = cases
  BlogColors
    background
    text
    textSubdued
    textVerySubdued
    textEmphasized
    icon
    iconSubdued
    iconEmphasized
    border
    borderSubdued
    borderEmphasized
    divider
    container
    containerSubdued
    interactive
    interactiveHover
    focusBorder
    focusOutline
    infoContainerSubdued
    element
    elementSubdued
    _
    button
    buttonText
    buttonEmphasized
    buttonTextEmphsaized ->
    BlogColors
      background
      text
      textSubdued
      textVerySubdued
      textEmphasized
      icon
      iconSubdued
      iconEmphasized
      border
      borderSubdued
      borderEmphasized
      divider
      container
      containerSubdued
      interactive
      interactiveHover
      focusBorder
      focusOutline
      infoContainerSubdued
      element
      elementSubdued
      elementEmphasized1
      button
      buttonText
      buttonEmphasized
      buttonTextEmphsaized

BlogTheme.BlogColors.elementSubdued : BlogColors -> BlogTheme.Color
BlogTheme.BlogColors.elementSubdued = cases
  BlogColors _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ elementSubdued _ _ _ _ _ ->
    elementSubdued

BlogTheme.BlogColors.elementSubdued.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> BlogColors ->{g} BlogColors
BlogTheme.BlogColors.elementSubdued.modify f = cases
  BlogColors
    background
    text
    textSubdued
    textVerySubdued
    textEmphasized
    icon
    iconSubdued
    iconEmphasized
    border
    borderSubdued
    borderEmphasized
    divider
    container
    containerSubdued
    interactive
    interactiveHover
    focusBorder
    focusOutline
    infoContainerSubdued
    element
    elementSubdued
    elementEmphasized
    button
    buttonText
    buttonEmphasized
    buttonTextEmphsaized ->
    BlogColors
      background
      text
      textSubdued
      textVerySubdued
      textEmphasized
      icon
      iconSubdued
      iconEmphasized
      border
      borderSubdued
      borderEmphasized
      divider
      container
      containerSubdued
      interactive
      interactiveHover
      focusBorder
      focusOutline
      infoContainerSubdued
      element
      (f elementSubdued)
      elementEmphasized
      button
      buttonText
      buttonEmphasized
      buttonTextEmphsaized

BlogTheme.BlogColors.elementSubdued.set :
  BlogTheme.Color -> BlogColors -> BlogColors
BlogTheme.BlogColors.elementSubdued.set elementSubdued1 = cases
  BlogColors
    background
    text
    textSubdued
    textVerySubdued
    textEmphasized
    icon
    iconSubdued
    iconEmphasized
    border
    borderSubdued
    borderEmphasized
    divider
    container
    containerSubdued
    interactive
    interactiveHover
    focusBorder
    focusOutline
    infoContainerSubdued
    element
    _
    elementEmphasized
    button
    buttonText
    buttonEmphasized
    buttonTextEmphsaized ->
    BlogColors
      background
      text
      textSubdued
      textVerySubdued
      textEmphasized
      icon
      iconSubdued
      iconEmphasized
      border
      borderSubdued
      borderEmphasized
      divider
      container
      containerSubdued
      interactive
      interactiveHover
      focusBorder
      focusOutline
      infoContainerSubdued
      element
      elementSubdued1
      elementEmphasized
      button
      buttonText
      buttonEmphasized
      buttonTextEmphsaized

BlogTheme.BlogColors.focusBorder : BlogColors -> BlogTheme.Color
BlogTheme.BlogColors.focusBorder = cases
  BlogColors _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ focusBorder _ _ _ _ _ _ _ _ _ ->
    focusBorder

BlogTheme.BlogColors.focusBorder.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> BlogColors ->{g} BlogColors
BlogTheme.BlogColors.focusBorder.modify f = cases
  BlogColors
    background
    text
    textSubdued
    textVerySubdued
    textEmphasized
    icon
    iconSubdued
    iconEmphasized
    border
    borderSubdued
    borderEmphasized
    divider
    container
    containerSubdued
    interactive
    interactiveHover
    focusBorder
    focusOutline
    infoContainerSubdued
    element
    elementSubdued
    elementEmphasized
    button
    buttonText
    buttonEmphasized
    buttonTextEmphsaized ->
    BlogColors
      background
      text
      textSubdued
      textVerySubdued
      textEmphasized
      icon
      iconSubdued
      iconEmphasized
      border
      borderSubdued
      borderEmphasized
      divider
      container
      containerSubdued
      interactive
      interactiveHover
      (f focusBorder)
      focusOutline
      infoContainerSubdued
      element
      elementSubdued
      elementEmphasized
      button
      buttonText
      buttonEmphasized
      buttonTextEmphsaized

BlogTheme.BlogColors.focusBorder.set :
  BlogTheme.Color -> BlogColors -> BlogColors
BlogTheme.BlogColors.focusBorder.set focusBorder1 = cases
  BlogColors
    background
    text
    textSubdued
    textVerySubdued
    textEmphasized
    icon
    iconSubdued
    iconEmphasized
    border
    borderSubdued
    borderEmphasized
    divider
    container
    containerSubdued
    interactive
    interactiveHover
    _
    focusOutline
    infoContainerSubdued
    element
    elementSubdued
    elementEmphasized
    button
    buttonText
    buttonEmphasized
    buttonTextEmphsaized ->
    BlogColors
      background
      text
      textSubdued
      textVerySubdued
      textEmphasized
      icon
      iconSubdued
      iconEmphasized
      border
      borderSubdued
      borderEmphasized
      divider
      container
      containerSubdued
      interactive
      interactiveHover
      focusBorder1
      focusOutline
      infoContainerSubdued
      element
      elementSubdued
      elementEmphasized
      button
      buttonText
      buttonEmphasized
      buttonTextEmphsaized

BlogTheme.BlogColors.focusOutline : BlogColors -> BlogTheme.Color
BlogTheme.BlogColors.focusOutline = cases
  BlogColors _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ focusOutline _ _ _ _ _ _ _ _ ->
    focusOutline

BlogTheme.BlogColors.focusOutline.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> BlogColors ->{g} BlogColors
BlogTheme.BlogColors.focusOutline.modify f = cases
  BlogColors
    background
    text
    textSubdued
    textVerySubdued
    textEmphasized
    icon
    iconSubdued
    iconEmphasized
    border
    borderSubdued
    borderEmphasized
    divider
    container
    containerSubdued
    interactive
    interactiveHover
    focusBorder
    focusOutline
    infoContainerSubdued
    element
    elementSubdued
    elementEmphasized
    button
    buttonText
    buttonEmphasized
    buttonTextEmphsaized ->
    BlogColors
      background
      text
      textSubdued
      textVerySubdued
      textEmphasized
      icon
      iconSubdued
      iconEmphasized
      border
      borderSubdued
      borderEmphasized
      divider
      container
      containerSubdued
      interactive
      interactiveHover
      focusBorder
      (f focusOutline)
      infoContainerSubdued
      element
      elementSubdued
      elementEmphasized
      button
      buttonText
      buttonEmphasized
      buttonTextEmphsaized

BlogTheme.BlogColors.focusOutline.set :
  BlogTheme.Color -> BlogColors -> BlogColors
BlogTheme.BlogColors.focusOutline.set focusOutline1 = cases
  BlogColors
    background
    text
    textSubdued
    textVerySubdued
    textEmphasized
    icon
    iconSubdued
    iconEmphasized
    border
    borderSubdued
    borderEmphasized
    divider
    container
    containerSubdued
    interactive
    interactiveHover
    focusBorder
    _
    infoContainerSubdued
    element
    elementSubdued
    elementEmphasized
    button
    buttonText
    buttonEmphasized
    buttonTextEmphsaized ->
    BlogColors
      background
      text
      textSubdued
      textVerySubdued
      textEmphasized
      icon
      iconSubdued
      iconEmphasized
      border
      borderSubdued
      borderEmphasized
      divider
      container
      containerSubdued
      interactive
      interactiveHover
      focusBorder
      focusOutline1
      infoContainerSubdued
      element
      elementSubdued
      elementEmphasized
      button
      buttonText
      buttonEmphasized
      buttonTextEmphsaized

BlogTheme.BlogColors.icon : BlogColors -> BlogTheme.Color
BlogTheme.BlogColors.icon = cases
  BlogColors _ _ _ _ _ icon _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ -> icon

BlogTheme.BlogColors.icon.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> BlogColors ->{g} BlogColors
BlogTheme.BlogColors.icon.modify f = cases
  BlogColors
    background
    text
    textSubdued
    textVerySubdued
    textEmphasized
    icon
    iconSubdued
    iconEmphasized
    border
    borderSubdued
    borderEmphasized
    divider
    container
    containerSubdued
    interactive
    interactiveHover
    focusBorder
    focusOutline
    infoContainerSubdued
    element
    elementSubdued
    elementEmphasized
    button
    buttonText
    buttonEmphasized
    buttonTextEmphsaized ->
    BlogColors
      background
      text
      textSubdued
      textVerySubdued
      textEmphasized
      (f icon)
      iconSubdued
      iconEmphasized
      border
      borderSubdued
      borderEmphasized
      divider
      container
      containerSubdued
      interactive
      interactiveHover
      focusBorder
      focusOutline
      infoContainerSubdued
      element
      elementSubdued
      elementEmphasized
      button
      buttonText
      buttonEmphasized
      buttonTextEmphsaized

BlogTheme.BlogColors.icon.set : BlogTheme.Color -> BlogColors -> BlogColors
BlogTheme.BlogColors.icon.set icon1 = cases
  BlogColors
    background
    text
    textSubdued
    textVerySubdued
    textEmphasized
    _
    iconSubdued
    iconEmphasized
    border
    borderSubdued
    borderEmphasized
    divider
    container
    containerSubdued
    interactive
    interactiveHover
    focusBorder
    focusOutline
    infoContainerSubdued
    element
    elementSubdued
    elementEmphasized
    button
    buttonText
    buttonEmphasized
    buttonTextEmphsaized ->
    BlogColors
      background
      text
      textSubdued
      textVerySubdued
      textEmphasized
      icon1
      iconSubdued
      iconEmphasized
      border
      borderSubdued
      borderEmphasized
      divider
      container
      containerSubdued
      interactive
      interactiveHover
      focusBorder
      focusOutline
      infoContainerSubdued
      element
      elementSubdued
      elementEmphasized
      button
      buttonText
      buttonEmphasized
      buttonTextEmphsaized

BlogTheme.BlogColors.iconEmphasized : BlogColors -> BlogTheme.Color
BlogTheme.BlogColors.iconEmphasized = cases
  BlogColors _ _ _ _ _ _ _ iconEmphasized _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ ->
    iconEmphasized

BlogTheme.BlogColors.iconEmphasized.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> BlogColors ->{g} BlogColors
BlogTheme.BlogColors.iconEmphasized.modify f = cases
  BlogColors
    background
    text
    textSubdued
    textVerySubdued
    textEmphasized
    icon
    iconSubdued
    iconEmphasized
    border
    borderSubdued
    borderEmphasized
    divider
    container
    containerSubdued
    interactive
    interactiveHover
    focusBorder
    focusOutline
    infoContainerSubdued
    element
    elementSubdued
    elementEmphasized
    button
    buttonText
    buttonEmphasized
    buttonTextEmphsaized ->
    BlogColors
      background
      text
      textSubdued
      textVerySubdued
      textEmphasized
      icon
      iconSubdued
      (f iconEmphasized)
      border
      borderSubdued
      borderEmphasized
      divider
      container
      containerSubdued
      interactive
      interactiveHover
      focusBorder
      focusOutline
      infoContainerSubdued
      element
      elementSubdued
      elementEmphasized
      button
      buttonText
      buttonEmphasized
      buttonTextEmphsaized

BlogTheme.BlogColors.iconEmphasized.set :
  BlogTheme.Color -> BlogColors -> BlogColors
BlogTheme.BlogColors.iconEmphasized.set iconEmphasized1 = cases
  BlogColors
    background
    text
    textSubdued
    textVerySubdued
    textEmphasized
    icon
    iconSubdued
    _
    border
    borderSubdued
    borderEmphasized
    divider
    container
    containerSubdued
    interactive
    interactiveHover
    focusBorder
    focusOutline
    infoContainerSubdued
    element
    elementSubdued
    elementEmphasized
    button
    buttonText
    buttonEmphasized
    buttonTextEmphsaized ->
    BlogColors
      background
      text
      textSubdued
      textVerySubdued
      textEmphasized
      icon
      iconSubdued
      iconEmphasized1
      border
      borderSubdued
      borderEmphasized
      divider
      container
      containerSubdued
      interactive
      interactiveHover
      focusBorder
      focusOutline
      infoContainerSubdued
      element
      elementSubdued
      elementEmphasized
      button
      buttonText
      buttonEmphasized
      buttonTextEmphsaized

BlogTheme.BlogColors.iconSubdued : BlogColors -> BlogTheme.Color
BlogTheme.BlogColors.iconSubdued = cases
  BlogColors _ _ _ _ _ _ iconSubdued _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ ->
    iconSubdued

BlogTheme.BlogColors.iconSubdued.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> BlogColors ->{g} BlogColors
BlogTheme.BlogColors.iconSubdued.modify f = cases
  BlogColors
    background
    text
    textSubdued
    textVerySubdued
    textEmphasized
    icon
    iconSubdued
    iconEmphasized
    border
    borderSubdued
    borderEmphasized
    divider
    container
    containerSubdued
    interactive
    interactiveHover
    focusBorder
    focusOutline
    infoContainerSubdued
    element
    elementSubdued
    elementEmphasized
    button
    buttonText
    buttonEmphasized
    buttonTextEmphsaized ->
    BlogColors
      background
      text
      textSubdued
      textVerySubdued
      textEmphasized
      icon
      (f iconSubdued)
      iconEmphasized
      border
      borderSubdued
      borderEmphasized
      divider
      container
      containerSubdued
      interactive
      interactiveHover
      focusBorder
      focusOutline
      infoContainerSubdued
      element
      elementSubdued
      elementEmphasized
      button
      buttonText
      buttonEmphasized
      buttonTextEmphsaized

BlogTheme.BlogColors.iconSubdued.set :
  BlogTheme.Color -> BlogColors -> BlogColors
BlogTheme.BlogColors.iconSubdued.set iconSubdued1 = cases
  BlogColors
    background
    text
    textSubdued
    textVerySubdued
    textEmphasized
    icon
    _
    iconEmphasized
    border
    borderSubdued
    borderEmphasized
    divider
    container
    containerSubdued
    interactive
    interactiveHover
    focusBorder
    focusOutline
    infoContainerSubdued
    element
    elementSubdued
    elementEmphasized
    button
    buttonText
    buttonEmphasized
    buttonTextEmphsaized ->
    BlogColors
      background
      text
      textSubdued
      textVerySubdued
      textEmphasized
      icon
      iconSubdued1
      iconEmphasized
      border
      borderSubdued
      borderEmphasized
      divider
      container
      containerSubdued
      interactive
      interactiveHover
      focusBorder
      focusOutline
      infoContainerSubdued
      element
      elementSubdued
      elementEmphasized
      button
      buttonText
      buttonEmphasized
      buttonTextEmphsaized

BlogTheme.BlogColors.infoContainerSubdued : BlogColors -> BlogTheme.Color
BlogTheme.BlogColors.infoContainerSubdued = cases
  BlogColors
    _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ infoContainerSubdued _ _ _ _ _ _ _ ->
    infoContainerSubdued

BlogTheme.BlogColors.infoContainerSubdued.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> BlogColors ->{g} BlogColors
BlogTheme.BlogColors.infoContainerSubdued.modify f = cases
  BlogColors
    background
    text
    textSubdued
    textVerySubdued
    textEmphasized
    icon
    iconSubdued
    iconEmphasized
    border
    borderSubdued
    borderEmphasized
    divider
    container
    containerSubdued
    interactive
    interactiveHover
    focusBorder
    focusOutline
    infoContainerSubdued
    element
    elementSubdued
    elementEmphasized
    button
    buttonText
    buttonEmphasized
    buttonTextEmphsaized ->
    BlogColors
      background
      text
      textSubdued
      textVerySubdued
      textEmphasized
      icon
      iconSubdued
      iconEmphasized
      border
      borderSubdued
      borderEmphasized
      divider
      container
      containerSubdued
      interactive
      interactiveHover
      focusBorder
      focusOutline
      (f infoContainerSubdued)
      element
      elementSubdued
      elementEmphasized
      button
      buttonText
      buttonEmphasized
      buttonTextEmphsaized

BlogTheme.BlogColors.infoContainerSubdued.set :
  BlogTheme.Color -> BlogColors -> BlogColors
BlogTheme.BlogColors.infoContainerSubdued.set infoContainerSubdued1 = cases
  BlogColors
    background
    text
    textSubdued
    textVerySubdued
    textEmphasized
    icon
    iconSubdued
    iconEmphasized
    border
    borderSubdued
    borderEmphasized
    divider
    container
    containerSubdued
    interactive
    interactiveHover
    focusBorder
    focusOutline
    _
    element
    elementSubdued
    elementEmphasized
    button
    buttonText
    buttonEmphasized
    buttonTextEmphsaized ->
    BlogColors
      background
      text
      textSubdued
      textVerySubdued
      textEmphasized
      icon
      iconSubdued
      iconEmphasized
      border
      borderSubdued
      borderEmphasized
      divider
      container
      containerSubdued
      interactive
      interactiveHover
      focusBorder
      focusOutline
      infoContainerSubdued1
      element
      elementSubdued
      elementEmphasized
      button
      buttonText
      buttonEmphasized
      buttonTextEmphsaized

BlogTheme.BlogColors.interactive : BlogColors -> BlogTheme.Color
BlogTheme.BlogColors.interactive = cases
  BlogColors _ _ _ _ _ _ _ _ _ _ _ _ _ _ interactive _ _ _ _ _ _ _ _ _ _ _ ->
    interactive

BlogTheme.BlogColors.interactive.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> BlogColors ->{g} BlogColors
BlogTheme.BlogColors.interactive.modify f = cases
  BlogColors
    background
    text
    textSubdued
    textVerySubdued
    textEmphasized
    icon
    iconSubdued
    iconEmphasized
    border
    borderSubdued
    borderEmphasized
    divider
    container
    containerSubdued
    interactive
    interactiveHover
    focusBorder
    focusOutline
    infoContainerSubdued
    element
    elementSubdued
    elementEmphasized
    button
    buttonText
    buttonEmphasized
    buttonTextEmphsaized ->
    BlogColors
      background
      text
      textSubdued
      textVerySubdued
      textEmphasized
      icon
      iconSubdued
      iconEmphasized
      border
      borderSubdued
      borderEmphasized
      divider
      container
      containerSubdued
      (f interactive)
      interactiveHover
      focusBorder
      focusOutline
      infoContainerSubdued
      element
      elementSubdued
      elementEmphasized
      button
      buttonText
      buttonEmphasized
      buttonTextEmphsaized

BlogTheme.BlogColors.interactive.set :
  BlogTheme.Color -> BlogColors -> BlogColors
BlogTheme.BlogColors.interactive.set interactive1 = cases
  BlogColors
    background
    text
    textSubdued
    textVerySubdued
    textEmphasized
    icon
    iconSubdued
    iconEmphasized
    border
    borderSubdued
    borderEmphasized
    divider
    container
    containerSubdued
    _
    interactiveHover
    focusBorder
    focusOutline
    infoContainerSubdued
    element
    elementSubdued
    elementEmphasized
    button
    buttonText
    buttonEmphasized
    buttonTextEmphsaized ->
    BlogColors
      background
      text
      textSubdued
      textVerySubdued
      textEmphasized
      icon
      iconSubdued
      iconEmphasized
      border
      borderSubdued
      borderEmphasized
      divider
      container
      containerSubdued
      interactive1
      interactiveHover
      focusBorder
      focusOutline
      infoContainerSubdued
      element
      elementSubdued
      elementEmphasized
      button
      buttonText
      buttonEmphasized
      buttonTextEmphsaized

BlogTheme.BlogColors.interactiveHover : BlogColors -> BlogTheme.Color
BlogTheme.BlogColors.interactiveHover = cases
  BlogColors _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ interactiveHover _ _ _ _ _ _ _ _ _ _ ->
    interactiveHover

BlogTheme.BlogColors.interactiveHover.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> BlogColors ->{g} BlogColors
BlogTheme.BlogColors.interactiveHover.modify f = cases
  BlogColors
    background
    text
    textSubdued
    textVerySubdued
    textEmphasized
    icon
    iconSubdued
    iconEmphasized
    border
    borderSubdued
    borderEmphasized
    divider
    container
    containerSubdued
    interactive
    interactiveHover
    focusBorder
    focusOutline
    infoContainerSubdued
    element
    elementSubdued
    elementEmphasized
    button
    buttonText
    buttonEmphasized
    buttonTextEmphsaized ->
    BlogColors
      background
      text
      textSubdued
      textVerySubdued
      textEmphasized
      icon
      iconSubdued
      iconEmphasized
      border
      borderSubdued
      borderEmphasized
      divider
      container
      containerSubdued
      interactive
      (f interactiveHover)
      focusBorder
      focusOutline
      infoContainerSubdued
      element
      elementSubdued
      elementEmphasized
      button
      buttonText
      buttonEmphasized
      buttonTextEmphsaized

BlogTheme.BlogColors.interactiveHover.set :
  BlogTheme.Color -> BlogColors -> BlogColors
BlogTheme.BlogColors.interactiveHover.set interactiveHover1 = cases
  BlogColors
    background
    text
    textSubdued
    textVerySubdued
    textEmphasized
    icon
    iconSubdued
    iconEmphasized
    border
    borderSubdued
    borderEmphasized
    divider
    container
    containerSubdued
    interactive
    _
    focusBorder
    focusOutline
    infoContainerSubdued
    element
    elementSubdued
    elementEmphasized
    button
    buttonText
    buttonEmphasized
    buttonTextEmphsaized ->
    BlogColors
      background
      text
      textSubdued
      textVerySubdued
      textEmphasized
      icon
      iconSubdued
      iconEmphasized
      border
      borderSubdued
      borderEmphasized
      divider
      container
      containerSubdued
      interactive
      interactiveHover1
      focusBorder
      focusOutline
      infoContainerSubdued
      element
      elementSubdued
      elementEmphasized
      button
      buttonText
      buttonEmphasized
      buttonTextEmphsaized

BlogTheme.BlogColors.text : BlogColors -> BlogTheme.Color
BlogTheme.BlogColors.text = cases
  BlogColors _ text _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ -> text

BlogTheme.BlogColors.text.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> BlogColors ->{g} BlogColors
BlogTheme.BlogColors.text.modify f = cases
  BlogColors
    background
    text
    textSubdued
    textVerySubdued
    textEmphasized
    icon
    iconSubdued
    iconEmphasized
    border
    borderSubdued
    borderEmphasized
    divider
    container
    containerSubdued
    interactive
    interactiveHover
    focusBorder
    focusOutline
    infoContainerSubdued
    element
    elementSubdued
    elementEmphasized
    button
    buttonText
    buttonEmphasized
    buttonTextEmphsaized ->
    BlogColors
      background
      (f text)
      textSubdued
      textVerySubdued
      textEmphasized
      icon
      iconSubdued
      iconEmphasized
      border
      borderSubdued
      borderEmphasized
      divider
      container
      containerSubdued
      interactive
      interactiveHover
      focusBorder
      focusOutline
      infoContainerSubdued
      element
      elementSubdued
      elementEmphasized
      button
      buttonText
      buttonEmphasized
      buttonTextEmphsaized

BlogTheme.BlogColors.text.set : BlogTheme.Color -> BlogColors -> BlogColors
BlogTheme.BlogColors.text.set text1 = cases
  BlogColors
    background
    _
    textSubdued
    textVerySubdued
    textEmphasized
    icon
    iconSubdued
    iconEmphasized
    border
    borderSubdued
    borderEmphasized
    divider
    container
    containerSubdued
    interactive
    interactiveHover
    focusBorder
    focusOutline
    infoContainerSubdued
    element
    elementSubdued
    elementEmphasized
    button
    buttonText
    buttonEmphasized
    buttonTextEmphsaized ->
    BlogColors
      background
      text1
      textSubdued
      textVerySubdued
      textEmphasized
      icon
      iconSubdued
      iconEmphasized
      border
      borderSubdued
      borderEmphasized
      divider
      container
      containerSubdued
      interactive
      interactiveHover
      focusBorder
      focusOutline
      infoContainerSubdued
      element
      elementSubdued
      elementEmphasized
      button
      buttonText
      buttonEmphasized
      buttonTextEmphsaized

BlogTheme.BlogColors.textEmphasized : BlogColors -> BlogTheme.Color
BlogTheme.BlogColors.textEmphasized = cases
  BlogColors _ _ _ _ textEmphasized _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ ->
    textEmphasized

BlogTheme.BlogColors.textEmphasized.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> BlogColors ->{g} BlogColors
BlogTheme.BlogColors.textEmphasized.modify f = cases
  BlogColors
    background
    text
    textSubdued
    textVerySubdued
    textEmphasized
    icon
    iconSubdued
    iconEmphasized
    border
    borderSubdued
    borderEmphasized
    divider
    container
    containerSubdued
    interactive
    interactiveHover
    focusBorder
    focusOutline
    infoContainerSubdued
    element
    elementSubdued
    elementEmphasized
    button
    buttonText
    buttonEmphasized
    buttonTextEmphsaized ->
    BlogColors
      background
      text
      textSubdued
      textVerySubdued
      (f textEmphasized)
      icon
      iconSubdued
      iconEmphasized
      border
      borderSubdued
      borderEmphasized
      divider
      container
      containerSubdued
      interactive
      interactiveHover
      focusBorder
      focusOutline
      infoContainerSubdued
      element
      elementSubdued
      elementEmphasized
      button
      buttonText
      buttonEmphasized
      buttonTextEmphsaized

BlogTheme.BlogColors.textEmphasized.set :
  BlogTheme.Color -> BlogColors -> BlogColors
BlogTheme.BlogColors.textEmphasized.set textEmphasized1 = cases
  BlogColors
    background
    text
    textSubdued
    textVerySubdued
    _
    icon
    iconSubdued
    iconEmphasized
    border
    borderSubdued
    borderEmphasized
    divider
    container
    containerSubdued
    interactive
    interactiveHover
    focusBorder
    focusOutline
    infoContainerSubdued
    element
    elementSubdued
    elementEmphasized
    button
    buttonText
    buttonEmphasized
    buttonTextEmphsaized ->
    BlogColors
      background
      text
      textSubdued
      textVerySubdued
      textEmphasized1
      icon
      iconSubdued
      iconEmphasized
      border
      borderSubdued
      borderEmphasized
      divider
      container
      containerSubdued
      interactive
      interactiveHover
      focusBorder
      focusOutline
      infoContainerSubdued
      element
      elementSubdued
      elementEmphasized
      button
      buttonText
      buttonEmphasized
      buttonTextEmphsaized

BlogTheme.BlogColors.textSubdued : BlogColors -> BlogTheme.Color
BlogTheme.BlogColors.textSubdued = cases
  BlogColors _ _ textSubdued _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ ->
    textSubdued

BlogTheme.BlogColors.textSubdued.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> BlogColors ->{g} BlogColors
BlogTheme.BlogColors.textSubdued.modify f = cases
  BlogColors
    background
    text
    textSubdued
    textVerySubdued
    textEmphasized
    icon
    iconSubdued
    iconEmphasized
    border
    borderSubdued
    borderEmphasized
    divider
    container
    containerSubdued
    interactive
    interactiveHover
    focusBorder
    focusOutline
    infoContainerSubdued
    element
    elementSubdued
    elementEmphasized
    button
    buttonText
    buttonEmphasized
    buttonTextEmphsaized ->
    BlogColors
      background
      text
      (f textSubdued)
      textVerySubdued
      textEmphasized
      icon
      iconSubdued
      iconEmphasized
      border
      borderSubdued
      borderEmphasized
      divider
      container
      containerSubdued
      interactive
      interactiveHover
      focusBorder
      focusOutline
      infoContainerSubdued
      element
      elementSubdued
      elementEmphasized
      button
      buttonText
      buttonEmphasized
      buttonTextEmphsaized

BlogTheme.BlogColors.textSubdued.set :
  BlogTheme.Color -> BlogColors -> BlogColors
BlogTheme.BlogColors.textSubdued.set textSubdued1 = cases
  BlogColors
    background
    text
    _
    textVerySubdued
    textEmphasized
    icon
    iconSubdued
    iconEmphasized
    border
    borderSubdued
    borderEmphasized
    divider
    container
    containerSubdued
    interactive
    interactiveHover
    focusBorder
    focusOutline
    infoContainerSubdued
    element
    elementSubdued
    elementEmphasized
    button
    buttonText
    buttonEmphasized
    buttonTextEmphsaized ->
    BlogColors
      background
      text
      textSubdued1
      textVerySubdued
      textEmphasized
      icon
      iconSubdued
      iconEmphasized
      border
      borderSubdued
      borderEmphasized
      divider
      container
      containerSubdued
      interactive
      interactiveHover
      focusBorder
      focusOutline
      infoContainerSubdued
      element
      elementSubdued
      elementEmphasized
      button
      buttonText
      buttonEmphasized
      buttonTextEmphsaized

BlogTheme.BlogColors.textVerySubdued : BlogColors -> BlogTheme.Color
BlogTheme.BlogColors.textVerySubdued = cases
  BlogColors _ _ _ textVerySubdued _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ ->
    textVerySubdued

BlogTheme.BlogColors.textVerySubdued.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> BlogColors ->{g} BlogColors
BlogTheme.BlogColors.textVerySubdued.modify f = cases
  BlogColors
    background
    text
    textSubdued
    textVerySubdued
    textEmphasized
    icon
    iconSubdued
    iconEmphasized
    border
    borderSubdued
    borderEmphasized
    divider
    container
    containerSubdued
    interactive
    interactiveHover
    focusBorder
    focusOutline
    infoContainerSubdued
    element
    elementSubdued
    elementEmphasized
    button
    buttonText
    buttonEmphasized
    buttonTextEmphsaized ->
    BlogColors
      background
      text
      textSubdued
      (f textVerySubdued)
      textEmphasized
      icon
      iconSubdued
      iconEmphasized
      border
      borderSubdued
      borderEmphasized
      divider
      container
      containerSubdued
      interactive
      interactiveHover
      focusBorder
      focusOutline
      infoContainerSubdued
      element
      elementSubdued
      elementEmphasized
      button
      buttonText
      buttonEmphasized
      buttonTextEmphsaized

BlogTheme.BlogColors.textVerySubdued.set :
  BlogTheme.Color -> BlogColors -> BlogColors
BlogTheme.BlogColors.textVerySubdued.set textVerySubdued1 = cases
  BlogColors
    background
    text
    textSubdued
    _
    textEmphasized
    icon
    iconSubdued
    iconEmphasized
    border
    borderSubdued
    borderEmphasized
    divider
    container
    containerSubdued
    interactive
    interactiveHover
    focusBorder
    focusOutline
    infoContainerSubdued
    element
    elementSubdued
    elementEmphasized
    button
    buttonText
    buttonEmphasized
    buttonTextEmphsaized ->
    BlogColors
      background
      text
      textSubdued
      textVerySubdued1
      textEmphasized
      icon
      iconSubdued
      iconEmphasized
      border
      borderSubdued
      borderEmphasized
      divider
      container
      containerSubdued
      interactive
      interactiveHover
      focusBorder
      focusOutline
      infoContainerSubdued
      element
      elementSubdued
      elementEmphasized
      button
      buttonText
      buttonEmphasized
      buttonTextEmphsaized

BlogTheme.Color.doc : Doc
BlogTheme.Color.doc =
  {{
  A {type BlogTheme.Color} is a type that represents a color. It's a simple
  wrapper around a {type Text} that contains the color value as a hex code. For
  example `` Color "#ff0000" `` represents the color red.
  }}

BlogTheme.Color.toText : BlogTheme.Color -> Text
BlogTheme.Color.toText = cases Color c -> c

BlogTheme.Color.toText.doc : Doc
BlogTheme.Color.toText.doc =
  {{
  Converts a {type BlogTheme.Color} to a {type Text} representation for use in
  CSS.
  }}

BlogTheme.colors : BlogTheme -> BlogColors
BlogTheme.colors = cases BlogTheme _ _ _ colors _ _ -> colors

BlogTheme.colors.modify :
  (BlogColors ->{g} BlogColors) -> BlogTheme ->{g} BlogTheme
BlogTheme.colors.modify f = cases
  BlogTheme name mainFont monospaceFont colors syntaxColors docColors ->
    BlogTheme name mainFont monospaceFont (f colors) syntaxColors docColors

BlogTheme.colors.set : BlogColors -> BlogTheme -> BlogTheme
BlogTheme.colors.set colors1 = cases
  BlogTheme name mainFont monospaceFont _ syntaxColors docColors ->
    BlogTheme name mainFont monospaceFont colors1 syntaxColors docColors

BlogTheme.doc : Doc
BlogTheme.doc =
  {{
  A {type BlogTheme} is a record type that represents the theme of a blog. It
  has the following fields:
  
  * {{ docLink (docEmbedTermLink do BlogTheme.name) }} is the name of the
    theme.
  * {{ docLink (docEmbedTermLink do mainFont) }} is the {type FontStack} that
    the blog uses for its main text.
  * {{ docLink (docEmbedTermLink do monospaceFont) }} is the {type FontStack}
    that the blog uses for monospace text.
  * {{ docLink (docEmbedTermLink do colors) }} is a {type BlogColors} record
    that contains the colors used by the blog.
  * {{ docLink (docEmbedTermLink do syntaxColors) }} is a {type SyntaxColors}
    record that contains the syntax highlighting colors used by the blog.
  }}

BlogTheme.docColors : BlogTheme -> DocColors
BlogTheme.docColors = cases BlogTheme _ _ _ _ _ docColors -> docColors

BlogTheme.DocColors.aside : DocColors -> BlogTheme.Color
BlogTheme.DocColors.aside = cases
  DocColors _ _ _ _ aside _ _ _ _ _ _ _ _ -> aside

BlogTheme.DocColors.aside.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> DocColors ->{g} DocColors
BlogTheme.DocColors.aside.modify f = cases
  DocColors
    background
    title
    text
    textSubdued
    aside
    asideSource
    callout
    calloutSource
    source
    border
    divider
    evalResult
    evalIcon ->
    DocColors
      background
      title
      text
      textSubdued
      (f aside)
      asideSource
      callout
      calloutSource
      source
      border
      divider
      evalResult
      evalIcon

BlogTheme.DocColors.aside.set : BlogTheme.Color -> DocColors -> DocColors
BlogTheme.DocColors.aside.set aside1 = cases
  DocColors
    background
    title
    text
    textSubdued
    _
    asideSource
    callout
    calloutSource
    source
    border
    divider
    evalResult
    evalIcon ->
    DocColors
      background
      title
      text
      textSubdued
      aside1
      asideSource
      callout
      calloutSource
      source
      border
      divider
      evalResult
      evalIcon

BlogTheme.DocColors.asideSource : DocColors -> BlogTheme.Color
BlogTheme.DocColors.asideSource = cases
  DocColors _ _ _ _ _ asideSource _ _ _ _ _ _ _ -> asideSource

BlogTheme.DocColors.asideSource.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> DocColors ->{g} DocColors
BlogTheme.DocColors.asideSource.modify f = cases
  DocColors
    background
    title
    text
    textSubdued
    aside
    asideSource
    callout
    calloutSource
    source
    border
    divider
    evalResult
    evalIcon ->
    DocColors
      background
      title
      text
      textSubdued
      aside
      (f asideSource)
      callout
      calloutSource
      source
      border
      divider
      evalResult
      evalIcon

BlogTheme.DocColors.asideSource.set : BlogTheme.Color -> DocColors -> DocColors
BlogTheme.DocColors.asideSource.set asideSource1 = cases
  DocColors
    background
    title
    text
    textSubdued
    aside
    _
    callout
    calloutSource
    source
    border
    divider
    evalResult
    evalIcon ->
    DocColors
      background
      title
      text
      textSubdued
      aside
      asideSource1
      callout
      calloutSource
      source
      border
      divider
      evalResult
      evalIcon

BlogTheme.DocColors.background : DocColors -> BlogTheme.Color
BlogTheme.DocColors.background = cases
  DocColors background _ _ _ _ _ _ _ _ _ _ _ _ -> background

BlogTheme.DocColors.background.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> DocColors ->{g} DocColors
BlogTheme.DocColors.background.modify f = cases
  DocColors
    background
    title
    text
    textSubdued
    aside
    asideSource
    callout
    calloutSource
    source
    border
    divider
    evalResult
    evalIcon ->
    DocColors
      (f background)
      title
      text
      textSubdued
      aside
      asideSource
      callout
      calloutSource
      source
      border
      divider
      evalResult
      evalIcon

BlogTheme.DocColors.background.set : BlogTheme.Color -> DocColors -> DocColors
BlogTheme.DocColors.background.set background1 = cases
  DocColors
    _
    title
    text
    textSubdued
    aside
    asideSource
    callout
    calloutSource
    source
    border
    divider
    evalResult
    evalIcon ->
    DocColors
      background1
      title
      text
      textSubdued
      aside
      asideSource
      callout
      calloutSource
      source
      border
      divider
      evalResult
      evalIcon

BlogTheme.DocColors.border : DocColors -> BlogTheme.Color
BlogTheme.DocColors.border = cases
  DocColors _ _ _ _ _ _ _ _ _ border _ _ _ -> border

BlogTheme.DocColors.border.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> DocColors ->{g} DocColors
BlogTheme.DocColors.border.modify f = cases
  DocColors
    background
    title
    text
    textSubdued
    aside
    asideSource
    callout
    calloutSource
    source
    border
    divider
    evalResult
    evalIcon ->
    DocColors
      background
      title
      text
      textSubdued
      aside
      asideSource
      callout
      calloutSource
      source
      (f border)
      divider
      evalResult
      evalIcon

BlogTheme.DocColors.border.set : BlogTheme.Color -> DocColors -> DocColors
BlogTheme.DocColors.border.set border1 = cases
  DocColors
    background
    title
    text
    textSubdued
    aside
    asideSource
    callout
    calloutSource
    source
    _
    divider
    evalResult
    evalIcon ->
    DocColors
      background
      title
      text
      textSubdued
      aside
      asideSource
      callout
      calloutSource
      source
      border1
      divider
      evalResult
      evalIcon

BlogTheme.DocColors.callout : DocColors -> BlogTheme.Color
BlogTheme.DocColors.callout = cases
  DocColors _ _ _ _ _ _ callout _ _ _ _ _ _ -> callout

BlogTheme.DocColors.callout.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> DocColors ->{g} DocColors
BlogTheme.DocColors.callout.modify f = cases
  DocColors
    background
    title
    text
    textSubdued
    aside
    asideSource
    callout
    calloutSource
    source
    border
    divider
    evalResult
    evalIcon ->
    DocColors
      background
      title
      text
      textSubdued
      aside
      asideSource
      (f callout)
      calloutSource
      source
      border
      divider
      evalResult
      evalIcon

BlogTheme.DocColors.callout.set : BlogTheme.Color -> DocColors -> DocColors
BlogTheme.DocColors.callout.set callout1 = cases
  DocColors
    background
    title
    text
    textSubdued
    aside
    asideSource
    _
    calloutSource
    source
    border
    divider
    evalResult
    evalIcon ->
    DocColors
      background
      title
      text
      textSubdued
      aside
      asideSource
      callout1
      calloutSource
      source
      border
      divider
      evalResult
      evalIcon

BlogTheme.DocColors.calloutSource : DocColors -> BlogTheme.Color
BlogTheme.DocColors.calloutSource = cases
  DocColors _ _ _ _ _ _ _ calloutSource _ _ _ _ _ -> calloutSource

BlogTheme.DocColors.calloutSource.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> DocColors ->{g} DocColors
BlogTheme.DocColors.calloutSource.modify f = cases
  DocColors
    background
    title
    text
    textSubdued
    aside
    asideSource
    callout
    calloutSource
    source
    border
    divider
    evalResult
    evalIcon ->
    DocColors
      background
      title
      text
      textSubdued
      aside
      asideSource
      callout
      (f calloutSource)
      source
      border
      divider
      evalResult
      evalIcon

BlogTheme.DocColors.calloutSource.set :
  BlogTheme.Color -> DocColors -> DocColors
BlogTheme.DocColors.calloutSource.set calloutSource1 = cases
  DocColors
    background
    title
    text
    textSubdued
    aside
    asideSource
    callout
    _
    source
    border
    divider
    evalResult
    evalIcon ->
    DocColors
      background
      title
      text
      textSubdued
      aside
      asideSource
      callout
      calloutSource1
      source
      border
      divider
      evalResult
      evalIcon

BlogTheme.DocColors.divider : DocColors -> BlogTheme.Color
BlogTheme.DocColors.divider = cases
  DocColors _ _ _ _ _ _ _ _ _ _ divider _ _ -> divider

BlogTheme.DocColors.divider.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> DocColors ->{g} DocColors
BlogTheme.DocColors.divider.modify f = cases
  DocColors
    background
    title
    text
    textSubdued
    aside
    asideSource
    callout
    calloutSource
    source
    border
    divider
    evalResult
    evalIcon ->
    DocColors
      background
      title
      text
      textSubdued
      aside
      asideSource
      callout
      calloutSource
      source
      border
      (f divider)
      evalResult
      evalIcon

BlogTheme.DocColors.divider.set : BlogTheme.Color -> DocColors -> DocColors
BlogTheme.DocColors.divider.set divider1 = cases
  DocColors
    background
    title
    text
    textSubdued
    aside
    asideSource
    callout
    calloutSource
    source
    border
    _
    evalResult
    evalIcon ->
    DocColors
      background
      title
      text
      textSubdued
      aside
      asideSource
      callout
      calloutSource
      source
      border
      divider1
      evalResult
      evalIcon

BlogTheme.DocColors.doc : Doc
BlogTheme.DocColors.doc =
  {{
  Represents the colors used in the blog theme for {type Doc} elements.
  
  # Fields
  
    * {{ docLink (docEmbedTermLink do DocColors.title) }} - The color of the
      {type Doc} title.
    * {{ docLink (docEmbedTermLink do DocColors.text) }} - The color of
      {type Doc} text.
    * {{ docLink (docEmbedTermLink do DocColors.textSubdued) }} - A subdued
      color for {type Doc} text.
    * {{ docLink (docEmbedTermLink do DocColors.aside) }} - The color of the
      {docAside} background.
    * {{ docLink (docEmbedTermLink do asideSource) }} - The background color of
      {docSource} elements in a {docAside}.
    * {{ docLink (docEmbedTermLink do callout) }} - The color of the
      {docCallout} background.
    * {{ docLink (docEmbedTermLink do calloutSource) }} - The background color
      of {docSource} elements in a {docCallout}.
    * {{ docLink (docEmbedTermLink do DocColors.border) }} - The color of
      borders around {type Doc} elements.
    * {{ docLink (docEmbedTermLink do DocColors.divider) }} - The color of
      horizontal dividers in {type Doc} elements.
  }}

BlogTheme.DocColors.evalIcon : DocColors -> BlogTheme.Color
BlogTheme.DocColors.evalIcon = cases
  DocColors _ _ _ _ _ _ _ _ _ _ _ _ evalIcon -> evalIcon

BlogTheme.DocColors.evalIcon.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> DocColors ->{g} DocColors
BlogTheme.DocColors.evalIcon.modify f = cases
  DocColors
    background
    title
    text
    textSubdued
    aside
    asideSource
    callout
    calloutSource
    source
    border
    divider
    evalResult
    evalIcon ->
    DocColors
      background
      title
      text
      textSubdued
      aside
      asideSource
      callout
      calloutSource
      source
      border
      divider
      evalResult
      (f evalIcon)

BlogTheme.DocColors.evalIcon.set : BlogTheme.Color -> DocColors -> DocColors
BlogTheme.DocColors.evalIcon.set evalIcon1 = cases
  DocColors
    background
    title
    text
    textSubdued
    aside
    asideSource
    callout
    calloutSource
    source
    border
    divider
    evalResult
    _ ->
    DocColors
      background
      title
      text
      textSubdued
      aside
      asideSource
      callout
      calloutSource
      source
      border
      divider
      evalResult
      evalIcon1

BlogTheme.DocColors.evalResult : DocColors -> BlogTheme.Color
BlogTheme.DocColors.evalResult = cases
  DocColors _ _ _ _ _ _ _ _ _ _ _ evalResult _ -> evalResult

BlogTheme.DocColors.evalResult.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> DocColors ->{g} DocColors
BlogTheme.DocColors.evalResult.modify f = cases
  DocColors
    background
    title
    text
    textSubdued
    aside
    asideSource
    callout
    calloutSource
    source
    border
    divider
    evalResult
    evalIcon ->
    DocColors
      background
      title
      text
      textSubdued
      aside
      asideSource
      callout
      calloutSource
      source
      border
      divider
      (f evalResult)
      evalIcon

BlogTheme.DocColors.evalResult.set : BlogTheme.Color -> DocColors -> DocColors
BlogTheme.DocColors.evalResult.set evalResult1 = cases
  DocColors
    background
    title
    text
    textSubdued
    aside
    asideSource
    callout
    calloutSource
    source
    border
    divider
    _
    evalIcon ->
    DocColors
      background
      title
      text
      textSubdued
      aside
      asideSource
      callout
      calloutSource
      source
      border
      divider
      evalResult1
      evalIcon

BlogTheme.docColors.modify :
  (DocColors ->{g} DocColors) -> BlogTheme ->{g} BlogTheme
BlogTheme.docColors.modify f = cases
  BlogTheme name mainFont monospaceFont colors syntaxColors docColors ->
    BlogTheme name mainFont monospaceFont colors syntaxColors (f docColors)

BlogTheme.docColors.set : DocColors -> BlogTheme -> BlogTheme
BlogTheme.docColors.set docColors1 = cases
  BlogTheme name mainFont monospaceFont colors syntaxColors _ ->
    BlogTheme name mainFont monospaceFont colors syntaxColors docColors1

BlogTheme.DocColors.source : DocColors -> BlogTheme.Color
BlogTheme.DocColors.source = cases
  DocColors _ _ _ _ _ _ _ _ source _ _ _ _ -> source

BlogTheme.DocColors.source.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> DocColors ->{g} DocColors
BlogTheme.DocColors.source.modify f = cases
  DocColors
    background
    title
    text
    textSubdued
    aside
    asideSource
    callout
    calloutSource
    source
    border
    divider
    evalResult
    evalIcon ->
    DocColors
      background
      title
      text
      textSubdued
      aside
      asideSource
      callout
      calloutSource
      (f source)
      border
      divider
      evalResult
      evalIcon

BlogTheme.DocColors.source.set : BlogTheme.Color -> DocColors -> DocColors
BlogTheme.DocColors.source.set source1 = cases
  DocColors
    background
    title
    text
    textSubdued
    aside
    asideSource
    callout
    calloutSource
    _
    border
    divider
    evalResult
    evalIcon ->
    DocColors
      background
      title
      text
      textSubdued
      aside
      asideSource
      callout
      calloutSource
      source1
      border
      divider
      evalResult
      evalIcon

BlogTheme.DocColors.text : DocColors -> BlogTheme.Color
BlogTheme.DocColors.text = cases DocColors _ _ text _ _ _ _ _ _ _ _ _ _ -> text

BlogTheme.DocColors.text.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> DocColors ->{g} DocColors
BlogTheme.DocColors.text.modify f = cases
  DocColors
    background
    title
    text
    textSubdued
    aside
    asideSource
    callout
    calloutSource
    source
    border
    divider
    evalResult
    evalIcon ->
    DocColors
      background
      title
      (f text)
      textSubdued
      aside
      asideSource
      callout
      calloutSource
      source
      border
      divider
      evalResult
      evalIcon

BlogTheme.DocColors.text.set : BlogTheme.Color -> DocColors -> DocColors
BlogTheme.DocColors.text.set text1 = cases
  DocColors
    background
    title
    _
    textSubdued
    aside
    asideSource
    callout
    calloutSource
    source
    border
    divider
    evalResult
    evalIcon ->
    DocColors
      background
      title
      text1
      textSubdued
      aside
      asideSource
      callout
      calloutSource
      source
      border
      divider
      evalResult
      evalIcon

BlogTheme.DocColors.textSubdued : DocColors -> BlogTheme.Color
BlogTheme.DocColors.textSubdued = cases
  DocColors _ _ _ textSubdued _ _ _ _ _ _ _ _ _ -> textSubdued

BlogTheme.DocColors.textSubdued.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> DocColors ->{g} DocColors
BlogTheme.DocColors.textSubdued.modify f = cases
  DocColors
    background
    title
    text
    textSubdued
    aside
    asideSource
    callout
    calloutSource
    source
    border
    divider
    evalResult
    evalIcon ->
    DocColors
      background
      title
      text
      (f textSubdued)
      aside
      asideSource
      callout
      calloutSource
      source
      border
      divider
      evalResult
      evalIcon

BlogTheme.DocColors.textSubdued.set : BlogTheme.Color -> DocColors -> DocColors
BlogTheme.DocColors.textSubdued.set textSubdued1 = cases
  DocColors
    background
    title
    text
    _
    aside
    asideSource
    callout
    calloutSource
    source
    border
    divider
    evalResult
    evalIcon ->
    DocColors
      background
      title
      text
      textSubdued1
      aside
      asideSource
      callout
      calloutSource
      source
      border
      divider
      evalResult
      evalIcon

BlogTheme.DocColors.title : DocColors -> BlogTheme.Color
BlogTheme.DocColors.title = cases
  DocColors _ title _ _ _ _ _ _ _ _ _ _ _ -> title

BlogTheme.DocColors.title.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> DocColors ->{g} DocColors
BlogTheme.DocColors.title.modify f = cases
  DocColors
    background
    title
    text
    textSubdued
    aside
    asideSource
    callout
    calloutSource
    source
    border
    divider
    evalResult
    evalIcon ->
    DocColors
      background
      (f title)
      text
      textSubdued
      aside
      asideSource
      callout
      calloutSource
      source
      border
      divider
      evalResult
      evalIcon

BlogTheme.DocColors.title.set : BlogTheme.Color -> DocColors -> DocColors
BlogTheme.DocColors.title.set title1 = cases
  DocColors
    background
    _
    text
    textSubdued
    aside
    asideSource
    callout
    calloutSource
    source
    border
    divider
    evalResult
    evalIcon ->
    DocColors
      background
      title1
      text
      textSubdued
      aside
      asideSource
      callout
      calloutSource
      source
      border
      divider
      evalResult
      evalIcon

BlogTheme.DocColors.toCSSRules : DocColors -> [Rule]
BlogTheme.DocColors.toCSSRules colors =
  use Color toText
  [ Rule "--color_doc_background" (colors |> DocColors.background |> toText)
  , Rule "--color_doc_title" (colors |> DocColors.title |> toText)
  , Rule "--color_doc_text" (colors |> DocColors.text |> toText)
  , Rule "--color_doc_aside" (colors |> DocColors.aside |> toText)
  , Rule "--color_doc_aside_source" (colors |> asideSource |> toText)
  , Rule "--color_doc_callout" (colors |> callout |> toText)
  , Rule "--color_doc_callout_source" (colors |> calloutSource |> toText)
  , Rule "--color_doc_text_subdued" (colors |> DocColors.textSubdued |> toText)
  , Rule "--color_doc_source" (colors |> DocColors.source |> toText)
  , Rule "--color_doc_border" (colors |> DocColors.border |> toText)
  , Rule "--color_doc_divider" (colors |> DocColors.divider |> toText)
  , Rule "--color_doc_eval-result" (colors |> evalResult |> toText)
  , Rule "--color_doc_eval-icon" (colors |> evalIcon |> toText)
  ]

BlogTheme.DocColors.toCSSRules.doc : Doc
BlogTheme.DocColors.toCSSRules.doc =
  {{ Converts a {type DocColors} to a list of CSS rules. }}

BlogTheme.FontStack.doc : Doc
BlogTheme.FontStack.doc =
  {{
  A {type FontStack} is a type that represents a stack of fonts. It's a simple
  wrapper around a list of {type Text} values that represent the names of the
  fonts in the stack. For example ``
  FontStack ["Helvetica", "Arial", "sans-serif"] `` represents a font stack
  that uses Helvetica, Arial, and then a generic sans-serif font.
  }}

BlogTheme.FontStack.toText : FontStack -> Text
BlogTheme.FontStack.toText = cases FontStack stack -> Text.join ", " stack

BlogTheme.FontStack.toText.doc : Doc
BlogTheme.FontStack.toText.doc =
  {{
  Converts a {type FontStack} to a {type Text} representation for use in CSS.
  }}

BlogTheme.mainFont : BlogTheme -> FontStack
BlogTheme.mainFont = cases BlogTheme _ mainFont _ _ _ _ -> mainFont

BlogTheme.mainFont.modify :
  (FontStack ->{g} FontStack) -> BlogTheme ->{g} BlogTheme
BlogTheme.mainFont.modify f = cases
  BlogTheme name mainFont monospaceFont colors syntaxColors docColors ->
    BlogTheme name (f mainFont) monospaceFont colors syntaxColors docColors

BlogTheme.mainFont.set : FontStack -> BlogTheme -> BlogTheme
BlogTheme.mainFont.set mainFont1 = cases
  BlogTheme name _ monospaceFont colors syntaxColors docColors ->
    BlogTheme name mainFont1 monospaceFont colors syntaxColors docColors

BlogTheme.monospaceFont : BlogTheme -> FontStack
BlogTheme.monospaceFont = cases
  BlogTheme _ _ monospaceFont _ _ _ -> monospaceFont

BlogTheme.monospaceFont.modify :
  (FontStack ->{g} FontStack) -> BlogTheme ->{g} BlogTheme
BlogTheme.monospaceFont.modify f = cases
  BlogTheme name mainFont monospaceFont colors syntaxColors docColors ->
    BlogTheme name mainFont (f monospaceFont) colors syntaxColors docColors

BlogTheme.monospaceFont.set : FontStack -> BlogTheme -> BlogTheme
BlogTheme.monospaceFont.set monospaceFont1 = cases
  BlogTheme name mainFont _ colors syntaxColors docColors ->
    BlogTheme name mainFont monospaceFont1 colors syntaxColors docColors

BlogTheme.name : BlogTheme -> Text
BlogTheme.name = cases BlogTheme name _ _ _ _ _ -> name

BlogTheme.name.modify : (Text ->{g} Text) -> BlogTheme ->{g} BlogTheme
BlogTheme.name.modify f = cases
  BlogTheme name mainFont monospaceFont colors syntaxColors docColors ->
    BlogTheme (f name) mainFont monospaceFont colors syntaxColors docColors

BlogTheme.name.set : Text -> BlogTheme -> BlogTheme
BlogTheme.name.set name1 = cases
  BlogTheme _ mainFont monospaceFont colors syntaxColors docColors ->
    BlogTheme name1 mainFont monospaceFont colors syntaxColors docColors

BlogTheme.syntaxColors : BlogTheme -> SyntaxColors
BlogTheme.syntaxColors = cases BlogTheme _ _ _ _ syntaxColors _ -> syntaxColors

BlogTheme.SyntaxColors.ability_ : SyntaxColors -> BlogTheme.Color
BlogTheme.SyntaxColors.ability_ = cases
  SyntaxColors _ _ _ _ _ _ _ _ ability_ _ _ _ _ _ _ _ _ _ -> ability_

BlogTheme.SyntaxColors.ability_.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> SyntaxColors ->{g} SyntaxColors
BlogTheme.SyntaxColors.ability_.modify f = cases
  SyntaxColors
    plain
    base
    verySubdued
    subdued
    keyword
    operator
    term
    termNamespace
    ability_
    type_
    typeNamespace
    constructor
    constructorNamespace
    text
    linkContainerHovered
    monochromeSubdued
    monochromeBase
    monochromeEmphasized ->
    SyntaxColors
      plain
      base
      verySubdued
      subdued
      keyword
      operator
      term
      termNamespace
      (f ability_)
      type_
      typeNamespace
      constructor
      constructorNamespace
      text
      linkContainerHovered
      monochromeSubdued
      monochromeBase
      monochromeEmphasized

BlogTheme.SyntaxColors.ability_.set :
  BlogTheme.Color -> SyntaxColors -> SyntaxColors
BlogTheme.SyntaxColors.ability_.set ability_1 = cases
  SyntaxColors
    plain
    base
    verySubdued
    subdued
    keyword
    operator
    term
    termNamespace
    _
    type_
    typeNamespace
    constructor
    constructorNamespace
    text
    linkContainerHovered
    monochromeSubdued
    monochromeBase
    monochromeEmphasized ->
    SyntaxColors
      plain
      base
      verySubdued
      subdued
      keyword
      operator
      term
      termNamespace
      ability_1
      type_
      typeNamespace
      constructor
      constructorNamespace
      text
      linkContainerHovered
      monochromeSubdued
      monochromeBase
      monochromeEmphasized

BlogTheme.SyntaxColors.base : SyntaxColors -> BlogTheme.Color
BlogTheme.SyntaxColors.base = cases
  SyntaxColors _ base _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ -> base

BlogTheme.SyntaxColors.base.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> SyntaxColors ->{g} SyntaxColors
BlogTheme.SyntaxColors.base.modify f = cases
  SyntaxColors
    plain
    base
    verySubdued
    subdued
    keyword
    operator
    term
    termNamespace
    ability_
    type_
    typeNamespace
    constructor
    constructorNamespace
    text
    linkContainerHovered
    monochromeSubdued
    monochromeBase
    monochromeEmphasized ->
    SyntaxColors
      plain
      (f base)
      verySubdued
      subdued
      keyword
      operator
      term
      termNamespace
      ability_
      type_
      typeNamespace
      constructor
      constructorNamespace
      text
      linkContainerHovered
      monochromeSubdued
      monochromeBase
      monochromeEmphasized

BlogTheme.SyntaxColors.base.set :
  BlogTheme.Color -> SyntaxColors -> SyntaxColors
BlogTheme.SyntaxColors.base.set base1 = cases
  SyntaxColors
    plain
    _
    verySubdued
    subdued
    keyword
    operator
    term
    termNamespace
    ability_
    type_
    typeNamespace
    constructor
    constructorNamespace
    text
    linkContainerHovered
    monochromeSubdued
    monochromeBase
    monochromeEmphasized ->
    SyntaxColors
      plain
      base1
      verySubdued
      subdued
      keyword
      operator
      term
      termNamespace
      ability_
      type_
      typeNamespace
      constructor
      constructorNamespace
      text
      linkContainerHovered
      monochromeSubdued
      monochromeBase
      monochromeEmphasized

BlogTheme.SyntaxColors.constructor : SyntaxColors -> BlogTheme.Color
BlogTheme.SyntaxColors.constructor = cases
  SyntaxColors _ _ _ _ _ _ _ _ _ _ _ constructor _ _ _ _ _ _ -> constructor

BlogTheme.SyntaxColors.constructor.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> SyntaxColors ->{g} SyntaxColors
BlogTheme.SyntaxColors.constructor.modify f = cases
  SyntaxColors
    plain
    base
    verySubdued
    subdued
    keyword
    operator
    term
    termNamespace
    ability_
    type_
    typeNamespace
    constructor
    constructorNamespace
    text
    linkContainerHovered
    monochromeSubdued
    monochromeBase
    monochromeEmphasized ->
    SyntaxColors
      plain
      base
      verySubdued
      subdued
      keyword
      operator
      term
      termNamespace
      ability_
      type_
      typeNamespace
      (f constructor)
      constructorNamespace
      text
      linkContainerHovered
      monochromeSubdued
      monochromeBase
      monochromeEmphasized

BlogTheme.SyntaxColors.constructor.set :
  BlogTheme.Color -> SyntaxColors -> SyntaxColors
BlogTheme.SyntaxColors.constructor.set constructor1 = cases
  SyntaxColors
    plain
    base
    verySubdued
    subdued
    keyword
    operator
    term
    termNamespace
    ability_
    type_
    typeNamespace
    _
    constructorNamespace
    text
    linkContainerHovered
    monochromeSubdued
    monochromeBase
    monochromeEmphasized ->
    SyntaxColors
      plain
      base
      verySubdued
      subdued
      keyword
      operator
      term
      termNamespace
      ability_
      type_
      typeNamespace
      constructor1
      constructorNamespace
      text
      linkContainerHovered
      monochromeSubdued
      monochromeBase
      monochromeEmphasized

BlogTheme.SyntaxColors.constructorNamespace : SyntaxColors -> BlogTheme.Color
BlogTheme.SyntaxColors.constructorNamespace = cases
  SyntaxColors _ _ _ _ _ _ _ _ _ _ _ _ constructorNamespace _ _ _ _ _ ->
    constructorNamespace

BlogTheme.SyntaxColors.constructorNamespace.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> SyntaxColors ->{g} SyntaxColors
BlogTheme.SyntaxColors.constructorNamespace.modify f = cases
  SyntaxColors
    plain
    base
    verySubdued
    subdued
    keyword
    operator
    term
    termNamespace
    ability_
    type_
    typeNamespace
    constructor
    constructorNamespace
    text
    linkContainerHovered
    monochromeSubdued
    monochromeBase
    monochromeEmphasized ->
    SyntaxColors
      plain
      base
      verySubdued
      subdued
      keyword
      operator
      term
      termNamespace
      ability_
      type_
      typeNamespace
      constructor
      (f constructorNamespace)
      text
      linkContainerHovered
      monochromeSubdued
      monochromeBase
      monochromeEmphasized

BlogTheme.SyntaxColors.constructorNamespace.set :
  BlogTheme.Color -> SyntaxColors -> SyntaxColors
BlogTheme.SyntaxColors.constructorNamespace.set constructorNamespace1 = cases
  SyntaxColors
    plain
    base
    verySubdued
    subdued
    keyword
    operator
    term
    termNamespace
    ability_
    type_
    typeNamespace
    constructor
    _
    text
    linkContainerHovered
    monochromeSubdued
    monochromeBase
    monochromeEmphasized ->
    SyntaxColors
      plain
      base
      verySubdued
      subdued
      keyword
      operator
      term
      termNamespace
      ability_
      type_
      typeNamespace
      constructor
      constructorNamespace1
      text
      linkContainerHovered
      monochromeSubdued
      monochromeBase
      monochromeEmphasized

BlogTheme.SyntaxColors.doc : Doc
BlogTheme.SyntaxColors.doc =
  {{
  A {type SyntaxColors} is a type that contains the syntax highlighting colors
  used by a blog. It has the following fields:
  
  * {{ docLink (docEmbedTermLink do plain) }} is the color used for plain text.
  * {{ docLink (docEmbedTermLink do SyntaxColors.base) }} is the base color
    used for syntax highlighting.
  * {{ docLink (docEmbedTermLink do verySubdued) }} is a very subdued version
    of the base color.
  * {{ docLink (docEmbedTermLink do subdued) }} is a subdued version of the
    base color.
  * {{ docLink (docEmbedTermLink do keyword) }} is the color used for keywords.
  * {{ docLink (docEmbedTermLink do SyntaxColors.operator) }} is the color used
    for operators.
  * {{ docLink (docEmbedTermLink do SyntaxColors.term) }} is the color used for
    terms.
  * {{ docLink (docEmbedTermLink do termNamespace) }} is the color used for
    term namespaces.
  * {{ docLink (docEmbedTermLink do ability_) }} is the color used for ability
    names.
  * {{ docLink (docEmbedTermLink do SyntaxColors.type_) }} is the color used
    for type names.
  * {{ docLink (docEmbedTermLink do typeNamespace) }} is the color used for
    type namespaces.
  * {{ docLink (docEmbedTermLink do constructor) }} is the color used for
    constructors.
  * {{ docLink (docEmbedTermLink do constructorNamespace) }} is the color used
    for the namespaces of constructors.
  * {{ docLink (docEmbedTermLink do SyntaxColors.text) }} is the color used for
    text strings.
  * {{ docLink (docEmbedTermLink do linkContainerHovered) }} is the color used
    for hyperlinked term/type names when they're hovered over.
  * {{ docLink (docEmbedTermLink do monochromeSubdued) }} is a subdued version
    of the base color that's used for monochrome text.
  * {{ docLink (docEmbedTermLink do monochromeBase) }} is the base color used
    for monochrome text.
  * {{ docLink (docEmbedTermLink do monochromeEmphasized) }} is an emphasized
    version of the base color that's used for monochrome text.
  }}

BlogTheme.SyntaxColors.keyword : SyntaxColors -> BlogTheme.Color
BlogTheme.SyntaxColors.keyword = cases
  SyntaxColors _ _ _ _ keyword _ _ _ _ _ _ _ _ _ _ _ _ _ -> keyword

BlogTheme.SyntaxColors.keyword.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> SyntaxColors ->{g} SyntaxColors
BlogTheme.SyntaxColors.keyword.modify f = cases
  SyntaxColors
    plain
    base
    verySubdued
    subdued
    keyword
    operator
    term
    termNamespace
    ability_
    type_
    typeNamespace
    constructor
    constructorNamespace
    text
    linkContainerHovered
    monochromeSubdued
    monochromeBase
    monochromeEmphasized ->
    SyntaxColors
      plain
      base
      verySubdued
      subdued
      (f keyword)
      operator
      term
      termNamespace
      ability_
      type_
      typeNamespace
      constructor
      constructorNamespace
      text
      linkContainerHovered
      monochromeSubdued
      monochromeBase
      monochromeEmphasized

BlogTheme.SyntaxColors.keyword.set :
  BlogTheme.Color -> SyntaxColors -> SyntaxColors
BlogTheme.SyntaxColors.keyword.set keyword1 = cases
  SyntaxColors
    plain
    base
    verySubdued
    subdued
    _
    operator
    term
    termNamespace
    ability_
    type_
    typeNamespace
    constructor
    constructorNamespace
    text
    linkContainerHovered
    monochromeSubdued
    monochromeBase
    monochromeEmphasized ->
    SyntaxColors
      plain
      base
      verySubdued
      subdued
      keyword1
      operator
      term
      termNamespace
      ability_
      type_
      typeNamespace
      constructor
      constructorNamespace
      text
      linkContainerHovered
      monochromeSubdued
      monochromeBase
      monochromeEmphasized

BlogTheme.SyntaxColors.linkContainerHovered : SyntaxColors -> BlogTheme.Color
BlogTheme.SyntaxColors.linkContainerHovered = cases
  SyntaxColors _ _ _ _ _ _ _ _ _ _ _ _ _ _ linkContainerHovered _ _ _ ->
    linkContainerHovered

BlogTheme.SyntaxColors.linkContainerHovered.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> SyntaxColors ->{g} SyntaxColors
BlogTheme.SyntaxColors.linkContainerHovered.modify f = cases
  SyntaxColors
    plain
    base
    verySubdued
    subdued
    keyword
    operator
    term
    termNamespace
    ability_
    type_
    typeNamespace
    constructor
    constructorNamespace
    text
    linkContainerHovered
    monochromeSubdued
    monochromeBase
    monochromeEmphasized ->
    SyntaxColors
      plain
      base
      verySubdued
      subdued
      keyword
      operator
      term
      termNamespace
      ability_
      type_
      typeNamespace
      constructor
      constructorNamespace
      text
      (f linkContainerHovered)
      monochromeSubdued
      monochromeBase
      monochromeEmphasized

BlogTheme.SyntaxColors.linkContainerHovered.set :
  BlogTheme.Color -> SyntaxColors -> SyntaxColors
BlogTheme.SyntaxColors.linkContainerHovered.set linkContainerHovered1 = cases
  SyntaxColors
    plain
    base
    verySubdued
    subdued
    keyword
    operator
    term
    termNamespace
    ability_
    type_
    typeNamespace
    constructor
    constructorNamespace
    text
    _
    monochromeSubdued
    monochromeBase
    monochromeEmphasized ->
    SyntaxColors
      plain
      base
      verySubdued
      subdued
      keyword
      operator
      term
      termNamespace
      ability_
      type_
      typeNamespace
      constructor
      constructorNamespace
      text
      linkContainerHovered1
      monochromeSubdued
      monochromeBase
      monochromeEmphasized

BlogTheme.syntaxColors.modify :
  (SyntaxColors ->{g} SyntaxColors) -> BlogTheme ->{g} BlogTheme
BlogTheme.syntaxColors.modify f = cases
  BlogTheme name mainFont monospaceFont colors syntaxColors docColors ->
    BlogTheme name mainFont monospaceFont colors (f syntaxColors) docColors

BlogTheme.SyntaxColors.monochromeBase : SyntaxColors -> BlogTheme.Color
BlogTheme.SyntaxColors.monochromeBase = cases
  SyntaxColors _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ monochromeBase _ ->
    monochromeBase

BlogTheme.SyntaxColors.monochromeBase.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> SyntaxColors ->{g} SyntaxColors
BlogTheme.SyntaxColors.monochromeBase.modify f = cases
  SyntaxColors
    plain
    base
    verySubdued
    subdued
    keyword
    operator
    term
    termNamespace
    ability_
    type_
    typeNamespace
    constructor
    constructorNamespace
    text
    linkContainerHovered
    monochromeSubdued
    monochromeBase
    monochromeEmphasized ->
    SyntaxColors
      plain
      base
      verySubdued
      subdued
      keyword
      operator
      term
      termNamespace
      ability_
      type_
      typeNamespace
      constructor
      constructorNamespace
      text
      linkContainerHovered
      monochromeSubdued
      (f monochromeBase)
      monochromeEmphasized

BlogTheme.SyntaxColors.monochromeBase.set :
  BlogTheme.Color -> SyntaxColors -> SyntaxColors
BlogTheme.SyntaxColors.monochromeBase.set monochromeBase1 = cases
  SyntaxColors
    plain
    base
    verySubdued
    subdued
    keyword
    operator
    term
    termNamespace
    ability_
    type_
    typeNamespace
    constructor
    constructorNamespace
    text
    linkContainerHovered
    monochromeSubdued
    _
    monochromeEmphasized ->
    SyntaxColors
      plain
      base
      verySubdued
      subdued
      keyword
      operator
      term
      termNamespace
      ability_
      type_
      typeNamespace
      constructor
      constructorNamespace
      text
      linkContainerHovered
      monochromeSubdued
      monochromeBase1
      monochromeEmphasized

BlogTheme.SyntaxColors.monochromeEmphasized : SyntaxColors -> BlogTheme.Color
BlogTheme.SyntaxColors.monochromeEmphasized = cases
  SyntaxColors _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ monochromeEmphasized ->
    monochromeEmphasized

BlogTheme.SyntaxColors.monochromeEmphasized.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> SyntaxColors ->{g} SyntaxColors
BlogTheme.SyntaxColors.monochromeEmphasized.modify f = cases
  SyntaxColors
    plain
    base
    verySubdued
    subdued
    keyword
    operator
    term
    termNamespace
    ability_
    type_
    typeNamespace
    constructor
    constructorNamespace
    text
    linkContainerHovered
    monochromeSubdued
    monochromeBase
    monochromeEmphasized ->
    SyntaxColors
      plain
      base
      verySubdued
      subdued
      keyword
      operator
      term
      termNamespace
      ability_
      type_
      typeNamespace
      constructor
      constructorNamespace
      text
      linkContainerHovered
      monochromeSubdued
      monochromeBase
      (f monochromeEmphasized)

BlogTheme.SyntaxColors.monochromeEmphasized.set :
  BlogTheme.Color -> SyntaxColors -> SyntaxColors
BlogTheme.SyntaxColors.monochromeEmphasized.set monochromeEmphasized1 = cases
  SyntaxColors
    plain
    base
    verySubdued
    subdued
    keyword
    operator
    term
    termNamespace
    ability_
    type_
    typeNamespace
    constructor
    constructorNamespace
    text
    linkContainerHovered
    monochromeSubdued
    monochromeBase
    _ ->
    SyntaxColors
      plain
      base
      verySubdued
      subdued
      keyword
      operator
      term
      termNamespace
      ability_
      type_
      typeNamespace
      constructor
      constructorNamespace
      text
      linkContainerHovered
      monochromeSubdued
      monochromeBase
      monochromeEmphasized1

BlogTheme.SyntaxColors.monochromeSubdued : SyntaxColors -> BlogTheme.Color
BlogTheme.SyntaxColors.monochromeSubdued = cases
  SyntaxColors _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ monochromeSubdued _ _ ->
    monochromeSubdued

BlogTheme.SyntaxColors.monochromeSubdued.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> SyntaxColors ->{g} SyntaxColors
BlogTheme.SyntaxColors.monochromeSubdued.modify f = cases
  SyntaxColors
    plain
    base
    verySubdued
    subdued
    keyword
    operator
    term
    termNamespace
    ability_
    type_
    typeNamespace
    constructor
    constructorNamespace
    text
    linkContainerHovered
    monochromeSubdued
    monochromeBase
    monochromeEmphasized ->
    SyntaxColors
      plain
      base
      verySubdued
      subdued
      keyword
      operator
      term
      termNamespace
      ability_
      type_
      typeNamespace
      constructor
      constructorNamespace
      text
      linkContainerHovered
      (f monochromeSubdued)
      monochromeBase
      monochromeEmphasized

BlogTheme.SyntaxColors.monochromeSubdued.set :
  BlogTheme.Color -> SyntaxColors -> SyntaxColors
BlogTheme.SyntaxColors.monochromeSubdued.set monochromeSubdued1 = cases
  SyntaxColors
    plain
    base
    verySubdued
    subdued
    keyword
    operator
    term
    termNamespace
    ability_
    type_
    typeNamespace
    constructor
    constructorNamespace
    text
    linkContainerHovered
    _
    monochromeBase
    monochromeEmphasized ->
    SyntaxColors
      plain
      base
      verySubdued
      subdued
      keyword
      operator
      term
      termNamespace
      ability_
      type_
      typeNamespace
      constructor
      constructorNamespace
      text
      linkContainerHovered
      monochromeSubdued1
      monochromeBase
      monochromeEmphasized

BlogTheme.SyntaxColors.operator : SyntaxColors -> BlogTheme.Color
BlogTheme.SyntaxColors.operator = cases
  SyntaxColors _ _ _ _ _ operator _ _ _ _ _ _ _ _ _ _ _ _ -> operator

BlogTheme.SyntaxColors.operator.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> SyntaxColors ->{g} SyntaxColors
BlogTheme.SyntaxColors.operator.modify f = cases
  SyntaxColors
    plain
    base
    verySubdued
    subdued
    keyword
    operator
    term
    termNamespace
    ability_
    type_
    typeNamespace
    constructor
    constructorNamespace
    text
    linkContainerHovered
    monochromeSubdued
    monochromeBase
    monochromeEmphasized ->
    SyntaxColors
      plain
      base
      verySubdued
      subdued
      keyword
      (f operator)
      term
      termNamespace
      ability_
      type_
      typeNamespace
      constructor
      constructorNamespace
      text
      linkContainerHovered
      monochromeSubdued
      monochromeBase
      monochromeEmphasized

BlogTheme.SyntaxColors.operator.set :
  BlogTheme.Color -> SyntaxColors -> SyntaxColors
BlogTheme.SyntaxColors.operator.set operator1 = cases
  SyntaxColors
    plain
    base
    verySubdued
    subdued
    keyword
    _
    term
    termNamespace
    ability_
    type_
    typeNamespace
    constructor
    constructorNamespace
    text
    linkContainerHovered
    monochromeSubdued
    monochromeBase
    monochromeEmphasized ->
    SyntaxColors
      plain
      base
      verySubdued
      subdued
      keyword
      operator1
      term
      termNamespace
      ability_
      type_
      typeNamespace
      constructor
      constructorNamespace
      text
      linkContainerHovered
      monochromeSubdued
      monochromeBase
      monochromeEmphasized

BlogTheme.SyntaxColors.plain : SyntaxColors -> BlogTheme.Color
BlogTheme.SyntaxColors.plain = cases
  SyntaxColors plain _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ -> plain

BlogTheme.SyntaxColors.plain.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> SyntaxColors ->{g} SyntaxColors
BlogTheme.SyntaxColors.plain.modify f = cases
  SyntaxColors
    plain
    base
    verySubdued
    subdued
    keyword
    operator
    term
    termNamespace
    ability_
    type_
    typeNamespace
    constructor
    constructorNamespace
    text
    linkContainerHovered
    monochromeSubdued
    monochromeBase
    monochromeEmphasized ->
    SyntaxColors
      (f plain)
      base
      verySubdued
      subdued
      keyword
      operator
      term
      termNamespace
      ability_
      type_
      typeNamespace
      constructor
      constructorNamespace
      text
      linkContainerHovered
      monochromeSubdued
      monochromeBase
      monochromeEmphasized

BlogTheme.SyntaxColors.plain.set :
  BlogTheme.Color -> SyntaxColors -> SyntaxColors
BlogTheme.SyntaxColors.plain.set plain1 = cases
  SyntaxColors
    _
    base
    verySubdued
    subdued
    keyword
    operator
    term
    termNamespace
    ability_
    type_
    typeNamespace
    constructor
    constructorNamespace
    text
    linkContainerHovered
    monochromeSubdued
    monochromeBase
    monochromeEmphasized ->
    SyntaxColors
      plain1
      base
      verySubdued
      subdued
      keyword
      operator
      term
      termNamespace
      ability_
      type_
      typeNamespace
      constructor
      constructorNamespace
      text
      linkContainerHovered
      monochromeSubdued
      monochromeBase
      monochromeEmphasized

BlogTheme.syntaxColors.set : SyntaxColors -> BlogTheme -> BlogTheme
BlogTheme.syntaxColors.set syntaxColors1 = cases
  BlogTheme name mainFont monospaceFont colors _ docColors ->
    BlogTheme name mainFont monospaceFont colors syntaxColors1 docColors

BlogTheme.SyntaxColors.subdued : SyntaxColors -> BlogTheme.Color
BlogTheme.SyntaxColors.subdued = cases
  SyntaxColors _ _ _ subdued _ _ _ _ _ _ _ _ _ _ _ _ _ _ -> subdued

BlogTheme.SyntaxColors.subdued.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> SyntaxColors ->{g} SyntaxColors
BlogTheme.SyntaxColors.subdued.modify f = cases
  SyntaxColors
    plain
    base
    verySubdued
    subdued
    keyword
    operator
    term
    termNamespace
    ability_
    type_
    typeNamespace
    constructor
    constructorNamespace
    text
    linkContainerHovered
    monochromeSubdued
    monochromeBase
    monochromeEmphasized ->
    SyntaxColors
      plain
      base
      verySubdued
      (f subdued)
      keyword
      operator
      term
      termNamespace
      ability_
      type_
      typeNamespace
      constructor
      constructorNamespace
      text
      linkContainerHovered
      monochromeSubdued
      monochromeBase
      monochromeEmphasized

BlogTheme.SyntaxColors.subdued.set :
  BlogTheme.Color -> SyntaxColors -> SyntaxColors
BlogTheme.SyntaxColors.subdued.set subdued1 = cases
  SyntaxColors
    plain
    base
    verySubdued
    _
    keyword
    operator
    term
    termNamespace
    ability_
    type_
    typeNamespace
    constructor
    constructorNamespace
    text
    linkContainerHovered
    monochromeSubdued
    monochromeBase
    monochromeEmphasized ->
    SyntaxColors
      plain
      base
      verySubdued
      subdued1
      keyword
      operator
      term
      termNamespace
      ability_
      type_
      typeNamespace
      constructor
      constructorNamespace
      text
      linkContainerHovered
      monochromeSubdued
      monochromeBase
      monochromeEmphasized

BlogTheme.SyntaxColors.term : SyntaxColors -> BlogTheme.Color
BlogTheme.SyntaxColors.term = cases
  SyntaxColors _ _ _ _ _ _ term _ _ _ _ _ _ _ _ _ _ _ -> term

BlogTheme.SyntaxColors.term.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> SyntaxColors ->{g} SyntaxColors
BlogTheme.SyntaxColors.term.modify f = cases
  SyntaxColors
    plain
    base
    verySubdued
    subdued
    keyword
    operator
    term
    termNamespace
    ability_
    type_
    typeNamespace
    constructor
    constructorNamespace
    text
    linkContainerHovered
    monochromeSubdued
    monochromeBase
    monochromeEmphasized ->
    SyntaxColors
      plain
      base
      verySubdued
      subdued
      keyword
      operator
      (f term)
      termNamespace
      ability_
      type_
      typeNamespace
      constructor
      constructorNamespace
      text
      linkContainerHovered
      monochromeSubdued
      monochromeBase
      monochromeEmphasized

BlogTheme.SyntaxColors.term.set :
  BlogTheme.Color -> SyntaxColors -> SyntaxColors
BlogTheme.SyntaxColors.term.set term1 = cases
  SyntaxColors
    plain
    base
    verySubdued
    subdued
    keyword
    operator
    _
    termNamespace
    ability_
    type_
    typeNamespace
    constructor
    constructorNamespace
    text
    linkContainerHovered
    monochromeSubdued
    monochromeBase
    monochromeEmphasized ->
    SyntaxColors
      plain
      base
      verySubdued
      subdued
      keyword
      operator
      term1
      termNamespace
      ability_
      type_
      typeNamespace
      constructor
      constructorNamespace
      text
      linkContainerHovered
      monochromeSubdued
      monochromeBase
      monochromeEmphasized

BlogTheme.SyntaxColors.termNamespace : SyntaxColors -> BlogTheme.Color
BlogTheme.SyntaxColors.termNamespace = cases
  SyntaxColors _ _ _ _ _ _ _ termNamespace _ _ _ _ _ _ _ _ _ _ -> termNamespace

BlogTheme.SyntaxColors.termNamespace.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> SyntaxColors ->{g} SyntaxColors
BlogTheme.SyntaxColors.termNamespace.modify f = cases
  SyntaxColors
    plain
    base
    verySubdued
    subdued
    keyword
    operator
    term
    termNamespace
    ability_
    type_
    typeNamespace
    constructor
    constructorNamespace
    text
    linkContainerHovered
    monochromeSubdued
    monochromeBase
    monochromeEmphasized ->
    SyntaxColors
      plain
      base
      verySubdued
      subdued
      keyword
      operator
      term
      (f termNamespace)
      ability_
      type_
      typeNamespace
      constructor
      constructorNamespace
      text
      linkContainerHovered
      monochromeSubdued
      monochromeBase
      monochromeEmphasized

BlogTheme.SyntaxColors.termNamespace.set :
  BlogTheme.Color -> SyntaxColors -> SyntaxColors
BlogTheme.SyntaxColors.termNamespace.set termNamespace1 = cases
  SyntaxColors
    plain
    base
    verySubdued
    subdued
    keyword
    operator
    term
    _
    ability_
    type_
    typeNamespace
    constructor
    constructorNamespace
    text
    linkContainerHovered
    monochromeSubdued
    monochromeBase
    monochromeEmphasized ->
    SyntaxColors
      plain
      base
      verySubdued
      subdued
      keyword
      operator
      term
      termNamespace1
      ability_
      type_
      typeNamespace
      constructor
      constructorNamespace
      text
      linkContainerHovered
      monochromeSubdued
      monochromeBase
      monochromeEmphasized

BlogTheme.SyntaxColors.text : SyntaxColors -> BlogTheme.Color
BlogTheme.SyntaxColors.text = cases
  SyntaxColors _ _ _ _ _ _ _ _ _ _ _ _ _ text _ _ _ _ -> text

BlogTheme.SyntaxColors.text.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> SyntaxColors ->{g} SyntaxColors
BlogTheme.SyntaxColors.text.modify f = cases
  SyntaxColors
    plain
    base
    verySubdued
    subdued
    keyword
    operator
    term
    termNamespace
    ability_
    type_
    typeNamespace
    constructor
    constructorNamespace
    text
    linkContainerHovered
    monochromeSubdued
    monochromeBase
    monochromeEmphasized ->
    SyntaxColors
      plain
      base
      verySubdued
      subdued
      keyword
      operator
      term
      termNamespace
      ability_
      type_
      typeNamespace
      constructor
      constructorNamespace
      (f text)
      linkContainerHovered
      monochromeSubdued
      monochromeBase
      monochromeEmphasized

BlogTheme.SyntaxColors.text.set :
  BlogTheme.Color -> SyntaxColors -> SyntaxColors
BlogTheme.SyntaxColors.text.set text1 = cases
  SyntaxColors
    plain
    base
    verySubdued
    subdued
    keyword
    operator
    term
    termNamespace
    ability_
    type_
    typeNamespace
    constructor
    constructorNamespace
    _
    linkContainerHovered
    monochromeSubdued
    monochromeBase
    monochromeEmphasized ->
    SyntaxColors
      plain
      base
      verySubdued
      subdued
      keyword
      operator
      term
      termNamespace
      ability_
      type_
      typeNamespace
      constructor
      constructorNamespace
      text1
      linkContainerHovered
      monochromeSubdued
      monochromeBase
      monochromeEmphasized

BlogTheme.SyntaxColors.toCSS : SyntaxColors -> CSS
BlogTheme.SyntaxColors.toCSS colors =
  CSS [RuleSet [Selector ":root"] (SyntaxColors.toCSSRules colors)]

BlogTheme.SyntaxColors.toCSS.doc : Doc
BlogTheme.SyntaxColors.toCSS.doc =
  {{ Converts a {type SyntaxColors} to a {type CSS} stylesheet. }}

BlogTheme.SyntaxColors.toCSSRules : SyntaxColors -> [Rule]
BlogTheme.SyntaxColors.toCSSRules colors =
  use Color toText
  [ Rule "--color_syntax_plain" (colors |> plain |> toText)
  , Rule "--color_syntax_base" (colors |> SyntaxColors.base |> toText)
  , Rule "--color_syntax_very-subdued" (colors |> verySubdued |> toText)
  , Rule "--color_syntax_subdued" (colors |> subdued |> toText)
  , Rule "--color_syntax_keyword" (colors |> keyword |> toText)
  , Rule "--color_syntax_operator" (colors |> SyntaxColors.operator |> toText)
  , Rule "--color_syntax_term" (colors |> SyntaxColors.term |> toText)
  , Rule "--color_syntax_term-namespace" (colors |> termNamespace |> toText)
  , Rule "--color_syntax_ability" (colors |> ability_ |> toText)
  , Rule "--color_syntax_type" (colors |> SyntaxColors.type_ |> toText)
  , Rule "--color_syntax_type-namespace" (colors |> typeNamespace |> toText)
  , Rule "--color_syntax_constructor" (colors |> constructor |> toText)
  , Rule
      "--color_syntax_constructor-namespace"
      (colors |> constructorNamespace |> toText)
  , Rule "--color_syntax_text" (colors |> SyntaxColors.text |> toText)
  , Rule
      "--color_syntax_link_container_hovered"
      (colors |> linkContainerHovered |> toText)
  , Rule
      "--color_syntax_monochrome-subdued"
      (colors |> monochromeSubdued |> toText)
  , Rule "--color_syntax_monochrome-base" (colors |> monochromeBase |> toText)
  , Rule
      "--color_syntax_monochrome_emphasized"
      (colors |> monochromeEmphasized |> toText)
  ]

BlogTheme.SyntaxColors.toCSSRules.doc : Doc
BlogTheme.SyntaxColors.toCSSRules.doc =
  {{ Converts a {type SyntaxColors} to a list of CSS rules. }}

BlogTheme.SyntaxColors.typeNamespace : SyntaxColors -> BlogTheme.Color
BlogTheme.SyntaxColors.typeNamespace = cases
  SyntaxColors _ _ _ _ _ _ _ _ _ _ typeNamespace _ _ _ _ _ _ _ -> typeNamespace

BlogTheme.SyntaxColors.typeNamespace.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> SyntaxColors ->{g} SyntaxColors
BlogTheme.SyntaxColors.typeNamespace.modify f = cases
  SyntaxColors
    plain
    base
    verySubdued
    subdued
    keyword
    operator
    term
    termNamespace
    ability_
    type_
    typeNamespace
    constructor
    constructorNamespace
    text
    linkContainerHovered
    monochromeSubdued
    monochromeBase
    monochromeEmphasized ->
    SyntaxColors
      plain
      base
      verySubdued
      subdued
      keyword
      operator
      term
      termNamespace
      ability_
      type_
      (f typeNamespace)
      constructor
      constructorNamespace
      text
      linkContainerHovered
      monochromeSubdued
      monochromeBase
      monochromeEmphasized

BlogTheme.SyntaxColors.typeNamespace.set :
  BlogTheme.Color -> SyntaxColors -> SyntaxColors
BlogTheme.SyntaxColors.typeNamespace.set typeNamespace1 = cases
  SyntaxColors
    plain
    base
    verySubdued
    subdued
    keyword
    operator
    term
    termNamespace
    ability_
    type_
    _
    constructor
    constructorNamespace
    text
    linkContainerHovered
    monochromeSubdued
    monochromeBase
    monochromeEmphasized ->
    SyntaxColors
      plain
      base
      verySubdued
      subdued
      keyword
      operator
      term
      termNamespace
      ability_
      type_
      typeNamespace1
      constructor
      constructorNamespace
      text
      linkContainerHovered
      monochromeSubdued
      monochromeBase
      monochromeEmphasized

BlogTheme.SyntaxColors.type_ : SyntaxColors -> BlogTheme.Color
BlogTheme.SyntaxColors.type_ = cases
  SyntaxColors _ _ _ _ _ _ _ _ _ type_ _ _ _ _ _ _ _ _ -> type_

BlogTheme.SyntaxColors.type_.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> SyntaxColors ->{g} SyntaxColors
BlogTheme.SyntaxColors.type_.modify f = cases
  SyntaxColors
    plain
    base
    verySubdued
    subdued
    keyword
    operator
    term
    termNamespace
    ability_
    type_
    typeNamespace
    constructor
    constructorNamespace
    text
    linkContainerHovered
    monochromeSubdued
    monochromeBase
    monochromeEmphasized ->
    SyntaxColors
      plain
      base
      verySubdued
      subdued
      keyword
      operator
      term
      termNamespace
      ability_
      (f type_)
      typeNamespace
      constructor
      constructorNamespace
      text
      linkContainerHovered
      monochromeSubdued
      monochromeBase
      monochromeEmphasized

BlogTheme.SyntaxColors.type_.set :
  BlogTheme.Color -> SyntaxColors -> SyntaxColors
BlogTheme.SyntaxColors.type_.set type_1 = cases
  SyntaxColors
    plain
    base
    verySubdued
    subdued
    keyword
    operator
    term
    termNamespace
    ability_
    _
    typeNamespace
    constructor
    constructorNamespace
    text
    linkContainerHovered
    monochromeSubdued
    monochromeBase
    monochromeEmphasized ->
    SyntaxColors
      plain
      base
      verySubdued
      subdued
      keyword
      operator
      term
      termNamespace
      ability_
      type_1
      typeNamespace
      constructor
      constructorNamespace
      text
      linkContainerHovered
      monochromeSubdued
      monochromeBase
      monochromeEmphasized

BlogTheme.SyntaxColors.verySubdued : SyntaxColors -> BlogTheme.Color
BlogTheme.SyntaxColors.verySubdued = cases
  SyntaxColors _ _ verySubdued _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ -> verySubdued

BlogTheme.SyntaxColors.verySubdued.modify :
  (BlogTheme.Color ->{g} BlogTheme.Color) -> SyntaxColors ->{g} SyntaxColors
BlogTheme.SyntaxColors.verySubdued.modify f = cases
  SyntaxColors
    plain
    base
    verySubdued
    subdued
    keyword
    operator
    term
    termNamespace
    ability_
    type_
    typeNamespace
    constructor
    constructorNamespace
    text
    linkContainerHovered
    monochromeSubdued
    monochromeBase
    monochromeEmphasized ->
    SyntaxColors
      plain
      base
      (f verySubdued)
      subdued
      keyword
      operator
      term
      termNamespace
      ability_
      type_
      typeNamespace
      constructor
      constructorNamespace
      text
      linkContainerHovered
      monochromeSubdued
      monochromeBase
      monochromeEmphasized

BlogTheme.SyntaxColors.verySubdued.set :
  BlogTheme.Color -> SyntaxColors -> SyntaxColors
BlogTheme.SyntaxColors.verySubdued.set verySubdued1 = cases
  SyntaxColors
    plain
    base
    _
    subdued
    keyword
    operator
    term
    termNamespace
    ability_
    type_
    typeNamespace
    constructor
    constructorNamespace
    text
    linkContainerHovered
    monochromeSubdued
    monochromeBase
    monochromeEmphasized ->
    SyntaxColors
      plain
      base
      verySubdued1
      subdued
      keyword
      operator
      term
      termNamespace
      ability_
      type_
      typeNamespace
      constructor
      constructorNamespace
      text
      linkContainerHovered
      monochromeSubdued
      monochromeBase
      monochromeEmphasized

BlogTheme.toCSS : BlogTheme -> CSS
BlogTheme.toCSS = cases
  BlogTheme name mainFont monospaceFont colors syntaxColors docColors ->
    use List ++
    rules =
      [ Rule "--font_main" (FontStack.toText mainFont)
      , Rule "--font_monospace" (FontStack.toText monospaceFont)
      , Rule "--font-size-mega-huge" "4rem"
      , Rule "--font-size-huge" "2rem"
      , Rule "--font-size-large" "1.5rem"
      , Rule "--font-size-base" "1rem"
      , Rule "--font-size-medium" "0.875rem"
      , Rule "--font-size-small" "0.75rem"
      , Rule "--border-radius-base" "0.25rem"
      , Rule "--color_background" (Color.toText (BlogColors.background colors))
      , Rule "--color_text" (Color.toText (BlogColors.text colors))
      , Rule
          "--color_text_subdued" (Color.toText (BlogColors.textSubdued colors))
      , Rule
          "--color_text_very-subdued" (Color.toText (textVerySubdued colors))
      , Rule "--color_text_emphasized" (Color.toText (textEmphasized colors))
      , Rule "--color_icon" (Color.toText (icon colors))
      , Rule "--color-icon_subdued" (Color.toText (iconSubdued colors))
      , Rule "--color_icon_emphasized" (Color.toText (iconEmphasized colors))
      , Rule "--color_border" (Color.toText (BlogColors.border colors))
      , Rule "--color_border_subdued" (Color.toText (borderSubdued colors))
      , Rule
          "--color_border_emphasized" (Color.toText (borderEmphasized colors))
      , Rule "--color_divider" (Color.toText (BlogColors.divider colors))
      , Rule "--color_container" (Color.toText (container colors))
      , Rule
          "--color_container_subdued" (Color.toText (containerSubdued colors))
      , Rule
          "--color_interactive" (Color.toText (BlogColors.interactive colors))
      , Rule
          "--color_interactive_hover" (Color.toText (interactiveHover colors))
      , Rule "--color_focus-border" (Color.toText (focusBorder colors))
      , Rule "--color_focus-outline" (Color.toText (focusOutline colors))
      , Rule "--color_element" (Color.toText (BlogColors.element colors))
      , Rule "--color_element_subdued" (Color.toText (elementSubdued colors))
      , Rule
          "--color_element_emphasized"
          (Color.toText (elementEmphasized colors))
      , Rule
          "--color_info_container_subdued"
          (Color.toText (infoContainerSubdued colors))
      , Rule "--color_button" (Color.toText (BlogColors.button colors))
      , Rule "--color_button_text" (Color.toText (buttonText colors))
      , Rule
          "--color_button_emphasized" (Color.toText (buttonEmphasized colors))
      , Rule
          "--color_button_text_emphasized"
          (Color.toText (buttonTextEmphasized colors))
      ]
        ++ SyntaxColors.toCSSRules syntaxColors
        ++ DocColors.toCSSRules docColors
    CSS [RuleSet [Selector ":root"] rules]

BlogTheme.toCSS.doc : Doc
BlogTheme.toCSS.doc =
  {{ Converts a {type BlogTheme} to a {type CSS} stylesheet. }}

BlogTheme.unisonLight : BlogTheme
BlogTheme.unisonLight =
  use BlogColors text
  sansSerif = FontStack ["'Inter'", "system-ui", "sans-serif"]
  monospace = FontStack ["'Fira Code'", "monospace"]
  grayLighten100 = Color "#ffffff"
  grayLighten60 = Color "#fafafb"
  grayLighten55 = Color "#f1f3f5"
  grayLighten50 = Color "#e4eaf3"
  grayLighten45 = Color "#d9e0e7"
  grayLighten40 = Color "#d1d5dc"
  grayLighten30 = Color "#bdbfc6"
  grayLighten20 = Color "#818286"
  grayBase = Color "#515258"
  grayDarken20 = Color "#2d2e35"
  grayDarken30 = Color "#18181c"
  blue1 = Color "#225ebe"
  blue2 = Color "#5695f4"
  blue5 = Color "#ecf2fa"
  pink1 = Color "#ff4756"
  pink2 = Color "#ff6c78"
  purple2 = Color "#734da3"
  purple3 = Color "#9a76c8"
  green1 = Color "#27ae60"
  colors =
    BlogColors
      grayLighten100
      grayDarken20
      grayLighten20
      grayLighten30
      grayDarken30
      grayLighten20
      grayLighten30
      grayDarken20
      grayLighten45
      grayLighten50
      grayLighten40
      grayLighten55
      grayLighten100
      grayLighten60
      blue1
      blue2
      blue1
      blue2
      blue5
      grayLighten100
      grayLighten60
      grayLighten55
      grayLighten60
      grayDarken30
      grayDarken30
      grayLighten100
  syntaxColors =
    SyntaxColors
      (text colors)
      grayDarken30
      grayLighten30
      grayBase
      pink2
      grayLighten30
      purple2
      purple3
      pink1
      blue1
      blue2
      blue1
      blue2
      green1
      grayLighten50
      (BlogColors.textSubdued colors)
      (text colors)
      (textEmphasized colors)
  docColors =
    DocColors
      (BlogColors.background colors)
      pink1
      (text colors)
      (textVerySubdued colors)
      (containerSubdued colors)
      (elementEmphasized colors)
      (infoContainerSubdued colors)
      (elementEmphasized colors)
      (elementSubdued colors)
      (borderSubdued colors)
      (BlogColors.divider colors)
      (elementEmphasized colors)
      (textVerySubdued colors)
  BlogTheme
    "unison-light-theme" sansSerif monospace colors syntaxColors docColors

BlogTheme.unisonLight.doc : Doc
BlogTheme.unisonLight.doc =
  {{ A default light theme for blogs, based on the Unison design system. }}

emails.EmailNotificationsConfig.baseURI : EmailNotificationsConfig -> URI
emails.EmailNotificationsConfig.baseURI = cases
  EmailNotificationsConfig _ baseURI -> baseURI

emails.EmailNotificationsConfig.baseURI.modify :
  (URI ->{g} URI) -> EmailNotificationsConfig ->{g} EmailNotificationsConfig
emails.EmailNotificationsConfig.baseURI.modify f = cases
  EmailNotificationsConfig senderEmail baseURI ->
    EmailNotificationsConfig senderEmail (f baseURI)

emails.EmailNotificationsConfig.baseURI.set :
  URI -> EmailNotificationsConfig -> EmailNotificationsConfig
emails.EmailNotificationsConfig.baseURI.set baseURI1 = cases
  EmailNotificationsConfig senderEmail _ ->
    EmailNotificationsConfig senderEmail baseURI1

emails.EmailNotificationsConfig.doc : Doc
emails.EmailNotificationsConfig.doc =
  {{
  One part of the configuration needed for enabling email notifications. (The
  other being an Environment setting called `sendgrid_api_key`; see
  {setSendgridApiKey})
  
  The {senderEmail} field represents the email address, notifications are sent
  from, while the {EmailNotificationsConfig.baseURI} field presents the domain
  and path that links to the blog appearing in the email will be prefixed with.
  }}

emails.EmailNotificationsConfig.senderEmail :
  EmailNotificationsConfig -> MailAddress
emails.EmailNotificationsConfig.senderEmail = cases
  EmailNotificationsConfig senderEmail _ -> senderEmail

emails.EmailNotificationsConfig.senderEmail.modify :
  (MailAddress ->{g} MailAddress)
  -> EmailNotificationsConfig
  ->{g} EmailNotificationsConfig
emails.EmailNotificationsConfig.senderEmail.modify f = cases
  EmailNotificationsConfig senderEmail baseURI ->
    EmailNotificationsConfig (f senderEmail) baseURI

emails.EmailNotificationsConfig.senderEmail.set :
  MailAddress -> EmailNotificationsConfig -> EmailNotificationsConfig
emails.EmailNotificationsConfig.senderEmail.set senderEmail1 = cases
  EmailNotificationsConfig _ baseURI ->
    EmailNotificationsConfig senderEmail1 baseURI

emails.NewPostEmailNotification.blog : NewPostEmailNotification -> Blog
emails.NewPostEmailNotification.blog = cases
  NewPostEmailNotification blog _ -> blog

emails.NewPostEmailNotification.blog.modify :
  (Blog ->{g} Blog) -> NewPostEmailNotification ->{g} NewPostEmailNotification
emails.NewPostEmailNotification.blog.modify f = cases
  NewPostEmailNotification blog post -> NewPostEmailNotification (f blog) post

emails.NewPostEmailNotification.blog.set :
  Blog -> NewPostEmailNotification -> NewPostEmailNotification
emails.NewPostEmailNotification.blog.set blog1 = cases
  NewPostEmailNotification _ post -> NewPostEmailNotification blog1 post

emails.NewPostEmailNotification.box :
  [Attribute] -> [Attribute] -> [Html] -> Html
emails.NewPostEmailNotification.box outerAttrs innerAttrs content =
  hojberg_html_2_6_0.table
    outerAttrs [tbody [] [tr [] [td innerAttrs content]]]

emails.NewPostEmailNotification.post : NewPostEmailNotification -> Post
emails.NewPostEmailNotification.post = cases
  NewPostEmailNotification _ post -> post

emails.NewPostEmailNotification.post.modify :
  (Post ->{g} Post) -> NewPostEmailNotification ->{g} NewPostEmailNotification
emails.NewPostEmailNotification.post.modify f = cases
  NewPostEmailNotification blog post -> NewPostEmailNotification blog (f post)

emails.NewPostEmailNotification.post.set :
  Post -> NewPostEmailNotification -> NewPostEmailNotification
emails.NewPostEmailNotification.post.set post1 = cases
  NewPostEmailNotification blog _ -> NewPostEmailNotification blog post1

emails.NewPostEmailNotification.styles : Text
emails.NewPostEmailNotification.styles =
  """
  /* reset */
  a[x-apple-data-detectors] {
    color: inherit !important;
    text-decoration: none !important;
    font-size: inherit !important;
    font-family: inherit !important;
    font-weight: inherit !important;
    line-height: inherit !important;
  }
  
  * {
    box-sizing: border-box;
  }
  
  body, h1, h2, h3, h4, h5, ul, p, ol, table, tr, td, li {
    margin: 0;
    padding: 0;
  }
  
  table {
    border-collapse: collapse;
    border-spacing: 0;
  }
  
  /* main document */
  
  :root {
    color-scheme: light dark;
    supported-color-schemes: light dark;
  
    /* Grays */
    --color-gray-darken-30: #18181c;
    --color-gray-darken-25: #22232a;
    --color-gray-darken-20: #2d2e35;
    --color-gray-darken-10: #41424b;
  
    --color-gray-base: #515258;
  
    --color-gray-lighten-20: #818286;
    --color-gray-lighten-30: #bdbfc6;
    --color-gray-lighten-40: #d1d5dc;
    --color-gray-lighten-45: #d9e0e7;
    --color-gray-lighten-50: #e4eaf3;
    --color-gray-lighten-55: #f1f3f5;
    --color-gray-lighten-60: #fafafb;
    --color-gray-lighten-100: #fffffe;
    /*                              ^
      use slight off white to trick darkmode inversion by email clients */
  
    /* Pinks */
    --color-pink-1: #ff4756;
    --color-pink-2: #ff6c78;
    --color-pink-3: #ff9ba3;
    --color-pink-4: #ffc1c6;
    --color-pink-5: #feeef0;
  
    /* Greens */
    --color-green-1: #27ae60;
    --color-green-2: #52d188;
    --color-green-3: #88f3b5;
    --color-green-4: #c6ffde;
    --color-green-5: #e8f8ef;
  
    /* Blues */
    --color-blue-1: #225ebe;
    --color-blue-2: #5695f4;
    --color-blue-3: #9ec5ff;
    --color-blue-4: #cbe0ff;
    --color-blue-5: #ecf2fa;
  
    /* Oranges */
    --color-orange-0: #b87120;
    --color-orange-1: #ff8800;
    --color-orange-2: #ffc41f;
    --color-orange-3: #ffe08b;
    --color-orange-4: #ffeebe;
    --color-orange-5: #fff7df;
  
    /* Purples */
    --color-purple-1: #55377b;
    --color-purple-2: #734da3;
    --color-purple-3: #9a76c8;
    --color-purple-4: #c6a8ec;
    --color-purple-5: #e2ccfd;
  }
  
  body {
    font-size: 16px;
    font-variant-ligatures: none;
    /* normal */
    -moz-text-size-adjust: none;
    -webkit-text-size-adjust: none;
    text-size-adjust: none;
    font-family: "Inter", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", sans-serif;
    font-size: 1rem;
    background: var(--color-gray-lighten-55);
    color: var(--color-gray-darken-30);
    width: 100%;
  }
  
  a, a:visited {
    color: var(--color-blue-1);
    transition: all 0.2s;
  }
  
  a:hover {
    color: var(--color-blue-2);
  }
  
  h1, h2, h3 {
    margin-bottom: 0.5em;
  }
  
  p {
    margin-bottom: 1em;
  }
  
  ul, ol {
    margin-left: 2rem;
    margin-bottom: 1em;
  }
  
  code {
    font-family: "Fira Code", "SF Mono", "Monaco", "Inconsolata", "Fira Mono", "Droid Sans Mono", "Source Code Pro", monospace !important;
    background: var(--color-gray-lighten-60);
    border-radius: 0.25rem;
    display: inline-block;
    padding: 0 0.25rem;
  }
  
  pre code {
    display: block;
    width: 100%;
    padding: 1rem;
    margin-bottom: 1em;
    border-radius: 0.5rem;
  }
  
  table {
    width: 100%;
  }
  
  .main {
    max-width: 48rem;
    margin: auto;
  }
  
  .main-card {
    padding: 1.5rem;
    border-radius: 0 0 0.5rem 0.5rem;
    background: var(--color-gray-lighten-100);
  }
  
  .footer {
    font-size: 0.875rem;
    padding: 1rem 1.5rem;
  }
  
  .footer-content {
    width: 100%;
  }
  
  .subscription {
    text-align: center;
  }
  
  @media (prefers-color-scheme: dark) {
    body {
      color: var(--color-gray-lighten-100) !important;
      background: var(--color-gray-darken-30) !important;
    }
  
    a, a:visited {
      color: var(--color-blue-3) !important;
    }
  
    a:hover {
      color: var(--color-blue-2) !important;
    }
  
    code {
      background: var(--color-gray-darken-30) !important;
    }
  
    .main-card {
      background: var(--color-gray-darken-20) !important;
    }
  }
  
  /* for android and outlook.com, ogsc for color, ogsb for background */
  [data-ogsc] body {
    color: var(--color-gray-lighten-100) !important;
  }
  
  [data-ogsb] body {
    background: var(--color-gray-darken-30) !important;
  }
  
  [data-ogsc] a, [data-ogsc] a:visited {
    color: var(--color-blue-3) !important;
  }
  
  [data-ogsc] a:hover {
    color: var(--color-blue-2) !important;
  }
  
  [data-ogsb] code {
    background: var(--color-gray-darken-30) !important;
  }
  
  [data-ogsb] .main-card {
    background: var(--color-gray-darken-20) !important;
  }
  
  @media screen and (max-width: 768px) {
    .main {
      margin: 0 auto !important;
    }
  
    .main-card {
      padding: 1rem !important;
      border-radius: 0 !important;
    }
  }
  """

emails.NewPostEmailNotification.subject : NewPostEmailNotification -> Text
emails.NewPostEmailNotification.subject notification =
  use Text ++
  md = Post.metadata (NewPostEmailNotification.post notification)
  blogTitle (NewPostEmailNotification.blog notification)
    ++ " | "
    ++ " New post: "
    ++ Metadata.title md

emails.NewPostEmailNotification.toHtml :
  EmailNotificationsConfig -> NewPostEmailNotification -> Html
emails.NewPostEmailNotification.toHtml config notification =
  use Attribute Attribute
  use Text ++
  use hojberg_html_2_6_0 link text
  b = NewPostEmailNotification.blog notification
  post_ = NewPostEmailNotification.post notification
  md = Post.metadata post_
  postHref =
    unison_base_3_21_0.IO.net.URI.toText
      (EmailNotificationsConfig.baseURI config)
      ++ ("/posts/"
        ++ Slug.toText (Post.slug post_))
  notificationContent =
    [ h2 [] [text ("New post: " ++ Metadata.title md)]
    , p [] [text (Metadata.summary md)]
    , a [class "button", href postHref] [text "Read"]
    ]
  hojberg_html_2_6_0.html
    []
    [ hojberg_html_2_6_0.head
        []
        [ hojberg_html_2_6_0.title
            [] [text (NewPostEmailNotification.subject notification)]
        , meta
            [ Attribute "name" "format-detection"
            , Attribute "content" "telephone=no"
            ]
        , meta
            [ Attribute "name" "format-detection"
            , Attribute "content" "date=no"
            ]
        , meta
            [ Attribute "name" "format-detection"
            , Attribute "content" "address=no"
            ]
        , meta
            [ Attribute "name" "format-detection"
            , Attribute "content" "email=no"
            ]
        , meta
            [Attribute "name" "color-scheme", Attribute "content" "light dark"]
        , meta
            [ Attribute "name" "supported-color-schemes"
            , Attribute "content" "light dark only"
            ]
        , link
            [Attribute "rel" "preconnect", href "https://fonts.googleapis.com"]
        , link
            [ Attribute "rel" "preconnect"
            , href "https://fonts.gstatic.com"
            , Attribute "crossorigin" "crossorigin"
            ]
        , link
            [ Attribute "rel" "stylesheet"
            , href
                "https://fonts.googleapis.com/css2?family=Fira+Code&family=Inter:wght@400;700&display=swap"
            ]
        , hojberg_html_2_6_0.style [Attribute "type" "text/css"] [text styles]
        ]
    , hojberg_html_2_6_0.body
        [Attribute.id "body"]
        [ hojberg_html_2_6_0.table
            [class "main"]
            [ tbody
                []
                [ tr [] [td [class "blog-title"] [h1 [] [text (blogTitle b)]]]
                , tr
                    []
                    [ td
                        [class "main-card"]
                        [box [] [class "main-content"] notificationContent]
                    ]
                ]
            ]
        ]
    ]

emails.NewPostEmailNotification.toHtml.doc : Doc
emails.NewPostEmailNotification.toHtml.doc =
  {{
  Convert a {type NewPostEmailNotification} to {type Html}, adding in title,
  fonts, and link to the new {type Post}}.
  
  Note that it doesn't include an unsubscribe link. It is expected that
  SendGrid (the Email service provider) will include that when the email is
  sent.
  }}

emails.NewPostEmailNotification.toHtmlMailContent :
  EmailNotificationsConfig -> NewPostEmailNotification -> MailContent
emails.NewPostEmailNotification.toHtmlMailContent config notification =
  use Text ++
  htmlText
    ("<!DOCTYPE html>\n"
      ++ hojberg_html_2_6_0.toText
        (NewPostEmailNotification.toHtml config notification))

emails.Subscriber.decode : '{Decoder} Subscriber
emails.Subscriber.decode =
  do
    Subscriber
      (object.at! "email" Decoder.text) (object.at! "name" Decoder.text)

emails.Subscriber.email : Subscriber -> Text
emails.Subscriber.email = cases Subscriber email _ -> email

emails.Subscriber.email.modify :
  (Text ->{g} Text) -> Subscriber ->{g} Subscriber
emails.Subscriber.email.modify f = cases
  Subscriber email name -> Subscriber (f email) name

emails.Subscriber.email.set : Text -> Subscriber -> Subscriber
emails.Subscriber.email.set email1 = cases
  Subscriber _ name -> Subscriber email1 name

emails.Subscriber.name : Subscriber -> Text
emails.Subscriber.name = cases Subscriber _ name -> name

emails.Subscriber.name.modify :
  (Text ->{g} Text) -> Subscriber ->{g} Subscriber
emails.Subscriber.name.modify f = cases
  Subscriber email name -> Subscriber email (f name)

emails.Subscriber.name.set : Text -> Subscriber -> Subscriber
emails.Subscriber.name.set name1 = cases
  Subscriber email _ -> Subscriber email name1

Page.activeNavItem : Page -> ActiveNavItem
Page.activeNavItem = cases Page _ activeNavItem _ _ -> activeNavItem

Page.ActiveNavItem.doc : Doc
Page.ActiveNavItem.doc =
  {{
  A {type ActiveNavItem} is a type that represents the active navigation item
  for a page. It can be one of the following:
  
  * {NoneActive} represents no active navigation item.
  * {LatestPost} represents the latest post as the active navigation item.
  * {AllPosts} represents all posts as the active navigation item.
  }}

Page.activeNavItem.modify :
  (ActiveNavItem ->{g} ActiveNavItem) -> Page ->{g} Page
Page.activeNavItem.modify f = cases
  Page title activeNavItem content css ->
    Page title (f activeNavItem) content css

Page.activeNavItem.set : ActiveNavItem -> Page -> Page
Page.activeNavItem.set activeNavItem1 = cases
  Page title _ content css -> Page title activeNavItem1 content css

Page.allPostsPage : BlogContext ->{Exception, Remote} Page
Page.allPostsPage blogContext =
  blog = BlogContext.blog blogContext
  byTime = postsByTime blog
  bySlug = posts blog
  slugs =
    OrderedTable.toStream byTime
      |> (unison_base_3_21_0.data.Stream.map cases
           (t, slug) -> (t, slug, OrderedTable.read bySlug slug))
      |> toList!
      |> List.map postLink
  Page.empty
    |> withActiveNavItem AllPosts
    |> withContent [hojberg_html_2_6_0.div [class "all-posts"] slugs]
    |> withCSS allPostsCSS

Page.allPostsPage.allPostsCSS : CSS
Page.allPostsPage.allPostsCSS =
  CSS
    [ RuleSet
        [Selector ".all-posts"]
        [ Rule "display" "flex"
        , Rule "flex-direction" "column"
        , Rule "gap" "1.5rem"
        ]
    , RuleSet
        [Selector "a.post-link"]
        [ Rule "color" "var(--color_text)"
        , Rule "display" "flex"
        , Rule "flex-direction" "column"
        , Rule "gap" "0.25"
        ]
    , RuleSet
        [Selector ".post-link .post_title"]
        [ Rule "font-size" "var(--font-size-large)"
        , Rule "font-weight" "900"
        , Rule "line-height" "1.1"
        , Rule "transition" "all 0.2s"
        ]
    , RuleSet
        [Selector ".post-link .metadata"]
        [ Rule "font-size" "var(--font-size-small)"
        , Rule "color" "var(--color_text_subdued)"
        , Rule "display" "flex"
        , Rule "flex-direction" "row"
        , Rule "justify-content" "space-between"
        , Rule "align-items" "center"
        , Rule "margin-bottom" "0.25rem"
        ]
    , RuleSet
        [ Selector ".post-link .primary-metadata"
        , Selector ".post-link .secondary-metadata"
        ]
        [ Rule "display" "flex"
        , Rule "flex-direction" "row"
        , Rule "gap" "0.5rem"
        , Rule "justify-content" "space-between"
        , Rule "align-items" "center"
        ]
    , RuleSet
        [Selector ".post-link .separator"]
        [Rule "color" "var(--color_text_very-subdued)"]
    , RuleSet
        [Selector ".post-link:hover"]
        [Rule "color" "var(--color_text)", Rule "text-decoration" "none"]
    , RuleSet
        [Selector ".post-link:hover .post_title"]
        [Rule "color" "var(--color_interactive)"]
    ]

Page.allPostsPage.postLink : (Instant, Slug, Post) -> Html
Page.allPostsPage.postLink = cases
  (publishedAt, slug, post) ->
    use Post metadata
    use Text ++
    use hojberg_html_2_6_0 div text
    title = Metadata.title (metadata post)
    publishedAt = Metadata.publishedAt (metadata post)
    authors = Metadata.authors (metadata post)
    summary = Metadata.summary (metadata post)
    s = Slug.toText slug
    a
      [href ("posts/" ++ s), class "post-link"]
      [ div [class "post_title"] [text title]
      , metadataToHtml (metadata post)
      , div [class "post_summary"] [text summary]
      ]

Page.atomFeedPage : URI -> Blog ->{Remote} Text
Page.atomFeedPage baseURI blog =
  use List :+
  use Map empty fromList
  use OrderedTable read
  use URI /
  use unison_base_3_21_0.IO.net URI.toText
  use unison_base_3_21_0.data.Stream map
  posts_ = posts blog
  slugStream : '{Remote, Stream (Instant, Slug)} ()
  slugStream = OrderedTable.toStream (postsByTime blog)
  postStream : '{Remote, Stream Post} ()
  postStream = map (cases (_, slug) -> read posts_ slug) slugStream
  lastPostTime = match Stream.head slugStream with
    Some (_, slug) -> read posts_ slug |> Post.metadata |> Metadata.publishedAt
    None           -> atUTC now!
  feedUpdated = OffsetDateTime.toText lastPostTime
  XMLElement
    "feed"
    (fromList [("xmlns", "http://www.w3.org/2005/Atom")])
    ([ XMLElement "title" empty [XMLCData (blogTitle blog)]
    , XMLElement "subtitle" empty [XMLCData (description blog)]
    , XMLElement "id" empty [XMLText ("urn:uuid:" Text.++ Blog.guid blog)]
    , XMLElement "updated" empty [XMLText feedUpdated]
    ]
      :+ XMLElement
           "link"
           (fromList
             [("rel", "self"), ("href", URI.toText (baseURI / "atom.xml"))])
           []
      :+ XMLElement
           "link"
           (fromList [("rel", "alternate"), ("href", URI.toText baseURI)])
           []
      List.++ toList!
        (unison_base_3_21_0.data.Stream.take
          20 (map (toAtom baseURI) postStream)))
    |> XMLNode.toXML
    |> (Text.++) "<?xml version='1.0' encoding='UTF-8'?>\n"

Page.atomFeedPage.doc : Doc
Page.atomFeedPage.doc =
  {{ Renders an Atom feed for the given {type Blog} as a {type Text} string. }}

Page.authorToHtml : BlogAuthor -> Html
Page.authorToHtml a =
  hojberg_html_2_6_0.div
    [class "author"] [hojberg_html_2_6_0.text (BlogAuthor.name a)]

Page.badrequestPage : Text -> Html
Page.badrequestPage err =
  use Text ++
  h1 [] [hojberg_html_2_6_0.text ("Bad Request: " ++ err)]

Page.badrequestPage.doc : Doc
Page.badrequestPage.doc =
  {{
  A helper function for rendering a "Bad Request" page with the given error
  message.
  }}

Page.comma : Html
Page.comma =
  hojberg_html_2_6_0.span [class "comma"] [hojberg_html_2_6_0.text ", "]

Page.content : Page -> [Html]
Page.content = cases Page _ _ content _ -> content

Page.content.modify : ([Html] ->{g} [Html]) -> Page ->{g} Page
Page.content.modify f = cases
  Page title activeNavItem content css ->
    Page title activeNavItem (f content) css

Page.content.set : [Html] -> Page -> Page
Page.content.set content1 = cases
  Page title activeNavItem _ css -> Page title activeNavItem content1 css

Page.css : Page -> [CSS]
Page.css = cases Page _ _ _ css -> css

Page.css.docStyles : Text
Page.css.docStyles =
  """
  .definition-doc {
    --doc_font-size: 1.125rem;
    --doc_font-size_small: var(--font-size-medium);
  
    position: relative;
    display: flex;
    line-height: 1.5;
    flex-direction: column;
    font-size: var(--doc_font-size);
    color: var(--color_doc_text);
  }
  
  /* TODO: re-enable */
  .definition-doc .fold-toggle {
    display: none;
  }
  
  .definition-doc .doc_group .doc_join {
    white-space: pre-line;
  }
  
  .definition-doc .source.code,
  .definition-doc .sources .source,
  .definition-doc .folded-sources .source,
  .definition-doc .source.example,
  .definition-doc .eval .source,
  .definition-doc .source.signatures .signature {
    padding: 0.5rem 0.75rem;
    background: var(--color_doc_source);
    border-radius: var(--border-radius-base);
    scrollbar-width: auto;
    scrollbar-color: var(--u-color_scrollbar) var(--u-color_scrollbar-track);
    overflow: auto;
    max-width: var(--c-width_doc_inner-content);
  }
  
  .definition-doc .source.code,
  .definition-doc .sources .source,
  .definition-doc .folded-sources .source,
  .definition-doc .source.example {
    margin-bottom: 1rem;
  }
  
  .definition-doc .source.signatures .signature {
    display: flex;
    flex-direction: column;
    gap: 1rem;
  }
  
  /* We don't want margin on .eval .source since its 2 very close source blocks */
  .definition-doc .eval .code {
    margin-bottom: 0;
  }
  
  .definition-doc .folded-sources .source {
    padding: 0.5rem;
  }
  
  .definition-doc .source.code::-webkit-scrollbar,
  .definition-doc .sources .source::-webkit-scrollbar,
  .definition-doc .folded-sources .source::-webkit-scrollbar,
  .definition-doc .source.example::-webkit-scrollbar,
  .definition-doc .eval .source::-webkit-scrollbar,
  .definition-doc .source.signatures .signature::-webkit-scrollbar,
  .definition-doc .doc_table::-webkit-scrollbar {
    height: 0.375rem;
  }
  
  .definition-doc .source.code::-webkit-scrollbar-track,
  .definition-doc .sources .source::-webkit-scrollbar-track,
  .definition-doc .folded-sources .source::-webkit-scrollbar-track,
  .definition-doc .source.example::-webkit-scrollbar-track,
  .definition-doc .eval .source::-webkit-scrollbar-track,
  .definition-doc .source.signatures .signature::-webkit-scrollbar-track,
  .definition-doc .doc_table::-webkit-scrollbar-track {
    background: var(--u-color_scrollbar-track);
  }
  
  .definition-doc .source.code::-webkit-scrollbar-thumb,
  .definition-doc .sources .source::-webkit-scrollbar-thumb,
  .definition-doc .folded-sources .source::-webkit-scrollbar-thumb,
  .definition-doc .source.example::-webkit-scrollbar-thumb,
  .definition-doc .eval .source::-webkit-scrollbar-thumb,
  .definition-doc .source.signatures .signature::-webkit-scrollbar-thumb,
  .definition-doc .doc_table::-webkit-scrollbar-thumb {
    background-color: var(--u-color_scrollbar);
    border-radius: var(--border-radius-base);
  }
  
  .definition-doc .source code:not(.hljs) {
    display: flex;
    flex-direction: column;
    flex: 1;
  }
  
  .definition-doc
    .source:is(.inline-code, .example-inline, .eval-inline, .signature-inline) {
    display: inline-block;
    padding: 0 0.25rem;
    background: var(--color_doc_source);
    border-radius: var(--border-radius-base);
    white-space: nowrap;
  }
  
  .definition-doc
    .doc_group
    .doc_join
    .source:is(.inline-code, .example-inline, .eval-inline, .signature-inline) {
    margin-right: 0;
  }
  
  .definition-doc
    .source:is(.inline-code, .example-inline, .eval-inline, .signature-inline)
    :is(.inline-code, code) {
    display: inline-flex;
    white-space: nowrap;
  }
  
  .definition-doc
    .doc_group
    .doc_join
    .source:is(.inline-code, .example-inline, .eval-inline, .signature-inline)
    :is(.inline-code, code) {
    margin-right: 0;
  }
  
  /* code and inline-code render sub definition-docs, not syntax */
  :is(.definition-doc .source.code, .definition-doc .source.inline-code)
    .word:last-child {
    margin-right: 0;
  }
  
  .definition-doc .eval .result .icon,
  .definition-doc .eval-inline .result .icon {
    color: var(--color_doc_text_subdued);
  }
  
  .definition-doc .eval .result .icon svg {
    stroke-width: 1px;
    stroke: var(--color_doc_text_subdued);
  }
  
  .definition-doc .eval {
    display: flex;
    flex-direction: column;
    /* really we want 0.25rem, but because .result is a "blank" element inbetween
     * the 2 sources we collapse to 0.125rem */
    gap: 0.125rem;
    margin-bottom: 1rem;
  }
  
  .definition-doc .eval .result {
    position: relative;
  }
  
  .definition-doc .eval .result-indicator {
    position: absolute;
    left: -0.75rem;
    top: -0.75rem;
    height: 1.5rem;
    width: 1.5rem;
    display: flex;
    align-items: center;
    justify-content: center;
    background: var(--color_doc_eval-result);
    box-shadow: 0 0 0 0.25rem var(--color_doc_background);
    line-height: 1;
    border-radius: 0.75rem;
  }
  
  .definition-doc .eval .result .icon {
    font-size: var(--doc_font-size);
    color: var(--color_doc_eval-icon);
  }
  
  .definition-doc strong {
    font-weight: bold;
  }
  
  .definition-doc .italic {
    font-style: italic;
  }
  
  .definition-doc .strikethrough {
    text-decoration: line-through;
  }
  
  .definition-doc blockquote {
    position: relative;
    padding: 0.5rem 1.25rem;
    margin-left: 0rem;
    margin-bottom: 1rem;
  }
  
  .definition-doc blockquote:before {
    position: absolute;
    content: " ";
    top: 0;
    bottom: 0;
    left: 0;
    background: var(--color_doc_border);
    width: 0.25rem;
    border-radius: var(--border-radius-base);
  }
  
  .definition-doc hr {
    background: var(--color_doc_divider);
    margin: 1.5rem 0;
  }
  
  .definition-doc .tooltip-trigger {
    text-decoration: underline dotted var(--color_doc_text_subdued);
    text-underline-offset: 2px;
    /* Other tooltip styling is handled by elements/tooltip */
  }
  
  .definition-doc .tooltip {
    min-width: 24rem;
  }
  
  .definition-doc .tooltip-bubble {
    margin-top: 0.25rem;
  }
  
  .definition-doc .tooltip-bubble > section:only-child {
    margin: 0;
  }
  
  .definition-doc aside {
    position: absolute;
    right: -17rem;
    width: 15rem;
    font-size: var(--doc_font-size_small);
    background: var(--color_doc_aside);
    padding: 0.5rem 0.75rem;
    margin-left: 1rem;
    border-radius: var(--border-radius-base);
    white-space: normal;
  }
  
  .definition-doc aside > section:first-child {
    margin: 0;
  }
  
  .definition-doc aside .source.code,
  .definition-doc aside .sources .source,
  .definition-doc aside .folded-sources .source,
  .definition-doc aside .source.example,
  .definition-doc aside .eval .source,
  .definition-doc aside .source.signatures .signature {
    background: var(--color_doc_aside_source);
    padding: 0.375rem;
    max-width: 14rem;
    /* accounting for the aside padding */
    overflow: auto;
  }
  
  .definition-doc
    aside
    .source:is(.inline-code, .example-inline, .eval-inline, .signature-inline) {
    background: var(--color_doc_aside_source);
    white-space: wrap;
  }
  
  .definition-doc .doc_callout {
    background: var(--color_doc_callout);
    padding: 0.75rem 1rem;
    margin-bottom: 1rem;
    border-radius: var(--border-radius-base);
    display: flex;
    flex-direction: row;
  }
  
  .definition-doc .doc_callout .doc_callout-content section .folded:last-child {
    margin-bottom: 0.25rem;
  }
  
  .definition-doc .folded-content .doc_callout:nth-child(2) {
    margin-top: 1rem;
  }
  
  .definition-doc .doc_callout.doc_callout-with-icon .doc_callout-content {
    padding-top: 1px;
    width: 100%;
  }
  
  .definition-doc .doc_callout .doc_callout-icon {
    margin-right: 0.5rem;
    font-size: var(--doc_font-size);
  }
  
  .definition-doc .doc_callout .source.code,
  .definition-doc .doc_callout .sources .source,
  .definition-doc .doc_callout .folded-sources .source,
  .definition-doc .doc_callout .source.example,
  .definition-doc .doc_callout .eval .source,
  .definition-doc .doc_callout .source.signatures .signature,
  .definition-doc
    .doc_callout
    .source:is(.inline-code, .example-inline, .eval-inline, .signature-inline) {
    background: var(--color_doc_callout_source);
  }
  
  .definition-doc .doc_table {
    max-width: calc(var(--c-width_doc_outer, 100vw) - 4rem);
    overflow-x: auto;
  }
  
  .definition-doc .doc_table table {
    margin-bottom: 1rem;
    table-layout: fixed;
    border-collapse: collapse;
  }
  
  .definition-doc .doc_table table td {
    border: 1px solid var(--color_doc_border);
    padding: 0.5rem;
    vertical-align: top;
  }
  
  .definition-doc .embed-svg {
    max-width: var(--c-width_doc_inner-content);
    border: 0;
  }
  
  .definition-doc .folded {
    margin-bottom: 1rem;
    display: flex;
    flex-direction: row;
  }
  
  .definition-doc .folded .folded-content {
    flex: 1;
  }
  
  .definition-doc .folded .builtin-summary {
    display: flex;
    flex: 1;
    flex-direction: row;
    align-items: center;
  }
  
  .definition-doc .source.folded .badge {
    margin-left: auto;
    justify-self: flex-end;
    border: 0;
    font-size: var(--doc_font-size_small);
    height: 1.25rem;
    padding: 0 0.25rem;
  }
  
  .definition-doc p {
    margin-bottom: 1em;
  }
  
  .definition-doc p:last-child {
    margin: 0;
  }
  
  .definition-doc ol,
  .definition-doc ul {
    margin-left: 1.5rem;
    margin-bottom: 1em;
  }
  
  .definition-doc ol:last-child,
  .definition-doc ul:last-child {
    margin-bottom: 0;
  }
  
  .definition-doc section {
    margin-bottom: 1rem;
    margin-top: 1.5rem;
  }
  
  .definition-doc section:first-child {
    margin-top: 0;
  }
  
  .definition-doc section:first-child > p:empty {
    display: none;
  }
  
  .definition-doc section:first-child > p:empty + section {
    margin-top: 0;
  }
  
  .definition-doc section:last-child {
    margin-bottom: 0;
  }
  
  .definition-doc section:last-child .source:last-child {
    margin-bottom: 0;
  }
  
  :is(
      .definition-doc h1,
      .definition-doc h2,
      .definition-doc h3,
      .definition-doc h4,
      .definition-doc h5,
      .definition-doc h6
    )
    p {
    margin: 0;
  }
  
  .definition-doc h1 {
    font-size: var(--font-size-large);
    margin-bottom: 0.75rem;
  }
  
  .definition-doc h1:first-child {
    line-height: 0.9;
    font-size: var(--font-size-mega-huge);
    text-align: center;
    margin-bottom: 4rem;
    color: var(--color_doc_title);
    text-wrap: pretty;
  }
  
  .definition-doc h1 .span:last-child > .word:last-child {
    margin-right: 0;
  }
  
  .definition-doc h2 {
    font-size: 1.25rem;
    margin-bottom: 0.5rem;
  }
  
  .definition-doc h3 {
    font-size: 1rem;
    margin-bottom: 0.5rem;
  }
  
  .definition-doc h4 {
    font-size: 0.875rem;
    margin-bottom: 0.5rem;
  }
  
  .definition-doc h5 {
    font-size: 0.875rem;
    margin-bottom: 0.5rem;
  }
  
  .definition-doc h6 {
    font-size: 0.875rem;
    margin-bottom: 0.5rem;
  }
  
  .definition-doc img {
    margin-bottom: 1rem;
    max-width: 100%;
  }
  
  .definition-doc .image-with-caption {
    width: 100%;
  }
  
  .definition-doc .image-with-caption .caption {
    text-align: center;
    font-style: italic;
  }
  
  .definition-doc .embed {
  }
  
  .definition-doc .embed-inline {
  }
  
  .definition-doc .doc_column {
    margin: 0;
    list-style-type: none;
    display: flex;
    flex-direction: column;
  }
  
  .definition-doc .doc_group {
  }
  
  .definition-doc video {
    background: var(--color_doc_source);
    border-radius: var(--border-radius-base);
    max-width: 100%;
    margin: 1rem 0;
  }
  
  .definition-doc .mermaid-diagram.mermaid-diagram_error {
    background: var(--color_doc_aside);
    border-radius: var(--border-radius-base);
    padding: 0.5rem 0.75rem;
  } 
  
  @media only screen and (max-width: 1012px) {
    .definition-doc .source.code,
    .definition-doc .sources .source,
    .definition-doc .folded-sources .source,
    .definition-doc .source.example,
    .definition-doc .eval .source,
    .definition-doc .source.signatures .signature,
    .definition-doc .mermaid-diagram,
    .definition-doc .embed-svg {
      width: 100%;
      overflow: auto;
    }
  
    .definition-doc aside .source.code,
    .definition-doc aside .sources .source,
    .definition-doc aside .folded-sources .source,
    .definition-doc aside .source.example,
    .definition-doc aside .eval .source,
    .definition-doc aside .source.signatures .signature {
      max-width: none;
      width: 100%;
    }
  
    .definition-doc .doc_callout .source.code,
    .definition-doc .doc_callout .sources .source,
    .definition-doc .doc_callout .folded-sources .source,
    .definition-doc .doc_callout .source.example,
    .definition-doc .doc_callout .eval .source,
    .definition-doc .doc_callout .source.signatures .signature {
      width: 100%;
    }
  
    .definition-doc .doc_callout .folded .source.code,
    .definition-doc .doc_callout .folded .sources .source,
    .definition-doc .doc_callout .folded .folded-sources .source,
    .definition-doc .doc_callout .folded .source.example,
    .definition-doc .doc_callout .folded .eval .source,
    .definition-doc .doc_callout .folded .source.signatures .signature {
      width: 100%;
    }
  
    .definition-doc aside {
      position: relative;
      right: auto;
      width: auto;
      margin: 1.5rem 1.5rem 1.5rem 1.5rem;
    }
  
    .definition-doc .doc_table {
      max-width: 100%;
      scrollbar-width: auto;
      scrollbar-color: var(--u-color_scrollbar) var(--u-color_scrollbar-track);
    }
  }
  
  @media only screen and (max-width: 768px) {
    .definition-doc .{
      --doc_font-size: var(--font-size-base);
    }
  
    .definition-doc .doc_table {
      max-width: calc(100% - 4rem);
    }
  
    .definition-doc h1:first-child {
      font-size: 3.125rem;
      margin-bottom: 2rem;
    }
  }
  """

Page.css.docStyles.doc : Doc
Page.css.docStyles.doc =
  {{ The default styles for {type Doc} pages in a blog. }}

Page.css.highlightJsStyles : Text
Page.css.highlightJsStyles =
  """
  .hljs-meta.prompt_ {
    color: var(--color_syntax_very-subdued);
  }
  
  .hljs-string {
    color: var(--color_syntax_text);
  }
  
  .hljs-literal,
  .hljs-symbol {
    color: var(--color_syntax_constructor);
  }
  
  .hljs-variable,
  .hljs-params {
    color: var(--color_syntax_base);
  }
  
  .hljs-number,
  .hljs-title.class_,
  .hljs-variable.constant_,
  .hljs-type {
    color: var(--color_syntax_type);
  }
  
  .hljs-title,
  .hljs-title.function_ {
    color: var(--color_syntax_term);
    font-weight: normal;
  }
  
  .hljs-operator {
    color: var(--color_syntax_very-subdued);
  }
  
  .hljs-keyword,
  .hljs-variable.language_,
  .hljs-built_in {
    color: var(--color_syntax_keyword);
  }
  
  .hljs-punctuation {
    color: var(--color_syntax_very-subdued);
  }
  
  .hljs-comment,
  .hljs-import,
  .hljs-import .hljs-keyword,
  .hljs-import .hljs-title,
  .hljs-import .hljs-operator {
    color: var(--color_syntax_very-subdued);
  }
  
  """

Page.css.mainStyles : BlogTheme -> CSS
Page.css.mainStyles blogTheme =
  use CSS ++
  pageStyles =
    CSS
      [ RuleSet
          [Selector "*"]
          [ Rule "margin" "0"
          , Rule "padding" "0"
          , Rule "box-sizing" "border-box"
          ]
      , RuleSet
          [Selector "html"]
          [ Rule "font-variant-ligatures" "none"
          , Rule "-moz-text-size-adjust" "none"
          , Rule "-webkit-text-size-adjust" "none"
          , Rule "text-size-adjust" "none"
          ]
      , RuleSet
          [Selector "body"]
          [ Rule "background" "var(--color_background)"
          , Rule "color" "var(--color_text)"
          , Rule "font-size" "16px"
          , Rule "font-family" "var(--font_main)"
          , Rule "line-height" "1.4"
          ]
      , RuleSet
          [Selector "a", Selector "a:visited"]
          [ Rule "color" "var(--color_interactive)"
          , Rule "transition" "all 0.5s"
          , Rule "text-decoration" "none"
          ]
      , RuleSet
          [Selector "a:hover"]
          [ Rule "color" "var(--color_interactive_hover)"
          , Rule "text-decoration" "underline"
          ]
      , RuleSet
          [Selector "h1"]
          [ Rule "font-size" "var(--font-size-huge)"
          , Rule "font-weight" "900"
          , Rule "margin-bottom" "0.25em"
          ]
      , RuleSet
          [Selector "h2"]
          [ Rule "font-size" "var(--font-size-large)"
          , Rule "margin-bottom" "0.25em"
          ]
      , RuleSet
          [Selector ".page-header"]
          [ Rule "margin-bottom" "2rem"
          , Rule "width" "100%"
          , Rule "display" "flex"
          , Rule "flex-direction" "row"
          , Rule "justify-content" "space-between"
          , Rule "align-items" "center"
          , Rule "border-bottom" "1px solid var(--color_border_subdued)"
          , Rule "padding" "1rem 2rem"
          ]
      , RuleSet [Selector ".page-header a"] [Rule "color" "var(--color_text)"]
      , RuleSet
          [Selector ".page-header h1"]
          [ Rule "font-size" "var(--font-size-base)"
          , Rule "font-weight" "bold"
          , Rule "margin" "0"
          ]
      , RuleSet
          [Selector ".main-nav"]
          [ Rule "display" "flex"
          , Rule "flex-direction" "row"
          , Rule "justify-content" "space-between"
          , Rule "align-items" "center"
          , Rule "gap" "0.75rem"
          , Rule "font-size" "var(--font-size-medium)"
          ]
      , RuleSet
          [Selector ".page-header a:hover"]
          [ Rule "text-decoration" "none"
          , Rule "color" "var(--color_interactive_hover)"
          ]
      , RuleSet
          [Selector ".main-nav a"] [Rule "color" "var(--color_text_subdued)"]
      , RuleSet
          [Selector ".main-nav a.active"]
          [Rule "color" "var(--color_text)", Rule "font-weight" "bold"]
      , RuleSet
          [Selector ".subscribe"]
          [Rule "color" "var(--color_text_subdued)", Rule "cursor" "pointer"]
      , RuleSet
          [Selector ".subscribe:hover"]
          [Rule "color" "var(--color_interactive_hover)"]
      , RuleSet
          [Selector ".subscribe-flyout"]
          [ Rule "display" "none"
          , Rule "position" "absolute"
          , Rule "top" "3rem"
          , Rule "right" "1.5rem"
          , Rule "min-width" "21rem"
          , Rule "font-size" "var(--font-size-medium)"
          , Rule "background" "var(--color_element_emphasized)"
          , Rule "padding" "1.5rem"
          , Rule "z-index" "100"
          , Rule "border-radius" "var(--border-radius-base)"
          , Rule "box-shadow" "0 0.125rem 0.125rem rgba(0, 0, 0, 0.25)"
          , Rule "flex-direction" "column"
          , Rule "gap" "0.75rem"
          ]
      , RuleSet [Selector ".subscribe-flyout.visible"] [Rule "display" "flex"]
      , RuleSet
          [Selector ".subscribe-flyout.visible::after"]
          [ Rule "bottom" "100%"
          , Rule "right" "10%"
          , Rule "border" "solid transparent"
          , Rule "content" "''"
          , Rule "height" "0"
          , Rule "width" "0"
          , Rule "position" "absolute"
          , Rule "pointer-events" "none"
          , Rule "border-color" "rgba(136, 183, 213, 0)"
          , Rule "border-bottom-color" "var(--color_element_emphasized)"
          , Rule "border-width" "0.5rem"
          , Rule "margin-left" "-0.5rem"
          ]
      , RuleSet
          [Selector ".subscribe-flyout input"]
          [ Rule "height" "2rem"
          , Rule "width" "100%"
          , Rule "padding" "0.25rem 0.5rem"
          , Rule "font-size" "var(--font-size-medium)"
          , Rule "border-radius" "var(--border-radius-base)"
          , Rule "border" "1px solid var(--color_border)"
          ]
      , RuleSet
          [Selector ".subscribe-flyout .form"]
          [ Rule "display" "flex"
          , Rule "flex-direction" "column"
          , Rule "align-items" "center"
          , Rule "gap" "0.5rem"
          ]
      , RuleSet
          [Selector ".subscribe-flyout p"]
          [ Rule "font-weight" "bold"
          , Rule "font-size" "var(--font-size-medium)"
          , Rule "color" "var(--color_text)"
          , Rule "margin" "0"
          ]
      , RuleSet
          [Selector ".subscribe-flyout .no-spam"]
          [ Rule "font-weight" "normal"
          , Rule "font-size" "var(--font-size-small)"
          , Rule "color" "var(--color_text_subdued)"
          , Rule "margin-bottom" "0.5rem"
          ]
      , RuleSet
          [Selector ".main-content"]
          [ Rule "margin" "2rem auto"
          , Rule "width" "min(44rem, calc(100% - 4rem))"
          ]
      , RuleSet
          [Selector ".main-footer"]
          [ Rule "margin-bottom" "2rem"
          , Rule "width" "100%"
          , Rule "text-align" "center"
          , Rule "font-size" "var(--font-size-small)"
          , Rule "color" "var(--color_text_subdued)"
          , Rule "border-top" "1px solid var(--color_border_subdued)"
          , Rule "padding-top" "2rem"
          ]
      , RuleSet
          [Selector ".icon"]
          [ Rule "display" "inline-block"
          , Rule "font-size" "var(--font-size-medium)"
          , Rule "width" "1em"
          , Rule "height" "1em"
          , Rule "color" "var(--color_icon)"
          , Rule "transition" "all 0.2s"
          ]
      , RuleSet
          [Selector ".button"]
          [ Rule "font-weight" "bold"
          , Rule "font-size" "var(--font-size-base)"
          , Rule "color" "var(--color_button_text_emphasized)"
          , Rule "background" "var(--color_button_emphasized)"
          , Rule "padding" "0.75rem 1rem"
          , Rule "border" "0"
          , Rule "border-radius" "var(--border-radius-base)"
          , Rule "display" "inline-flex"
          , Rule "align-items" "center"
          , Rule "justify-content" "center"
          ]
      , RuleSet [Selector ".button[disabled]"] [Rule "opacity" "0.25"]
      , RuleSet
          [Selector ".fold-toggle"]
          [ Rule "--color-fold-toggle-icon" "var(--color_icon)"
          , Rule
              "--color-fold-toggle-hover-icon"
              "var(--color_interactive_hovered)"
          , Rule "display" "inline-flex"
          , Rule "align-items" "center"
          , Rule "justify-content" "center"
          , Rule "flex-direction" "row"
          , Rule "width" "1.25rem"
          , Rule "height" "1.25rem"
          , Rule "margin-right" "0.25rem"
          , Rule "line-height" "1"
          , Rule "border-radius" "var(--border-radius-base)"
          , Rule "transition" "all 0.2s"
          , Rule "color" "var(--color-fold-toggle-icon)"
          , Rule "font-size" "var(--font-size-small)"
          , Rule "cursor" "pointer"
          ]
      , RuleSet
          [Selector ".fold-toggle.disabled"]
          [Rule "cursor" "default", Rule "opacity" "0.5"]
      , RuleSet
          [Selector ".fold-toggle.folded-open"]
          [Rule "transform" "rotate(90deg)"]
      , RuleSet
          [Selector ".fold-toggle:not(.disabled):hover"]
          [ Rule "color" "var(--color-fold-toggle-hover-icon)"
          , Rule "transform" "scale(1.25)"
          ]
      ]
  BlogTheme.toCSS blogTheme ++ pageStyles

Page.css.mainStyles.doc : Doc
Page.css.mainStyles.doc = {{ The main styles for a blog page. }}

Page.css.modify : ([CSS] ->{g} [CSS]) -> Page ->{g} Page
Page.css.modify f = cases
  Page title activeNavItem content css ->
    Page title activeNavItem content (f css)

Page.css.set : [CSS] -> Page -> Page
Page.css.set css1 = cases
  Page title activeNavItem content _ -> Page title activeNavItem content css1

Page.css.syntaxStyles : Text
Page.css.syntaxStyles =
  """
  pre {
    margin: 0;
  }
  
  .inline-code {
    display: inline-block;
  }
  
  code {
    display: inline-block;
    font-family: var(--font_monospace);
    line-height: 1.6;
  }
  
  .inline-code code {
    line-height: 1.4;
  }
  
  code a {
    display: inline-block;
    padding: 0 0.25rem;
    margin: 0 -0.25rem;
    border-radius: var(--border-radius-base);
    line-height: 1.4;
  }
  
  code a:hover {
    background: var(--color_syntax_link_container_hovered);
    text-decoration: none;
  }
  
  code a:active {
    transform: translate(0, 0.1rem);
  }
  
  code a:active .tooltip-trigger.tooltip_show .tooltip {
    display: none;
  }
  
  .rich .fqn .sep {
    color: var(--color_syntax_very-subdued);
  }
  .rich .text-literal,
  .rich .bytes-literal,
  .rich .char-literal {
    color: var(--color_syntax_text);
  }
  
  .rich .boolean-literal,
  .rich .data-constructor-reference {
    color: var(--color_syntax_constructor);
  }
  
  .rich .data-constructor-reference .segment {
    color: var(--color_syntax_constructor-namespace);
  }
  
  .rich .data-constructor-reference .segment:last-child {
    color: var(--color_syntax_constructor);
  }
  
  .rich .var,
  .rich .data-type-params {
    color: var(--color_syntax_base);
  }
  
  .rich .numeric-literal,
  .rich .type-reference,
  .rich .data-type-modifier {
    color: var(--color_syntax_type);
  }
  
  .rich .type-reference .fqn .segment {
    color: var(--color_syntax_type-namespace);
  }
  
  .rich .type-reference .fqn .segment:last-child {
    color: var(--color_syntax_type);
  }
  
  .rich .term-reference,
  .rich .ability-constructor-reference,
  .rich .hash-qualifier {
    color: var(--color_syntax_term);
  }
  
  .rich .term-reference .fqn .segment,
  .rich .ability-constructor-reference .fqn .segment,
  .rich .hash-qualifier .fqn .segment {
    color: var(--color_syntax_term-namespace);
  }
  
  .rich .term-reference .fqn .segment:last-child,
  .rich .ability-constructor-reference .fqn .segment:last-child,
  .rich .hash-qualifier .fqn .segment:last-child {
    color: var(--color_syntax_term);
  }
  
  .rich .op.cons,
  .rich .op.snoc,
  .rich .op.concat,
  .rich .type-operator,
  .rich .binding-equals,
  .rich .type-ascription-colon {
    color: var(--color_syntax_operator);
  }
  
  .rich .delay-force-char {
    color: var(--color_syntax_ability);
    font-weight: bold;
  }
  
  .rich .control-keyword,
  .rich .data-type-keyword,
  .rich .link-keyword,
  .rich .doc-keyword {
    color: var(--color_syntax_keyword);
  }
  
  .rich .delimeter-char {
    color: var(--color_syntax_very-subdued);
  }
  
  .rich .comment,
  .rich .ability-braces,
  .rich .unit,
  .rich .use-keyword,
  .rich .use-prefix,
  .rich .use-suffix,
  .rich .blank,
  .rich .parenthesis,
  .rich .arrow,
  .rich .doc-delimeter {
    color: var(--color_syntax_very-subdued);
  }
  
  .monochrome .text-literal,
  .monochrome .bytes-literal,
  .monochrome .char-literal,
  .monochrome .blank,
  .monochrome .var,
  .monochrome .data-type-params {
    color: var(--color_syntax_monochrome_base);
  }
  
  .monochrome .type-reference,
  .monochrome .boolean-literal,
  .monochrome .data-constructor-reference,
  .monochrome .numeric-literal,
  .monochrome .term-reference,
  .monochrome .data-type-modifier,
  .monochrome .hash-qualifier,
  .monochrome .ability-constructor-reference {
    color: var(--color_syntax_monochrome_emphasized);
  }
  
  .monochrome .delay-force-char {
    color: var(--color_syntax_monochrome_emphasized);
    font-weight: bold;
  }
  
  .monochrome .op.cons,
  .monochrome .op.snoc,
  .monochrome .op.concat,
  .monochrome .type-operator,
  .monochrome .type-ascription-colon,
  .monochrome .control-keyword,
  .monochrome .data-type-keyword,
  .monochrome .link-keyword,
  .monochrome .doc-keyword,
  .monochrome .comment,
  .monochrome .ability-braces,
  .monochrome .binding-equals,
  .monochrome .unit,
  .monochrome .use-keyword,
  .monochrome .use-prefix,
  .monochrome .use-suffix,
  .monochrome .delimeter-char,
  .monochrome .parenthesis,
  .monochrome .doc-delimeter {
    color: var(--color_syntax_monochrome_subdued);
  }
  
  .plain .text-literal,
  .plain .bytes-literal,
  .plain .char-literal,
  .plain .boolean-literal,
  .plain .data-constructor-reference,
  .plain .blank,
  .plain .var,
  .plain .data-type-params,
  .plain .numeric-literal,
  .plain .term-reference,
  .plain .data-type-modifier,
  .plain .hash-qualifier,
  .plain .ability-constructor-reference,
  .plain .type-reference,
  .plain .op.cons,
  .plain .op.snoc,
  .plain .op.concat,
  .plain .type-operator,
  .plain .type-ascription-colon,
  .plain .delay-force-char,
  .plain .control-keyword,
  .plain .data-type-keyword,
  .plain .link-keyword,
  .plain .doc-keyword,
  .plain .comment,
  .plain .ability-braces,
  .plain .binding-equals,
  .plain .unit,
  .plain .use-keyword,
  .plain .use-prefix,
  .plain .use-suffix,
  .plain .delimeter-char,
  .plain .parenthesis,
  .plain .doc-delimeter {
    color: var(--color_syntax_plain);
  }
  """

Page.css.syntaxStyles.doc : Doc
Page.css.syntaxStyles.doc = {{ The default styles for syntax highlighting. }}

Page.doc : Doc
Page.doc =
  {{
  A {type Page} represents a page of the blog website. It has the following
  fields:
  
  * {Post.title} is the title of the page.
  * {{ docLink (docEmbedTermLink do activeNavItem) }} is the active navigation
    item for the page, of type {type ActiveNavItem}.
  * {{ docLink (docEmbedTermLink do Page.content) }} is a list of {type Html}
    values that represent the content of the page.
  }}

Page.empty : Page
Page.empty = Page "" NoneActive [] []

Page.empty.doc : Doc
Page.empty.doc = {{ An empty {type Page}. }}

Page.NavItem.doc : Doc
Page.NavItem.doc =
  {{
  A {type NavItem} represents an item in the navigation bar of a page. It has
  the following fields:
  
  * {{ docLink (docEmbedTermLink do url) }} is the URL of the item.
  * {{ docLink (docEmbedTermLink do NavItem.text) }} is the text of the item.
  }}

Page.NavItem.text : NavItem -> Text
Page.NavItem.text = cases NavItem _ text -> text

Page.NavItem.text.modify : (Text ->{g} Text) -> NavItem ->{g} NavItem
Page.NavItem.text.modify f = cases NavItem url text -> NavItem url (f text)

Page.NavItem.text.set : Text -> NavItem -> NavItem
Page.NavItem.text.set text1 = cases NavItem url _ -> NavItem url text1

Page.NavItem.toHtml : Boolean -> NavItem -> Html
Page.NavItem.toHtml isActive navItem =
  use List ++
  activeAttr = if isActive then [class "active"] else []
  a
    (activeAttr ++ [href (url navItem)])
    [hojberg_html_2_6_0.text (NavItem.text navItem)]

Page.NavItem.toHtml.doc : Doc
Page.NavItem.toHtml.doc =
  {{ Renders the given {type NavItem} as an {type Html} element. }}

Page.NavItem.url : NavItem -> Text
Page.NavItem.url = cases NavItem url _ -> url

Page.NavItem.url.modify : (Text ->{g} Text) -> NavItem ->{g} NavItem
Page.NavItem.url.modify f = cases NavItem url text -> NavItem (f url) text

Page.NavItem.url.set : Text -> NavItem -> NavItem
Page.NavItem.url.set url1 = cases NavItem _ text -> NavItem url1 text

Page.navItems : NavItems
Page.navItems =
  NavItems (NavItem "./" "Latest post") (NavItem "posts" "All posts")

Page.NavItems.allPosts : NavItems -> NavItem
Page.NavItems.allPosts = cases NavItems _ allPosts -> allPosts

Page.NavItems.allPosts.modify :
  (NavItem ->{g} NavItem) -> NavItems ->{g} NavItems
Page.NavItems.allPosts.modify f = cases
  NavItems latestPost allPosts -> NavItems latestPost (f allPosts)

Page.NavItems.allPosts.set : NavItem -> NavItems -> NavItems
Page.NavItems.allPosts.set allPosts1 = cases
  NavItems latestPost _ -> NavItems latestPost allPosts1

Page.NavItems.doc : Doc
Page.NavItems.doc =
  {{
  A {type NavItems} represents the items in the navigation bar of a page. It
  has two {type NavItem} fields:
  
  * {{ docLink (docEmbedTermLink do latestPost) }} is the item for the latest
    post.
  * {{ docLink (docEmbedTermLink do allPosts) }} is the item for all posts.
  }}

Page.navItems.doc : Doc
Page.navItems.doc =
  {{
  The default {type NavItems} for a blog. Includes a link to the latest post
  and a link to all posts.
  }}

Page.NavItems.latestPost : NavItems -> NavItem
Page.NavItems.latestPost = cases NavItems latestPost _ -> latestPost

Page.NavItems.latestPost.modify :
  (NavItem ->{g} NavItem) -> NavItems ->{g} NavItems
Page.NavItems.latestPost.modify f = cases
  NavItems latestPost allPosts -> NavItems (f latestPost) allPosts

Page.NavItems.latestPost.set : NavItem -> NavItems -> NavItems
Page.NavItems.latestPost.set latestPost1 = cases
  NavItems _ allPosts -> NavItems latestPost1 allPosts

Page.notFoundPage : Text -> Page
Page.notFoundPage message =
  use hojberg_html_2_6_0 text
  Page.empty
    |> withContent [h1 [] [text "Page not found"], p [] [text message]]

Page.notFoundPage.doc : Doc
Page.notFoundPage.doc =
  {{
  A helper function for rendering a "404: Not Found" page with the given error
  message.
  }}

Page.pageHeader : BlogContext -> Page -> Html
Page.pageHeader blogContext page =
  use Attribute Attribute
  use List ++
  use NavItem toHtml
  use hojberg_html_2_6_0 div text
  blog = BlogContext.blog blogContext
  navItems =
    match (Page.navItems, activeNavItem page) with
      (NavItems latest all, NoneActive) ->
        [toHtml false latest, toHtml false all]
      (NavItems latest all, LatestPost) ->
        [toHtml true latest, toHtml false all]
      (NavItems latest all, AllPosts) -> [toHtml false latest, toHtml true all]
  subscribe =
    if BlogContext.isEmailNotificationEnabled blogContext then
      [ div [class "subscribe"] [text "Subscribe"]
      , div
          [class "subscribe-flyout"]
          [ p [] [text "Get notified of new posts."]
          , div
              [class "form"]
              [ input
                  [ class "subscriber-name"
                  , Attribute "aria-label" "Name"
                  , Attribute "placeholder" "Name"
                  , Attribute "required" "required"
                  , Attribute "type" "text"
                  ]
              , input
                  [ class "subscriber-email"
                  , Attribute "aria-label" "Email Address"
                  , Attribute "placeholder" "Email Address"
                  , Attribute "required" "required"
                  , Attribute "type" "email"
                  ]
              ]
          , p
              [class "no-spam"]
              [text "We won't send you spam. Unsubscribe at any time."]
          , hojberg_html_2_6_0.button
              [class "button medium emphasized"] [text "Subscribe"]
          ]
      ]
    else []
  hojberg_html_2_6_0.header
    [class "page-header"]
    [ a
        [href "./"]
        [h1 [] [text (blogTitle blog)], div [] [text (description blog)]]
    , nav [class "main-nav"] (navItems ++ subscribe)
    ]

Page.postPage : BlogContext -> Slug ->{Exception, Remote} DocumentResult
Page.postPage blogContext slug =
  use OrderedTable tryRead
  blog = BlogContext.blog blogContext
  match Remote.both (do tryRead (posts blog) slug) do
    tryRead (htmlPosts blog) slug with
    (Some p, Some html) ->
      Success (toHtmlDocument blogContext (postPage_ blogContext p html))
    _ -> NotFound (toHtmlDocument blogContext (notFoundPage "Post not found"))

Page.postPage.doc : Doc
Page.postPage.doc =
  {{
  Renders the post with the given {type Slug} from the given {type Blog} as a
  {type Html} page.
  }}

Page.postPage.metadataToHtml : Metadata -> Html
Page.postPage.metadataToHtml metadata =
  use List intersperse map
  use hojberg_html_2_6_0 div text
  div
    [class "metadata"]
    [ div
        [class "primary-metadata"]
        [ div
            [class "published-at"]
            [ text
                (LocalDate.toShortText
                  (OffsetDateTime.date (Metadata.publishedAt metadata)))
            ]
        , sep
        , div
            [class "authors"]
            (metadata |> authors |> map authorToHtml |> intersperse comma)
        ]
    , div
        [class "secondary-metadata"]
        (map text (Metadata.tags metadata) |> intersperse comma)
    ]

Page.postPage.postCSS : CSS
Page.postPage.postCSS =
  CSS
    [ RuleSet
        [Selector ".post"]
        [ Rule "margin-top" "4rem"
        , Rule "display" "flex"
        , Rule "flex-direction" "column"
        , Rule "gap" "0.5rem"
        ]
    , RuleSet
        [Selector ".post .metadata"]
        [ Rule "font-size" "var(--font-size-medium)"
        , Rule "color" "var(--color_text_subdued)"
        , Rule "display" "flex"
        , Rule "justify-content" "center"
        , Rule "align-items" "center"
        , Rule "flex-direction" "column"
        , Rule "gap" "0.5rem"
        ]
    , RuleSet
        [ Selector ".post .primary-metadata"
        , Selector ".post .secondary-metadata"
        ]
        [ Rule "display" "flex"
        , Rule "flex-direction" "row"
        , Rule "gap" "0.5rem"
        , Rule "justify-content" "center"
        , Rule "align-items" "center"
        ]
    , RuleSet
        [Selector ".post .separator"]
        [Rule "color" "var(--color_text_very-subdued)"]
    ]

Page.postPage_ : BlogContext -> Post -> Html ->{Exception} Page
Page.postPage_ blogContext post postHtml =
  Page.empty
    |> withActiveNavItem LatestPost
    |> withCSS postCSS
    |> withContent
         [ hojberg_html_2_6_0.div
             [class "post"] [metadataToHtml (Post.metadata post), postHtml]
         ]

Page.rssFeedPage : URI -> Blog ->{Remote} Text
Page.rssFeedPage baseURI blog =
  use List :+
  use Map empty
  use OrderedTable read
  use unison_base_3_21_0.data.Stream map
  posts_ = posts blog
  slugStream : '{Remote, Stream (Instant, Slug)} ()
  slugStream = OrderedTable.toStream (postsByTime blog)
  postStream : '{Remote, Stream Post} ()
  postStream = map (cases (_, slug) -> read posts_ slug) slugStream
  lastPostTime = match Stream.head slugStream with
    Some (_, slug) -> read posts_ slug |> Post.metadata |> Metadata.publishedAt
    None           -> atUTC now!
  rssTimeStamp = OffsetDateTime.toRFC2822 lastPostTime
  XMLElement
    "rss"
    (Map.fromList [("version", "2.0")])
    [ XMLElement
        "channel"
        empty
        ([ XMLElement "title" empty [XMLCData (blogTitle blog)]
        , XMLElement "description" empty [XMLCData (description blog)]
        ]
          :+ XMLElement
            "link"
            empty
            [XMLCData (unison_base_3_21_0.IO.net.URI.toText baseURI)]
          List.++ [ XMLElement "lastBuildDate" empty [XMLText rssTimeStamp]
                  , XMLElement "pubDate" empty [XMLText rssTimeStamp]
                  ]
          List.++ toList!
                    (map
                      (toRSS baseURI)
                      (unison_base_3_21_0.data.Stream.take 20 postStream)))
    ]
    |> XMLNode.toXML
    |> (Text.++) "<?xml version='1.0' encoding='UTF-8'?>\n"

Page.rssFeedPage.doc : Doc
Page.rssFeedPage.doc =
  {{ Renders the RSS feed for the given {type Blog} as a {type Text}. }}

Page.scripts : [Html]
Page.scripts =
  use Attribute Attribute
  js =
    """
    // -- KATEX -----------------------------------------------------------------
    import katex from 'https://cdn.jsdelivr.net/npm/katex@0.16.9/dist/katex.mjs';
    
    class EmbedKatex extends HTMLElement {
      constructor() {
        super();
      }
    
      connectedCallback() {
        const markup = this.getAttribute('markup');
        const display = this.getAttribute('display');
    
        katex.render(markup, this, {
          throwOnError: false,
          displayMode: display === 'block',
        });
      }
    }
    
    customElements.define('embed-katex', EmbedKatex);
    
    // -- MERMAID ---------------------------------------------------------------
    import mermaid from 'https://cdn.jsdelivr.net/npm/mermaid@10/dist/mermaid.esm.min.mjs';
    
    class MermaidDiagram extends HTMLElement {
      constructor() {
        super();
      }
    
      async connectedCallback() {
        const diagram = this.getAttribute('diagram');
        const themeName = this.getAttribute('theme-name');
    
        // Generate a unique-ish diagram id, so we can have more than 1 diagram on
        // the page at a time
        const diagramId = 'mermaid-diagram_' + Date.now().toString();
    
        try {
          mermaid.mermaidAPI.initialize({
            theme: themeName,
            startOnLoad: false,
            securityLevel: 'sandbox',
          });
    
          const { svg } = await await mermaid.render(diagramId, diagram);
    
          this.innerHTML = svg;
          const iframe = this.querySelector('iframe');
          iframe?.classList?.add('mermaid-diagram');
        } catch (e) {
          const err = document.createElement('div');
    
          err.textContent =
            '🆘 Unfortunately, the Mermaid diagram could not be rendered.';
          err.classList.add('mermaid-diagram');
          err.classList.add('mermaid-diagram_error');
          err.setAttribute('title', e.toString());
    
          this.appendChild(err);
    
          // When Mermaid fails, it sometimes leaves an orphaned iframe at the end
          // of <body>. Remove it.
          document.getElementById('i' + diagramId)?.remove();
    
          // Rethrow error so we can ensure we log it.
          throw e;
        }
      }
    }
    
    customElements.define('mermaid-diagram', MermaidDiagram);
    
    // -- SVGS ------------------------------------------------------------------
    
    class EmbedSvg extends HTMLElement {
      constructor() {
        super();
      }
    
      connectedCallback() {
        const markup = this.textContent;
    
        // Always render in an iframe as SVGs can do all sort of nasty stuff like
        // run JavaScript and its CSS can effect the rest of the page.
        const iframe = document.createElement('iframe');
        iframe.setAttribute('srcdoc', `<body style='margin:0;'>${markup}<body>`);
        iframe.setAttribute('sandbox', '');
        iframe.setAttribute('frameborder', '0');
        iframe.setAttribute('scrolling', 'no');
        iframe.classList.add('embed-svg');
    
        this.innerHTML = '';
        this.appendChild(iframe);
      }
    }
    
    customElements.define('embed-svg', EmbedSvg);
    
    // -- Subscribe flyout
    
    const subscribe = document.querySelector('.subscribe');
    const flyout = document.querySelector('.subscribe-flyout');
    
    if (subscribe) {
      subscribe.addEventListener('click', (ev) => {
        flyout.classList.toggle('visible');
        document.querySelector('input.subscriber-name').focus();
      });
    
      const button = flyout.querySelector('button');
    
      // If they have already subscribed this session, there's no button.
      if (button) {
    
        button.addEventListener('click', async (ev) => {
          const form = document.querySelector('.form');
          const nameField = document.querySelector('input.subscriber-name');
          const emailField = document.querySelector('input.subscriber-email');
          const name = nameField.value;
          const email = emailField.value;
    
          if (name && email && email.includes('@')) {
            nameField.setAttribute('disabled', true);
            emailField.setAttribute('disabled', true);
            button.setAttribute('disabled', true);
    
            const response = await fetch('subscribe', {
              method: 'POST',
              headers: {
                'Content-Type': 'application/json',
              },
              body: JSON.stringify({ name, email }),
            });
           
    
            if (response.status === 200) {
              flyout.innerText = '✅ Subscribed';
              setTimeout(() => {
                flyout.classList.toggle('visible');
              }, 1000);
            }
            else {
              nameField.removeAttribute('disabled');
              emailField.removeAttribute('disabled');
              button.removeAttribute('disabled')
    
              let errorMsg = document.querySelector('.error-msg');
    
              if (!errorMsg) {
                errorMsg = document.createElement('div');
                errorMsg.classList.add('error-msg');
                flyout.insertBefore(errorMsg, button);
              }
    
              errorMsg.innerText = '⚠️ An expected error happened.'; 
            }
          }
          else {
            let errorMsg = document.querySelector('.error-msg');
    
            if (!errorMsg) {
              errorMsg = document.createElement('div');
              errorMsg.classList.add('error-msg');
              flyout.insertBefore(errorMsg, button);
            }
    
            errorMsg.innerText = '⚠️ Please provide a valid name and email.';
          }
        });
      }
    }
      
    """
  [ hojberg_html_2_6_0.link
      [ rel "stylesheet"
      , href "https://cdn.jsdelivr.net/npm/katex@0.16.9/dist/katex.css"
      , Attribute
          "integrity"
          "sha384-OH8qNTHoMMVNVcKdKewlipV4SErXqccxxlg6HC9Cwjr5oZu2AdBej1TndeCirael"
      , Attribute "crossorigin" "anonymous"
      ]
  , script [Attribute "type" "module"] [unsafeText js]
  , script
      [ Attribute
          "src"
          "https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.9.0/highlight.min.js"
      ]
      []
  ]

Page.scripts.doc : Doc
Page.scripts.doc = {{ The default scripts for a blog page. }}

Page.sep : Html
Page.sep =
  hojberg_html_2_6_0.span [class "separator"] [hojberg_html_2_6_0.text "|"]

Page.title : Page -> Text
Page.title = cases Page title _ _ _ -> title

Page.title.modify : (Text ->{g} Text) -> Page ->{g} Page
Page.title.modify f = cases
  Page title activeNavItem content css ->
    Page (f title) activeNavItem content css

Page.title.set : Text -> Page -> Page
Page.title.set title1 = cases
  Page _ activeNavItem content css -> Page title1 activeNavItem content css

Page.toHtml : BlogContext -> Page ->{Exception} Html
Page.toHtml blogContext page =
  use Attribute Attribute
  use hojberg_html_2_6_0 link text
  blog = BlogContext.blog blogContext
  currentYear =
    year (OffsetDateTime.date (atUTC (BlogContext.now blogContext)))
  pageCss : CSS
  pageCss = List.foldLeft (CSS.++) (CSS []) (Page.css page)
  basePath =
    use Text ++ ==
    p =
      unison_base_3_21_0.IO.net.URI.Path.toText
        (BlogContext.basePath blogContext)
    if p == "/" then p else p ++ "/"
  styles =
    blog
      |> Blog.theme
      |> mainStyles
      |> (css -> css CSS.++ pageCss)
      |> CSS.toText
      |> (css_ -> css_ Text.++ "\n" Text.++ docStyles)
      |> (css_ -> css_ Text.++ "\n" Text.++ syntaxStyles)
      |> (css_ -> css_ Text.++ "\n" Text.++ highlightJsStyles)
  hojberg_html_2_6_0.html
    []
    [ hojberg_html_2_6_0.head
        []
        ([ hojberg_html_2_6_0.title [] [text (blogTitle blog)]
        , meta
            [ Attribute "name" "viewport"
            , Attribute
                "content"
                "width=device-width, initial-scale=1, shrink-to-fit=no"
            ]
        , link
            [Attribute "rel" "preconnect", href "https://fonts.googleapis.com"]
        , link
            [ Attribute "rel" "preconnect"
            , href "https://fonts.gstatic.com"
            , Attribute "crossorigin" "crossorigin"
            ]
        , link
            [ href
                "https://fonts.googleapis.com/css2?family=Fira+Code:wght@300..700&family=Inter:wght@100..900&display=swap"
            , Attribute "rel" "stylesheet"
            ]
        , link
            [ Attribute "rel" "alternate"
            , Attribute "type" "application/rss+xml"
            , Attribute.title "RSS"
            , href "rss"
            ]
        , link
            [ Attribute "rel" "alternate"
            , Attribute "type" "application/atom+xml"
            , href "atom"
            , Attribute.title "Atom"
            ]
        , hojberg_html_2_6_0.style [] [text styles]
        , hojberg_html_2_6_0.base [href basePath]
        ]
          List.++ scripts)
    , hojberg_html_2_6_0.body
        []
        [ pageHeader blogContext page
        , hojberg_html_2_6_0.main [class "main-content"] (Page.content page)
        , hojberg_html_2_6_0.footer
            [class "main-footer"]
            [ text
                ("© "
                  Text.++ Int.toText currentYear
                  Text.++ " "
                  Text.++ blogTitle blog)
            ]
        , script
            []
            [ unsafeText
                "if (hljs) { \n  document.querySelectorAll('.rich.source.code.by-language code').forEach(el => { \n    hljs.highlightElement(el); \n  }); \n}"
            ]
        ]
    ]

Page.toHtml.doc : Doc
Page.toHtml.doc =
  {{ Renders the given {type Page} as an {type Html} element. }}

Page.toHtmlDocument : BlogContext -> Page ->{Exception} Text
Page.toHtmlDocument blogContext page =
  use Text ++
  "<!DOCTYPE html>\n"
    ++ hojberg_html_2_6_0.toText (Page.toHtml blogContext page)

Page.toHtmlDocument.doc : Doc
Page.toHtmlDocument.doc =
  {{ Renders the given {type Page} as an HTML document. }}

Page.withActiveNavItem : ActiveNavItem -> Page -> Page
Page.withActiveNavItem = activeNavItem.set

Page.withActiveNavItem.doc : Doc
Page.withActiveNavItem.doc =
  {{ Sets the active nav item for the given {type Page}. }}

Page.withContent : [Html] -> Page -> Page
Page.withContent = Page.content.set

Page.withContent.doc : Doc
Page.withContent.doc = {{ Sets the content for the given {type Page}. }}

Page.withCSS : CSS -> Page -> Page
Page.withCSS css_ page =
  use List :+
  sheets = Page.css page :+ css_
  css.set sheets page

Page.withCSS_ : [CSS] -> Page -> Page
Page.withCSS_ sheets = css.set sheets

Page.withTitle : Text -> Page -> Page
Page.withTitle = Page.title.set

Page.withTitle.doc : Doc
Page.withTitle.doc = {{ Sets the title for the given {type Page}. }}

Post.addAuthor : BlogAuthor -> Post -> Post
Post.addAuthor =
  use List +:
  metadata.modify << authors.modify << (+:)

Post.addAuthor.doc : Doc
Post.addAuthor.doc =
  {{ Adds the given {type BlogAuthor} to the given {type Post}. }}

Post.addTag : Text -> Post -> Post
Post.addTag =
  use List +:
  metadata.modify << Metadata.tags.modify << (+:)

Post.addTag.doc : Doc
Post.addTag.doc = {{ Adds the given tag to the given {type Post}. }}

Post.cloudPublish :
  '{g, Exception, Cloud} Blog -> Post ->{g, Exception, Cloud} ()
Post.cloudPublish blog post =
  use OrderedTable.write tx
  b = blog()
  Cloud.submit (cloudEnvironment b) do
    randomly do
      transact.random (OrderedTable.database (posts b)) do
        slug = Metadata.slug (Post.metadata post)
        tx (postsByTime b) (Post.key post) slug
        tx (posts b) slug post
        tx
          (htmlPosts b)
          slug
          (h1 [] [hojberg_html_2_6_0.text (Post.title post)])

Post.cloudPublish.doc : Doc
Post.cloudPublish.doc =
  {{
  To publish posts to your blog, first create a Unison {type Doc} and push it
  to [Unison Share](https://share.unison-lang.org) then write an adhoc function
  to provide post metadata and publish it:
  
  `raw
  publishMyPost =
    Cloud.main do
      title = "My cool Post"
      author = BlogAuthor "Alice" "This is a bio" None
      docPath = NamespacePath.fromList ["posts", "myCoolPost"]
      publishedAt = !Instant.now
  
      post = Post.post title author publishedAt docPath
      
      Post.publish myBlog post
  `
  }}

Post.doc : Doc
Post.doc =
  {{
  A {type Post} represents a blog post. It has the following fields:
  
  * {{ docLink (docEmbedTermLink do Post.metadata) }} is a {type Metadata}
    record that contains the metadata for the post, such as the title, summary,
    authors, published date, tags, slug, and GUID.
  * {{ docLink (docEmbedTermLink do docPath) }} is a {type NamespacePath} that
    points to the location of the {type Doc} for the post in the Unison Share
    project.
  }}

Post.docPath : Post -> NamespacePath
Post.docPath = cases Post _ docLocation -> docLocation

Post.docPath.modify : (NamespacePath ->{g} NamespacePath) -> Post ->{g} Post
Post.docPath.modify f = cases
  Post metadata docLocation -> Post metadata (f docLocation)

Post.docPath.set : NamespacePath -> Post -> Post
Post.docPath.set docLocation1 = cases
  Post metadata _ -> Post metadata docLocation1

Post.key : Post -> Instant
Post.key = toInstant << Metadata.publishedAt << Post.metadata

Post.key.doc : Doc
Post.key.doc = {{ Returns the key for the given {type Post}. }}

Post.metadata : Post -> Metadata
Post.metadata = cases Post metadata _ -> metadata

Post.Metadata.authors : Metadata -> [BlogAuthor]
Post.Metadata.authors = cases Metadata _ _ authors _ _ _ _ -> authors

Post.Metadata.authors.modify :
  ([BlogAuthor] ->{g} [BlogAuthor]) -> Metadata ->{g} Metadata
Post.Metadata.authors.modify f = cases
  Metadata title summary authors publishedAt tags slug guid ->
    Metadata title summary (f authors) publishedAt tags slug guid

Post.Metadata.authors.set : [BlogAuthor] -> Metadata -> Metadata
Post.Metadata.authors.set authors1 = cases
  Metadata title summary _ publishedAt tags slug guid ->
    Metadata title summary authors1 publishedAt tags slug guid

Post.Metadata.doc : Doc
Post.Metadata.doc =
  {{
  A {type Metadata} is a record type that contains the metadata for a blog
  post. It has the following fields:
  
  * {Post.title} is the title of the post.
  * {{ docLink (docEmbedTermLink do Metadata.summary) }} is a short summary of
    the post.
  * {{ docLink (docEmbedTermLink do authors) }} is a list of {type BlogAuthor}
    that represent the authors of the post.
  * {{ docLink (docEmbedTermLink do Metadata.publishedAt) }} is the date and
    time when the post was published.
  * {{ docLink (docEmbedTermLink do Metadata.tags) }} is a list of tags for the
    post.
  * {{ docLink (docEmbedTermLink do Metadata.slug) }} is the unique identifier
    for the post.
  * {{ docLink (docEmbedTermLink do Metadata.guid) }} is a unique identifier
    for the post.
  }}

Post.Metadata.guid : Metadata -> Text
Post.Metadata.guid = cases Metadata _ _ _ _ _ _ guid -> guid

Post.Metadata.guid.modify : (Text ->{g} Text) -> Metadata ->{g} Metadata
Post.Metadata.guid.modify f = cases
  Metadata title summary authors publishedAt tags slug guid ->
    Metadata title summary authors publishedAt tags slug (f guid)

Post.Metadata.guid.set : Text -> Metadata -> Metadata
Post.Metadata.guid.set guid1 = cases
  Metadata title summary authors publishedAt tags slug _ ->
    Metadata title summary authors publishedAt tags slug guid1

Post.metadata.modify : (Metadata ->{g} Metadata) -> Post ->{g} Post
Post.metadata.modify f = cases
  Post metadata docLocation -> Post (f metadata) docLocation

Post.Metadata.publishedAt : Metadata -> OffsetDateTime
Post.Metadata.publishedAt = cases
  Metadata _ _ _ publishedAt _ _ _ -> publishedAt

Post.Metadata.publishedAt.modify :
  (OffsetDateTime ->{g} OffsetDateTime) -> Metadata ->{g} Metadata
Post.Metadata.publishedAt.modify f = cases
  Metadata title summary authors publishedAt tags slug guid ->
    Metadata title summary authors (f publishedAt) tags slug guid

Post.Metadata.publishedAt.set : OffsetDateTime -> Metadata -> Metadata
Post.Metadata.publishedAt.set publishedAt1 = cases
  Metadata title summary authors _ tags slug guid ->
    Metadata title summary authors publishedAt1 tags slug guid

Post.metadata.set : Metadata -> Post -> Post
Post.metadata.set metadata1 = cases
  Post _ docLocation -> Post metadata1 docLocation

Post.Metadata.slug : Metadata -> Slug
Post.Metadata.slug = cases Metadata _ _ _ _ _ slug _ -> slug

Post.Metadata.slug.modify : (Slug ->{g} Slug) -> Metadata ->{g} Metadata
Post.Metadata.slug.modify f = cases
  Metadata title summary authors publishedAt tags slug guid ->
    Metadata title summary authors publishedAt tags (f slug) guid

Post.Metadata.slug.set : Slug -> Metadata -> Metadata
Post.Metadata.slug.set slug1 = cases
  Metadata title summary authors publishedAt tags _ guid ->
    Metadata title summary authors publishedAt tags slug1 guid

Post.Metadata.summary : Metadata -> Text
Post.Metadata.summary = cases Metadata _ summary _ _ _ _ _ -> summary

Post.Metadata.summary.modify : (Text ->{g} Text) -> Metadata ->{g} Metadata
Post.Metadata.summary.modify f = cases
  Metadata title summary authors publishedAt tags slug guid ->
    Metadata title (f summary) authors publishedAt tags slug guid

Post.Metadata.summary.set : Text -> Metadata -> Metadata
Post.Metadata.summary.set summary1 = cases
  Metadata title _ authors publishedAt tags slug guid ->
    Metadata title summary1 authors publishedAt tags slug guid

Post.Metadata.tags : Metadata -> [Text]
Post.Metadata.tags = cases Metadata _ _ _ _ tags _ _ -> tags

Post.Metadata.tags.modify : ([Text] ->{g} [Text]) -> Metadata ->{g} Metadata
Post.Metadata.tags.modify f = cases
  Metadata title summary authors publishedAt tags slug guid ->
    Metadata title summary authors publishedAt (f tags) slug guid

Post.Metadata.tags.set : [Text] -> Metadata -> Metadata
Post.Metadata.tags.set tags1 = cases
  Metadata title summary authors publishedAt _ slug guid ->
    Metadata title summary authors publishedAt tags1 slug guid

Post.Metadata.title : Metadata -> Text
Post.Metadata.title = cases Metadata title _ _ _ _ _ _ -> title

Post.Metadata.title.modify : (Text ->{g} Text) -> Metadata ->{g} Metadata
Post.Metadata.title.modify f = cases
  Metadata title summary authors publishedAt tags slug guid ->
    Metadata (f title) summary authors publishedAt tags slug guid

Post.Metadata.title.set : Text -> Metadata -> Metadata
Post.Metadata.title.set title1 = cases
  Metadata _ summary authors publishedAt tags slug guid ->
    Metadata title1 summary authors publishedAt tags slug guid

Post.new :
  Text
  -> Text
  -> BlogAuthor
  -> OffsetDateTime
  -> NamespacePath
  ->{Exception, Random} Post
Post.new title summary author timestamp path =
  slug = Slug.fromText title
  guid = UUID.toText version4()
  Post (Metadata title summary [author] timestamp [] slug guid) path

Post.new.doc : Doc
Post.new.doc =
  {{
  Creates a new {type Post} with the given title, summary, author, timestamp,
  and path. Use e.g. {{ docLink (docEmbedTermLink do addTag) }} and {{
  docLink (docEmbedTermLink do addAuthor) }} to add tags and authors.
  }}

Post.publishedAt : Post -> OffsetDateTime
Post.publishedAt post = Metadata.publishedAt (Post.metadata post)

Post.publishedAt.doc : Doc
Post.publishedAt.doc =
  {{ Returns the published at time for the given {type Post}. }}

Post.slug : Post -> Slug
Post.slug = Metadata.slug << Post.metadata

Post.slug.doc : Doc
Post.slug.doc = {{ Returns the slug for the given {type Post}. }}

Post.title : Post -> Text
Post.title p = Metadata.title (Post.metadata p)

Post.title.doc : Doc
Post.title.doc = {{ Returns the title for the given {type Post}. }}

Post.toAtom : URI -> Post ->{Remote} XMLNode
Post.toAtom baseURI = cases
  Post
    (Metadata postTitle summary authors publishedAt tags slug postGuid)
    location ->
    XMLElement
      "entry"
      Map.empty
      ([ XMLElement "title" Map.empty [XMLCData postTitle]
      , XMLElement "summary" Map.empty [XMLCData summary]
      ]
        List.++ List.map
                  (cases
                    BlogAuthor name bio avatar email ->
                      XMLElement
                        "author"
                        Map.empty
                        [ XMLElement "name" Map.empty [XMLCData name]
                        , XMLElement "email" Map.empty [XMLCData email]
                        ])
                  authors
        List.++ [ XMLElement
                    "id" Map.empty [XMLText ("urn:uuid:" Text.++ postGuid)]
                , XMLElement
                    "published"
                    Map.empty
                    [XMLText (OffsetDateTime.toText publishedAt)]
                ]
        List.:+ XMLElement
          "link"
          (Map.fromList
            [ ( "href"
              , unison_base_3_21_0.IO.net.URI.toText
                  (baseURI URI./ "posts" URI./ Slug.toText slug)
              )
            ])
          []
        List.++ List.map
          (tag ->
            XMLElement "category" (Map.fromList [("term", tag)]) List.empty)
          tags)

Post.toAtom.doc : Doc
Post.toAtom.doc = {{ Converts the given {type Post} to an Atom feed entry. }}

Post.toRSS : URI -> Post -> XMLNode
Post.toRSS baseURI = cases
  Post
    (Metadata postTitle summary authors publishedAt tags slug postGuid)
    location ->
    XMLElement
      "item"
      Map.empty
      ([ XMLElement "title" Map.empty [XMLCData postTitle]
      , XMLElement
          "link"
          Map.empty
          [XMLCData (unison_base_3_21_0.IO.net.URI.toText baseURI)]
      , XMLElement "description" Map.empty [XMLCData summary]
      , XMLElement
          "pubDate" Map.empty [XMLText (OffsetDateTime.toRFC2822 publishedAt)]
      , XMLElement
          "author"
          Map.empty
          [ XMLCData
              (foldDelimited (Text.++) BlogAuthor.email ", " "" "" authors)
          ]
      , XMLElement "guid" Map.empty [XMLCData postGuid]
      ]
        List.++ List.map
          (XMLElement "category" Map.empty << List.singleton << XMLCData) tags)

Post.toRSS.doc : Doc
Post.toRSS.doc = {{ Converts the given {type Post} to an RSS feed entry. }}

Post.unpublish : '{g} Blog -> Slug ->{g, Exception, Cloud} ()
Post.unpublish blog slug =
  use OrderedTable.delete tx
  b = blog()
  Cloud.submit (cloudEnvironment b) do
    deletePost p = transact (OrderedTable.database (posts b)) do
      tx (posts b) slug
      tx (htmlPosts b) slug
      tx (postsByTime b) (toInstant (Post.publishedAt p))
    slug
      |> OrderedTable.tryRead (posts b)
      |> Optional.map deletePost
      |> base_2_14_0.ignore

Post.unpublish.doc : Doc
Post.unpublish.doc =
  {{
  Unpublishes the post with the given {type Slug} from the given {type Blog}.
  }}

Post.withAuthors : [BlogAuthor] -> Post -> Post
Post.withAuthors = metadata.modify << authors.set

Post.withAuthors.doc : Doc
Post.withAuthors.doc = {{ Sets the authors for the given {type Post}. }}

Post.withPublishedAt : OffsetDateTime -> Post -> Post
Post.withPublishedAt dt post =
  md = Post.metadata post
  md_ = publishedAt.set dt md
  metadata.set md post

Post.withPublishedOn : LocalDate -> Post -> Post
Post.withPublishedOn date post =
  dt = fromTimeAndDate (OffsetTime (UTCOffset +0) (LocalTime 0 0 0 0)) date
  md = Post.metadata post
  md_ = publishedAt.set dt md
  metadata.set md post

Post.withSlug : Slug -> Post -> Post
Post.withSlug = metadata.modify << slug.set

Post.withSlug.doc : Doc
Post.withSlug.doc = {{ Sets the slug for the given {type Post}. }}

Post.withSummary : Text -> Post -> Post
Post.withSummary = metadata.modify << Metadata.summary.set

Post.withSummary.doc : Doc
Post.withSummary.doc =
  {{ Sets the {Metadata.summary} for the given {type Post}. }}

Post.withTags : [Text] -> Post -> Post
Post.withTags = metadata.modify << Metadata.tags.set

Post.withTags.doc : Doc
Post.withTags.doc = {{ Sets the tags for the given {type Post}. }}

Post.withTitle : Text -> Post -> Post
Post.withTitle = metadata.modify << Metadata.title.set

Post.withTitle.doc : Doc
Post.withTitle.doc = {{ Sets the title for the given {type Post}. }}

README : Doc
README =
  {{
  # A blog engine for Unison Cloud
  
    This library provides a simple way to write and manage a blog that's hosted
    on Unison Cloud and Unison Share.
    
    Here's the idea: you write each blog posts as a {type Doc} value, making
    use of Unison's incredible {type Doc} type to include images, links,
    hyperlinked Unison Code examples, and other rich content with ease. You
    keep all your blog posts in a project on Unison Share. Then you use this
    library to assemble them into a blog that gets deployed to Unison Cloud as
    a beautiful website complete with RSS/Atom feeds and email subscriptions.
    [See this example blog](https://hojberg.unison-services.cloud/s/example-blog)
    for an idea of what your blog could look like.
    
    This library provides facilities for customizing the look and feel of your
    blog, or you can just use the defaults if you like.
    
    ## Getting started
    
       ### Step 1: Get a Unison Cloud account
       
           To get started, you'll need to have a
           [Unison Cloud](https://unison.cloud) account and have the Unison
           Codebase Manager (UCM) installed. Your Cloud account is also your
           [Unison Share](https://share.unison-lang.org) account, where you
           will store your blog posts.
       
       ### Step 2: Install the blog engine in a project
       
           Create a new project for your blog in UCM:
           
           ``` ucm
           > project.create myblog
           ```
           
           Then install this library into your project:
           
           ``` ucm
           > pull @unison/blog-engine/releases/latest lib.blogEngine
           ```
       
       ### Step 3: Define your blog
       
           Now you can start creating your blog. You can start by defining a
           term that creates a new {type Blog}:
           
               @source{sampleBlog}
           
           The `slug` is an identifier for your blog which will become the
           {type ServiceName} of the deployed HTTP service. The `shareProject`
           is the project on Unison Share where you're going to store your blog
           posts. You can store your posts in the same project as your blog
           definition, or in a different project.
           **The project that hosts the posts needs to be public** so that the
           blog engine can access them, but the blog project itself can remain
           private if you want.
           
           {Blog.new} does a few things for you:
           
           1. It creates a new {type Environment} for your blog in Unison
              Cloud, using the `slug` as the name, or grabs it if it already
              exists.
           2. It creates a new {type Database} for your blog in Unison Cloud
              (or grabs the existing one), using the `slug` as the name.
           3. It creates a {type Blog} value that you can use to publish posts
              to your blog. If you already have a blog with the `slug` name, it
              grabs it from the {type Database}.
           
           Add this term to your project:
           
           ``` ucm
           myBlogProject/main> add
           ```
       
       ### Step 4: Define a deployment for your blog
       
           Next, define a deployment for your blog:
           
           {{
           docSource
             [docSourceElement (docEmbedTermLink do sampleBlog.deploy) []] }}
           
           `add` that to your codebase as well.
       
       ### Step 5: Define a blog author
       
           Then define a {type BlogAuthor} for yourself:
           
               @source{sampleAuthor}
           
           Now that you have a {type Blog} and an author object, you can start
           publishing posts.
       
       ### Step 6: Write a blog post
       
           A blog post is just any {type Doc} value:
           
               @source{helloWorld}
       
       ### Step 7: Add the post to your blog
       
           Now you can publish the post to your blog. One way of doing this is
           just adding it to a function called `build` (you can call it
           whatever you like):
           
           {{
           docSource
             [docSourceElement (docEmbedTermLink do sampleBlog.build) []] }}
           
           You might even want to add a function that does both the build and
           the deploy in one go:
           
           {{ docSource [docSourceElement (docEmbedTermLink do buildDeploy) []]
           }}
           
           {{
           Doc.Aside
             {{
             If you want to test out your blog locally before publishing, you
             will need to use a single function
             {{ (docLink (docEmbedTermLink do buildDeploy)) }}; this is due to
             the fact that currently, state isn't persisted across runs in the
             local interpreter, so a single call to e.g. {run.local.serve} will
             be needed; just replace the usage of {Cloud.main} with
             `do Cloud.run.local`.
             }} }}
       
       ### Step 8: Push your blog to Unison Share
       
           Once you've written your blog posts, you can push them to Unison
           Share. This makes them available to your blog engine when it deploys
           your blog to Unison Cloud.
           
           From UCM:
           
           ``` ucm
           myblog/main> push
           ```
       
       ### Step 9: Make your project public
       
           Make sure that the project that hosts your blog posts is public.
           This is done from Unison Share. Go to the project Settings and set
           the Project Visibility to "Public" and hit Save.
       
       ### Step 10: Deploy your blog
       
           Finally, to build and deploy your blog, run this in UCM to publish
           your post to the cloud and deploy the blog server:
           
           ``` ucm
           myblog/main> run buildDeploy
           ```
           
           This will give you a URL where your blog is hosted.
    
    ## Blogging workflow
    
       Now that you're all set up, a typical workflow for writing and
       publishing a blog post is as follows:
       
       1. Write your blog post as a {type Doc} value in the project your
          {type Blog} refers to in its {type ProjectRef}
       2. Add the post to your `build` function, passing it to {publish}
       3. `update` in UCM.
       4. `push` to Unison Share.
       5. `run buildDeploy` in UCM to republish all posts and redeploy your
          blog to Unison Cloud.
    
    ## Posts with multiple authors
    
       By default, {BlogEnv.post} takes a single {type BlogAuthor} as the
       author of the post. If you have multiple authors, you can define a
       {type BlogAuthor} for each of them and use either
       `Post.addAuthor author post` for each one or use
       `Post.withAuthors authors post` to replace the list of authors with a
       new list.
    
    ## Adding tags to your posts
    
       You can add tags to your posts by using {addTag}. This adds a tag to the
       list of tags for the post. You can also use {withTags} to replace the
       list of tags with a new list. Readers can then filter posts by tag on
       your blog's website.
    
    ## Add support for SendGrid Email Notifications
    
       You can add support for your readers to be notified via email when you
       publish new posts and 2 steps:
       
       1. Add {type EmailNotificationsConfig} to your blog with
          {withEmailNotificationsConfig}. This sets up the base URI for linking
          to your blog from emails, and the email address you're sending from.
       2. Add your
          [SendGrid API key](https://docs.sendgrid.com/api-reference/api-keys/create-api-keys)
          to your cloud environment with {setSendgridApiKey}. Note that the API
          key should **not** be added to your codebase. Instead, create an
          ephemeral term as follows in your scratch file and `run` it:
       
       ``` unison
       deleteMe = Cloud.main do setSendgridApiKey !sampleBlog "SG.xyz"
       ```
       
       Where `sampleBlog` is your {type Blog} and `SG.xyz` is your SendGrid API
       key.
       
       We recommend using Sendgrid's subscriptions feature that automatically
       manages unsubscribes and adds the unsubscribe link to outgoing
       notifications.
  }}

README.posts.helloWorld : Doc
README.posts.helloWorld = {{ Hello, world, this is my first blog post! }}

README.sampleAuthor : BlogAuthor
README.sampleAuthor =
  BlogAuthor "My Name" "A short bio about me" None "me@example.com"

README.sampleBlog : '{Exception, Cloud} Blog
README.sampleBlog = do
  slug = "myblog"
  title = "My Blog"
  shareProject = ProjectRef "my-username" "myblog"
  Blog.new slug title shareProject

README.sampleBlog.build : '{IO, Exception, Cloud} ()
README.sampleBlog.build =
  do
    withBlog sampleBlog() do
      publish
        (BlogEnv.post
          "Hello World" sampleAuthor (NamespacePath ["helloWorldPost"])
          |> withSummary "My first post")

README.sampleBlog.buildDeploy : '{IO, Exception} URI
README.sampleBlog.buildDeploy = Cloud.main do
  sampleBlog.build()
  sampleBlog.deploy()

README.sampleBlog.deploy : '{IO, Exception, Cloud} URI
README.sampleBlog.deploy = do
  blog = sampleBlog()
  Blog.deploy blog

ReleaseNotes : Doc
ReleaseNotes = {{ Upgrade library dependencies }}

up.base.time.LocalDate.NamedMonth.toShortText : NamedMonth -> Text
up.base.time.LocalDate.NamedMonth.toShortText = cases
  Jan -> "Jan"
  Feb -> "Feb"
  Mar -> "Mar"
  Apr -> "Apr"
  May -> "May"
  Jun -> "Jun"
  Jul -> "Jul"
  Aug -> "Aug"
  Sep -> "Sep"
  Oct -> "Oct"
  Nov -> "Nov"
  Dec -> "Dec"

up.base.time.LocalDate.NamedMonth.toText : NamedMonth -> Text
up.base.time.LocalDate.NamedMonth.toText = cases
  Jan -> "January"
  Feb -> "February"
  Mar -> "March"
  Apr -> "April"
  May -> "May"
  Jun -> "June"
  Jul -> "July"
  Aug -> "August"
  Sep -> "September"
  Oct -> "October"
  Nov -> "November"
  Dec -> "December"

up.base.time.LocalDate.NamedMonth.tryFromNat : Nat -> Optional NamedMonth
up.base.time.LocalDate.NamedMonth.tryFromNat = cases
  1  -> Some Jan
  2  -> Some Feb
  3  -> Some Mar
  4  -> Some Apr
  5  -> Some May
  6  -> Some Jun
  7  -> Some Jul
  8  -> Some Aug
  9  -> Some Sep
  10 -> Some Oct
  11 -> Some Nov
  12 -> Some Dec
  _  -> None

up.base.time.LocalDate.toNamedMonth : LocalDate -> NamedMonth
up.base.time.LocalDate.toNamedMonth d =
  use Text ++
  getOrBug ("Invalid month :" ++ Nat.toText (month d)) (tryFromNat (month d))

up.base.time.LocalDate.toShortText : LocalDate -> Text
up.base.time.LocalDate.toShortText d =
  use Text ++
  d |> toNamedMonth |> NamedMonth.toShortText
    ++ " "
    ++ Nat.toText (LocalDate.day d)
    ++ ", "
    ++ Int.toText (year d)

up.HttpResponse.ensureSuccess : HttpResponse ->{Exception} HttpResponse
up.HttpResponse.ensureSuccess response =
  http.HttpResponse.expectSuccess response
  response

up.uriParser.Parser.root : Parser a a
up.uriParser.Parser.root = Parser cases
  s@(Parser.State.State visited [] params frag committed value)   -> [s]
  s@(Parser.State.State visited [""] params frag committed value) -> [s]
  _                                                               -> []

up.uriParser.Parser.root.doc : Doc
up.uriParser.Parser.root.doc =
  use Parser noCapture
  use unison_base_3_21_0.IO.net URI.parse
  use uriParser.Parser root
  {{
  The {{ docLink (docEmbedTermLink do root) }} parser matches the root of the
  URI. It matches the empty string or the absence of a path component. It does
  not consume any input.
  
  # Example
  
    It can be used to match the root of a URI without a trailing slash:
    
    ```
    catch do Parser.parse (noCapture root) (URI.parse "https://example.com")
    ```
    
    Or with a trailing slash:
    
    ```
    catch do Parser.parse (noCapture root) (URI.parse "https://example.com/")
    ```
    
    But it does not match any other path:
    
    ```
    catch do
      Parser.parse (noCapture root) (URI.parse "https://example.com/foo")
    ```
  }}
````
