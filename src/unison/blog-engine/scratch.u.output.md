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

