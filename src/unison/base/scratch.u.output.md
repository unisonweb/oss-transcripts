# Base

This is Unison's standard library. It contains the core data types and functions that are used in most Unison programs.

## Library contents list

``` ucm
@unison/base/main> pull.without-history @unison/base/releases/3.28.1

  Downloaded 13444 entities.

  ✅

  Successfully updated @unison/base/main from
  @unison/base/releases/3.28.1.

@unison/base/main> find

  1.    structural ability abilities.Abort
  2.    abilities.Abort.abort : {Abort} a
  3.    abilities.Abort.abort.doc : Doc
  4.    abilities.Abort.abortWhen : Boolean ->{Abort} ()
  5.    abilities.Abort.abortWhen.doc : Doc
  6.    abilities.Abort.doc : Doc
  7.    abilities.Abort.tests.ex1 : [Result]
  8.    abilities.Abort.tests.ex2 : [Result]
  9.    abilities.Abort.tests.ex3 : [Result]
  10.   abilities.Abort.toBug : '{g, Abort} a ->{g} a
  11.   abilities.Abort.toBug.doc : Doc
  12.   abilities.Abort.toDefault : '{g} a
                                    -> '{g, Abort} a
                                    -> '{g} a
  13.   abilities.Abort.toDefault.doc : Doc
  14.   abilities.Abort.toDefault! : '{g} a
                                     -> '{g, Abort} a
                                     ->{g} a
  15.   abilities.Abort.toDefault!.doc : Doc
  16.   abilities.Abort.toDefault!.handler : '{g} a
                                             -> Request
                                               {Abort} a
                                             ->{g} a
  17.   abilities.Abort.toDefaultValue : a
                                         -> '{g, Abort} a
                                         -> '{g} a
  18.   abilities.Abort.toDefaultValue.doc : Doc
  19.   abilities.Abort.toDefaultValue! : a
                                          -> '{g, Abort} a
                                          ->{g} a
  20.   abilities.Abort.toDefaultValue!.doc : Doc
  21.   abilities.Abort.toDefaultValue!.handler : a
                                                  -> Request
                                                    {Abort} a
                                                  -> a
  22.   abilities.Abort.toException : '{g, Abort} a
                                      -> Type
                                      -> Text
                                      ->{g, Exception} a
  23.   abilities.Abort.toException.doc : Doc
  24.   abilities.Abort.toException.doesn'tThrowOnNoAbort : [Result]
  25.   abilities.Abort.toException.throwsOnAbort : [Result]
  26.   abilities.Abort.toGenericException : Text
                                             -> e
                                             -> '{g, Abort} a
                                             ->{g, Exception} a
  27.   abilities.Abort.toGenericException.doc : Doc
  28.   abilities.Abort.toGenericException.doesn'tThrowOnNoAbort : [Result]
  29.   abilities.Abort.toGenericException.throwsOnAbort : [Result]
  30.   abilities.Abort.toLazyThrow : 'e
                                      -> '{g, Abort} a
                                      ->{g, Throw e} a
  31.   abilities.Abort.toLazyThrow.doc : Doc
  32.   abilities.Abort.toOptional : '{g, Abort} a
                                     -> '{g} Optional a
  33.   abilities.Abort.toOptional.doc : Doc
  34.   abilities.Abort.toOptional! : '{g, Abort} a
                                      ->{g} Optional a
  35.   abilities.Abort.toOptional!.doc : Doc
  36.   abilities.Abort.toThrow : e
                                  -> '{g, Abort} a
                                  ->{g, Throw e} a
  37.   abilities.Abort.toThrow.doc : Doc
  38.   structural ability abilities.Ask a
  39.   abilities.Ask.ask : {Ask a} a
  40.   abilities.Ask.ask.doc : Doc
  41.   abilities.Ask.doc : Doc
  42.   abilities.Ask.map : (a ->{g1} b)
                            -> '{g2, Ask b} r
                            -> '{g1, g2, Ask a} r
  43.   abilities.Ask.map.doc : Doc
  44.   abilities.Ask.map! : (a ->{g1} b)
                             -> '{g2, Ask b} r
                             ->{g1, g2, Ask a} r
  45.   abilities.Ask.map!.doc : Doc
  46.   abilities.Ask.map!.example : Text
  47.   abilities.Ask.map!.test : [Result]
  48.   abilities.Ask.provide : a -> '{g, Ask a} r ->{g} r
  49.   abilities.Ask.provide.doc : Doc
  50.   abilities.Ask.provide.handler : a
                                        -> Request {Ask a} r
                                        -> r
  51.   abilities.Ask.provide' : '{g} a -> '{g, Ask a} r ->{g} r
  52.   abilities.Ask.provide'.doc : Doc
  53.   abilities.Ask.provide'.handler : '{g} a
                                         -> Request {Ask a} r
                                         ->{g} r
  54.   abilities.Ask.provide'.tests : [Result]
  55.   abilities.Ask.tests.ex1 : [Result]
  56.   abilities.Ask.toStore : '{g, Ask a} r ->{g, Store a} r
  57.   abilities.Ask.toStore.doc : Doc
  58.   abilities.Ask.toStore.handler : Request {Ask a} r
                                        ->{Store a} r
  59.   abilities.Ask.toStore.tests : [Result]
  60.   ability abilities.Clock
  61.   abilities.Clock.doc : Doc
  62.   abilities.Clock.elapsed : {Clock} Duration
  63.   abilities.Clock.now : {Clock} Instant
  64.   abilities.Clock.runClock : (a ->{g, Clock} b)
                                   -> a
                                   ->{g, IO, Exception} b
  65.   abilities.Clock.runClock.doc : Doc
  66.   structural ability abilities.Each
  67.   abilities.Each.allowThrow : '{Throw e, Stream a} ()
                                    ->{Each, Throw e} a
  68.   abilities.Each.allowThrow.doc : Doc
  69.   abilities.Each.append : '{g, Each} a
                                -> '{g, Each} a
                                ->{g, Each} a
  70.   abilities.Each.append.doc : Doc
  71.   abilities.Each.count : '{g, Each} a ->{g} Nat
  72.   abilities.Each.count.doc : Doc
  73.   abilities.Each.count.tests : [Result]
  74.   abilities.Each.doc : Doc
  75.   abilities.Each.each : [a] ->{Each} a
  76.   abilities.Each.each.doc : Doc
  77.   abilities.Each.eachCapture : Pattern t -> t ->{Each} t
  78.   abilities.Each.eachCapture.doc : Doc
  79.   abilities.Each.eachChar : Text ->{Each} Char
  80.   abilities.Each.eachChar.doc : Doc
  81.   abilities.Each.fail : '{Each} a
  82.   abilities.Each.fail.doc : Doc
  83.   abilities.Each.filter : (a ->{e} Boolean)
                                -> a
                                ->{e, Each} a
  84.   abilities.Each.filter.doc : Doc
  85.   abilities.Each.first : '{g, Each} a ->{g, Abort} a
  86.   abilities.Each.first.doc : Doc
  87.   abilities.Each.fromAbort : '{g, Abort} a ->{g, Each} a
  88.   abilities.Each.fromAbort.doc : Doc
  89.   abilities.Each.fromException : '{g, Exception} a
                                       ->{g, Each} a
  90.   abilities.Each.fromException.doc : Doc
  91.   abilities.Each.fromThrow : '{g, Throw e} a ->{g, Each} a
  92.   abilities.Each.fromThrow.doc : Doc
  93.   abilities.Each.guard : Boolean ->{Each} ()
  94.   abilities.Each.guard.doc : Doc
  95.   abilities.Each.ifThenElse : '{g, Each} a
                                    -> (a ->{g, Each} b)
                                    -> '{g, Each} b
                                    ->{g, Each} b
  96.   abilities.Each.ifThenElse.doc : Doc
  97.   abilities.Each.ifThenElse.examples.jimsAncestors : [Text]
  98.   abilities.Each.ifThenElse.examples.notJimsAncestors : [Text]
  99.   abilities.Each.ifThenElse.examples.notJimsAncestors' : [Text]
  100.  abilities.Each.interleave : '{g, Each} a
                                    -> '{g, Each} a
                                    ->{g, Each} a
  101.  abilities.Each.interleave.doc : Doc
  102.  abilities.Each.interleaveMap : (a ->{g, Each} b)
                                       -> '{g, Each} a
                                       ->{g, Each} b
  103.  abilities.Each.interleaveMap.doc : Doc
  104.  abilities.Each.lazily : '{Stream a} () ->{Each} a
  105.  abilities.Each.lazily.doc : Doc
  106.  abilities.Each.left : Either a b ->{Each} a
  107.  abilities.Each.left.doc : Doc
  108.  abilities.Each.limit : Nat -> '{g, Each} a ->{g, Each} a
  109.  abilities.Each.limit.doc : Doc
  110.  abilities.Each.negate : '{g, Each} a ->{g, Each} ()
  111.  abilities.Each.negate.doc : Doc
  112.  abilities.Each.observe : '{g, Each} a ->{g} Optional a
  113.  abilities.Each.observe.doc : Doc
  114.  abilities.Each.once : '{g, Each} a ->{g, Each} a
  115.  abilities.Each.once.doc : Doc
  116.  abilities.Each.optionally : Optional a ->{Each} a
  117.  abilities.Each.optionally.doc : Doc
  118.  abilities.Each.range : Nat -> Nat ->{Each} Nat
  119.  abilities.Each.range.doc : Doc
  120.  abilities.Each.rangeClosed : Nat -> Nat ->{Each} Nat
  121.  abilities.Each.rangeClosed.doc : Doc
  122.  abilities.Each.repeat : Nat ->{Each} ()
  123.  abilities.Each.repeat.doc : Doc
  124.  abilities.Each.repeatForever : '{Each} ()
  125.  abilities.Each.repeatForever.doc : Doc
  126.  abilities.Each.right : Either a b ->{Each} b
  127.  abilities.Each.right.doc : Doc
  128.  abilities.Each.run : '{g, Each} a ->{g} ()
  129.  abilities.Each.run.doc : Doc
  130.  abilities.Each.split : '{g, Each} a
                               ->{g} Optional (a, '{g, Each} a)
  131.  abilities.Each.split.doc : Doc
  132.  abilities.Each.toArray : '{g, Each} a
                                 ->{g, Exception} data.Array a
  133.  abilities.Each.toArray.doc : Doc
  134.  abilities.Each.toList : '{g, Each} a ->{g} [a]
  135.  abilities.Each.toList.doc : Doc
  136.  abilities.Each.toOptional : '{g, Each} a
                                    ->{g} Optional a
  137.  abilities.Each.toOptional.doc : Doc
  138.  abilities.Each.toStream : '{g, Each} a
                                  -> '{g, Stream a} ()
  139.  abilities.Each.toStream.doc : Doc
  140.  abilities.Each.toStream! : '{g, Each} a
                                   ->{g, Stream a} ()
  141.  abilities.Each.toStream!.doc : Doc
  142.  structural ability abilities.Exception
  143.  abilities.Exception.abortOnException : '{g, Exception} a
                                               ->{g, Abort} a
  144.  abilities.Exception.abortOnException.doc : Doc
  145.  abilities.Exception.bracket : '{g, Exception} r
                                      -> (r ->{g, Exception} ())
                                      -> (r ->{g, Exception} a)
                                      ->{g, Exception} a
  146.  abilities.Exception.bracket.doc : Doc
  147.  abilities.Exception.catch : '{g, Exception} a
                                    ->{g} Either Failure a
  148.  abilities.Exception.catch.doc : Doc
  149.  abilities.Exception.catchMany : [Type]
                                        -> '{g, Exception} a
                                        ->{g, Exception} Either
                                          Failure a
  150.  abilities.Exception.catchMany.doc : Doc
  151.  abilities.Exception.catchOnly : Type
                                        -> '{g, Exception} a
                                        ->{g, Exception} Either
                                          Failure a
  152.  abilities.Exception.catchOnly.doc : Doc
  153.  abilities.Exception.doc : Doc
  154.  abilities.Exception.doc.div : Nat
                                      -> Nat
                                      ->{Exception} Nat
  155.  abilities.Exception.failOnError : Text
                                          -> Either e a
                                          ->{Exception} a
  156.  abilities.Exception.failOnError.doc : Doc
  157.  abilities.Exception.finally : '{g, Exception} ()
                                      -> '{g, Exception} a
                                      ->{g, Exception} a
  158.  abilities.Exception.finally.doc : Doc
  159.  type abilities.Exception.Generic
  160.  abilities.Exception.Generic.doc : Doc
  161.  abilities.Exception.Generic.failure : Text
                                              -> a
                                              -> Failure
  162.  abilities.Exception.Generic.failure.doc : Doc
  163.  abilities.Exception.hush : '{g, Exception} t
                                   ->{g} Optional t
  164.  abilities.Exception.hush.doc : Doc
  165.  abilities.Exception.onException : (Failure ->{e} ())
                                          -> '{g, Exception} a
                                          ->{e, g, Exception} a
  166.  abilities.Exception.onException.doc : Doc
  167.  abilities.Exception.orElse : '{f} a
                                     -> '{g, Exception} a
                                     ->{f, g} a
  168.  abilities.Exception.orElse.doc : Doc
  169.  abilities.Exception.raise : Failure ->{Exception} x
  170.  abilities.Exception.raise.doc : Doc
  171.  abilities.Exception.raiseFailure : Type
                                           -> Text
                                           -> a
                                           ->{Exception} x
  172.  abilities.Exception.raiseFailure.doc : Doc
  173.  abilities.Exception.raiseGeneric : Text
                                           -> a
                                           ->{Exception} b
  174.  abilities.Exception.raiseGeneric.doc : Doc
  175.  abilities.Exception.reraise : Either Failure a
                                      ->{Exception} a
  176.  abilities.Exception.reraise.doc : Doc
  177.  abilities.Exception.unsafeRun! : '{g, Exception} a
                                         ->{g} a
  178.  abilities.Exception.unsafeRun!.doc : Doc
  179.  abilities.force : '{e} a ->{e} a
  180.  abilities.force.doc : Doc
  181.  abilities.forever : '{e} a ->{e} b
  182.  abilities.forever.doc : Doc
  183.  abilities.forever' : '{g} a -> '{g} b
  184.  abilities.forever'.doc : Doc
  185.  ability abilities.Label
  186.  abilities.Label.doc : Doc
  187.  abilities.Label.formatLabels : [(Text, Map Text Text)]
                                       -> Text
  188.  abilities.Label.formatLabels.doc : Doc
  189.  abilities.Label.getLabels : '{g, Label} a
                                    ->{g} [(Text, Map Text Text)]
  190.  abilities.Label.getLabels.doc : Doc
  191.  abilities.Label.label : Text -> a ->{Label} ()
  192.  abilities.Label.label.doc : Doc
  193.  abilities.Label.labeled : Text -> '{g} a ->{g, Label} a
  194.  abilities.Label.labeled.doc : Doc
  195.  abilities.Label.popScope : {Label} ()
  196.  abilities.Label.pushScope : Text ->{Label} ()
  197.  abilities.Label.run : '{g, Label} r
                              ->{g} ([(Text, Map Text Text)], r)
  198.  abilities.Label.run.doc : Doc
  199.  abilities.Label.runToText : '{g, Label} a
                                    ->{g} (Text, a)
  200.  abilities.Label.runToText.doc : Doc
  201.  abilities.Label.toText : '{g, Label} a ->{g} Text
  202.  abilities.Label.toText.doc : Doc
  203.  ability abilities.Random
  204.  abilities.Random.boolean : '{Random} Boolean
  205.  abilities.Random.boolean.doc : Doc
  206.  abilities.Random.bytes : Nat ->{Random} Bytes
  207.  abilities.Random.bytes.base32Hex : '{Random} Bytes
  208.  abilities.Random.bytes.base32Hex.doc : Doc
  209.  abilities.Random.bytes.doc : Doc
  210.  abilities.Random.char.ascii.control : '{Random} Char
  211.  abilities.Random.char.ascii.control.doc : Doc
  212.  abilities.Random.char.ascii.control.tests : [Result]
  213.  abilities.Random.char.ascii.lower : '{Random} Char
  214.  abilities.Random.char.ascii.lower.doc : Doc
  215.  abilities.Random.char.ascii.lower.tests : [Result]
  216.  abilities.Random.char.ascii.printable : '{Random} Char
  217.  abilities.Random.char.ascii.printable.doc : Doc
  218.  abilities.Random.char.ascii.printable.tests : [Result]
  219.  abilities.Random.char.ascii.upper : '{Random} Char
  220.  abilities.Random.char.ascii.upper.doc : Doc
  221.  abilities.Random.char.ascii.upper.tests : [Result]
  222.  abilities.Random.char.base32Hex : '{Random} Char
  223.  abilities.Random.char.base32Hex.doc : Doc
  224.  abilities.Random.char.digit : '{Random} Char
  225.  abilities.Random.char.digit.doc : Doc
  226.  abilities.Random.char.hex : '{Random} Char
  227.  abilities.Random.char.hex.doc : Doc
  228.  abilities.Random.char.interval : Char
                                         -> Char
                                         ->{Random} Char
  229.  abilities.Random.char.interval.doc : Doc
  230.  abilities.Random.char.unicode : '{Random} Char
  231.  abilities.Random.char.unicode.doc : Doc
  232.  abilities.Random.doc : Doc
  233.  abilities.Random.either : '{Random} r
                                  -> '{Random} r
                                  ->{Random} r
  234.  abilities.Random.either.doc : Doc
  235.  abilities.Random.exponential : Float ->{Random} Float
  236.  abilities.Random.exponential.doc : Doc
  237.  abilities.Random.float : '{Random} Float
  238.  abilities.Random.float.doc : Doc
  239.  abilities.Random.functionOf : '{g, Random} b
                                      ->{Random} (∀ a. a ->{g} b)
  240.  abilities.Random.functionOf.doc : Doc
  241.  abilities.Random.impl.bytesFromNats : '{g, Random} Nat
                                              -> Nat
                                              ->{g, Random} Bytes
  242.  abilities.Random.impl.bytesFromNats.doc : Doc
  243.  abilities.Random.int : '{Random} Int
  244.  abilities.Random.int.doc : Doc
  245.  abilities.Random.intIn : Int -> Int ->{Random} Int
  246.  abilities.Random.intIn.doc : Doc
  247.  abilities.Random.intIn.tests.ex1 : [Result]
  248.  abilities.Random.intIn.tests.fairness : [Result]
  249.  abilities.Random.lcg : Nat -> '{g, Random} t ->{g} t
  250.  abilities.Random.lcg.doc : Doc
  251.  abilities.Random.lcg.handler : Nat
                                       -> Request {Random} a
                                       -> a
  252.  abilities.Random.lcg.handler.doc : Doc
  253.  abilities.Random.listOf : '{g, Random} a
                                  -> '{g, Random} Nat
                                  ->{g, Random} [a]
  254.  abilities.Random.listOf.doc : Doc
  255.  abilities.Random.mapOf : '{g1, Random} k
                                 -> '{g2, Random} v
                                 -> '{g1, g2, Random} Nat
                                 ->{g1, g2, Random} Map k v
  256.  abilities.Random.mapOf.doc : Doc
  257.  abilities.Random.nat : '{Random} Nat
  258.  abilities.Random.nat.doc : Doc
  259.  abilities.Random.nat.natsWithSum : Nat
                                           -> Nat
                                           ->{Random} [Nat]
  260.  abilities.Random.nat.natsWithSum.doc : Doc
  261.  abilities.Random.nat.natsWithSum.tests : [Result]
  262.  abilities.Random.nat! : {Random} Nat
  263.  abilities.Random.natIn : Nat -> Nat ->{Random} Nat
  264.  abilities.Random.natIn.doc : Doc
  265.  abilities.Random.natIn.tests.ex1 : [Result]
  266.  abilities.Random.natIn.tests.fairness : [Result]
  267.  abilities.Random.oneOf : [a] ->{Random} a
  268.  abilities.Random.oneOf.doc : Doc
  269.  abilities.Random.oneOfNonempty : List.Nonempty a
                                         ->{Random} a
  270.  abilities.Random.oneOfNonempty.doc : Doc
  271.  abilities.Random.optional : '{g, Random} a
                                    ->{g} '{g, Random} Optional
                                      a
  272.  abilities.Random.optional.doc : Doc
  273.  abilities.Random.optional! : '{g, Random} a
                                     ->{g, Random} Optional a
  274.  abilities.Random.optional!.doc : Doc
  275.  structural type abilities.Random.RNG
  276.  abilities.Random.RNG.doc : Doc
  277.  abilities.Random.RNG.fromLcg : Nat -> RNG
  278.  abilities.Random.RNG.fromLcg.doc : Doc
  279.  abilities.Random.RNG.fromSplitmix : Nat -> RNG
  280.  abilities.Random.RNG.fromSplitmix.doc : Doc
  281.  abilities.Random.RNG.RNG : (∀ g a.
                                     '{g, Random} a ->{g} a)
                                   -> RNG
  282.  abilities.Random.RNG.run : RNG -> '{g, Random} a ->{g} a
  283.  abilities.Random.RNG.run.doc : Doc
  284.  abilities.Random.RNG.split : RNG -> (RNG, RNG)
  285.  abilities.Random.RNG.split.doc : Doc
  286.  abilities.Random.run : '{g, Random} a ->{g, IO} a
  287.  abilities.Random.run.doc : Doc
  288.  abilities.Random.shuffle : [a] ->{Random} [a]
  289.  abilities.Random.shuffle.doc : Doc
  290.  abilities.Random.shuffle.tests : [Result]
  291.  abilities.Random.split : '{Random} ('{g, Random} t
                                 ->{g} t)
  292.  abilities.Random.split.doc : Doc
  293.  abilities.Random.split! : {Random} (∀ g a.
                                    '{g, Random} a ->{g} a)
  294.  abilities.Random.splitmix : Nat
                                    -> '{g, Random} t
                                    ->{g} t
  295.  abilities.Random.splitmix.doc : Doc
  296.  abilities.Random.splitmix.handler : Nat
                                            -> Nat
                                            -> Request
                                              {Random} a2
                                            -> a2
  297.  abilities.Random.splitmix.impl.goldenGamma : Nat
  298.  abilities.Random.splitmix.impl.mix64 : Nat -> Nat
  299.  abilities.Random.splitmix.impl.mix64variant13 : Nat
                                                        -> Nat
  300.  abilities.Random.splitmix.impl.mixGamma : Nat -> Nat
  301.  abilities.Random.splitmix.impl.shiftXor : Nat
                                                  -> Nat
                                                  -> Nat
  302.  abilities.Random.splitmix.impl.shiftXorMultiply : Nat
                                                          -> Nat
                                                          -> Nat
                                                          -> Nat
  303.  abilities.Random.splits : (a ->{g1} Nat)
                                  -> (Nat -> a ->{g2} (a, a))
                                  -> Nat
                                  -> a
                                  -> '{g1, g2, Random, Stream a} ()
  304.  abilities.Random.splits.bytes : Nat
                                        -> Bytes
                                        -> '{Random,
                                        Stream Bytes} ()
  305.  abilities.Random.splits.bytes.doc : Doc
  306.  abilities.Random.splits.bytes.tests : [Result]
  307.  abilities.Random.splits.doc : Doc
  308.  abilities.Random.splits.list : Nat
                                       -> [a]
                                       -> '{Random, Stream [a]} ()
  309.  abilities.Random.splits.list.doc : Doc
  310.  abilities.Random.splits.list.tests : [Result]
  311.  abilities.Random.splits.text : Nat
                                       -> Text
                                       -> '{Random, Stream Text} ()
  312.  abilities.Random.splits.text.doc : Doc
  313.  abilities.Random.text.base32Hex : '{Random} Text
  314.  abilities.Random.text.base32Hex.doc : Doc
  315.  abilities.Random.text.ofChars : '{Random} Char
                                        -> Nat
                                        ->{Random} Text
  316.  abilities.Random.text.ofChars.doc : Doc
  317.  abilities.Random.weighted : [(Nat, '{g, Random} a)]
                                    ->{g} '{g, Random} a
  318.  abilities.Random.weighted.doc : Doc
  319.  abilities.Random.weighted.fromStream : '{g,
                                               Stream
                                                 ( Nat,
                                                   '{g, Random} a)} r
                                               ->{g} '{g,
                                               Random} a
  320.  abilities.Random.weighted.fromStream.doc : Doc
  321.  abilities.repeat : Nat -> '{e} () ->{e} ()
  322.  abilities.repeat.doc : Doc
  323.  builtin type abilities.Request
  324.  abilities.Request.doc : Doc
  325.  structural ability abilities.Store a
  326.  abilities.Store.accumulateLeft : (a ->{g, Store s} b)
                                         -> s
                                         -> [a]
                                         ->{g} [b]
  327.  abilities.Store.accumulateLeft.doc : Doc
  328.  abilities.Store.accumulateRight : (a ->{g, Store s} b)
                                          -> s
                                          -> [a]
                                          ->{g} [b]
  329.  abilities.Store.accumulateRight.doc : Doc
  330.  abilities.Store.doc : Doc
  331.  abilities.Store.examples.stack.add : '{Abort,
                                             Store [Int]} ()
  332.  abilities.Store.examples.stack.binop : (a
                                               ->{e} a
                                               ->{g} a)
                                               ->{e,
                                               g,
                                               Abort,
                                               Store [a]} ()
  333.  abilities.Store.examples.stack.pop : '{Abort, Store [a]} a
  334.  abilities.Store.examples.stack.push : a ->{Store [a]} ()
  335.  abilities.Store.examples.stack.runStack : '{Abort,
                                                  Store [Int]} a
                                                  -> Optional a
  336.  abilities.Store.get : {Store a} a
  337.  abilities.Store.get.doc : Doc
  338.  abilities.Store.get.examples.ex1 : Nat
  339.  abilities.Store.getOrUpdate : k
                                      -> '{Store (Map k v)} v
                                      ->{Store (Map k v)} v
  340.  abilities.Store.getOrUpdate.doc : Doc
  341.  abilities.Store.getOrUpdate.examples.fibonacci : Nat
                                                         ->{Store
                                                           (Map
                                                             Nat
                                                             Natural)} Natural
  342.  abilities.Store.local : (a ->{g} b)
                                -> (a ->{g} b ->{g} a)
                                -> '{g, Store b} v
                                -> '{g, Store a} v
  343.  abilities.Store.local.deprecated : a
                                           -> '{g, Store a} v
                                           ->{g, Store a} v
  344.  abilities.Store.local.deprecated.examples.ex1 : ( Nat,
                                                          Nat,
                                                          Nat)
  345.  abilities.Store.local.deprecated.test : [Result]
  346.  abilities.Store.local.doc : Doc
  347.  abilities.Store.local! : (a ->{g} b)
                                 -> (a ->{g} b ->{g} a)
                                 -> '{g, Store b} v
                                 ->{g, Store a} v
  348.  abilities.Store.local!.doc : Doc
  349.  abilities.Store.local!.examples.ex1 : (Text, Nat)
  350.  abilities.Store.local!.tests.ex1 : [Result]
  351.  abilities.Store.modify : (a ->{g} a) ->{g, Store a} ()
  352.  abilities.Store.modify.doc : Doc
  353.  abilities.Store.modify.examples.increment : Nat
  354.  abilities.Store.modify.test : [Result]
  355.  abilities.Store.put : a ->{Store a} ()
  356.  abilities.Store.put.doc : Doc
  357.  abilities.Store.put.examples.ex1 : Nat
  358.  abilities.Store.unfold : s
                                 -> '{g, Abort, Store s} r
                                 -> '{g} [r]
  359.  abilities.Store.unfold.doc : Doc
  360.  abilities.Store.unfold! : s
                                  -> '{g, Abort, Store s} r
                                  ->{g} [r]
  361.  abilities.Store.unfold!.doc : Doc
  362.  abilities.Store.unfold!.tests.ex1 : [Result]
  363.  abilities.Store.withInitialValue : a
                                           -> '{g, Store a} v
                                           ->{g} v
  364.  abilities.Store.withInitialValue.doc : Doc
  365.  abilities.Store.withInitialValue.handler : a
                                                   -> Request
                                                     (Store a) v
                                                   -> v
  366.  abilities.Store.withInitialValue.laws.law1 : v
                                                     ->{Store v} Test
  367.  abilities.Store.withInitialValue.tests.law1 : [Result]
  368.  structural ability abilities.Throw e
  369.  abilities.Throw.catchWith : (e ->{g1} a)
                                    -> '{g2, Throw e} a
                                    ->{g1, g2} a
  370.  abilities.Throw.catchWith.doc : Doc
  371.  abilities.Throw.doc : Doc
  372.  abilities.Throw.tests.ex1 : [Result]
  373.  abilities.Throw.tests.ex2 : [Result]
  374.  abilities.Throw.tests.ex3 : [Result]
  375.  abilities.Throw.throw : e ->{Throw e} a
  376.  abilities.Throw.toBug : '{g, Throw e} o ->{g} o
  377.  abilities.Throw.toBug.doc : Doc
  378.  abilities.Throw.toEither : '{g, Throw e} a
                                   ->{g} Either e a
  379.  abilities.Throw.toEither.doc : Doc
  380.  abilities.Throw.toEither.handler : Request {Throw e} a
                                           -> Either e a
  381.  abilities.Throw.toException : (e ->{g1} Failure)
                                      -> '{g2, Throw e} a
                                      ->{g1, g2, Exception} a
  382.  abilities.Throw.toException.doc : Doc
  383.  abilities.Throw.toOptional : '{g, Throw e} a
                                     ->{g} Optional a
  384.  abilities.Throw.toOptional.doc : Doc
  385.  abilities.Throw.unwrap : '{g, Throw a} a -> '{g} a
  386.  abilities.Throw.unwrap.doc : Doc
  387.  abilities.Throw.unwrap! : '{g, Throw a} a ->{g} a
  388.  abilities.Throw.unwrap!.doc : Doc
  389.  abilities.Throw.unwrap!.docs.sumUntil : Nat
                                                -> [Nat]
                                                -> Nat
  390.  ability abilities.Wait
  391.  abilities.Wait.doc : Doc
  392.  abilities.Wait.runWait : (a ->{g, Wait} b)
                                 -> a
                                 ->{g, IO, Exception} b
  393.  abilities.Wait.runWait.doc : Doc
  394.  abilities.Wait.wait : Duration ->{Wait} ()
  395.  builtin type Any
  396.  Any.Any : a -> Any
  397.  Any.doc : Doc
  398.  Any.unsafeExtract : Any -> a
  399.  Any.unsafeExtract.doc : Doc
  400.  builtin type Boolean
  401.  Boolean.!= : Boolean -> Boolean -> Boolean
  402.  Boolean.< : Boolean -> Boolean -> Boolean
  403.  Boolean.<= : Boolean -> Boolean -> Boolean
  404.  Boolean.== : Boolean -> Boolean -> Boolean
  405.  Boolean.> : Boolean -> Boolean -> Boolean
  406.  Boolean.>= : Boolean -> Boolean -> Boolean
  407.  Boolean.and : Boolean -> Boolean -> Boolean
  408.  Boolean.and.doc : Doc
  409.  Boolean.doc : Doc
  410.  Boolean.docs.binaryTruthTable : Text
                                        -> (Boolean
                                        ->{g} Boolean
                                        ->{g1} Boolean)
                                        ->{g, g1} Doc
  411.  Boolean.docs.binaryTruthTable.doc : Doc
  412.  Boolean.docs.unaryTruthTable : Text
                                       -> (Boolean -> Boolean)
                                       -> Doc
  413.  Boolean.docs.unaryTruthTable.doc : Doc
  414.  Boolean.eq : Boolean -> Boolean -> Boolean
  415.  Boolean.eq.doc : Doc
  416.  Boolean.given : Boolean -> Boolean -> Boolean
  417.  Boolean.given.doc : Doc
  418.  Boolean.given.test : [Result]
  419.  Boolean.gt : Boolean -> Boolean -> Boolean
  420.  Boolean.gt.doc : Doc
  421.  Boolean.gteq : Boolean -> Boolean -> Boolean
  422.  Boolean.iff : Boolean -> Boolean -> Boolean
  423.  Boolean.iff.doc : Doc
  424.  Boolean.implies : Boolean -> Boolean -> Boolean
  425.  Boolean.implies.doc : Doc
  426.  Boolean.implies.test : [Result]
  427.  Boolean.lt : Boolean -> Boolean -> Boolean
  428.  Boolean.lt.doc : Doc
  429.  Boolean.lteq : Boolean -> Boolean -> Boolean
  430.  Boolean.nand : Boolean -> Boolean -> Boolean
  431.  Boolean.nand.doc : Doc
  432.  Boolean.neq : Boolean -> Boolean -> Boolean
  433.  Boolean.nor : Boolean -> Boolean -> Boolean
  434.  Boolean.nor.doc : Doc
  435.  Boolean.not : Boolean -> Boolean
  436.  Boolean.not.doc : Doc
  437.  Boolean.or : Boolean -> Boolean -> Boolean
  438.  Boolean.or.doc : Doc
  439.  Boolean.toNat : Boolean -> Nat
  440.  Boolean.toNat.doc : Doc
  441.  Boolean.toText : Boolean -> Text
  442.  Boolean.toText.doc : Doc
  443.  Boolean.until : (a ->{e} Boolean) -> '{e} a ->{e} a
  444.  Boolean.until.doc : Doc
  445.  Boolean.until.test : [Result]
  446.  Boolean.when : Boolean -> '{e} () ->{e} ()
  447.  Boolean.when.doc : Doc
  448.  Boolean.while : (a ->{e} Boolean) -> '{e} a ->{e} a
  449.  Boolean.while.doc : Doc
  450.  Boolean.while.test : [Result]
  451.  Boolean.xor : Boolean -> Boolean -> Boolean
  452.  Boolean.xor.doc : Doc
  453.  Boolean.xor.test : [Result]
  454.  bug : a -> b
  455.  bug.doc : Doc
  456.  bug.impossible : Request Exception a -> a
  457.  bug.impossible.doc : Doc
  458.  builtin type Bytes
  459.  Bytes.++ : Bytes -> Bytes -> Bytes
  460.  Bytes.++.doc : Doc
  461.  Bytes.== : Bytes -> Bytes -> Boolean
  462.  Bytes.at : Nat -> Bytes -> Optional Nat
  463.  Bytes.at.doc : Doc
  464.  Bytes.at! : Nat -> Bytes ->{Abort} Nat
  465.  Bytes.at!.doc : Doc
  466.  Bytes.base32Hex : Bytes -> Text
  467.  Bytes.base32Hex.b32h : Nat -> Char
  468.  Bytes.base32Hex.b32h.doc : Doc
  469.  Bytes.base32Hex.doc : Doc
  470.  Bytes.base32Hex.encodeChunk : Nat -> Nat -> Text
  471.  Bytes.base32Hex.encodeChunk.doc : Doc
  472.  Bytes.base32Hex.grab : Bytes -> Optional Hex32Piece
  473.  Bytes.base32Hex.grab.doc : Doc
  474.  Bytes.base32Hex.grab1 : Bytes -> Optional Hex32Piece
  475.  Bytes.base32Hex.grab1.doc : Doc
  476.  structural type Bytes.base32Hex.Hex32Piece
  477.  Bytes.base32Hex.Hex32Piece.Double : Nat
                                            -> Nat
                                            -> Nat
                                            -> Bytes
                                            -> Hex32Piece
  478.  Bytes.base32Hex.Hex32Piece.Single : Nat
                                            -> Nat
                                            -> Bytes
                                            -> Hex32Piece
  479.  Bytes.constantTimeEqual : Bytes -> Bytes -> Boolean
  480.  Bytes.constantTimeEqual.doc : Doc
  481.  Bytes.constantTimeEqual.tests : [Result]
  482.  Bytes.decodeNat16be : Bytes -> Optional (Nat, Bytes)
  483.  Bytes.decodeNat16be.doc : Doc
  484.  Bytes.decodeNat16le : Bytes -> Optional (Nat, Bytes)
  485.  Bytes.decodeNat16le.doc : Doc
  486.  Bytes.decodeNat16sbe : Nat -> Bytes -> ([Nat], Bytes)
  487.  Bytes.decodeNat16sbe.doc : Doc
  488.  Bytes.decodeNat32be : Bytes -> Optional (Nat, Bytes)
  489.  Bytes.decodeNat32be.doc : Doc
  490.  Bytes.decodeNat32le : Bytes -> Optional (Nat, Bytes)
  491.  Bytes.decodeNat32le.doc : Doc
  492.  Bytes.decodeNat32sbe : Nat -> Bytes -> ([Nat], Bytes)
  493.  Bytes.decodeNat32sbe.doc : Doc
  494.  Bytes.decodeNat64be : Bytes -> Optional (Nat, Bytes)
  495.  Bytes.decodeNat64be.doc : Doc
  496.  Bytes.decodeNat64le : Bytes -> Optional (Nat, Bytes)
  497.  Bytes.decodeNat64le.doc : Doc
  498.  Bytes.decodeNat64sbe : Nat -> Bytes -> ([Nat], Bytes)
  499.  Bytes.decodeNat64sbe.doc : Doc
  500.  Bytes.doc : Doc
  501.  Bytes.drop : Nat -> Bytes -> Bytes
  502.  Bytes.drop.doc : Doc
  503.  Bytes.empty : Bytes
  504.  Bytes.empty.doc : Doc
  505.  Bytes.encodeNat16be : Nat -> Bytes
  506.  Bytes.encodeNat16be.doc : Doc
  507.  Bytes.encodeNat16le : Nat -> Bytes
  508.  Bytes.encodeNat16le.doc : Doc
  509.  Bytes.encodeNat32be : Nat -> Bytes
  510.  Bytes.encodeNat32be.doc : Doc
  511.  Bytes.encodeNat32le : Nat -> Bytes
  512.  Bytes.encodeNat32le.doc : Doc
  513.  Bytes.encodeNat64be : Nat -> Bytes
  514.  Bytes.encodeNat64be.doc : Doc
  515.  Bytes.encodeNat64le : Nat -> Bytes
  516.  Bytes.encodeNat64le.doc : Doc
  517.  Bytes.flatten : Bytes -> Bytes
  518.  Bytes.flatten.doc : Doc
  519.  Bytes.fromBase16 : Bytes ->{Exception} Bytes
  520.  Bytes.fromBase16.doc : Doc
  521.  Bytes.fromBase16.impl : Bytes -> Either Text Bytes
  522.  Bytes.fromBase16.impl.doc : Doc
  523.  Bytes.fromBase32 : Bytes ->{Exception} Bytes
  524.  Bytes.fromBase32.doc : Doc
  525.  Bytes.fromBase32.impl : Bytes -> Either Text Bytes
  526.  Bytes.fromBase32.impl.doc : Doc
  527.  Bytes.fromBase32Hex : Bytes -> Either Text Bytes
  528.  Bytes.fromBase32Hex.alignment : Nat -> Nat
  529.  Bytes.fromBase32Hex.alignment.doc : Doc
  530.  Bytes.fromBase32Hex.doc : Doc
  531.  Bytes.fromBase32Hex.finalize : Nat -> Nat -> Bytes
  532.  Bytes.fromBase32Hex.finalize.doc : Doc
  533.  Bytes.fromBase32Hex.h32b : Nat -> Either Text Nat
  534.  Bytes.fromBase32Hex.h32b.doc : Doc
  535.  Bytes.fromBase32Hex.push : Nat
                                   -> Nat
                                   -> Nat
                                   -> Either Nat (Bytes, Nat)
  536.  Bytes.fromBase32Hex.push.doc : Doc
  537.  Bytes.fromBase32Hex.tests.inverse : [Result]
  538.  Bytes.fromBase64 : Bytes ->{Exception} Bytes
  539.  Bytes.fromBase64.doc : Doc
  540.  Bytes.fromBase64.impl : Bytes -> Either Text Bytes
  541.  Bytes.fromBase64.impl.doc : Doc
  542.  Bytes.fromBase64UrlUnpadded : Bytes -> Either Text Bytes
  543.  Bytes.fromBase64UrlUnpadded.doc : Doc
  544.  Bytes.fromHex : Text ->{Exception} Bytes
  545.  Bytes.fromHex.doc : Doc
  546.  Bytes.fromHex.impl : Text -> Either Text Bytes
  547.  Bytes.fromList : [Nat] ->{Exception} Bytes
  548.  Bytes.fromList.doc : Doc
  549.  Bytes.fromList.impl : [Nat] -> Bytes
  550.  Bytes.gzip.compress : Bytes -> Bytes
  551.  Bytes.gzip.compress.doc : Doc
  552.  Bytes.gzip.decompress : Bytes ->{Exception} Bytes
  553.  Bytes.gzip.decompress.doc : Doc
  554.  Bytes.gzip.decompress.impl : Bytes -> Either Text Bytes
  555.  Bytes.gzip.decompress.impl.doc : Doc
  556.  Bytes.indexOf : Bytes -> Bytes -> Optional Nat
  557.  Bytes.indexOf.doc : Doc
  558.  Bytes.indexOf.tests.infix : [Result]
  559.  Bytes.isEmpty : Bytes -> Boolean
  560.  Bytes.isEmpty.doc : Doc
  561.  Bytes.shiftLeft : Nat -> Bytes -> Bytes
  562.  Bytes.shiftLeft.doc : Doc
  563.  Bytes.shiftRight : Nat -> Bytes -> Bytes
  564.  Bytes.shiftRight.doc : Doc
  565.  Bytes.size : Bytes -> Nat
  566.  Bytes.size.doc : Doc
  567.  Bytes.splitAt : Nat -> Bytes -> (Bytes, Bytes)
  568.  Bytes.splitAt.doc : Doc
  569.  Bytes.splitAt.tests : [Result]
  570.  Bytes.take : Nat -> Bytes -> Bytes
  571.  Bytes.take.doc : Doc
  572.  Bytes.toBase16 : Bytes -> Bytes
  573.  Bytes.toBase16.doc : Doc
  574.  Bytes.toBase16.text : Bytes -> Text
  575.  Bytes.toBase16.text.deprecated : Bytes -> Text
  576.  Bytes.toBase16.text.doc : Doc
  577.  Bytes.toBase32 : Bytes -> Bytes
  578.  Bytes.toBase32.doc : Doc
  579.  Bytes.toBase32Hex : Bytes -> Bytes
  580.  Bytes.toBase32Hex.doc : Doc
  581.  Bytes.toBase32Hex.tests.inverse : [Result]
  582.  Bytes.toBase32Hex.text : Bytes -> Text
  583.  Bytes.toBase32Hex.text.doc : Doc
  584.  Bytes.toBase64 : Bytes -> Bytes
  585.  Bytes.toBase64.doc : Doc
  586.  Bytes.toBase64UrlUnpadded : Bytes -> Bytes
  587.  Bytes.toBase64UrlUnpadded.doc : Doc
  588.  Bytes.toHex : Bytes -> Text
  589.  Bytes.toHex.deprecated : Bytes -> Text
  590.  Bytes.toHex.doc : Doc
  591.  Bytes.toList : Bytes -> [Nat]
  592.  Bytes.toList.doc : Doc
  593.  Bytes.toNat64sbe : Bytes -> ([Nat], Bytes)
  594.  Bytes.toNat64sbe.doc : Doc
  595.  Bytes.truncateLeft : Nat -> Bytes -> Bytes
  596.  Bytes.truncateLeft.doc : Doc
  597.  Bytes.truncateRight : Nat -> Bytes -> Bytes
  598.  Bytes.truncateRight.doc : Doc
  599.  Bytes.zlib.compress : Bytes -> Bytes
  600.  Bytes.zlib.compress.doc : Doc
  601.  Bytes.zlib.decompress : Bytes ->{Exception} Bytes
  602.  Bytes.zlib.decompress.doc : Doc
  603.  Bytes.zlib.decompress.impl : Bytes -> Either Text Bytes
  604.  Bytes.zlib.decompress.impl.doc : Doc
  605.  CHANGELOG : [(LocalDate, Doc)]
  606.  builtin type Char
  607.  Char.!= : Char -> Char -> Boolean
  608.  Char.!=.doc : Doc
  609.  Char.< : Char -> Char -> Boolean
  610.  Char.<.doc : Doc
  611.  Char.<= : Char -> Char -> Boolean
  612.  Char.<=.doc : Doc
  613.  Char.== : Char -> Char -> Boolean
  614.  Char.==.doc : Doc
  615.  Char.> : Char -> Char -> Boolean
  616.  Char.>.doc : Doc
  617.  Char.>= : Char -> Char -> Boolean
  618.  Char.>=.doc : Doc
  619.  Char.ascii.fromBase36Digit : Nat -> Optional Char
  620.  Char.ascii.fromBase36Digit.doc : Doc
  621.  Char.ascii.isAlphaNum : Char -> Boolean
  622.  Char.ascii.isAlphaNum.doc : Doc
  623.  Char.ascii.isAscii : Char -> Boolean
  624.  Char.ascii.isAscii.doc : Doc
  625.  Char.ascii.isBlank : Char -> Boolean
  626.  Char.ascii.isBlank.doc : Doc
  627.  Char.ascii.isControl : Char -> Boolean
  628.  Char.ascii.isControl.doc : Doc
  629.  Char.ascii.isDigit : Char -> Boolean
  630.  Char.ascii.isDigit.doc : Doc
  631.  Char.ascii.isGraph : Char -> Boolean
  632.  Char.ascii.isGraph.doc : Doc
  633.  Char.ascii.isHexDigit : Char -> Boolean
  634.  Char.ascii.isHexDigit.doc : Doc
  635.  Char.ascii.isLetter : Char -> Boolean
  636.  Char.ascii.isLetter.doc : Doc
  637.  Char.ascii.isLower : Char -> Boolean
  638.  Char.ascii.isLower.doc : Doc
  639.  Char.ascii.isPrint : Char -> Boolean
  640.  Char.ascii.isPrint.doc : Doc
  641.  Char.ascii.isPunct : Char -> Boolean
  642.  Char.ascii.isPunct.doc : Doc
  643.  Char.ascii.isSpace : Char -> Boolean
  644.  Char.ascii.isSpace.doc : Doc
  645.  Char.ascii.isUpper : Char -> Boolean
  646.  Char.ascii.isUpper.doc : Doc
  647.  Char.ascii.lowerUpperDiff : Int
  648.  Char.ascii.lowerUpperDiff.doc : Doc
  649.  Char.ascii.README : Doc
  650.  Char.ascii.tests.propUpperLower : [Result]
  651.  Char.ascii.tests.propUpperLower.doc : Doc
  652.  Char.ascii.tests.toLower : [Result]
  653.  Char.ascii.tests.toUpper : [Result]
  654.  Char.ascii.toBase36Digit : Char -> Optional Nat
  655.  Char.ascii.toBase36Digit.doc : Doc
  656.  Char.ascii.toLower : Char -> Char
  657.  Char.ascii.toLower.doc : Doc
  658.  Char.ascii.toUpper : Char -> Char
  659.  Char.ascii.toUpper.doc : Doc
  660.  builtin type Char.Class
  661.  Char.Class.+ : Class -> Class -> Class
  662.  Char.Class.+.doc : Doc
  663.  Char.Class.- : Class -> Class -> Class
  664.  Char.Class.-.doc : Doc
  665.  Char.Class.alphanumeric : Class
  666.  Char.Class.alphanumeric.doc : Doc
  667.  Char.Class.and : Class -> Class -> Class
  668.  Char.Class.and.doc : Doc
  669.  Char.Class.any : Class
  670.  Char.Class.any.doc : Doc
  671.  Char.Class.anyOf : [Char] -> Class
  672.  Char.Class.anyOf.doc : Doc
  673.  Char.Class.ascii : Class
  674.  Char.Class.ascii.doc : Doc
  675.  Char.Class.control : Class
  676.  Char.Class.control.doc : Doc
  677.  Char.Class.digit : Class
  678.  Char.Class.digit.doc : Doc
  679.  Char.Class.doc : Doc
  680.  Char.Class.fromChar : Char -> Class
  681.  Char.Class.fromChar.doc : Doc
  682.  Char.Class.hexDigit : Class
  683.  Char.Class.hexDigit.doc : Doc
  684.  Char.Class.in : Text -> Class
  685.  Char.Class.in.doc : Doc
  686.  Char.Class.is : Class -> Char -> Boolean
  687.  Char.Class.is.doc : Doc
  688.  Char.Class.letter : Class
  689.  Char.Class.letter.doc : Doc
  690.  Char.Class.lower : Class
  691.  Char.Class.lower.doc : Doc
  692.  Char.Class.mark : Class
  693.  Char.Class.mark.doc : Doc
  694.  Char.Class.not : Class -> Class
  695.  Char.Class.not.doc : Doc
  696.  Char.Class.number : Class
  697.  Char.Class.number.doc : Doc
  698.  Char.Class.or : Class -> Class -> Class
  699.  Char.Class.or.doc : Doc
  700.  Char.Class.printable : Class
  701.  Char.Class.printable.doc : Doc
  702.  Char.Class.punctuation : Class
  703.  Char.Class.punctuation.doc : Doc
  704.  Char.Class.range : Char -> Char -> Class
  705.  Char.Class.range.doc : Doc
  706.  Char.Class.separator : Class
  707.  Char.Class.separator.doc : Doc
  708.  Char.Class.symbol : Class
  709.  Char.Class.symbol.doc : Doc
  710.  Char.Class.upper : Class
  711.  Char.Class.upper.doc : Doc
  712.  Char.Class.visible : Class
  713.  Char.Class.visible.doc : Doc
  714.  Char.Class.whitespace : Class
  715.  Char.Class.whitespace.doc : Doc
  716.  Char.Class.word : Class
  717.  Char.Class.word.doc : Doc
  718.  Char.doc : Doc
  719.  Char.eq : Char -> Char -> Boolean
  720.  Char.eq.doc : Doc
  721.  Char.fromNat : Nat -> Optional Char
  722.  Char.fromNat.doc : Doc
  723.  Char.fromNat.impl : Nat -> Char
  724.  Char.gt : Char -> Char -> Boolean
  725.  Char.gt.doc : Doc
  726.  Char.gteq : Char -> Char -> Boolean
  727.  Char.gteq.doc : Doc
  728.  Char.inRange : Char -> Char -> Char -> Boolean
  729.  Char.inRange.doc : Doc
  730.  Char.isWhitespace : Char -> Boolean
  731.  Char.isWhitespace.doc : Doc
  732.  Char.lt : Char -> Char -> Boolean
  733.  Char.lt.doc : Doc
  734.  Char.lteq : Char -> Char -> Boolean
  735.  Char.lteq.doc : Doc
  736.  Char.neq : Char -> Char -> Boolean
  737.  Char.neq.doc : Doc
  738.  Char.range : Char -> Char -> [Char]
  739.  Char.range.doc : Doc
  740.  Char.rangeClosed : Char -> Char -> [Char]
  741.  Char.rangeClosed.doc : Doc
  742.  Char.toLowercase : Char -> Char
  743.  Char.toLowercase.doc : Doc
  744.  Char.toNat : Char -> Nat
  745.  Char.toNat.doc : Doc
  746.  Char.toText : Char -> Text
  747.  Char.toText.doc : Doc
  748.  Char.toUppercase : Char -> Char
  749.  Char.toUppercase.doc : Doc
  750.  Char.toUtf8 : Char -> Bytes
  751.  Char.toUtf8.doc : Doc
  752.  type crypto.CryptoFailure
  753.  type crypto.Ed25519.PrivateKey
  754.  crypto.Ed25519.PrivateKey.doc : Doc
  755.  crypto.Ed25519.PrivateKey.PrivateKey : Bytes
                                               -> Ed25519.PrivateKey
  756.  type crypto.Ed25519.PublicKey
  757.  crypto.Ed25519.PublicKey.doc : Doc
  758.  crypto.Ed25519.PublicKey.PublicKey : Bytes
                                             -> Ed25519.PublicKey
  759.  crypto.Ed25519.PublicKey.toBytes : Ed25519.PublicKey
                                           -> Bytes
  760.  crypto.Ed25519.PublicKey.toBytes.doc : Doc
  761.  crypto.Ed25519.sign : Ed25519.PrivateKey
                              -> Ed25519.PublicKey
                              -> Bytes
                              ->{Exception} Ed25519.Signature
  762.  crypto.Ed25519.sign.doc : Doc
  763.  crypto.Ed25519.sign.impl : Bytes
                                   -> Bytes
                                   -> Bytes
                                   -> Either Failure Bytes
  764.  type crypto.Ed25519.Signature
  765.  crypto.Ed25519.Signature.doc : Doc
  766.  crypto.Ed25519.Signature.Signature : Bytes
                                             -> Ed25519.Signature
  767.  crypto.Ed25519.verify : Ed25519.PublicKey
                                -> Bytes
                                -> Ed25519.Signature
                                ->{Exception} Boolean
  768.  crypto.Ed25519.verify.doc : Doc
  769.  crypto.Ed25519.verify.impl : Bytes
                                     -> Bytes
                                     -> Bytes
                                     -> Either Failure Boolean
  770.  crypto.hash : HashAlgorithm -> a -> Bytes
  771.  crypto.hash.doc : Doc
  772.  builtin type crypto.HashAlgorithm
  773.  crypto.HashAlgorithm.Blake2b_256 : HashAlgorithm
  774.  crypto.HashAlgorithm.Blake2b_256.doc : Doc
  775.  crypto.HashAlgorithm.Blake2b_512 : HashAlgorithm
  776.  crypto.HashAlgorithm.Blake2b_512.doc : Doc
  777.  crypto.HashAlgorithm.Blake2s_256 : HashAlgorithm
  778.  crypto.HashAlgorithm.Blake2s_256.doc : Doc
  779.  crypto.HashAlgorithm.doc : Doc
  780.  crypto.HashAlgorithm.Md5 : HashAlgorithm
  781.  crypto.HashAlgorithm.Md5.doc : Doc
  782.  crypto.HashAlgorithm.Sha1 : HashAlgorithm
  783.  crypto.HashAlgorithm.Sha1.doc : Doc
  784.  crypto.HashAlgorithm.Sha2_256 : HashAlgorithm
  785.  crypto.HashAlgorithm.Sha2_256.doc : Doc
  786.  crypto.HashAlgorithm.Sha2_512 : HashAlgorithm
  787.  crypto.HashAlgorithm.Sha2_512.doc : Doc
  788.  crypto.HashAlgorithm.Sha3_256 : HashAlgorithm
  789.  crypto.HashAlgorithm.Sha3_256.doc : Doc
  790.  crypto.HashAlgorithm.Sha3_512 : HashAlgorithm
  791.  crypto.HashAlgorithm.Sha3_512.doc : Doc
  792.  crypto.hashBytes : HashAlgorithm -> Bytes -> Bytes
  793.  crypto.hashBytes.doc : Doc
  794.  crypto.hmac : HashAlgorithm -> Bytes -> a -> Bytes
  795.  crypto.hmac.doc : Doc
  796.  crypto.hmac.verify : HashAlgorithm
                             -> Bytes
                             -> a
                             -> Bytes
                             -> Boolean
  797.  crypto.hmac.verify.doc : Doc
  798.  crypto.hmac.verify.test.happy : [Result]
  799.  crypto.hmac.verify.test.sad : [Result]
  800.  crypto.hmac.verifyBytes : HashAlgorithm
                                  -> Bytes
                                  -> Bytes
                                  -> Bytes
                                  -> Boolean
  801.  crypto.hmac.verifyBytes.doc : Doc
  802.  crypto.hmac.verifyBytes.test.happy : [Result]
  803.  crypto.hmac.verifyBytes.test.sad : [Result]
  804.  crypto.hmacBytes : HashAlgorithm
                           -> Bytes
                           -> Bytes
                           -> Bytes
  805.  crypto.hmacBytes.doc : Doc
  806.  type crypto.Rsa.PrivateKey
  807.  crypto.Rsa.PrivateKey.doc : Doc
  808.  crypto.Rsa.PrivateKey.PrivateKey : Bytes
                                           -> Rsa.PrivateKey
  809.  type crypto.Rsa.PublicKey
  810.  crypto.Rsa.PublicKey.doc : Doc
  811.  crypto.Rsa.PublicKey.PublicKey : Bytes -> Rsa.PublicKey
  812.  crypto.Rsa.sign : Rsa.PrivateKey
                          -> Bytes
                          ->{Exception} Rsa.Signature
  813.  crypto.Rsa.sign.doc : Doc
  814.  crypto.Rsa.sign.impl : Bytes
                               -> Bytes
                               -> Either Failure Bytes
  815.  crypto.Rsa.sign.test : [Result]
  816.  type crypto.Rsa.Signature
  817.  crypto.Rsa.Signature.doc : Doc
  818.  crypto.Rsa.Signature.Signature : Bytes -> Rsa.Signature
  819.  crypto.Rsa.verify : Rsa.PublicKey
                            -> Bytes
                            -> Rsa.Signature
                            ->{Exception} Boolean
  820.  crypto.Rsa.verify.doc : Doc
  821.  crypto.Rsa.verify.impl : Bytes
                                 -> Bytes
                                 -> Bytes
                                 -> Either Failure Boolean
  822.  crypto.Rsa.verify.test : [Result]
  823.  structural type data.Array a
  824.  data.Array.append : data.Array a
                            -> data.Array a
                            -> data.Array a
  825.  data.Array.append.doc : Doc
  826.  data.Array.Arr : Nat
                         -> Nat
                         -> data.Array.Raw a
                         -> data.Array a
  827.  data.Array.Arr.doc : Doc
  828.  type data.Array.ArrayFailure
  829.  data.Array.ArrayFailure.doc : Doc
  830.  data.Array.ArrayFailure.raise : Text
                                        -> a
                                        ->{Exception} b
  831.  data.Array.ArrayFailure.raise.doc : Doc
  832.  data.Array.at : Nat -> data.Array a -> Optional a
  833.  data.Array.at.doc : Doc
  834.  data.Array.at! : Nat -> data.Array a ->{Abort} a
  835.  data.Array.at!.doc : Doc
  836.  data.Array.cons : a -> data.Array a -> data.Array a
  837.  data.Array.cons.doc : Doc
  838.  data.Array.copy : Nat
                          -> Nat
                          -> Nat
                          -> data.Array a
                          -> mutable.Array g a
                          ->{g, Exception} ()
  839.  data.Array.copy.doc : Doc
  840.  data.Array.copy.tests.doesCopy : [Result]
  841.  data.Array.copy.tests.doesNotCopyPastEndOfDestinationArray : [Result]
  842.  data.Array.copy.tests.doesNotCopyPastEndOfSourceArray : [Result]
  843.  data.Array.doc : Doc
  844.  data.Array.drop : Nat
                          -> data.Array a
                          ->{Exception} data.Array a
  845.  data.Array.drop.doc : Doc
  846.  data.Array.empty : data.Array a
  847.  data.Array.empty.doc : Doc
  848.  data.Array.fill : Nat -> a -> data.Array a
  849.  data.Array.fill.doc : Doc
  850.  data.Array.find : (a ->{g} Boolean)
                          -> data.Array a
                          ->{g} Optional a
  851.  data.Array.find.doc : Doc
  852.  data.Array.find.tests.consistentWithList : [Result]
  853.  data.Array.findLast : (a ->{g} Boolean)
                              -> data.Array a
                              ->{g} Optional a
  854.  data.Array.findLast.doc : Doc
  855.  data.Array.firstIndexOf : (a ->{g} Boolean)
                                  -> data.Array a
                                  ->{g} Optional Nat
  856.  data.Array.firstIndexOf.doc : Doc
  857.  data.Array.firstIndexOf.tests.finds : [Result]
  858.  data.Array.foldLeft : (a ->{g} b ->{h} a)
                              -> a
                              -> data.Array b
                              ->{g, h} a
  859.  data.Array.foldLeft.doc : Doc
  860.  data.Array.foldRight : (a ->{g} b ->{h} b)
                               -> b
                               -> data.Array a
                               ->{g, h} b
  861.  data.Array.foldRight.doc : Doc
  862.  data.Array.fromList : [a] -> data.Array a
  863.  data.Array.fromList.doc : Doc
  864.  data.Array.isEmpty : data.Array a -> Boolean
  865.  data.Array.isEmpty.doc : Doc
  866.  data.Array.lastIndexOf : (a ->{g} Boolean)
                                 -> data.Array a
                                 ->{g} Optional Nat
  867.  data.Array.lastIndexOf.doc : Doc
  868.  data.Array.map : (a ->{g} b)
                         -> data.Array a
                         ->{g} data.Array b
  869.  data.Array.map.doc : Doc
  870.  data.Array.new! : a
                          -> Nat
                          -> (∀ s.
                            mutable.Array {Scope s} a
                            ->{g, Exception, Scope s} ())
                          ->{g} data.Array a
  871.  data.Array.new!.doc : Doc
  872.  data.Array.new!.tests : [Result]
  873.  data.Array.of : x -> Nat -> data.Array x
  874.  data.Array.of.doc : Doc
  875.  data.Array.randomChoice : data.Array a
                                  ->{Exception, Random} a
  876.  data.Array.randomChoice.doc : Doc
  877.  data.Array.randomChoice.test : [Result]
  878.  builtin type data.Array.Raw
  879.  data.Array.Raw.copyTo! : mutable.Array.Raw g a
                                 -> Nat
                                 -> data.Array.Raw a
                                 -> Nat
                                 -> Nat
                                 ->{g, Exception} ()
  880.  data.Array.Raw.copyTo!.doc : Doc
  881.  data.Array.Raw.doc : Doc
  882.  data.Array.Raw.fromList : [a] -> data.Array.Raw a
  883.  data.Array.Raw.read : data.Array.Raw a
                              -> Nat
                              ->{Exception} a
  884.  data.Array.Raw.read.doc : Doc
  885.  data.Array.Raw.size : data.Array.Raw a -> Nat
  886.  data.Array.Raw.size.doc : Doc
  887.  data.Array.read : data.Array a -> Nat ->{Exception} a
  888.  data.Array.read.doc : Doc
  889.  data.Array.singleton : a -> data.Array a
  890.  data.Array.singleton.doc : Doc
  891.  data.Array.size : data.Array a -> Nat
  892.  data.Array.size.doc : Doc
  893.  data.Array.slice : Nat
                           -> Nat
                           -> data.Array a
                           ->{Exception} data.Array a
  894.  data.Array.slice.doc : Doc
  895.  data.Array.snoc : data.Array a -> a -> data.Array a
  896.  data.Array.snoc.doc : Doc
  897.  data.Array.take : Nat
                          -> data.Array t
                          ->{Exception} data.Array t
  898.  data.Array.take.doc : Doc
  899.  data.Array.toList : data.Array a -> [a]
  900.  data.Array.toList.doc : Doc
  901.  data.Array.unsafeAt : Nat -> data.Array a -> a
  902.  data.Array.unsafeAt.doc : Doc
  903.  structural type data.Bag a
  904.  data.Bag.* : Bag a -> Bag b -> Bag (a, b)
  905.  data.Bag.*.doc : Doc
  906.  data.Bag.+ : Bag a -> Bag a -> Bag a
  907.  data.Bag.+.doc : Doc
  908.  data.Bag.== : Bag a -> Bag a -> Boolean
  909.  data.Bag.add : k -> Bag k -> Bag k
  910.  data.Bag.add.doc : Doc
  911.  data.Bag.add.tests.adds : [Result]
  912.  data.Bag.addAll : Bag a -> Bag a -> Bag a
  913.  data.Bag.addAll.doc : Doc
  914.  data.Bag.addAll.tests.homomorphism : [Result]
  915.  data.Bag.addN : Nat -> k -> Bag k -> Bag k
  916.  data.Bag.addN.doc : Doc
  917.  data.Bag.addN.test : [Result]
  918.  data.Bag.all : (a ->{g} Boolean) -> Bag a ->{g} Boolean
  919.  data.Bag.all.doc : Doc
  920.  data.Bag.all.test : [Result]
  921.  data.Bag.any : (a ->{g} Boolean) -> Bag a ->{g} Boolean
  922.  data.Bag.any.doc : Doc
  923.  data.Bag.any.test : [Result]
  924.  data.Bag.contains : Bag a -> a -> Boolean
  925.  data.Bag.contains.doc : Doc
  926.  data.Bag.contains.test : [Result]
  927.  data.Bag.convolve : (i ->{g} a ->{g} t)
                            -> Bag i
                            -> Bag a
                            ->{g} Bag t
  928.  data.Bag.convolve.doc : Doc
  929.  data.Bag.convolve.tests.associative : [Result]
  930.  data.Bag.convolve.tests.natural : [Result]
  931.  data.Bag.convolve.tests.unit : [Result]
  932.  data.Bag.count : a -> Bag a -> Nat
  933.  data.Bag.count.doc : Doc
  934.  data.Bag.count.tests.counts : [Result]
  935.  data.Bag.counts : Bag a -> Map a Nat
  936.  data.Bag.counts.doc : Doc
  937.  data.Bag.difference : Bag a -> Bag a -> Bag a
  938.  data.Bag.difference.doc : Doc
  939.  data.Bag.difference.tests.homomorphism : [Result]
  940.  data.Bag.doc : Doc
  941.  data.Bag.elementOf : a -> Bag a -> Boolean
  942.  data.Bag.elementOf.doc : Doc
  943.  data.Bag.elementOf.test : [Result]
  944.  data.Bag.empty : Bag a
  945.  data.Bag.empty.doc : Doc
  946.  data.Bag.empty.test : [Result]
  947.  data.Bag.equals : Bag a -> Bag a -> Boolean
  948.  data.Bag.equals.doc : Doc
  949.  data.Bag.equals.tests.reflexive : [Result]
  950.  data.Bag.equals.tests.symmetric : [Result]
  951.  data.Bag.equals.tests.transitive : [Result]
  952.  data.Bag.filter : (i ->{e} Boolean) -> Bag i ->{e} Bag i
  953.  data.Bag.filter.doc : Doc
  954.  data.Bag.flatMap : (a ->{e} Bag b) -> Bag a ->{e} Bag b
  955.  data.Bag.flatMap.doc : Doc
  956.  data.Bag.flatMap.tests.associative : [Result]
  957.  data.Bag.flatMap.tests.unit : [Result]
  958.  data.Bag.foldLeft : (b ->{g} a ->{g} b)
                            -> b
                            -> Bag a
                            ->{g} b
  959.  data.Bag.foldLeft.doc : Doc
  960.  data.Bag.foldLeft.tests.asList : [Result]
  961.  data.Bag.foldRight : (a ->{g} b ->{g} b)
                             -> b
                             -> Bag a
                             ->{g} b
  962.  data.Bag.foldRight.doc : Doc
  963.  data.Bag.foldRight.tests.asList : [Result]
  964.  data.Bag.from : Bag a -> Bag a -> Boolean
  965.  data.Bag.from.doc : Doc
  966.  data.Bag.from.tests.subset : [Result]
  967.  data.Bag.fromList : [k] -> Bag k
  968.  data.Bag.fromList.doc : Doc
  969.  data.Bag.fromList.tests.roundtrip : [Result]
  970.  data.Bag.fromMap : Map k Nat -> Bag k
  971.  data.Bag.fromMap.doc : Doc
  972.  data.Bag.fromMap.tests.roundTrip : [Result]
  973.  data.Bag.fromOccurrenceList : [(a, Nat)] -> Bag a
  974.  data.Bag.fromOccurrenceList.doc : Doc
  975.  data.Bag.fromOccurrenceList.tests.roundTrip : [Result]
  976.  data.Bag.fromText : Text -> Bag Char
  977.  data.Bag.fromText.doc : Doc
  978.  data.Bag.fromText.tests.anagram : [Result]
  979.  data.Bag.internal.compare : (Nat
                                    ->{e} Nat
                                    ->{e} Boolean)
                                    -> Bag a
                                    -> Bag a
                                    ->{e} Boolean
  980.  data.Bag.internal.compare.doc : Doc
  981.  data.Bag.internal.MkBag : Map a Nat -> Bag a
  982.  data.Bag.internal.normalize : Bag a -> Bag a
  983.  data.Bag.intersect : Bag a -> Bag a -> Bag a
  984.  data.Bag.intersect.doc : Doc
  985.  data.Bag.intersect.tests.commutative : [Result]
  986.  data.Bag.intersect.tests.distributive : [Result]
  987.  data.Bag.intersect.tests.homomorphism : [Result]
  988.  data.Bag.intersect.tests.idempotent : [Result]
  989.  data.Bag.intersect.tests.zero : [Result]
  990.  data.Bag.isEmpty : Bag a -> Boolean
  991.  data.Bag.isEmpty.doc : Doc
  992.  data.Bag.isEmpty.test : [Result]
  993.  data.Bag.map : (a ->{g} b) -> Bag a ->{g} Bag b
  994.  data.Bag.map.doc : Doc
  995.  data.Bag.map.tests.functor : [Result]
  996.  data.Bag.map.tests.surjection : [Result]
  997.  data.Bag.mapCounts : (Nat ->{e} Nat)
                             -> Bag a
                             ->{e} Bag a
  998.  data.Bag.mapCounts.doc : Doc
  999.  data.Bag.mapCounts.tests.functor : [Result]
  1000. data.Bag.modify : ((a, Nat) ->{e} (b, Nat))
                          -> Bag a
                          ->{e} Bag b
  1001. data.Bag.modify.doc : Doc
  1002. data.Bag.modify.tests.double : [Result]
  1003. data.Bag.modify.tests.functor : [Result]
  1004. data.Bag.modify.tests.zero : [Result]
  1005. data.Bag.none : (a ->{g} Boolean) -> Bag a ->{g} Boolean
  1006. data.Bag.none.doc : Doc
  1007. data.Bag.none.test : [Result]
  1008. data.Bag.nth : Nat -> Bag a -> Optional a
  1009. data.Bag.nth.doc : Doc
  1010. data.Bag.nth.tests : [Result]
  1011. data.Bag.occurrenceList : Bag a -> [(a, Nat)]
  1012. data.Bag.occurrenceList.doc : Doc
  1013. data.Bag.product : Bag a -> Bag b -> Bag (a, b)
  1014. data.Bag.product.doc : Doc
  1015. data.Bag.product.tests.spec : [Result]
  1016. data.Bag.randomChoice : Bag a ->{Exception, Random} a
  1017. data.Bag.randomChoice.doc : Doc
  1018. data.Bag.randomChoice.test : [Result]
  1019. data.Bag.remove : k -> Bag k -> Bag k
  1020. data.Bag.remove.doc : Doc
  1021. data.Bag.remove.tests.removes : [Result]
  1022. data.Bag.removeAll : k -> Bag k -> Bag k
  1023. data.Bag.removeAll.doc : Doc
  1024. data.Bag.removeAll.tests.removes : [Result]
  1025. data.Bag.removeN : Nat -> k -> Bag k -> Bag k
  1026. data.Bag.removeN.doc : Doc
  1027. data.Bag.removeN.tests.removes : [Result]
  1028. data.Bag.removeWhere : (a ->{e} Boolean)
                               -> Bag a
                               ->{e} Bag a
  1029. data.Bag.removeWhere.doc : Doc
  1030. data.Bag.removeWhere.tests.removes : [Result]
  1031. data.Bag.scale : Nat -> Bag a -> Bag a
  1032. data.Bag.scale.doc : Doc
  1033. data.Bag.scale.tests.scales : [Result]
  1034. data.Bag.similarity : Bag a -> Bag a -> Float
  1035. data.Bag.similarity.doc : Doc
  1036. data.Bag.singleton : k -> Bag k
  1037. data.Bag.singleton.doc : Doc
  1038. data.Bag.singleton.tests.one : [Result]
  1039. data.Bag.size : Bag a -> Nat
  1040. data.Bag.size.doc : Doc
  1041. data.Bag.size.test : [Result]
  1042. data.Bag.subbag : Bag a -> Bag a -> Boolean
  1043. data.Bag.subbag.doc : Doc
  1044. data.Bag.subbag.tests.homomorphism : [Result]
  1045. data.Bag.superbag : Bag a -> Bag a -> Boolean
  1046. data.Bag.superbag.doc : Doc
  1047. data.Bag.superbag.tests.homomorphism : [Result]
  1048. data.Bag.tests.bagOf : '{Gen} a -> '{Gen} Bag a
  1049. data.Bag.tests.bagOf.doc : Doc
  1050. data.Bag.toList : Bag a -> [a]
  1051. data.Bag.toList.doc : Doc
  1052. data.Bag.toList.tests.roundtrip : [Result]
  1053. data.Bag.toSet : Bag a -> Set a
  1054. data.Bag.toSet.doc : Doc
  1055. data.Bag.toSet.tests.roundtrip : [Result]
  1056. data.Bag.toText : Bag Char -> Text
  1057. data.Bag.toText.doc : Doc
  1058. data.Bag.toText.tests.roundtrip : [Result]
  1059. data.Bag.traverse : (a ->{e} b) -> Bag a ->{e} Bag b
  1060. data.Bag.traverse.doc : Doc
  1061. data.Bag.traverse.tests.functor : [Result]
  1062. data.Bag.union : Bag a -> Bag a -> Bag a
  1063. data.Bag.union.doc : Doc
  1064. data.Bag.union.tests.commutative : [Result]
  1065. data.Bag.union.tests.distributive : [Result]
  1066. data.Bag.union.tests.homomorphism : [Result]
  1067. data.Bag.union.tests.idempotent : [Result]
  1068. data.Bag.union.tests.unit : [Result]
  1069. structural type data.ByteArray
  1070. data.ByteArray.++ : data.ByteArray
                            -> data.ByteArray
                            -> data.ByteArray
  1071. data.ByteArray.++.doc : Doc
  1072. data.ByteArray.append : data.ByteArray
                                -> data.ByteArray
                                -> data.ByteArray
  1073. data.ByteArray.append.doc : Doc
  1074. data.ByteArray.append.test : [Result]
  1075. data.ByteArray.BArr : Nat
                              -> Nat
                              -> data.ByteArray.Raw
                              -> data.ByteArray
  1076. data.ByteArray.BArr.doc : Doc
  1077. data.ByteArray.base32Hex : data.ByteArray -> Text
  1078. data.ByteArray.base32Hex.doc : Doc
  1079. data.ByteArray.base32Hex.test : [Result]
  1080. data.ByteArray.doc : Doc
  1081. data.ByteArray.drop : Nat
                              -> data.ByteArray
                              -> data.ByteArray
  1082. data.ByteArray.drop.doc : Doc
  1083. data.ByteArray.drop.test : [Result]
  1084. data.ByteArray.find : (Nat ->{g} Boolean)
                              -> data.ByteArray
                              ->{g, Exception} Optional Nat
  1085. data.ByteArray.find.doc : Doc
  1086. data.ByteArray.findLast : (Nat ->{g} Boolean)
                                  -> data.ByteArray
                                  ->{g, Exception} Optional Nat
  1087. data.ByteArray.findLast.doc : Doc
  1088. data.ByteArray.firstIndexOf : (Nat ->{g} Boolean)
                                      -> data.ByteArray
                                      ->{g, Exception} Optional
                                        Nat
  1089. data.ByteArray.firstIndexOf.doc : Doc
  1090. data.ByteArray.fromBytes : Bytes -> data.ByteArray
  1091. data.ByteArray.fromBytes.doc : Doc
  1092. data.ByteArray.fromList : [Nat] -> data.ByteArray
  1093. data.ByteArray.fromList.doc : Doc
  1094. data.ByteArray.join : [data.ByteArray] -> data.ByteArray
  1095. data.ByteArray.join.doc : Doc
  1096. data.ByteArray.join.test : [Result]
  1097. data.ByteArray.lastIndexOf : (Nat ->{g} Boolean)
                                     -> data.ByteArray
                                     ->{g, Exception} Optional
                                       Nat
  1098. data.ByteArray.lastIndexOf.doc : Doc
  1099. data.ByteArray.new! : Nat
                              -> (∀ s.
                                mutable.ByteArray (Scope s)
                                ->{g, Exception, Scope s} ())
                              ->{g} data.ByteArray
  1100. data.ByteArray.new!.doc : Doc
  1101. data.ByteArray.randomChoice : data.ByteArray
                                      ->{Exception, Random} Nat
  1102. data.ByteArray.randomChoice.doc : Doc
  1103. data.ByteArray.randomChoice.test : [Result]
  1104. builtin type data.ByteArray.Raw
  1105. data.ByteArray.Raw.base32Hex : data.ByteArray.Raw
                                       -> Nat
                                       -> Nat
                                       -> Text
  1106. data.ByteArray.Raw.base32Hex.doc : Doc
  1107. data.ByteArray.Raw.copyTo! : mutable.ByteArray.Raw g
                                     -> Nat
                                     -> data.ByteArray.Raw
                                     -> Nat
                                     -> Nat
                                     ->{g, Exception} ()
  1108. data.ByteArray.Raw.copyTo!.doc : Doc
  1109. data.ByteArray.Raw.doc : Doc
  1110. data.ByteArray.Raw.fromBytes : Bytes
                                       -> data.ByteArray.Raw
  1111. data.ByteArray.Raw.fromBytes.doc : Doc
  1112. data.ByteArray.Raw.new! : Nat
                                  -> (∀ s.
                                    mutable.ByteArray.Raw
                                      (Scope s)
                                    ->{g, Exception, Scope s} ())
                                  ->{g} data.ByteArray.Raw
  1113. data.ByteArray.Raw.new!.doc : Doc
  1114. data.ByteArray.Raw.read16be : data.ByteArray.Raw
                                      -> Nat
                                      ->{Exception} Nat
  1115. data.ByteArray.Raw.read16be.doc : Doc
  1116. data.ByteArray.Raw.read24be : data.ByteArray.Raw
                                      -> Nat
                                      ->{Exception} Nat
  1117. data.ByteArray.Raw.read24be.doc : Doc
  1118. data.ByteArray.Raw.read32be : data.ByteArray.Raw
                                      -> Nat
                                      ->{Exception} Nat
  1119. data.ByteArray.Raw.read32be.doc : Doc
  1120. data.ByteArray.Raw.read40be : data.ByteArray.Raw
                                      -> Nat
                                      ->{Exception} Nat
  1121. data.ByteArray.Raw.read40be.doc : Doc
  1122. data.ByteArray.Raw.read64be : data.ByteArray.Raw
                                      -> Nat
                                      ->{Exception} Nat
  1123. data.ByteArray.Raw.read64be.doc : Doc
  1124. data.ByteArray.Raw.read8 : data.ByteArray.Raw
                                   -> Nat
                                   ->{Exception} Nat
  1125. data.ByteArray.Raw.read8.doc : Doc
  1126. data.ByteArray.Raw.size : data.ByteArray.Raw -> Nat
  1127. data.ByteArray.Raw.size.doc : Doc
  1128. data.ByteArray.Raw.toByteList : data.ByteArray.Raw
                                        -> [Nat]
  1129. data.ByteArray.Raw.toByteList.doc : Doc
  1130. data.ByteArray.Raw.toBytes : data.ByteArray.Raw -> Bytes
  1131. data.ByteArray.Raw.toBytes.doc : Doc
  1132. data.ByteArray.read16be : data.ByteArray
                                  -> Nat
                                  ->{Exception} Nat
  1133. data.ByteArray.read16be.doc : Doc
  1134. data.ByteArray.read32be : data.ByteArray
                                  -> Nat
                                  ->{Exception} Nat
  1135. data.ByteArray.read32be.doc : Doc
  1136. data.ByteArray.read64be : data.ByteArray
                                  -> Nat
                                  ->{Exception} Nat
  1137. data.ByteArray.read64be.doc : Doc
  1138. data.ByteArray.read8 : data.ByteArray
                               -> Nat
                               ->{Exception} Nat
  1139. data.ByteArray.read8.doc : Doc
  1140. data.ByteArray.size : data.ByteArray -> Nat
  1141. data.ByteArray.size.doc : Doc
  1142. data.ByteArray.size.test : [Result]
  1143. data.ByteArray.slice : Nat
                               -> Nat
                               -> data.ByteArray
                               ->{Exception} data.ByteArray
  1144. data.ByteArray.slice.doc : Doc
  1145. data.ByteArray.take : Nat
                              -> data.ByteArray
                              -> data.ByteArray
  1146. data.ByteArray.take.doc : Doc
  1147. data.ByteArray.take.test : [Result]
  1148. data.ByteArray.toList : data.ByteArray -> [Nat]
  1149. data.ByteArray.toList.doc : Doc
  1150. data.ByteArray.toList.test : [Result]
  1151. data.ByteArray.write8 : data.ByteArray
                                -> Nat
                                -> Nat
                                ->{Exception} data.ByteArray
  1152. data.ByteArray.write8.doc : Doc
  1153. structural type data.deprecated.Heap k v
  1154. data.deprecated.Heap.breakOffMax : Heap k v
                                           -> ( k,
                                             v,
                                             Optional (Heap k v))
  1155. data.deprecated.Heap.breakOffMax.doc : Doc
  1156. data.deprecated.Heap.children : Heap k v -> [Heap k v]
  1157. data.deprecated.Heap.children.doc : Doc
  1158. data.deprecated.Heap.doc : Doc
  1159. data.deprecated.Heap.fromKeys : [a]
                                        -> Optional (Heap a a)
  1160. data.deprecated.Heap.fromKeys.doc : Doc
  1161. data.deprecated.Heap.fromList : List.Nonempty (k, v)
                                        -> Heap k v
  1162. data.deprecated.Heap.fromList.doc : Doc
  1163. data.deprecated.Heap.Heap : Nat
                                    -> k
                                    -> v
                                    -> [Heap k v]
                                    -> Heap k v
  1164. data.deprecated.Heap.insert : k
                                      -> v
                                      -> Heap k v
                                      -> Heap k v
  1165. data.deprecated.Heap.insert.doc : Doc
  1166. data.deprecated.Heap.max : Heap k v -> (k, v)
  1167. data.deprecated.Heap.max.doc : Doc
  1168. data.deprecated.Heap.maxKey : Heap k v -> k
  1169. data.deprecated.Heap.maxKey.doc : Doc
  1170. data.deprecated.Heap.mayFromList : [(k, v)]
                                           -> Optional
                                             (Heap k v)
  1171. data.deprecated.Heap.pop : Heap k v
                                   -> Optional (Heap k v)
  1172. data.deprecated.Heap.pop.doc : Doc
  1173. data.deprecated.Heap.singleton : k -> v -> Heap k v
  1174. data.deprecated.Heap.singleton.doc : Doc
  1175. data.deprecated.Heap.size : Heap k v -> Nat
  1176. data.deprecated.Heap.size.doc : Doc
  1177. data.deprecated.Heap.sort : [a] -> [a]
  1178. data.deprecated.Heap.sort.doc : Doc
  1179. data.deprecated.Heap.sortDescending : [a] -> [a]
  1180. data.deprecated.Heap.sortDescending.doc : Doc
  1181. data.deprecated.Heap.take : Nat -> Heap k v -> [(k, v)]
  1182. data.deprecated.Heap.take.doc : Doc
  1183. data.deprecated.Heap.toList : Heap k v
                                      -> List.Nonempty (k, v)
  1184. data.deprecated.Heap.toList.doc : Doc
  1185. data.deprecated.Heap.union : Heap k v
                                     -> Heap k v
                                     -> Heap k v
  1186. data.deprecated.Heap.union.doc : Doc
  1187. structural type data.deprecated.Weighted a
  1188. data.deprecated.Weighted.<|> : Weighted a
                                       -> Weighted a
                                       -> Weighted a
  1189. data.deprecated.Weighted.append : Weighted a
                                          -> Weighted a
                                          -> Weighted a
  1190. data.deprecated.Weighted.append.doc : Doc
  1191. data.deprecated.Weighted.append.examples.ex : [Nat]
  1192. data.deprecated.Weighted.dedupe : Weighted a
                                          -> Weighted a
  1193. data.deprecated.Weighted.dedupe.doc : Doc
  1194. data.deprecated.Weighted.doc : Doc
  1195. data.deprecated.Weighted.drop : Nat
                                        -> Weighted a
                                        -> Weighted a
  1196. data.deprecated.Weighted.drop.doc : Doc
  1197. data.deprecated.Weighted.Fail : Weighted a
  1198. data.deprecated.Weighted.Fail.doc : Doc
  1199. data.deprecated.Weighted.filter : (a -> Boolean)
                                          -> Weighted a
                                          -> Weighted a
  1200. data.deprecated.Weighted.filter.doc : Doc
  1201. data.deprecated.Weighted.flatMap : (a -> Weighted b)
                                           -> Weighted a
                                           -> Weighted b
  1202. data.deprecated.Weighted.flatMap.doc : Doc
  1203. data.deprecated.Weighted.floats : Weighted Float
  1204. data.deprecated.Weighted.floats.doc : Doc
  1205. data.deprecated.Weighted.fromList : [a] -> Weighted a
  1206. data.deprecated.Weighted.fromList.doc : Doc
  1207. data.deprecated.Weighted.ints : Weighted Int
  1208. data.deprecated.Weighted.ints.doc : Doc
  1209. data.deprecated.Weighted.lists : Weighted a
                                         -> Weighted [a]
  1210. data.deprecated.Weighted.lists.doc : Doc
  1211. data.deprecated.Weighted.map : (a -> b)
                                       -> Weighted a
                                       -> Weighted b
  1212. data.deprecated.Weighted.map.doc : Doc
  1213. data.deprecated.Weighted.mergeWith : (a -> b -> c)
                                             -> Weighted a
                                             -> Weighted b
                                             -> Weighted c
  1214. data.deprecated.Weighted.mergeWith.doc : Doc
  1215. data.deprecated.Weighted.nats : Weighted Nat
  1216. data.deprecated.Weighted.nats.doc : Doc
  1217. data.deprecated.Weighted.natsInOrder : Weighted Nat
  1218. data.deprecated.Weighted.normalFloats : Weighted Float
  1219. data.deprecated.Weighted.normalFloats.doc : Doc
  1220. data.deprecated.Weighted.sample : Nat
                                          -> Weighted a
                                          -> [a]
  1221. data.deprecated.Weighted.sample.doc : Doc
  1222. data.deprecated.Weighted.take : Nat
                                        -> Weighted a
                                        -> Weighted a
  1223. data.deprecated.Weighted.take.doc : Doc
  1224. data.deprecated.Weighted.weight : Nat
                                          ->{e} '{e} Weighted a
                                          ->{e} Weighted a
  1225. data.deprecated.Weighted.Weight : Nat
                                          -> 'Weighted a
                                          -> Weighted a
  1226. data.deprecated.Weighted.weight.doc : Doc
  1227. data.deprecated.Weighted.yield : a -> Weighted a
  1228. data.deprecated.Weighted.Yield : a
                                         -> Weighted a
                                         -> Weighted a
  1229. data.deprecated.Weighted.Yield.doc : Doc
  1230. data.deprecated.Weighted.yield.doc : Doc
  1231. type data.Graph v
  1232. data.Graph.AdjLists : data.Array.Raw [Nat]
                              -> data.Array.Raw v
                              -> Graph v
  1233. data.Graph.build : [(v, k, [k])] -> Graph v
  1234. data.Graph.build.doc : Doc
  1235. data.Graph.dfs : Graph v
                         -> [Nat]
                         ->{Exception} [RoseTree Nat]
  1236. data.Graph.dfs.crawl : Graph v
                               -> NatSet
                               -> [RoseTree Nat]
                               -> Nat
                               ->{Exception} ( NatSet,
                                 [RoseTree Nat])
  1237. data.Graph.dfs.crawl.doc : Doc
  1238. data.Graph.dfs.crawls : Graph v
                                -> NatSet
                                -> [Nat]
                                ->{Exception} ( NatSet,
                                  [RoseTree Nat])
  1239. data.Graph.dfs.crawls.doc : Doc
  1240. data.Graph.dfs.doc : Doc
  1241. data.Graph.doc : Doc
  1242. data.Graph.edgeCount : Graph v -> Nat
  1243. data.Graph.edgeCount.doc : Doc
  1244. data.Graph.edges : Graph v -> Nat ->{Exception} [Nat]
  1245. data.Graph.edges.doc : Doc
  1246. data.Graph.isReachable : Graph v
                                 -> Nat
                                 -> Nat
                                 ->{Exception} Boolean
  1247. data.Graph.isReachable.doc : Doc
  1248. data.Graph.reverse : Graph v ->{Exception} Graph v
  1249. data.Graph.reverse.doc : Doc
  1250. type data.Graph.SCC v
  1251. data.Graph.SCC.Acyclic : v -> SCC v
  1252. data.Graph.SCC.add : a -> SCC a -> SCC a
  1253. data.Graph.SCC.add.doc : Doc
  1254. data.Graph.SCC.augment : Boolean
                                 -> a
                                 -> Optional (SCC a)
                                 -> SCC a
  1255. data.Graph.SCC.augment.doc : Doc
  1256. data.Graph.SCC.Cyclic : [v] -> SCC v
  1257. data.Graph.SCC.doc : Doc
  1258. data.Graph.SCC.flatten : SCC v -> [v]
  1259. data.Graph.SCC.flatten.doc : Doc
  1260. data.Graph.SCC.map : (a ->{g1} b) -> SCC a ->{g1} SCC b
  1261. data.Graph.SCC.map.doc : Doc
  1262. data.Graph.sccs : Graph v -> [SCC v]
  1263. data.Graph.sccs.classify : Graph v
                                   -> RoseTree Nat
                                   ->{Exception} SCC Nat
  1264. data.Graph.sccs.classify.doc : Doc
  1265. data.Graph.sccs.crawl : Graph v
                                -> NatSet
                                -> [Nat]
                                -> Nat
                                ->{Exception} (NatSet, [Nat])
  1266. data.Graph.sccs.crawl.doc : Doc
  1267. data.Graph.sccs.crawls : Graph v
                                 -> (NatSet, [Nat])
                                 -> [Nat]
                                 ->{Exception} (NatSet, [Nat])
  1268. data.Graph.sccs.crawls.doc : Doc
  1269. data.Graph.sccs.doc : Doc
  1270. data.Graph.stronglyConnectedComponents : [(v, k, [k])]
                                                 -> [SCC v]
  1271. data.Graph.stronglyConnectedComponents.doc : Doc
  1272. data.Graph.tests.build : [Result]
  1273. data.Graph.tests.checkAcyclic : Graph v
                                        -> Nat
                                        ->{Exception} Boolean
  1274. data.Graph.tests.checkCyclic : Graph v
                                       -> [Nat]
                                       ->{Exception} Boolean
  1275. data.Graph.tests.checkTopOrder : Graph v
                                         -> [v]
                                         ->{Exception} ()
  1276. data.Graph.tests.checkTopOrder.doc : Doc
  1277. data.Graph.tests.checkTopSCCs : Graph v
                                        -> [SCC v]
                                        ->{Exception} ()
  1278. data.Graph.tests.checkTopSCCs.doc : Doc
  1279. data.Graph.tests.isUnreachable : Text
                                         -> Graph v
                                         -> v
                                         -> [v]
                                         ->{Exception} Boolean
  1280. data.Graph.tests.isUnreachable.doc : Doc
  1281. data.Graph.tests.randomDAG : (Nat -> a)
                                     ->{Random} Graph a
  1282. data.Graph.tests.randomGraph : (Nat -> a)
                                       ->{Random} Graph a
  1283. data.Graph.tests.randomGraph.doc : Doc
  1284. data.Graph.tests.reverse : [Result]
  1285. data.Graph.tests.reverse.matchEdges : Graph v1
                                              -> Graph v
                                              ->{Exception} ()
  1286. data.Graph.tests.reverse.matchEdges.doc : Doc
  1287. data.Graph.tests.sccs : [Result]
  1288. data.Graph.tests.topSort.test : [Result]
  1289. data.Graph.topSort : Graph v ->{Abort} [v]
  1290. data.Graph.topSort.crawl : Graph v
                                   -> NatSet
                                   -> (NatSet, [v])
                                   -> Nat
                                   ->{Exception, Abort} ( NatSet,
                                     [v])
  1291. data.Graph.topSort.crawl.doc : Doc
  1292. data.Graph.topSort.crawls : Graph v
                                    -> NatSet
                                    -> (NatSet, [v])
                                    -> [Nat]
                                    ->{Exception, Abort} ( NatSet,
                                      [v])
  1293. data.Graph.topSort.doc : Doc
  1294. data.Graph.vertex : Graph v -> Nat ->{Exception} v
  1295. data.Graph.vertex.doc : Doc
  1296. data.Graph.vertexCount : Graph v -> Nat
  1297. data.Graph.vertexCount.doc : Doc
  1298. data.Graph.vertexNum : Graph v
                               -> v
                               ->{Exception} Optional Nat
  1299. data.Graph.vertexNum.doc : Doc
  1300. structural type data.Id a
  1301. data.Id.apply : Id i -> Id (i ->{g} t) ->{g} Id t
  1302. data.Id.apply.doc : Doc
  1303. data.Id.doc : Doc
  1304. data.Id.flatMap : (i ->{g} o) -> Id i ->{g} o
  1305. data.Id.flatMap.doc : Doc
  1306. data.Id.Id : a -> Id a
  1307. data.Id.map : (i ->{g} o) -> Id i ->{g} Id o
  1308. data.Id.map.doc : Doc
  1309. builtin type data.List
  1310. data.List.++ : [a] -> [a] -> [a]
  1311. data.List.++.doc : Doc
  1312. data.List.+: : a -> [a] -> [a]
  1313. data.List.+:.doc : Doc
  1314. data.List.:+ : [a] -> a -> [a]
  1315. data.List.:+.doc : Doc
  1316. data.List.align : [a] -> [b] -> [OneOrBoth a b]
  1317. data.List.align.doc : Doc
  1318. data.List.alignWith : (OneOrBoth a b ->{g} c)
                              -> [a]
                              -> [b]
                              ->{g} [c]
  1319. data.List.alignWith.doc : Doc
  1320. data.List.all : (a ->{e} Boolean) -> [a] ->{e} Boolean
  1321. data.List.all.doc : Doc
  1322. data.List.all.tests.deMorgan : [Result]
  1323. data.List.all.tests.homomorphism : [Result]
  1324. data.List.allPairs : [a] -> [(a, a)]
  1325. data.List.allPairs.doc : Doc
  1326. data.List.any : (a ->{e} Boolean) -> [a] ->{e} Boolean
  1327. data.List.any.doc : Doc
  1328. data.List.any.tests.deMorgan : [Result]
  1329. data.List.any.tests.homomorphism : [Result]
  1330. data.List.anyIndexOf : a -> [a] -> Optional Nat
  1331. data.List.anyIndexOf.doc : Doc
  1332. data.List.anyIndexOf.evaluated.empty : Optional Nat
  1333. data.List.anyIndexOf.evaluated.lower : Optional Nat
  1334. data.List.anyIndexOf.evaluated.notSorted : Optional Nat
  1335. data.List.anyIndexOf.evaluated.sorted : Optional Nat
  1336. data.List.anyIndexOf.evaluated.upper : Optional Nat
  1337. data.List.anyIndexOf.examples.input.lower : [Nat]
  1338. data.List.anyIndexOf.examples.input.notSorted : [Nat]
  1339. data.List.anyIndexOf.examples.input.sorted : [Nat]
  1340. data.List.anyIndexOf.examples.input.upper : [Nat]
  1341. data.List.anyIndexOf.tests.empty : [Result]
  1342. data.List.anyIndexOf.tests.lower : [Result]
  1343. data.List.anyIndexOf.tests.notSorted : [Result]
  1344. data.List.anyIndexOf.tests.sorted : [Result]
  1345. data.List.anyIndexOf.tests.upper : [Result]
  1346. data.List.apply : [a ->{e} b] -> [a] ->{e} [b]
  1347. data.List.apply.doc : Doc
  1348. data.List.at : Nat -> [a] -> Optional a
  1349. data.List.at.doc : Doc
  1350. data.List.at.tests.index : [Result]
  1351. data.List.at! : Nat -> [a] ->{Abort} a
  1352. data.List.at!.doc : Doc
  1353. data.List.chunk : Nat -> [a] -> [[a]]
  1354. data.List.chunk.doc : Doc
  1355. data.List.combinations : Nat -> [a] -> [[a]]
  1356. data.List.combinations.doc : Doc
  1357. data.List.compare : (a ->{f} b ->{g} Ordering)
                            -> [a]
                            -> [b]
                            ->{f, g} Ordering
  1358. data.List.compare.doc : Doc
  1359. data.List.concatOptional : Optional [a] -> [a]
  1360. data.List.concatOptional.doc : Doc
  1361. data.List.concatOptional.tests.prop1 : [Result]
  1362. data.List.concatOptional.tests.test1 : [Result]
  1363. data.List.cons : a -> [a] -> [a]
  1364. data.List.cons.doc : Doc
  1365. data.List.contains : a -> [a] -> Boolean
  1366. data.List.contains.doc : Doc
  1367. data.List.contains.tests.negative1 : [Result]
  1368. data.List.contains.tests.negative2 : [Result]
  1369. data.List.contains.tests.negative3 : [Result]
  1370. data.List.contains.tests.positive : [Result]
  1371. data.List.contains.tests.prop1 : [Result]
  1372. data.List.containsNot : a -> [a] -> Boolean
  1373. data.List.containsNot.doc : Doc
  1374. data.List.count : (a ->{e} Boolean) -> [a] ->{e} Nat
  1375. data.List.count.doc : Doc
  1376. data.List.countElement : a -> [a] -> Nat
  1377. data.List.countElement.doc : Doc
  1378. data.List.deleteAt : Nat -> [a] -> [a]
  1379. data.List.deleteAt.doc : Doc
  1380. data.List.deleteAt.test : [Result]
  1381. data.List.deleteFirst : (a ->{g} Boolean)
                                -> [a]
                                ->{g} [a]
  1382. data.List.deleteFirst.doc : Doc
  1383. data.List.deleteFirst.tests.ex1 : [Result]
  1384. data.List.deleteFirst.tests.ex2 : [Result]
  1385. data.List.deleteFirst.tests.ex3 : [Result]
  1386. data.List.deprecated.lubIndexOf : a -> [a] -> Nat
  1387. data.List.deprecated.lubIndexOf.doc : Doc
  1388. data.List.deprecated.lubIndexOf.evaluated.empty : Nat
  1389. data.List.deprecated.lubIndexOf.evaluated.notSorted : Nat
  1390. data.List.deprecated.lubIndexOf.evaluated.sorted : Nat
  1391. data.List.deprecated.lubIndexOf.tests.empty : [Result]
  1392. data.List.deprecated.lubIndexOf.tests.notSorted : [Result]
  1393. data.List.deprecated.lubIndexOf.tests.sorted : [Result]
  1394. data.List.deprecated.lubIndexOf' : a
                                           -> Nat
                                           -> [a]
                                           -> Nat
  1395. data.List.deprecated.lubIndexOf'.doc : Doc
  1396. data.List.diagonal : [[a]] -> [a]
  1397. data.List.diagonal.doc : Doc
  1398. data.List.diagonals : [[a]] -> [[a]]
  1399. data.List.diagonals.doc : Doc
  1400. data.List.distinct : [a] -> [a]
  1401. data.List.distinct.doc : Doc
  1402. data.List.distinct.tests.preservation : [Result]
  1403. data.List.distinctBy : (a ->{g} b) -> [a] ->{g} [a]
  1404. data.List.distinctBy.doc : Doc
  1405. data.List.distinctBy.tests.preservation : [Result]
  1406. data.List.distinctBy.tests.removesDuplicates : [Result]
  1407. data.List.doc : Doc
  1408. data.List.docs.addingAndRemoving : Doc
  1409. data.List.docs.combining : Doc
  1410. data.List.docs.constructing : Doc
  1411. data.List.docs.converting : Doc
  1412. data.List.docs.elements : Doc
  1413. data.List.docs.nonempty : Doc
  1414. data.List.docs.splittingAndRearranging : Doc
  1415. data.List.docs.traversing : Doc
  1416. data.List.drop : Nat -> [a] -> [a]
  1417. data.List.drop.doc : Doc
  1418. data.List.dropLast : [a] -> [a]
  1419. data.List.dropLast.doc : Doc
  1420. data.List.dropRight : Nat -> [a] -> [a]
  1421. data.List.dropRight.doc : Doc
  1422. data.List.dropRightWhile : (a ->{g} Boolean)
                                   -> [a]
                                   ->{g} [a]
  1423. data.List.dropRightWhile.doc : Doc
  1424. data.List.dropRightWhile.tests : [Result]
  1425. data.List.dropRightWhile.tests.all : [Result]
  1426. data.List.dropRightWhile.tests.last : [Result]
  1427. data.List.dropRightWhile.tests.none : [Result]
  1428. data.List.dropUntil : (a ->{e} Boolean) -> [a] ->{e} [a]
  1429. data.List.dropUntil.doc : Doc
  1430. data.List.dropWhile : (a ->{e} Boolean) -> [a] ->{e} [a]
  1431. data.List.dropWhile.doc : Doc
  1432. data.List.dropWhile.examples.ex1 : [Nat]
  1433. data.List.dropWhile.tests.all : [Result]
  1434. data.List.dropWhile.tests.middle : [Result]
  1435. data.List.dropWhile.tests.none : [Result]
  1436. data.List.empty : [a]
  1437. data.List.empty.doc : Doc
  1438. data.List.equals : (a ->{f} b ->{g} Boolean)
                           -> [a]
                           -> [b]
                           ->{f, g} Boolean
  1439. data.List.equals.doc : Doc
  1440. data.List.every : Nat -> [a] -> [a]
  1441. data.List.every.doc : Doc
  1442. data.List.fill : Nat -> a -> [a]
  1443. data.List.fill.doc : Doc
  1444. data.List.fill.examples.ex1 : [Text]
  1445. data.List.fill.tests.ex1 : [Result]
  1446. data.List.fill' : Nat -> '{g} a ->{g} [a]
  1447. data.List.fill'.doc : Doc
  1448. data.List.fill'.tests : [Result]
  1449. data.List.filter : (a ->{𝕖} Boolean) -> [a] ->{𝕖} [a]
  1450. data.List.filter.doc : Doc
  1451. data.List.filter.tests.empty : [Result]
  1452. data.List.filter.tests.negative : [Result]
  1453. data.List.filter.tests.positive : [Result]
  1454. data.List.filterMap : (a ->{e} Optional b)
                              -> [a]
                              ->{e} [b]
  1455. data.List.filterMap.doc : Doc
  1456. data.List.filterMap.examples.ex1 : [Nat]
  1457. data.List.filterMap.tests.identity : [Result]
  1458. data.List.filterMap.tests.mapsAndFilters : [Result]
  1459. data.List.find : (a ->{g} Boolean)
                         -> [a]
                         ->{g} Optional a
  1460. data.List.find.doc : Doc
  1461. data.List.find.tests.ex1 : [Result]
  1462. data.List.find.tests.ex2 : [Result]
  1463. data.List.find! : (a ->{g} Boolean)
                          -> [a]
                          ->{g, Abort} a
  1464. data.List.find!.doc : Doc
  1465. data.List.findFirstIndex : (a ->{e} Boolean)
                                   -> [a]
                                   ->{e} Optional Nat
  1466. data.List.findLastIndex : (a ->{e} Boolean)
                                  -> [a]
                                  ->{e} Optional Nat
  1467. data.List.findMap : (a ->{g} Optional b)
                            -> [a]
                            ->{g} Optional b
  1468. data.List.findMap.doc : Doc
  1469. data.List.findMap.tests.ex1 : [Result]
  1470. data.List.findMap.tests.ex2 : [Result]
  1471. data.List.firstIndexOf : a -> [a] -> Optional Nat
  1472. data.List.firstIndexOf.doc : Doc
  1473. data.List.firstIndexOf.tests.negative1 : [Result]
  1474. data.List.firstIndexOf.tests.negative2 : [Result]
  1475. data.List.firstIndexOf.tests.negative3 : [Result]
  1476. data.List.firstIndexOf.tests.positive1 : [Result]
  1477. data.List.firstIndexOf.tests.positive2 : [Result]
  1478. data.List.firstIndexOf.tests.positive3 : [Result]
  1479. data.List.flatMap : (a ->{e} [b]) -> [a] ->{e} [b]
  1480. data.List.flatMap.doc : Doc
  1481. data.List.flatMap.examples.ex1 : [Nat]
  1482. data.List.flatMap.examples.ex2 : [Nat]
  1483. data.List.flatMap.tests.associative : [Result]
  1484. data.List.flatMap.tests.flatMapIdentityIsJoin : [Result]
  1485. data.List.flatMap.tests.identity : [Result]
  1486. data.List.flatMapRight : (a ->{e} [b]) -> [a] ->{e} [b]
  1487. data.List.flatMapRight.doc : Doc
  1488. data.List.flatMapRight.examples.ex1 : [Nat]
  1489. data.List.flatMapRight.examples.ex2 : [Nat]
  1490. data.List.flatMapRight.tests.flatMapIdentityIsJoin : [Result]
  1491. data.List.foldDelimited : (b ->{g2} b ->{g1} b)
                                  -> (a ->{g} b)
                                  -> b
                                  -> b
                                  -> b
                                  -> [a]
                                  ->{g, g1, g2} b
  1492. data.List.foldDelimited.doc : Doc
  1493. data.List.foldLeft : (b ->{𝕖} a ->{𝕖} b)
                             -> b
                             -> [a]
                             ->{𝕖} b
  1494. data.List.foldLeft.doc : Doc
  1495. data.List.foldLeft.tests.dual : [Result]
  1496. data.List.foldLeft.tests.endomorphic : [Result]
  1497. data.List.foldLeft.tests.length : [Result]
  1498. data.List.foldMap : (a ->{e} b)
                            -> (b ->{e} b ->{e} b)
                            -> b
                            -> [a]
                            ->{e} b
  1499. data.List.foldMap.doc : Doc
  1500. data.List.foldRight : (a ->{e} b ->{e} b)
                              -> b
                              -> [a]
                              ->{e} b
  1501. data.List.foldRight.doc : Doc
  1502. data.List.foldRight.tests.dual : [Result]
  1503. data.List.foldRight.tests.endomorphic : [Result]
  1504. data.List.foldRight.tests.homomorphism : [Result]
  1505. data.List.foldRight.tests.length : [Result]
  1506. data.List.foreach : (a ->{g} ()) -> [a] ->{g} ()
  1507. data.List.foreach.deprecated : (a ->{g} b)
                                       -> [a]
                                       ->{g} ()
  1508. data.List.foreach.deprecated.doc : Doc
  1509. data.List.foreach.deprecated.tests : [Result]
  1510. data.List.foreach.doc : Doc
  1511. data.List.foreach.flipped : [a] -> (a ->{g} ()) ->{g} ()
  1512. data.List.foreach.flipped.deprecated : [a]
                                               -> (a ->{g} b)
                                               ->{g} ()
  1513. data.List.foreach.flipped.deprecated.doc : Doc
  1514. data.List.foreach.flipped.doc : Doc
  1515. data.List.groupBy : (v ->{e} k)
                            -> [v]
                            ->{e} Map k (List.Nonempty v)
  1516. data.List.groupBy.doc : Doc
  1517. data.List.groupBy.examples.ex1 : [[Nat]]
  1518. data.List.groupBy.examples.ex2 : [[Nat]]
  1519. data.List.groupBy.reversed : (v ->{e} k)
                                     -> [v]
                                     ->{e} Map
                                       k (List.Nonempty v)
  1520. data.List.groupBy.tests.groups : [Result]
  1521. data.List.groupConsecutive : [a] -> [List.Nonempty a]
  1522. data.List.groupConsecutive.doc : Doc
  1523. data.List.groupConsecutive.tests.base : [Result]
  1524. data.List.groupMap : (a ->{e} k)
                             -> (a ->{e} v)
                             -> [a]
                             ->{e} Map k (List.Nonempty v)
  1525. data.List.groupMap.doc : Doc
  1526. data.List.groupMap.tests.groups : [Result]
  1527. data.List.groupMapReduce : (a ->{e} k)
                                   -> (a ->{e} v)
                                   -> (v ->{e} v ->{e} v)
                                   -> [a]
                                   ->{e} Map k v
  1528. data.List.groupMapReduce.doc : Doc
  1529. data.List.groupMapReduce.tests.groups : [Result]
  1530. data.List.groupSublistsBy : (a ->{e} a ->{e} Boolean)
                                    -> [a]
                                    ->{e} [List.Nonempty a]
  1531. data.List.groupSublistsBy.doc : Doc
  1532. data.List.groupSublistsBy.examples.ex1 : [[Nat]]
  1533. data.List.groupSublistsBy.examples.ex2 : [[Nat]]
  1534. data.List.groupWith : (a ->{e} a ->{f} Boolean)
                              -> [a]
                              ->{e, f} [[a]]
  1535. data.List.groupWith.doc : Doc
  1536. data.List.halve : [a] -> ([a], [a])
  1537. data.List.halve.doc : Doc
  1538. data.List.head : [a] -> Optional a
  1539. data.List.head.doc : Doc
  1540. data.List.head.examples.evaluated.elems : Optional Nat
  1541. data.List.head.examples.evaluated.empty : Optional a
  1542. data.List.head.examples.evaluated.single : Optional Nat
  1543. data.List.head.test : [Result]
  1544. data.List.indexed : [a] -> [(a, Nat)]
  1545. data.List.indexed.doc : Doc
  1546. data.List.indexed.tests.isIndexed : [Result]
  1547. data.List.indexOfSublist : [a] -> [a] -> Optional Nat
  1548. data.List.indexOfSublist.doc : Doc
  1549. data.List.init : [a] -> Optional [a]
  1550. data.List.init.doc : Doc
  1551. data.List.initialize : Nat -> (Nat ->{e} a) ->{e} [a]
  1552. data.List.initialize.doc : Doc
  1553. data.List.initialize.examples.ex1 : [Nat]
  1554. data.List.initialize.tests.tests.ex1 : [Result]
  1555. data.List.inits : [a] -> [[a]]
  1556. data.List.inits.doc : Doc
  1557. data.List.insertAfter : (a ->{e} a ->{f} Boolean)
                                -> a
                                -> [a]
                                ->{e, f} [a]
  1558. data.List.insertAfter.doc : Doc
  1559. data.List.insertAt : Nat -> a -> [a] -> [a]
  1560. data.List.insertAt.doc : Doc
  1561. data.List.insertSortedDistinct : a -> [a] -> [a]
  1562. data.List.insertSortedDistinct.doc : Doc
  1563. data.List.insertSortedDistinct.tests : [Result]
  1564. data.List.intercalate : [a] -> [[a]] -> [a]
  1565. data.List.intercalate.doc : Doc
  1566. data.List.intercalate.tests.empty : [Result]
  1567. data.List.intercalate.tests.empty1 : [Result]
  1568. data.List.intercalate.tests.empty2 : [Result]
  1569. data.List.intercalate.tests.simple : [Result]
  1570. data.List.intercalate.tests.size : [Result]
  1571. data.List.interleave : [a] -> [a] -> [a]
  1572. data.List.interleave.doc : Doc
  1573. data.List.intersperse : a -> [a] -> [a]
  1574. data.List.intersperse.doc : Doc
  1575. data.List.intersperse.tests.base : [Result]
  1576. data.List.intersperse.tests.empty : [Result]
  1577. data.List.isEmpty : [a] -> Boolean
  1578. data.List.isEmpty.doc : Doc
  1579. data.List.isInfixOf : [a] -> [a] -> Boolean
  1580. data.List.isInfixOf.doc : Doc
  1581. data.List.isInfixOf.tests.prop1 : [Result]
  1582. data.List.isPrefixOf : [a] -> [a] -> Boolean
  1583. data.List.isPrefixOf.doc : Doc
  1584. data.List.isPrefixOf.tests.prop1 : [Result]
  1585. data.List.isPrefixOf.tests.prop2 : [Result]
  1586. data.List.isSortedBy : (a -> a ->{e} Boolean)
                               -> [a]
                               ->{e} Boolean
  1587. data.List.isSortedBy.doc : Doc
  1588. data.List.isSuffixOf : [a] -> [a] -> Boolean
  1589. data.List.isSuffixOf.doc : Doc
  1590. data.List.isSuffixOf.tests.prop1 : [Result]
  1591. data.List.isSuffixOf.tests.prop2 : [Result]
  1592. data.List.iterate : (a ->{Abort} a) -> a -> [a]
  1593. data.List.iterate.doc : Doc
  1594. data.List.iterate.tests.ex1 : [Result]
  1595. data.List.join : [[a]] -> [a]
  1596. data.List.join.doc : Doc
  1597. data.List.join.tests.associative : [Result]
  1598. data.List.join.tests.homomorphism : [Result]
  1599. data.List.join.tests.unit : [Result]
  1600. data.List.last : [a] -> Optional a
  1601. data.List.last.doc : Doc
  1602. data.List.last.examples.elems : [Nat]
  1603. data.List.last.examples.empty : [a]
  1604. data.List.last.examples.evaluated.elems : Optional Nat
  1605. data.List.last.examples.evaluated.empty : Optional a
  1606. data.List.last.examples.evaluated.single : Optional Nat
  1607. data.List.last.examples.single : [Nat]
  1608. data.List.last.tests.elems : [Result]
  1609. data.List.last.tests.empty : [Result]
  1610. data.List.last.tests.isHeadOnReversedList : [Result]
  1611. data.List.last.tests.single : [Result]
  1612. data.List.lefts : [Either a b] -> [a]
  1613. data.List.lefts.doc : Doc
  1614. data.List.lefts.tests.ex1 : [Result]
  1615. data.List.map : (a ->{𝕖} b) -> [a] ->{𝕖} [b]
  1616. data.List.map.doc : Doc
  1617. data.List.map.tests.functor : [Result]
  1618. data.List.map2 : (a ->{e} b ->{e} c)
                         -> [a]
                         -> [b]
                         ->{e} [c]
  1619. data.List.map2.doc : Doc
  1620. data.List.mapIndexed : (Nat ->{𝕖} a ->{𝕖} b)
                               -> [a]
                               ->{𝕖} [b]
  1621. data.List.mapIndexed.doc : Doc
  1622. data.List.mapIndexed.tests.ex1 : [Result]
  1623. data.List.mapIndexed.tests.ex2 : [Result]
  1624. data.List.mapIndexed.tests.mapsAndIndexes : [Result]
  1625. data.List.mapRight : (a ->{g} b) -> [a] ->{g} [b]
  1626. data.List.mapRight.doc : Doc
  1627. data.List.maximum : [a] -> Optional a
  1628. data.List.maximum.doc : Doc
  1629. data.List.maximum.tests.base : [Result]
  1630. data.List.maximum.tests.empty : [Result]
  1631. data.List.maximumBy : (a ->{e} a ->{e} Ordering)
                              -> [a]
                              ->{e} Optional a
  1632. data.List.maximumOn : (b ->{f} b ->{g} Ordering)
                              -> (a ->{e} b)
                              -> [a]
                              ->{e, f, g} Optional a
  1633. data.List.maximumOn.doc : Doc
  1634. data.List.mayNonempty : [a]
                                -> Optional (List.Nonempty a)
  1635. data.List.mayNonempty.doc : Doc
  1636. data.List.minimum : [a] -> Optional a
  1637. data.List.minimum.doc : Doc
  1638. data.List.minimum.tests.base : [Result]
  1639. data.List.minimumBy : (a ->{e} a ->{e} Ordering)
                              -> [a]
                              ->{e} Optional a
  1640. data.List.modifyAt : Nat
                             -> (a ->{g} a)
                             -> [a]
                             ->{g} Optional [a]
  1641. data.List.modifyAt.doc : Doc
  1642. data.List.modifyAt.tests : [Result]
  1643. data.List.mostFrequent : [a] -> Optional a
  1644. data.List.mostFrequent.doc : Doc
  1645. data.List.none : (i ->{e} Boolean) -> [i] ->{e} Boolean
  1646. data.List.none.doc : Doc
  1647. structural type data.List.Nonempty a
  1648. data.List.nonempty : [a] ->{Abort} List.Nonempty a
  1649. data.List.Nonempty.++ : List.Nonempty a
                                -> List.Nonempty a
                                -> List.Nonempty a
  1650. data.List.Nonempty.++.doc : Doc
  1651. data.List.Nonempty.+| : a -> [a] -> List.Nonempty a
  1652. data.List.Nonempty.+|.doc : Doc
  1653. data.List.Nonempty.align : List.Nonempty a
                                   -> List.Nonempty b
                                   -> List.Nonempty
                                     (OneOrBoth a b)
  1654. data.List.Nonempty.align.doc : Doc
  1655. data.List.Nonempty.align.tests : [Result]
  1656. data.List.Nonempty.alignWith : (OneOrBoth a b ->{g} c)
                                       -> List.Nonempty a
                                       -> List.Nonempty b
                                       ->{g} List.Nonempty c
  1657. data.List.Nonempty.alignWith.doc : Doc
  1658. data.List.Nonempty.alignWith.tests : [Result]
  1659. data.List.Nonempty.append : List.Nonempty a
                                    -> List.Nonempty a
                                    -> List.Nonempty a
  1660. data.List.Nonempty.append.doc : Doc
  1661. data.List.Nonempty.append.tests.associative : [Result]
  1662. data.List.Nonempty.append.tests.homomorphism : [Result]
  1663. data.List.Nonempty.appendList : List.Nonempty a
                                        -> [a]
                                        -> List.Nonempty a
  1664. data.List.Nonempty.appendList.doc : Doc
  1665. data.List.Nonempty.at : Nat
                                -> List.Nonempty a
                                -> Optional a
  1666. data.List.Nonempty.at.doc : Doc
  1667. data.List.Nonempty.cons : a
                                  -> List.Nonempty a
                                  -> List.Nonempty a
  1668. data.List.Nonempty.cons.doc : Doc
  1669. data.List.Nonempty.doc : Doc
  1670. data.List.nonempty.doc : Doc
  1671. data.List.Nonempty.examples.construction.ex1 : List.Nonempty
                                                         Nat
  1672. data.List.Nonempty.examples.construction.ex2 : Optional
                                                         (List.Nonempty
                                                           Nat)
  1673. data.List.Nonempty.filterMap : (a ->{g} Optional b)
                                       -> List.Nonempty a
                                       ->{g} Optional
                                         (List.Nonempty b)
  1674. data.List.Nonempty.filterMap.doc : Doc
  1675. data.List.Nonempty.filterMap.test.example : [Result]
  1676. data.List.Nonempty.flatMap : (a ->{e} List.Nonempty b)
                                     -> List.Nonempty a
                                     ->{e} List.Nonempty b
  1677. data.List.Nonempty.flatMap.doc : Doc
  1678. data.List.Nonempty.flatMap.tests.flatMapIdIsjoin : [Result]
  1679. data.List.Nonempty.foldLeft : (b ->{e} a ->{e} b)
                                      -> b
                                      -> List.Nonempty a
                                      ->{e} b
  1680. data.List.Nonempty.foldLeft.doc : Doc
  1681. data.List.Nonempty.foldLeft.tests.listConsistency : [Result]
  1682. data.List.Nonempty.foldLeft.tests.multiple : [Result]
  1683. data.List.Nonempty.foldLeft.tests.single : [Result]
  1684. data.List.Nonempty.foldMap : (b ->{e} b ->{e} b)
                                     -> (a ->{e} b)
                                     -> List.Nonempty a
                                     ->{e} b
  1685. data.List.Nonempty.foldMap.doc : Doc
  1686. data.List.Nonempty.foldMap.examples.ex1 : Text
  1687. data.List.Nonempty.foldMap.test : [Result]
  1688. data.List.Nonempty.foldRight : (a ->{e} b ->{e} b)
                                       -> b
                                       -> List.Nonempty a
                                       ->{e} b
  1689. data.List.Nonempty.foldRight.doc : Doc
  1690. data.List.Nonempty.foldRight.tests.listConsistency : [Result]
  1691. data.List.Nonempty.foldRight.tests.multiple : [Result]
  1692. data.List.Nonempty.foldRight.tests.single : [Result]
  1693. data.List.Nonempty.head : List.Nonempty a -> a
  1694. data.List.Nonempty.head.doc : Doc
  1695. data.List.Nonempty.head.test : [Result]
  1696. data.List.Nonempty.init : List.Nonempty a -> [a]
  1697. data.List.Nonempty.init.doc : Doc
  1698. data.List.Nonempty.init.test : [Result]
  1699. data.List.Nonempty.join : List.Nonempty
                                    (List.Nonempty a)
                                  -> List.Nonempty a
  1700. data.List.Nonempty.join.doc : Doc
  1701. data.List.Nonempty.join.examples.ex1 : List.Nonempty Nat
  1702. data.List.Nonempty.join.tests.associative : [Result]
  1703. data.List.Nonempty.join.tests.unit : [Result]
  1704. data.List.Nonempty.last : List.Nonempty a -> a
  1705. data.List.Nonempty.last.doc : Doc
  1706. data.List.Nonempty.last.test : [Result]
  1707. data.List.Nonempty.map : (a ->{e} b)
                                 -> List.Nonempty a
                                 ->{e} List.Nonempty b
  1708. data.List.Nonempty.map.doc : Doc
  1709. data.List.Nonempty.map.tests.functor : [Result]
  1710. data.List.Nonempty.maximum : List.Nonempty a -> a
  1711. data.List.Nonempty.maximum.doc : Doc
  1712. data.List.Nonempty.maximum.test : [Result]
  1713. data.List.Nonempty.maximumBy : (a
                                       ->{e} a
                                       ->{e} Ordering)
                                       -> List.Nonempty a
                                       ->{e} a
  1714. data.List.Nonempty.maximumBy.doc : Doc
  1715. data.List.Nonempty.maximumBy.test : [Result]
  1716. data.List.Nonempty.minimum : List.Nonempty a -> a
  1717. data.List.Nonempty.minimum.doc : Doc
  1718. data.List.Nonempty.minimum.test : [Result]
  1719. data.List.Nonempty.minimumBy : (a
                                       ->{e} a
                                       ->{e} Ordering)
                                       -> List.Nonempty a
                                       ->{e} a
  1720. data.List.Nonempty.minimumBy.doc : Doc
  1721. data.List.Nonempty.minimumBy.test : [Result]
  1722. data.List.Nonempty.Nonempty : a
                                      -> [a]
                                      -> List.Nonempty a
  1723. data.List.Nonempty.prependList : [a]
                                         -> List.Nonempty a
                                         -> List.Nonempty a
  1724. data.List.Nonempty.prependList.doc : Doc
  1725. data.List.Nonempty.randomChoice : List.Nonempty a
                                          ->{Random} a
  1726. data.List.Nonempty.randomChoice.doc : Doc
  1727. data.List.Nonempty.randomChoice.test : [Result]
  1728. data.List.Nonempty.reduceLeft : (a ->{e} a ->{e} a)
                                        -> List.Nonempty a
                                        ->{e} a
  1729. data.List.Nonempty.reduceLeft.doc : Doc
  1730. data.List.Nonempty.reduceLeft.test : [Result]
  1731. data.List.Nonempty.reduceRight : (a ->{e} a ->{e} a)
                                         -> List.Nonempty a
                                         ->{e} a
  1732. data.List.Nonempty.reduceRight.doc : Doc
  1733. data.List.Nonempty.reduceRight.test : [Result]
  1734. data.List.Nonempty.reverse : List.Nonempty a
                                     -> List.Nonempty a
  1735. data.List.Nonempty.reverse.doc : Doc
  1736. data.List.Nonempty.scanLeft : (a ->{e} a ->{e} a)
                                      -> List.Nonempty a
                                      ->{e} List.Nonempty a
  1737. data.List.Nonempty.scanLeft.doc : Doc
  1738. data.List.Nonempty.scanLeft.test : [Result]
  1739. data.List.Nonempty.scanRight : (a ->{e} a ->{e} a)
                                       -> List.Nonempty a
                                       ->{e} List.Nonempty a
  1740. data.List.Nonempty.scanRight.doc : Doc
  1741. data.List.Nonempty.scanRight.test : [Result]
  1742. data.List.Nonempty.sequenceOptional : List.Nonempty
                                                (Optional a)
                                              -> Optional
                                                (List.Nonempty a)
  1743. data.List.Nonempty.sequenceOptional.doc : Doc
  1744. data.List.Nonempty.sequenceOptional.test.example : [Result]
  1745. data.List.Nonempty.singleton : a -> List.Nonempty a
  1746. data.List.Nonempty.singleton.doc : Doc
  1747. data.List.Nonempty.singleton.test : [Result]
  1748. data.List.Nonempty.size : List.Nonempty a -> Nat
  1749. data.List.Nonempty.size.doc : Doc
  1750. data.List.Nonempty.size.test : [Result]
  1751. data.List.Nonempty.snoc : List.Nonempty a
                                  -> a
                                  -> List.Nonempty a
  1752. data.List.Nonempty.snoc.doc : Doc
  1753. data.List.Nonempty.somes : List.Nonempty (Optional a)
                                   -> Optional (List.Nonempty a)
  1754. data.List.Nonempty.somes.doc : Doc
  1755. data.List.Nonempty.somes.tests.ex1 : [Result]
  1756. data.List.Nonempty.tail : List.Nonempty a -> [a]
  1757. data.List.Nonempty.tail.doc : Doc
  1758. data.List.Nonempty.tail.test : [Result]
  1759. data.List.Nonempty.toList : List.Nonempty a -> [a]
  1760. data.List.Nonempty.toList.doc : Doc
  1761. data.List.Nonempty.toSet : List.Nonempty a -> Set a
  1762. data.List.Nonempty.toSet.doc : Doc
  1763. data.List.Nonempty.traverseOptional : (a
                                              ->{g} Optional b)
                                              -> List.Nonempty a
                                              ->{g} Optional
                                                (List.Nonempty b)
  1764. data.List.Nonempty.traverseOptional.doc : Doc
  1765. data.List.Nonempty.traverseOptional.test.example : [Result]
  1766. data.List.Nonempty.zipWith : (a ->{g1} b ->{g} c)
                                     -> List.Nonempty a
                                     -> List.Nonempty b
                                     ->{g1, g} List.Nonempty c
  1767. data.List.Nonempty.zipWith.doc : Doc
  1768. data.List.Nonempty.|+ : [a] -> a -> List.Nonempty a
  1769. data.List.Nonempty.|+.doc : Doc
  1770. data.List.nonEmptySubsequences : [a]
                                         -> [List.Nonempty a]
  1771. data.List.nonEmptySubsequences.doc : Doc
  1772. data.List.nonEmptySubsequences.tests.base : [Result]
  1773. data.List.of : x -> Nat -> [x]
  1774. data.List.of.doc : Doc
  1775. data.List.partition : (a ->{g} Boolean)
                              -> [a]
                              ->{g} ([a], [a])
  1776. data.List.partition.doc : Doc
  1777. data.List.partitionBy : (a ->{g} Boolean)
                                -> [a]
                                ->{g} [List.Nonempty a]
  1778. data.List.partitionBy.doc : Doc
  1779. data.List.partitionEithers : [Either a b] -> ([a], [b])
  1780. data.List.partitionEithers.doc : Doc
  1781. data.List.partitionEithers.tests.ex1 : [Result]
  1782. data.List.partitionMap : (a ->{g} Either b c)
                                 -> [a]
                                 ->{g} ([b], [c])
  1783. data.List.partitionMap.doc : Doc
  1784. data.List.powerslice : [a] -> [[a]]
  1785. data.List.powerslice.doc : Doc
  1786. data.List.powerslice.examples.ex1 : [[Nat]]
  1787. data.List.powerslice.examples.ex2 : [[a]]
  1788. data.List.powerslice.tests.prop1 : [Result]
  1789. data.List.powerslice.tests.test1 : [Result]
  1790. data.List.randomChoice : [a] ->{Exception, Random} a
  1791. data.List.randomChoice.doc : Doc
  1792. data.List.randomChoice.test : [Result]
  1793. data.List.range : Nat -> Nat -> [Nat]
  1794. data.List.range.doc : Doc
  1795. data.List.rangeClosed : Nat -> Nat -> [Nat]
  1796. data.List.rangeClosed.doc : Doc
  1797. data.List.rangeClosed.tests.empty : [Result]
  1798. data.List.rangeClosed.tests.empty2 : [Result]
  1799. data.List.rangeClosed.tests.empty3 : [Result]
  1800. data.List.rangeClosed.tests.fromBig : [Result]
  1801. data.List.rangeClosed.tests.fromOne : [Result]
  1802. data.List.rangeClosed.tests.fromZero : [Result]
  1803. data.List.rangeClosed.tests.rangeSize : [Result]
  1804. data.List.rangeClosed.tests.single0 : [Result]
  1805. data.List.rangeClosed.tests.single1 : [Result]
  1806. data.List.rangeClosed.tests.single99 : [Result]
  1807. data.List.rangeClosed.tests._checkRangeClosed : Nat
                                                        -> Nat
                                                        -> [Nat]
                                                        -> [Result]
  1808. data.List.replace : Nat -> a -> [a] -> [a]
  1809. data.List.replace.doc : Doc
  1810. data.List.replicate : Nat -> '{e} a ->{e} [a]
  1811. data.List.replicate.doc : Doc
  1812. data.List.replicate.test : [Result]
  1813. data.List.replicate.test.doc : Doc
  1814. data.List.reverse : [a] -> [a]
  1815. data.List.reverse.doc : Doc
  1816. data.List.rights : [Either a b] -> [b]
  1817. data.List.rights.doc : Doc
  1818. data.List.rights.tests.ex1 : [Result]
  1819. data.List.scanLeft : (b ->{e} a ->{e} b)
                             -> b
                             -> [a]
                             ->{e} List.Nonempty b
  1820. data.List.scanLeft.doc : Doc
  1821. data.List.scanLeft.examples.ex1 : List.Nonempty Nat
  1822. data.List.scanLeft.examples.ex2 : List.Nonempty Nat
  1823. data.List.scanLeft.examples.ex3 : List.Nonempty Nat
  1824. data.List.scanLeft.examples.ex4 : List.Nonempty Nat
  1825. data.List.scanLeft.examples.ex5 : List.Nonempty Nat
  1826. data.List.scanLeft.test : [Result]
  1827. data.List.scanRight : (a ->{e} b ->{e} b)
                              -> b
                              -> [a]
                              ->{e} List.Nonempty b
  1828. data.List.scanRight.doc : Doc
  1829. data.List.scanRight.examples.ex1 : List.Nonempty Nat
  1830. data.List.scanRight.examples.ex2 : List.Nonempty Nat
  1831. data.List.scanRight.examples.ex3 : List.Nonempty Nat
  1832. data.List.scanRight.examples.ex4 : List.Nonempty Boolean
  1833. data.List.scanRight.examples.ex5 : List.Nonempty Nat
  1834. data.List.scanRight.test : [Result]
  1835. data.List.sequenceOptional : [Optional a]
                                     -> Optional [a]
  1836. data.List.sequenceOptional.doc : Doc
  1837. data.List.singleton : a -> [a]
  1838. data.List.singleton.doc : Doc
  1839. data.List.size : [a] -> Nat
  1840. data.List.size.doc : Doc
  1841. data.List.skip : Nat -> [a] -> [a]
  1842. data.List.skip.doc : Doc
  1843. data.List.slice : Nat -> Nat -> [a] -> [a]
  1844. data.List.slice.doc : Doc
  1845. data.List.slidingPairs : [a] -> [(a, a)]
  1846. data.List.slidingPairs.doc : Doc
  1847. data.List.slidingPairs.tests.concat : [Result]
  1848. data.List.slidingWindow : Nat -> [a] -> [[a]]
  1849. data.List.slidingWindow.doc : Doc
  1850. data.List.slidingWindow.tests.ex1 : [Result]
  1851. data.List.slidingWindow.tests.ex2 : [Result]
  1852. data.List.slidingWindow.tests.ex3 : [Result]
  1853. data.List.slidingWindow.tests.ex4 : [Result]
  1854. data.List.slidingWindow.tests.ex5 : [Result]
  1855. data.List.slidingWindow.tests.isSlidingPairsForLength2 : [Result]
  1856. data.List.snoc : [a] -> a -> [a]
  1857. data.List.snoc.doc : Doc
  1858. data.List.snoc.tests.isReversedConsOnReversedList : [Result]
  1859. data.List.somes : [Optional a] -> [a]
  1860. data.List.somes.doc : Doc
  1861. data.List.somes.tests.ex1 : [Result]
  1862. data.List.sort : [a] -> [a]
  1863. data.List.sort.doc : Doc
  1864. data.List.sort.test : [Result]
  1865. data.List.sortBy : (a ->{e} b) -> [a] ->{e} [a]
  1866. data.List.sortBy.doc : Doc
  1867. data.List.sortWith : (a -> a ->{e} Boolean)
                             -> [a]
                             ->{e} [a]
  1868. data.List.sortWith.doc : Doc
  1869. data.List.sortWith.tests.isOrdered : [Result]
  1870. data.List.sortWith.tests.length : [Result]
  1871. data.List.sortWith.tests.permutation : [Result]
  1872. data.List.span : (a ->{e} Boolean)
                         -> [a]
                         ->{e} ([a], [a])
  1873. data.List.span.doc : Doc
  1874. data.List.span.tests.alle : [Result]
  1875. data.List.span.tests.allf : [Result]
  1876. data.List.span.tests.middle : [Result]
  1877. data.List.split : (a ->{e} Boolean) -> [a] ->{e} [[a]]
  1878. data.List.split.doc : Doc
  1879. data.List.split.tests.base : [Result]
  1880. data.List.split.tests.double : [Result]
  1881. data.List.split.tests.empty : [Result]
  1882. data.List.splitAt : Nat -> [a] -> ([a], [a])
  1883. data.List.splitAt.doc : Doc
  1884. data.List.splitAt.tests.base : [Result]
  1885. data.List.splitAt.tests.ob : [Result]
  1886. data.List.splitAt.tests.zero : [Result]
  1887. data.List.stripPrefix : [a] -> [a] -> Optional [a]
  1888. data.List.stripPrefix.doc : Doc
  1889. data.List.stripPrefix.tests.all : [Result]
  1890. data.List.stripPrefix.tests.base : [Result]
  1891. data.List.stripPrefix.tests.none : [Result]
  1892. data.List.subsequences : [a] -> [[a]]
  1893. data.List.subsequences.doc : Doc
  1894. data.List.subsequences.tests.base : [Result]
  1895. data.List.tail : [a] -> Optional [a]
  1896. data.List.tail.doc : Doc
  1897. data.List.tail.tests.isReversedInitOnReversedList : [Result]
  1898. data.List.tail.tests.prop1 : [Result]
  1899. data.List.tail.tests.test1 : [Result]
  1900. data.List.tail.tests.test2 : [Result]
  1901. data.List.tails : [a] -> [[a]]
  1902. data.List.tails.doc : Doc
  1903. data.List.take : Nat -> [a] -> [a]
  1904. data.List.take.doc : Doc
  1905. data.List.takeRight : Nat -> [a] -> [a]
  1906. data.List.takeRight.doc : Doc
  1907. data.List.takeUntil : (a ->{e} Boolean) -> [a] ->{e} [a]
  1908. data.List.takeUntil.doc : Doc
  1909. data.List.takeWhile : (a ->{e} Boolean) -> [a] ->{e} [a]
  1910. data.List.takeWhile.doc : Doc
  1911. data.List.takeWhile.tests.all : [Result]
  1912. data.List.takeWhile.tests.middle : [Result]
  1913. data.List.takeWhile.tests.none : [Result]
  1914. data.List.tests.sequenceOptional.empty : [Result]
  1915. data.List.tests.sequenceOptional.non_empty : [Result]
  1916. data.List.tests.sequenceOptional.non_empty_2 : [Result]
  1917. data.List.tests.traverseOptional.empty : [Result]
  1918. data.List.tests.traverseOptional.non_empty : [Result]
  1919. data.List.tests.traverseOptional.non_empty_2 : [Result]
  1920. data.List.toBag : [k] -> Bag k
  1921. data.List.toBag.doc : Doc
  1922. data.List.toMap : [(k, v)] -> Map k v
  1923. data.List.toMap.doc : Doc
  1924. data.List.toSet : [k] -> Set k
  1925. data.List.toSet.doc : Doc
  1926. data.List.toStream : [a] ->{Stream a} ()
  1927. data.List.toStream.doc : Doc
  1928. data.List.toText : (a ->{g} Text) -> [a] ->{g} Text
  1929. data.List.toText.doc : Doc
  1930. data.List.toText.tests : [Result]
  1931. data.List.transpose : [[a]] -> [[a]]
  1932. data.List.transpose.doc : Doc
  1933. data.List.transpose.tests.identityProp : [Result]
  1934. data.List.transpose.tests.joinProp : [Result]
  1935. data.List.transpose.tests.lengthProp : [Result]
  1936. data.List.traverseOptional : (a ->{g} Optional b)
                                     -> [a]
                                     ->{g} Optional [b]
  1937. data.List.traverseOptional.doc : Doc
  1938. data.List.uncollate : [a] -> ([a], [a])
  1939. data.List.uncollate.doc : Doc
  1940. data.List.uncons : [a] -> Optional (a, [a])
  1941. data.List.uncons.doc : Doc
  1942. data.List.uncons.tests.applyOrEmpty : (i1
                                              ->{g1} i
                                              ->{g} [elem])
                                              -> Optional
                                                (i1, i)
                                              ->{g1, g} [elem]
  1943. data.List.uncons.tests.isHeadAndTailMerged : [Result]
  1944. data.List.uncons.tests.isInverseOfCons : [Result]
  1945. data.List.uncons.tests.isReversedUnsnocOnReversedList : [Result]
  1946. data.List.uncons.tests.merge : (Optional a1, Optional a)
                                       -> Optional (a1, a)
  1947. data.List.unfold : s
                           -> (s ->{𝕖} Optional (a, s))
                           ->{𝕖} [a]
  1948. data.List.unfold.doc : Doc
  1949. data.List.unsafeAt : Nat -> [a] -> a
  1950. data.List.unsafeAt.doc : Doc
  1951. data.List.unsnoc : [a] -> Optional ([a], a)
  1952. data.List.unsnoc.doc : Doc
  1953. data.List.unsnoc.tests.isInitAndLastMerged : [Result]
  1954. data.List.unsnoc.tests.isInverseOfSnoc : [Result]
  1955. data.List.unzip : [(a, b)] -> ([a], [b])
  1956. data.List.unzip.doc : Doc
  1957. data.List.updateAt : (a ->{g1} a)
                             -> Nat
                             -> [a]
                             ->{g1} [a]
  1958. data.List.updateAt.doc : Doc
  1959. data.List.updateAt.tests.updates : [Result]
  1960. data.List.zip : [a] -> [b] -> [(a, b)]
  1961. data.List.zip.doc : Doc
  1962. data.List.zip.tests.length : [Result]
  1963. data.List.zip.tests.productLaw : [Result]
  1964. data.List.zipWith : (a ->{𝕖} b ->{𝕖} c)
                            -> [a]
                            -> [b]
                            ->{𝕖} [c]
  1965. data.List.zipWith.doc : Doc
  1966. data.List.zipWith.tests.edge1 : [Result]
  1967. data.List.zipWith.tests.edge2 : [Result]
  1968. data.List.zipWith.tests.edge3 : [Result]
  1969. data.List.zipWith.tests.edge4 : [Result]
  1970. data.List.zipWith.tests.ex1 : [Result]
  1971. data.List.zipWith.tests.ex2 : [Result]
  1972. data.List.zipWith.tests.zipWithRange : [Result]
  1973. type data.Map k v
  1974. data.Map.== : Map k v -> Map k v -> Boolean
  1975. data.Map.==.doc : Doc
  1976. data.Map.==.tests.reflexive : [Result]
  1977. data.Map.==.tests.symmetric : [Result]
  1978. data.Map.==.tests.transitive : [Result]
  1979. data.Map.adjust : (v ->{e} v)
                          -> k
                          -> Map k v
                          ->{e} Map k v
  1980. data.Map.adjust.doc : Doc
  1981. data.Map.adjust.tests.adjusts : [Result]
  1982. data.Map.adjust.tests.alterMap : [Result]
  1983. data.Map.adjustWithKey : (k ->{e} v ->{e} v)
                                 -> k
                                 -> Map k v
                                 ->{e} Map k v
  1984. data.Map.adjustWithKey.doc : Doc
  1985. data.Map.adjustWithKey.tests.adjusts : [Result]
  1986. data.Map.align : Map k a
                         -> Map k b
                         -> Map k (OneOrBoth a b)
  1987. data.Map.align.doc : Doc
  1988. data.Map.alignWith : (OneOrBoth a b ->{g} c)
                             -> Map k a
                             -> Map k b
                             ->{g} Map k c
  1989. data.Map.alignWith.doc : Doc
  1990. data.Map.alignWithKey : (k ->{e} OneOrBoth a b ->{f} c)
                                -> Map k a
                                -> Map k b
                                ->{e, f} Map k c
  1991. data.Map.alignWithKey.doc : Doc
  1992. data.Map.alignWithKey.tests.effects : [Result]
  1993. data.Map.alter : (Optional v ->{e} Optional v)
                         -> k
                         -> Map k v
                         ->{e} Map k v
  1994. data.Map.alter.doc : Doc
  1995. data.Map.alter.tests.functor : [Result]
  1996. data.Map.alter.tests.homomorphism : [Result]
  1997. data.Map.alter.tests.naturality : [Result]
  1998. data.Map.breakOffMax : Map k v
                               -> Optional ((k, v), Map k v)
  1999. data.Map.breakOffMax.doc : Doc
  2000. data.Map.breakOffMax.tests.isMax : [Result]
  2001. data.Map.breakOffMax! : Map k v
                                ->{Abort} ((k, v), Map k v)
  2002. data.Map.breakOffMax!.doc : Doc
  2003. data.Map.breakOffMin : Map k v
                               -> Optional ((k, v), Map k v)
  2004. data.Map.breakOffMin.doc : Doc
  2005. data.Map.breakOffMin.tests.isMin : [Result]
  2006. data.Map.breakOffMin! : Map k v
                                ->{Abort} ((k, v), Map k v)
  2007. data.Map.breakOffMin!.doc : Doc
  2008. data.Map.contains : k -> Map k v -> Boolean
  2009. data.Map.contains.doc : Doc
  2010. data.Map.contains.tests.delete : [Result]
  2011. data.Map.contains.tests.put : [Result]
  2012. data.Map.delete : k -> Map k v -> Map k v
  2013. data.Map.delete.doc : Doc
  2014. data.Map.delete.tests.deletes : [Result]
  2015. data.Map.delete.tests.preservesOtherKeys : [Result]
  2016. data.Map.difference : Map k a -> Map k b -> Map k a
  2017. data.Map.difference.doc : Doc
  2018. data.Map.difference.tests.prop : [Result]
  2019. data.Map.doc : Doc
  2020. data.Map.empty : Map k v
  2021. data.Map.empty.doc : Doc
  2022. data.Map.filter : (v ->{g} Boolean)
                          -> Map k v
                          ->{g} Map k v
  2023. data.Map.filter.doc : Doc
  2024. data.Map.filterAlignWithKey : (k
                                      ->{e} OneOrBoth a b
                                      ->{f} Optional c)
                                      -> Map k a
                                      -> Map k b
                                      ->{e, f} Map k c
  2025. data.Map.filterAlignWithKey.doc : Doc
  2026. data.Map.filterAlignWithKey.tests.difference : [Result]
  2027. data.Map.filterAlignWithKey.tests.effects : [Result]
  2028. data.Map.filterAlignWithKey.tests.empty : [Result]
  2029. data.Map.filterAlignWithKey.tests.intersection : [Result]
  2030. data.Map.filterAlignWithKey.tests.leftIdentity : [Result]
  2031. data.Map.filterAlignWithKey.tests.rightIdentity : [Result]
  2032. data.Map.filterAlignWithKey.tests.union : [Result]
  2033. data.Map.filterKeys : (k ->{g} Boolean)
                              -> Map k v
                              ->{g} Map k v
  2034. data.Map.filterKeys.doc : Doc
  2035. data.Map.filterWithKey : (k ->{e} a ->{f} Boolean)
                                 -> Map k a
                                 ->{e, f} Map k a
  2036. data.Map.filterWithKey.doc : Doc
  2037. data.Map.filterWithKey.tests.emptyFiltersEverything : [Result]
  2038. data.Map.filterWithKey.tests.filterComposition : [Result]
  2039. data.Map.filterWithKey.tests.filtersDeleted : [Result]
  2040. data.Map.filterWithKey.tests.filtersInserted : [Result]
  2041. data.Map.filterWithKey.tests.trueIdentity : [Result]
  2042. data.Map.foldLeft : (a ->{e} b ->{e} a)
                            -> a
                            -> Map k b
                            ->{e} a
  2043. data.Map.foldLeft.doc : Doc
  2044. data.Map.foldLeft.tests.onElements : [Result]
  2045. data.Map.foldLeftWithKey : (a ->{e} k ->{e} b ->{e} a)
                                   -> a
                                   -> Map k b
                                   ->{e} a
  2046. data.Map.foldLeftWithKey.doc : Doc
  2047. data.Map.foldLeftWithKey.tests.onAssoc : [Result]
  2048. data.Map.foldMap : (a ->{e} a ->{e} a)
                           -> (k ->{e} v ->{e} a)
                           -> Map k v
                           ->{e} Optional a
  2049. data.Map.foldMap.doc : Doc
  2050. data.Map.foldRight : (a ->{e} b ->{e} b)
                             -> b
                             -> Map k a
                             ->{e} b
  2051. data.Map.foldRight.doc : Doc
  2052. data.Map.foldRight.tests.onElements : [Result]
  2053. data.Map.foldRightWithKey : (k ->{e} a ->{e} b ->{e} b)
                                    -> b
                                    -> Map k a
                                    ->{e} b
  2054. data.Map.foldRightWithKey.doc : Doc
  2055. data.Map.foldRightWithKey.tests.onElements : [Result]
  2056. data.Map.foreach : Map k v
                           -> (k ->{e} v ->{e} ())
                           ->{e} ()
  2057. data.Map.foreach.doc : Doc
  2058. data.Map.fromList : [(k, v)] -> Map k v
  2059. data.Map.fromList.doc : Doc
  2060. data.Map.fromList.tests.roundtrip : [Result]
  2061. data.Map.fromListWith : (v ->{e} v ->{e} v)
                                -> [(k, v)]
                                ->{e} Map k v
  2062. data.Map.fromListWith.doc : Doc
  2063. data.Map.fromListWith.tests.roundtrip : [Result]
  2064. data.Map.fromListWithKey : (k ->{e} v ->{e} v ->{e} v)
                                   -> [(k, v)]
                                   ->{e} Map k v
  2065. data.Map.fromListWithKey.doc : Doc
  2066. data.Map.fromListWithKey.tests.roundtrip : [Result]
  2067. data.Map.get : k -> Map k v -> Optional v
  2068. data.Map.get.doc : Doc
  2069. data.Map.get.tests.spec : [Result]
  2070. data.Map.getMax : Map k v -> Optional (k, v)
  2071. data.Map.getMax.doc : Doc
  2072. data.Map.getMax.tests.isMax : [Result]
  2073. data.Map.getMin : Map k v -> Optional (k, v)
  2074. data.Map.getMin.doc : Doc
  2075. data.Map.getMin.tests.isMin : [Result]
  2076. data.Map.getOrAbort : k -> Map k v ->{Abort} v
  2077. data.Map.getOrAbort.doc : Doc
  2078. data.Map.getOrElse : v -> k -> Map k v -> v
  2079. data.Map.getOrElse.doc : Doc
  2080. data.Map.getOrElse.tests.spec : [Result]
  2081. data.Map.getOrThrow : e -> k -> Map k v ->{Throw e} v
  2082. data.Map.getOrThrow.doc : Doc
  2083. data.Map.insert : k -> v -> Map k v -> Map k v
  2084. data.Map.insert.doc : Doc
  2085. data.Map.insertIfMissing : k
                                   -> '{g} v
                                   -> Map k v
                                   ->{g} (Map k v, Either v v)
  2086. data.Map.insertIfMissing.doc : Doc
  2087. data.Map.insertNonempty : k
                                  -> v
                                  -> Map k v
                                  -> Map.Nonempty k v
  2088. data.Map.insertNonempty.doc : Doc
  2089. data.Map.internal.balance : k
                                    -> v
                                    -> Map k v
                                    -> Map k v
                                    -> Map k v
  2090. data.Map.internal.balanceL : k
                                     -> v
                                     -> Map k v
                                     -> Map k v
                                     -> Map k v
  2091. data.Map.internal.balanceR : k
                                     -> v
                                     -> Map k v
                                     -> Map k v
                                     -> Map k v
  2092. data.Map.internal.bin : k
                                -> v
                                -> Map k v
                                -> Map k v
                                -> Map k v
  2093. data.Map.internal.Bin : Nat
                                -> k
                                -> v
                                -> Map k v
                                -> Map k v
                                -> Map k v
  2094. data.Map.internal.delta : Nat
  2095. data.Map.internal.glue : Map k v -> Map k v -> Map k v
  2096. data.Map.internal.link : k
                                 -> v
                                 -> Map k v
                                 -> Map k v
                                 -> Map k v
  2097. data.Map.internal.link2 : Map k v -> Map k v -> Map k v
  2098. type data.Map.internal.MaxView k v
  2099. data.Map.internal.MaxView.MaxView : k
                                            -> v
                                            -> Map k v
                                            -> MaxView k v
  2100. data.Map.internal.maxViewSure : k
                                        -> v
                                        -> Map k v
                                        -> Map k v
                                        -> MaxView k v
  2101. type data.Map.internal.MinView k v
  2102. data.Map.internal.MinView.MinView : k
                                            -> v
                                            -> Map k v
                                            -> MinView k v
  2103. data.Map.internal.minViewSure : k
                                        -> v
                                        -> Map k v
                                        -> Map k v
                                        -> MinView k v
  2104. data.Map.internal.putMax : k -> v -> Map k v -> Map k v
  2105. data.Map.internal.putMin : k -> v -> Map k v -> Map k v
  2106. data.Map.internal.putWithKeyR : (k
                                        ->{e} v
                                        ->{e} v
                                        ->{e} v)
                                        -> k
                                        -> v
                                        -> Map k v
                                        ->{e} Map k v
  2107. data.Map.internal.putWithR : (v ->{e} v ->{e} v)
                                     -> k
                                     -> v
                                     -> Map k v
                                     ->{e} Map k v
  2108. data.Map.internal.ratio : Nat
  2109. data.Map.internal.splitLookup : k
                                        -> Map k v
                                        -> ( Map k v,
                                          Optional v,
                                          Map k v)
  2110. data.Map.internal.Tip : Map k v
  2111. data.Map.intersect : Map k a -> Map k b -> Map k a
  2112. data.Map.intersect.doc : Doc
  2113. data.Map.intersect.tests.associative : [Result]
  2114. data.Map.intersect.tests.idempotent : [Result]
  2115. data.Map.intersect.tests.zero : [Result]
  2116. data.Map.intersectWith : (a ->{e} b ->{e} c)
                                 -> Map k a
                                 -> Map k b
                                 ->{e} Map k c
  2117. data.Map.intersectWith.doc : Doc
  2118. data.Map.intersectWith.tests.commutative : [Result]
  2119. data.Map.intersectWith.tests.idempotent : [Result]
  2120. data.Map.intersectWith.tests.zero : [Result]
  2121. data.Map.intersectWithKey : (k ->{e} a ->{e} b ->{e} c)
                                    -> Map k a
                                    -> Map k b
                                    ->{e} Map k c
  2122. data.Map.intersectWithKey.doc : Doc
  2123. data.Map.intersectWithKey.tests.commutative : [Result]
  2124. data.Map.intersectWithKey.tests.idempotent : [Result]
  2125. data.Map.intersectWithKey.tests.zero : [Result]
  2126. data.Map.isEmpty : Map k v -> Boolean
  2127. data.Map.isEmpty.doc : Doc
  2128. data.Map.isEmpty.tests.spec : [Result]
  2129. data.Map.keys : Map k a -> [k]
  2130. data.Map.keys.doc : Doc
  2131. data.Map.keys.tests.spec : [Result]
  2132. data.Map.lookup : k -> Map k v -> Optional v
  2133. data.Map.lookup.doc : Doc
  2134. data.Map.map : (a ->{e} b) -> Map k a ->{e} Map k b
  2135. data.Map.map.doc : Doc
  2136. data.Map.map.tests.functor : [Result]
  2137. data.Map.mapKeys : (k1 ->{g} k2)
                           -> Map k1 v
                           ->{g} Map k2 v
  2138. data.Map.mapKeys.doc : Doc
  2139. data.Map.mapKeys.tests.functorish : [Result]
  2140. data.Map.mapKeys.tests.retainGreatest : [Result]
  2141. data.Map.mapKeysWith : (v ->{g} v ->{g} v)
                               -> (k1 ->{g} k2)
                               -> Map k1 v
                               ->{g} Map k2 v
  2142. data.Map.mapKeysWith.doc : Doc
  2143. data.Map.mapKeysWith.tests.functorish : [Result]
  2144. data.Map.mapKeysWith.tests.greatestFirst : [Result]
  2145. data.Map.mapOptional : (a ->{f} Optional b)
                               -> Map k a
                               ->{f} Map k b
  2146. data.Map.mapOptional.doc : Doc
  2147. data.Map.mapOptionalWithKey : (k
                                      ->{e} a
                                      ->{f} Optional b)
                                      -> Map k a
                                      ->{e, f} Map k b
  2148. data.Map.mapOptionalWithKey.doc : Doc
  2149. data.Map.mapWithKey : (k ->{e} a ->{e} b)
                              -> Map k a
                              ->{e} Map k b
  2150. data.Map.mapWithKey.doc : Doc
  2151. data.Map.mapWithKey.tests.functorish : [Result]
  2152. data.Map.mapWithKey.tests.worksLikeList : [Result]
  2153. data.Map.mergeWith : (OneOrBoth a b ->{g} Optional c)
                             -> Map k a
                             -> Map k b
                             ->{g} Map k c
  2154. data.Map.mergeWith.doc : Doc
  2155. data.Map.mergeWithKey : (k
                                ->{e} OneOrBoth a b
                                ->{f} Optional c)
                                -> Map k a
                                -> Map k b
                                ->{e, f} Map k c
  2156. data.Map.mergeWithKey.doc : Doc
  2157. type data.Map.Nonempty k v
  2158. data.Map.Nonempty.== : Map.Nonempty k v
                               -> Map.Nonempty k v
                               -> Boolean
  2159. data.Map.Nonempty.==.doc : Doc
  2160. data.Map.Nonempty.==.tests.reflexive : [Result]
  2161. data.Map.Nonempty.==.tests.symmetrical : [Result]
  2162. data.Map.Nonempty.==.tests.transitive : [Result]
  2163. data.Map.Nonempty.adjust : (v ->{e} v)
                                   -> k
                                   -> Map.Nonempty k v
                                   ->{e} Map.Nonempty k v
  2164. data.Map.Nonempty.adjust.doc : Doc
  2165. data.Map.Nonempty.adjust.tests.adjusts : [Result]
  2166. data.Map.Nonempty.adjustWithKey : (k ->{e} v ->{e} v)
                                          -> k
                                          -> Map.Nonempty k v
                                          ->{e} Map.Nonempty k v
  2167. data.Map.Nonempty.adjustWithKey.doc : Doc
  2168. data.Map.Nonempty.adjustWithKey.tests.adjusts : [Result]
  2169. data.Map.Nonempty.align : Map.Nonempty k a
                                  -> Map.Nonempty k b
                                  -> Map.Nonempty
                                    k (OneOrBoth a b)
  2170. data.Map.Nonempty.align.doc : Doc
  2171. data.Map.Nonempty.alignWith : (OneOrBoth a b ->{g} c)
                                      -> Map.Nonempty k a
                                      -> Map.Nonempty k b
                                      ->{g} Map.Nonempty k c
  2172. data.Map.Nonempty.alignWith.doc : Doc
  2173. data.Map.Nonempty.alignWithKey : (k
                                         ->{e} OneOrBoth a b
                                         ->{f} c)
                                         -> Map.Nonempty k a
                                         -> Map.Nonempty k b
                                         ->{e, f} Map.Nonempty
                                           k c
  2174. data.Map.Nonempty.alignWithKey.doc : Doc
  2175. data.Map.Nonempty.alter : (Optional v ->{e} Optional v)
                                  -> k
                                  -> Map.Nonempty k v
                                  ->{e} Map k v
  2176. data.Map.Nonempty.alter.doc : Doc
  2177. data.Map.Nonempty.Bin : Nat
                                -> k
                                -> v
                                -> Map k v
                                -> Map k v
                                -> Map.Nonempty k v
  2178. data.Map.Nonempty.breakOffMax : Map.Nonempty k v
                                        -> ((k, v), Map k v)
  2179. data.Map.Nonempty.breakOffMax.doc : Doc
  2180. data.Map.Nonempty.breakOffMin : Map.Nonempty k v
                                        -> ((k, v), Map k v)
  2181. data.Map.Nonempty.breakOffMin.doc : Doc
  2182. data.Map.Nonempty.contains : k
                                     -> Map.Nonempty k v
                                     -> Boolean
  2183. data.Map.Nonempty.contains.doc : Doc
  2184. data.Map.Nonempty.delete : k
                                   -> Map.Nonempty k v
                                   -> Map k v
  2185. data.Map.Nonempty.delete.doc : Doc
  2186. data.Map.Nonempty.doc : Doc
  2187. data.Map.Nonempty.filter : (v ->{g} Boolean)
                                   -> Map.Nonempty k v
                                   ->{g} Map k v
  2188. data.Map.Nonempty.filter.doc : Doc
  2189. data.Map.Nonempty.filterAlignWithKey : (k
                                               ->{e} OneOrBoth
                                                 a b
                                               ->{f} Optional c)
                                               -> Map.Nonempty
                                                 k a
                                               -> Map.Nonempty
                                                 k b
                                               ->{e, f} Map k c
  2190. data.Map.Nonempty.filterAlignWithKey.doc : Doc
  2191. data.Map.Nonempty.filterKeys : (k ->{g} Boolean)
                                       -> Map.Nonempty k v
                                       ->{g} Map k v
  2192. data.Map.Nonempty.filterKeys.doc : Doc
  2193. data.Map.Nonempty.filterWithKey : (k
                                          ->{e} a
                                          ->{f} Boolean)
                                          -> Map.Nonempty k a
                                          ->{e, f} Map k a
  2194. data.Map.Nonempty.filterWithKey.doc : Doc
  2195. data.Map.Nonempty.foldLeft : (a ->{e} b ->{e} a)
                                     -> a
                                     -> Map.Nonempty k b
                                     ->{e} a
  2196. data.Map.Nonempty.foldLeft.doc : Doc
  2197. data.Map.Nonempty.foldLeftWithKey : (a
                                            ->{e} k
                                            ->{e} b
                                            ->{e} a)
                                            -> a
                                            -> Map.Nonempty k b
                                            ->{e} a
  2198. data.Map.Nonempty.foldLeftWithKey.doc : Doc
  2199. data.Map.Nonempty.foldMap : (a ->{e} a ->{e} a)
                                    -> (k ->{e} v ->{e} a)
                                    -> Map.Nonempty k v
                                    ->{e} a
  2200. data.Map.Nonempty.foldMap.doc : Doc
  2201. data.Map.Nonempty.foldRight : (a ->{e} b ->{e} b)
                                      -> b
                                      -> Map.Nonempty k a
                                      ->{e} b
  2202. data.Map.Nonempty.foldRight.doc : Doc
  2203. data.Map.Nonempty.foldRightWithKey : (k
                                             ->{e} a
                                             ->{e} b
                                             ->{e} b)
                                             -> b
                                             -> Map.Nonempty k a
                                             ->{e} b
  2204. data.Map.Nonempty.foldRightWithKey.doc : Doc
  2205. data.Map.Nonempty.foreach : Map.Nonempty k v
                                    -> (k ->{e} v ->{e} ())
                                    ->{e} ()
  2206. data.Map.Nonempty.foreach.doc : Doc
  2207. data.Map.Nonempty.fromList : List.Nonempty (k, v)
                                     -> Map.Nonempty k v
  2208. data.Map.Nonempty.fromList.doc : Doc
  2209. data.Map.Nonempty.fromListWith : (v ->{e} v ->{e} v)
                                         -> List.Nonempty (k, v)
                                         ->{e} Map.Nonempty k v
  2210. data.Map.Nonempty.fromListWith.doc : Doc
  2211. data.Map.Nonempty.fromListWithKey : (k
                                            ->{e} v
                                            ->{e} v
                                            ->{e} v)
                                            -> List.Nonempty
                                              (k, v)
                                            ->{e} Map.Nonempty
                                              k v
  2212. data.Map.Nonempty.fromListWithKey.doc : Doc
  2213. data.Map.Nonempty.get : k
                                -> Map.Nonempty k v
                                -> Optional v
  2214. data.Map.Nonempty.get.doc : Doc
  2215. data.Map.Nonempty.getMax : Map.Nonempty k v
                                   -> Optional (k, v)
  2216. data.Map.Nonempty.getMax.doc : Doc
  2217. data.Map.Nonempty.getMin : Map.Nonempty k v
                                   -> Optional (k, v)
  2218. data.Map.Nonempty.getMin.doc : Doc
  2219. data.Map.Nonempty.getOrAbort : k
                                       -> Map.Nonempty k v
                                       ->{Abort} v
  2220. data.Map.Nonempty.getOrAbort.doc : Doc
  2221. data.Map.Nonempty.getOrElse : v
                                      -> k
                                      -> Map.Nonempty k v
                                      -> v
  2222. data.Map.Nonempty.getOrElse.doc : Doc
  2223. data.Map.Nonempty.getOrThrow : e
                                       -> k
                                       -> Map.Nonempty k v
                                       ->{Throw e} v
  2224. data.Map.Nonempty.getOrThrow.doc : Doc
  2225. data.Map.Nonempty.insert : k
                                   -> v
                                   -> Map.Nonempty k v
                                   -> Map.Nonempty k v
  2226. data.Map.Nonempty.insert.doc : Doc
  2227. data.Map.Nonempty.internal.balanceL : k
                                              -> v
                                              -> Map k v
                                              -> Map k v
                                              -> Map.Nonempty
                                                k v
  2228. data.Map.Nonempty.internal.balanceR : k
                                              -> v
                                              -> Map k v
                                              -> Map k v
                                              -> Map.Nonempty
                                                k v
  2229. data.Map.Nonempty.internal.link : k
                                          -> v
                                          -> Map k v
                                          -> Map k v
                                          -> Map.Nonempty k v
  2230. data.Map.Nonempty.internal.putMax : k
                                            -> v
                                            -> Map k v
                                            -> Map.Nonempty k v
  2231. data.Map.Nonempty.internal.putMin : k
                                            -> v
                                            -> Map k v
                                            -> Map.Nonempty k v
  2232. data.Map.Nonempty.internal.putWithKeyR : (k
                                                 ->{e} v
                                                 ->{e} v
                                                 ->{e} v)
                                                 -> k
                                                 -> v
                                                 -> Map.Nonempty
                                                   k v
                                                 ->{e} Map.Nonempty
                                                   k v
  2233. data.Map.Nonempty.intersect : Map.Nonempty k a
                                      -> Map.Nonempty k b
                                      -> Map k a
  2234. data.Map.Nonempty.intersect.doc : Doc
  2235. data.Map.Nonempty.intersectWith : (a ->{e} b ->{e} c)
                                          -> Map.Nonempty k a
                                          -> Map.Nonempty k b
                                          ->{e} Map k c
  2236. data.Map.Nonempty.intersectWith.doc : Doc
  2237. data.Map.Nonempty.intersectWithKey : (k
                                             ->{e} a
                                             ->{e} b
                                             ->{e} c)
                                             -> Map.Nonempty k a
                                             -> Map.Nonempty k b
                                             ->{e} Map k c
  2238. data.Map.Nonempty.intersectWithKey.doc : Doc
  2239. data.Map.Nonempty.keys : Map.Nonempty k a
                                 -> List.Nonempty k
  2240. data.Map.Nonempty.keys.doc : Doc
  2241. data.Map.Nonempty.map : (a ->{e} b)
                                -> Map.Nonempty k a
                                ->{e} Map.Nonempty k b
  2242. data.Map.Nonempty.map.doc : Doc
  2243. data.Map.Nonempty.mapKeys : (k1 ->{g} k2)
                                    -> Map.Nonempty k1 v
                                    ->{g} Map.Nonempty k2 v
  2244. data.Map.Nonempty.mapKeys.doc : Doc
  2245. data.Map.Nonempty.mapKeysWith : (v ->{g} v ->{g} v)
                                        -> (k1 ->{g} k2)
                                        -> Map.Nonempty k1 v
                                        ->{g} Map.Nonempty k2 v
  2246. data.Map.Nonempty.mapKeysWith.doc : Doc
  2247. data.Map.Nonempty.mapWithKey : (k ->{e} a ->{e} b)
                                       -> Map.Nonempty k a
                                       ->{e} Map.Nonempty k b
  2248. data.Map.Nonempty.mapWithKey.doc : Doc
  2249. data.Map.Nonempty.mergeWith : (OneOrBoth a b
                                      ->{g} Optional c)
                                      -> Map.Nonempty k a
                                      -> Map.Nonempty k b
                                      ->{g} Map k c
  2250. data.Map.Nonempty.mergeWith.doc : Doc
  2251. data.Map.Nonempty.mergeWithKey : (k
                                         ->{e} OneOrBoth a b
                                         ->{f} Optional c)
                                         -> Map.Nonempty k a
                                         -> Map.Nonempty k b
                                         ->{e, f} Map k c
  2252. data.Map.Nonempty.mergeWithKey.doc : Doc
  2253. data.Map.Nonempty.nth : Nat
                                -> Map.Nonempty k v
                                -> Optional (k, v)
  2254. data.Map.Nonempty.nth.doc : Doc
  2255. data.Map.Nonempty.nth.tests : [Result]
  2256. data.Map.Nonempty.putGetWithKey : (k
                                          ->{e} v
                                          ->{e} v
                                          ->{e} v)
                                          -> k
                                          -> v
                                          -> Map.Nonempty k v
                                          ->{e} ( Optional v,
                                            Map.Nonempty k v)
  2257. data.Map.Nonempty.putGetWithKey.doc : Doc
  2258. data.Map.Nonempty.putWith : (v ->{e} v ->{e} v)
                                    -> k
                                    -> v
                                    -> Map.Nonempty k v
                                    ->{e} Map.Nonempty k v
  2259. data.Map.Nonempty.putWith.doc : Doc
  2260. data.Map.Nonempty.putWithKey : (k
                                       ->{e} v
                                       ->{e} v
                                       ->{e} v)
                                       -> k
                                       -> v
                                       -> Map.Nonempty k v
                                       ->{e} Map.Nonempty k v
  2261. data.Map.Nonempty.putWithKey.doc : Doc
  2262. data.Map.Nonempty.randomChoice : Map.Nonempty k v
                                         ->{Random} (k, v)
  2263. data.Map.Nonempty.randomChoice.doc : Doc
  2264. data.Map.Nonempty.randomChoice.test : [Result]
  2265. data.Map.Nonempty.randomKey : Map.Nonempty k v
                                      ->{Random} k
  2266. data.Map.Nonempty.randomKey.doc : Doc
  2267. data.Map.Nonempty.randomValue : Map.Nonempty k v
                                        ->{Random} v
  2268. data.Map.Nonempty.randomValue.doc : Doc
  2269. data.Map.Nonempty.singleton : k -> v -> Map.Nonempty k v
  2270. data.Map.Nonempty.singleton.doc : Doc
  2271. data.Map.Nonempty.size : Map.Nonempty k v -> Nat
  2272. data.Map.Nonempty.size.doc : Doc
  2273. data.Map.Nonempty.tests.nonemptyMapOf : '{Gen} k
                                                -> '{Gen} v
                                                -> '{Gen} Map.Nonempty
                                                  k v
  2274. data.Map.Nonempty.tests.nonemptyMapOf.doc : Doc
  2275. data.Map.Nonempty.toList : Map.Nonempty k v -> [(k, v)]
  2276. data.Map.Nonempty.toList.doc : Doc
  2277. data.Map.Nonempty.toMap : Map.Nonempty k v -> Map k v
  2278. data.Map.Nonempty.toMap.doc : Doc
  2279. data.Map.Nonempty.toNonemptyList : Map.Nonempty k v
                                           -> List.Nonempty
                                             (k, v)
  2280. data.Map.Nonempty.toNonemptyList.doc : Doc
  2281. data.Map.Nonempty.toNonemptyMap : List.Nonempty (k, v)
                                          -> Map.Nonempty k v
  2282. data.Map.Nonempty.toNonemptyMap.doc : Doc
  2283. data.Map.Nonempty.union : Map.Nonempty k v
                                  -> Map.Nonempty k v
                                  -> Map.Nonempty k v
  2284. data.Map.Nonempty.union.doc : Doc
  2285. data.Map.Nonempty.unions : List.Nonempty
                                     (Map.Nonempty k v)
                                   -> Map.Nonempty k v
  2286. data.Map.Nonempty.unions.doc : Doc
  2287. data.Map.Nonempty.unionWith : (v ->{e} v ->{e} v)
                                      -> Map.Nonempty k v
                                      -> Map.Nonempty k v
                                      ->{e} Map.Nonempty k v
  2288. data.Map.Nonempty.unionWith.doc : Doc
  2289. data.Map.Nonempty.unionWithKey : (k
                                         ->{e} v
                                         ->{e} v
                                         ->{e} v)
                                         -> Map.Nonempty k v
                                         -> Map.Nonempty k v
                                         ->{e} Map.Nonempty k v
  2290. data.Map.Nonempty.unionWithKey.doc : Doc
  2291. data.Map.Nonempty.update : (v ->{e} Optional v)
                                   -> k
                                   -> Map.Nonempty k v
                                   ->{e} Map k v
  2292. data.Map.Nonempty.update.doc : Doc
  2293. data.Map.Nonempty.upsert : (Optional v ->{e} v)
                                   -> k
                                   -> Map.Nonempty k v
                                   ->{e} Map.Nonempty k v
  2294. data.Map.Nonempty.upsert.doc : Doc
  2295. data.Map.Nonempty.values : Map.Nonempty k v
                                   -> List.Nonempty v
  2296. data.Map.Nonempty.values.doc : Doc
  2297. data.Map.nth : Nat -> Map k v -> Optional (k, v)
  2298. data.Map.nth.doc : Doc
  2299. data.Map.nth.tests : [Result]
  2300. data.Map.put : k -> v -> Map k v -> Map k v
  2301. data.Map.put.doc : Doc
  2302. data.Map.putGetWithKey : (k ->{e} v ->{e} v ->{e} v)
                                 -> k
                                 -> v
                                 -> Map k v
                                 ->{e} (Optional v, Map k v)
  2303. data.Map.putGetWithKey.doc : Doc
  2304. data.Map.putGetWithKey.tests.putsAndGets : [Result]
  2305. data.Map.putWith : (v ->{e} v ->{e} v)
                           -> k
                           -> v
                           -> Map k v
                           ->{e} Map k v
  2306. data.Map.putWith.doc : Doc
  2307. data.Map.putWith.tests.puts : [Result]
  2308. data.Map.putWithKey : (k ->{e} v ->{e} v ->{e} v)
                              -> k
                              -> v
                              -> Map k v
                              ->{e} Map k v
  2309. data.Map.putWithKey.doc : Doc
  2310. data.Map.randomChoice : Map k v
                                ->{Exception, Random} (k, v)
  2311. data.Map.randomChoice.doc : Doc
  2312. data.Map.randomChoice.test : [Result]
  2313. data.Map.randomKey : Map k v ->{Exception, Random} k
  2314. data.Map.randomKey.doc : Doc
  2315. data.Map.randomValue : Map k v ->{Exception, Random} v
  2316. data.Map.randomValue.doc : Doc
  2317. data.Map.singleton : k -> v -> Map k v
  2318. data.Map.singleton.doc : Doc
  2319. data.Map.singleton.tests.roundtrip : [Result]
  2320. data.Map.size : Map k v -> Nat
  2321. data.Map.size.doc : Doc
  2322. data.Map.size.tests.numberOfKeys : [Result]
  2323. data.Map.split : k -> Map k a -> (Map k a, Map k a)
  2324. data.Map.split.doc : Doc
  2325. data.Map.split.tests.splits : [Result]
  2326. data.Map.takeLargest : Nat -> Map k v -> Map k v
  2327. data.Map.takeLargest.doc : Doc
  2328. data.Map.takeLargest.tests : [Result]
  2329. data.Map.takeSmallest : Nat -> Map k v -> Map k v
  2330. data.Map.takeSmallest.doc : Doc
  2331. data.Map.takeSmallest.tests : [Result]
  2332. data.Map.tests.mapOf : '{Gen} k
                               -> '{Gen} v
                               -> '{Gen} Map k v
  2333. data.Map.tests.mapOf.doc : Doc
  2334. data.Map.toList : Map k v -> [(k, v)]
  2335. data.Map.toList.doc : Doc
  2336. data.Map.toList.tests.roundtrip : [Result]
  2337. data.Map.union : Map k v -> Map k v -> Map k v
  2338. data.Map.union.doc : Doc
  2339. data.Map.union.tests.associative : [Result]
  2340. data.Map.union.tests.idempotent : [Result]
  2341. data.Map.union.tests.unit : [Result]
  2342. data.Map.unions : [Map k v] -> Map k v
  2343. data.Map.unions.doc : Doc
  2344. data.Map.unionWith : (v ->{e} v ->{e} v)
                             -> Map k v
                             -> Map k v
                             ->{e} Map k v
  2345. data.Map.unionWith.doc : Doc
  2346. data.Map.unionWith.tests.commutative : [Result]
  2347. data.Map.unionWith.tests.idempotent : [Result]
  2348. data.Map.unionWith.tests.unit : [Result]
  2349. data.Map.unionWithKey : (k ->{e} v ->{e} v ->{e} v)
                                -> Map k v
                                -> Map k v
                                ->{e} Map k v
  2350. data.Map.unionWithKey.doc : Doc
  2351. data.Map.unionWithKey.tests.commutative : [Result]
  2352. data.Map.unionWithKey.tests.idempotent : [Result]
  2353. data.Map.unionWithKey.tests.unit : [Result]
  2354. data.Map.update : (v ->{e} Optional v)
                          -> k
                          -> Map k v
                          ->{e} Map k v
  2355. data.Map.update.doc : Doc
  2356. data.Map.update.tests.updates : [Result]
  2357. data.Map.updateWithKey : (k ->{e} v ->{e} Optional v)
                                 -> k
                                 -> Map k v
                                 ->{e} Map k v
  2358. data.Map.updateWithKey.doc : Doc
  2359. data.Map.updateWithKey.tests.updates : [Result]
  2360. data.Map.upsert : (Optional a ->{g} a)
                          -> k
                          -> Map k a
                          ->{g} Map k a
  2361. data.Map.upsert.doc : Doc
  2362. data.Map.values : Map k v -> [v]
  2363. data.Map.values.doc : Doc
  2364. data.Map.values.tests.roundtrip : [Result]
  2365. data.Multimap.insert : k -> v -> Map k [v] -> Map k [v]
  2366. data.Multimap.insert.doc : Doc
  2367. data.Multimap.lookup : k -> Map k [elem] -> [elem]
  2368. data.Multimap.lookup.doc : Doc
  2369. type data.NatBag
  2370. data.NatBag.add : Nat -> NatBag -> NatBag
  2371. data.NatBag.add.doc : Doc
  2372. data.NatBag.add.nonempty : Nat
                                   -> NatBag
                                   -> NatBag.Nonempty
  2373. data.NatBag.add.nonempty.doc : Doc
  2374. data.NatBag.add.nonempty.test : [Result]
  2375. data.NatBag.addAll : NatBag -> NatBag -> NatBag
  2376. data.NatBag.addAll.doc : Doc
  2377. data.NatBag.addAll.test : [Result]
  2378. data.NatBag.addMany : NatBag -> [Nat] -> NatBag
  2379. data.NatBag.addMany.doc : Doc
  2380. data.NatBag.addMany.test : [Result]
  2381. data.NatBag.addN : Nat -> Nat -> NatBag -> NatBag
  2382. data.NatBag.addN.doc : Doc
  2383. data.NatBag.addN.test : [Result]
  2384. data.NatBag.all : (Nat ->{g} Boolean)
                          ->{g} NatBag
                          ->{g} Boolean
  2385. data.NatBag.all.doc : Doc
  2386. data.NatBag.all.test : [Result]
  2387. data.NatBag.any : (Nat ->{g} Boolean)
                          ->{g} NatBag
                          ->{g} Boolean
  2388. data.NatBag.any.doc : Doc
  2389. data.NatBag.any.test : [Result]
  2390. data.NatBag.contains : Nat -> NatBag -> Boolean
  2391. data.NatBag.contains.doc : Doc
  2392. data.NatBag.contains.test : [Result]
  2393. data.NatBag.convolve : (Nat ->{e} Nat ->{e} Nat)
                               -> NatBag
                               -> NatBag
                               ->{e} NatBag
  2394. data.NatBag.convolve.doc : Doc
  2395. data.NatBag.count : Nat -> NatBag -> Nat
  2396. data.NatBag.count.doc : Doc
  2397. data.NatBag.count.test : [Result]
  2398. data.NatBag.counts : NatBag -> NatMap Nat
  2399. data.NatBag.counts.doc : Doc
  2400. data.NatBag.counts.test : [Result]
  2401. data.NatBag.difference : NatBag -> NatBag -> NatBag
  2402. data.NatBag.difference.doc : Doc
  2403. data.NatBag.difference.test : [Result]
  2404. data.NatBag.doc : Doc
  2405. data.NatBag.empty : NatBag
  2406. data.NatBag.empty.doc : Doc
  2407. data.NatBag.equals : NatBag -> NatBag -> Boolean
  2408. data.NatBag.filter : (Nat ->{e} Boolean)
                             -> NatBag
                             ->{e} NatBag
  2409. data.NatBag.filter.doc : Doc
  2410. data.NatBag.filterMap : (Nat ->{e} Optional Nat)
                                -> NatBag
                                ->{e} NatBag
  2411. data.NatBag.filterMap.doc : Doc
  2412. data.NatBag.flatMap : (Nat ->{e} NatBag)
                              -> NatBag
                              ->{e} NatBag
  2413. data.NatBag.flatMap.doc : Doc
  2414. data.NatBag.foldLeft : (a ->{e} Nat ->{e} a)
                               -> a
                               -> NatBag
                               ->{e} a
  2415. data.NatBag.foldLeft.doc : Doc
  2416. data.NatBag.foldRight : (Nat ->{e} a ->{e} a)
                                -> a
                                -> NatBag
                                ->{e} a
  2417. data.NatBag.foldRight.doc : Doc
  2418. data.NatBag.from : NatBag -> NatBag -> Boolean
  2419. data.NatBag.from.doc : Doc
  2420. data.NatBag.fromBag : Bag Nat -> NatBag
  2421. data.NatBag.fromBag.doc : Doc
  2422. data.NatBag.fromList : [Nat] -> NatBag
  2423. data.NatBag.fromList.doc : Doc
  2424. data.NatBag.fromList.test : [Result]
  2425. data.NatBag.fromNatSet : NatSet -> NatBag
  2426. data.NatBag.fromNatSet.doc : Doc
  2427. data.NatBag.fromNatSet.test : [Result]
  2428. data.NatBag.fromOccurrenceList : [(Nat, Nat)] -> NatBag
  2429. data.NatBag.fromOccurrenceList.doc : Doc
  2430. data.NatBag.getMax : NatBag ->{Abort} Nat
  2431. data.NatBag.getMax.doc : Doc
  2432. data.NatBag.getMin : NatBag ->{Abort} Nat
  2433. data.NatBag.getMin.doc : Doc
  2434. data.NatBag.intersect : NatBag -> NatBag -> NatBag
  2435. data.NatBag.intersect.doc : Doc
  2436. data.NatBag.intersect.test : [Result]
  2437. data.NatBag.isEmpty : NatBag -> Boolean
  2438. data.NatBag.isEmpty.doc : Doc
  2439. data.NatBag.map : (Nat ->{e} Nat) -> NatBag ->{e} NatBag
  2440. data.NatBag.map.doc : Doc
  2441. data.NatBag.NatBag : NatMap Nat -> NatBag
  2442. type data.NatBag.Nonempty
  2443. data.NatBag.Nonempty.add : Nat
                                   -> NatBag.Nonempty
                                   -> NatBag.Nonempty
  2444. data.NatBag.Nonempty.add.doc : Doc
  2445. data.NatBag.Nonempty.add.test : [Result]
  2446. data.NatBag.Nonempty.addAll : NatBag.Nonempty
                                      -> NatBag.Nonempty
                                      -> NatBag.Nonempty
  2447. data.NatBag.Nonempty.addAll.doc : Doc
  2448. data.NatBag.Nonempty.addAll.test : [Result]
  2449. data.NatBag.Nonempty.addMany : NatBag.Nonempty
                                       -> [Nat]
                                       -> NatBag.Nonempty
  2450. data.NatBag.Nonempty.addMany.doc : Doc
  2451. data.NatBag.Nonempty.addMany.test : [Result]
  2452. data.NatBag.Nonempty.addN : Nat
                                    -> Nat
                                    -> NatBag.Nonempty
                                    -> NatBag.Nonempty
  2453. data.NatBag.Nonempty.addN.doc : Doc
  2454. data.NatBag.Nonempty.addN.test : [Result]
  2455. data.NatBag.Nonempty.count : Nat
                                     -> NatBag.Nonempty
                                     -> Nat
  2456. data.NatBag.Nonempty.count.doc : Doc
  2457. data.NatBag.Nonempty.count.test : [Result]
  2458. data.NatBag.Nonempty.counts : NatBag.Nonempty
                                      -> NatMap.Nonempty Nat
  2459. data.NatBag.Nonempty.counts.doc : Doc
  2460. data.NatBag.Nonempty.difference : NatBag.Nonempty
                                          -> NatBag.Nonempty
                                          -> NatBag
  2461. data.NatBag.Nonempty.difference.doc : Doc
  2462. data.NatBag.Nonempty.difference.test : [Result]
  2463. data.NatBag.Nonempty.equals : NatBag.Nonempty
                                      -> NatBag.Nonempty
                                      -> Boolean
  2464. data.NatBag.Nonempty.equals.doc : Doc
  2465. data.NatBag.Nonempty.equals.test : [Result]
  2466. data.NatBag.Nonempty.fromList : List.Nonempty Nat
                                        -> NatBag.Nonempty
  2467. data.NatBag.Nonempty.fromList.doc : Doc
  2468. data.NatBag.Nonempty.fromList.test : [Result]
  2469. data.NatBag.Nonempty.fromNatSet : NatSet.Nonempty
                                          -> NatBag.Nonempty
  2470. data.NatBag.Nonempty.fromNatSet.doc : Doc
  2471. data.NatBag.Nonempty.fromNatSet.test : [Result]
  2472. data.NatBag.Nonempty.fromOccurrenceList : List.Nonempty
                                                    (Nat, Nat)
                                                  -> NatBag.Nonempty
  2473. data.NatBag.Nonempty.fromOccurrenceList.doc : Doc
  2474. data.NatBag.Nonempty.getMax : NatBag.Nonempty -> Nat
  2475. data.NatBag.Nonempty.getMax.doc : Doc
  2476. data.NatBag.Nonempty.getMin : NatBag.Nonempty -> Nat
  2477. data.NatBag.Nonempty.getMin.doc : Doc
  2478. data.NatBag.Nonempty.intersect : NatBag.Nonempty
                                         -> NatBag.Nonempty
                                         -> NatBag
  2479. data.NatBag.Nonempty.intersect.doc : Doc
  2480. data.NatBag.Nonempty.intersect.test : [Result]
  2481. data.NatBag.Nonempty.NatBag.Nonempty : NatMap.Nonempty
                                                 Nat
                                               -> NatBag.Nonempty
  2482. data.NatBag.Nonempty.nth : Nat
                                   -> NatBag.Nonempty
                                   -> Optional Nat
  2483. data.NatBag.Nonempty.nth.doc : Doc
  2484. data.NatBag.Nonempty.nth.tests : [Result]
  2485. data.NatBag.Nonempty.occurrenceList : NatBag.Nonempty
                                              -> List.Nonempty
                                                (Nat, Nat)
  2486. data.NatBag.Nonempty.occurrenceList.doc : Doc
  2487. data.NatBag.Nonempty.randomChoice : NatBag.Nonempty
                                            ->{Random} Nat
  2488. data.NatBag.Nonempty.randomChoice.test : [Result]
  2489. data.NatBag.Nonempty.remove : Nat
                                      -> NatBag.Nonempty
                                      -> NatBag
  2490. data.NatBag.Nonempty.remove.doc : Doc
  2491. data.NatBag.Nonempty.remove.test : [Result]
  2492. data.NatBag.Nonempty.removeAll : Nat
                                         -> NatBag.Nonempty
                                         -> NatBag
  2493. data.NatBag.Nonempty.removeAll.doc : Doc
  2494. data.NatBag.Nonempty.removeAll.test : [Result]
  2495. data.NatBag.Nonempty.removeMax : NatBag.Nonempty
                                         -> NatBag
  2496. data.NatBag.Nonempty.removeMax.doc : Doc
  2497. data.NatBag.Nonempty.removeMin : NatBag.Nonempty
                                         -> NatBag
  2498. data.NatBag.Nonempty.removeMin.doc : Doc
  2499. data.NatBag.Nonempty.removeN : Nat
                                       -> Nat
                                       -> NatBag.Nonempty
                                       -> NatBag
  2500. data.NatBag.Nonempty.removeN.doc : Doc
  2501. data.NatBag.Nonempty.removeN.test : [Result]
  2502. data.NatBag.Nonempty.size : NatBag.Nonempty -> Nat
  2503. data.NatBag.Nonempty.size.doc : Doc
  2504. data.NatBag.Nonempty.subbag : NatBag.Nonempty
                                      -> NatBag.Nonempty
                                      -> Boolean
  2505. data.NatBag.Nonempty.subbag.doc : Doc
  2506. data.NatBag.Nonempty.subbag.test : [Result]
  2507. data.NatBag.Nonempty.superbag : NatBag.Nonempty
                                        -> NatBag.Nonempty
                                        -> Boolean
  2508. data.NatBag.Nonempty.superbag.doc : Doc
  2509. data.NatBag.Nonempty.superbag.test : [Result]
  2510. data.NatBag.Nonempty.toBag : NatBag.Nonempty -> Bag Nat
  2511. data.NatBag.Nonempty.toBag.doc : Doc
  2512. data.NatBag.Nonempty.toBag.test : [Result]
  2513. data.NatBag.Nonempty.toList : NatBag.Nonempty
                                      -> List.Nonempty Nat
  2514. data.NatBag.Nonempty.toList.doc : Doc
  2515. data.NatBag.Nonempty.toList.test : [Result]
  2516. data.NatBag.Nonempty.toNatBag : NatBag.Nonempty
                                        -> NatBag
  2517. data.NatBag.Nonempty.toNatBag.doc : Doc
  2518. data.NatBag.Nonempty.toNatSet : NatBag.Nonempty
                                        -> NatSet.Nonempty
  2519. data.NatBag.Nonempty.toNatSet.doc : Doc
  2520. data.NatBag.Nonempty.toNatSet.test : [Result]
  2521. data.NatBag.Nonempty.union : NatBag.Nonempty
                                     -> NatBag.Nonempty
                                     -> NatBag.Nonempty
  2522. data.NatBag.Nonempty.union.doc : Doc
  2523. data.NatBag.Nonempty.union.test : [Result]
  2524. data.NatBag.nth : Nat -> NatBag -> Optional Nat
  2525. data.NatBag.nth.doc : Doc
  2526. data.NatBag.nth.tests : [Result]
  2527. data.NatBag.occurrenceList : NatBag -> [(Nat, Nat)]
  2528. data.NatBag.occurrenceList.doc : Doc
  2529. data.NatBag.partition : (Nat ->{e} Boolean)
                                -> NatBag
                                ->{e} (NatBag, NatBag)
  2530. data.NatBag.partition.doc : Doc
  2531. data.NatBag.randomChoice : NatBag ->{Random} Nat
  2532. data.NatBag.randomChoice.doc : Doc
  2533. data.NatBag.randomChoice.test : [Result]
  2534. data.NatBag.remove : Nat -> NatBag -> NatBag
  2535. data.NatBag.remove.doc : Doc
  2536. data.NatBag.remove.test : [Result]
  2537. data.NatBag.removeAll : Nat -> NatBag -> NatBag
  2538. data.NatBag.removeAll.doc : Doc
  2539. data.NatBag.removeAll.test : [Result]
  2540. data.NatBag.removeN : Nat -> Nat -> NatBag -> NatBag
  2541. data.NatBag.removeN.doc : Doc
  2542. data.NatBag.removeN.test : [Result]
  2543. data.NatBag.scale : Nat -> NatBag -> NatBag
  2544. data.NatBag.scale.doc : Doc
  2545. data.NatBag.singleton : Nat -> NatBag.Nonempty
  2546. data.NatBag.singleton.doc : Doc
  2547. data.NatBag.singleton.test : [Result]
  2548. data.NatBag.size : NatBag -> Nat
  2549. data.NatBag.size.doc : Doc
  2550. data.NatBag.subbag : NatBag -> NatBag -> Boolean
  2551. data.NatBag.subbag.doc : Doc
  2552. data.NatBag.subbag.test : [Result]
  2553. data.NatBag.superbag : NatBag -> NatBag -> Boolean
  2554. data.NatBag.superbag.doc : Doc
  2555. data.NatBag.superbag.test : [Result]
  2556. data.NatBag.toBag : NatBag -> Bag Nat
  2557. data.NatBag.toBag.doc : Doc
  2558. data.NatBag.toBag.test : [Result]
  2559. data.NatBag.toList : NatBag -> [Nat]
  2560. data.NatBag.toList.doc : Doc
  2561. data.NatBag.toList.test : [Result]
  2562. data.NatBag.toNatSet : NatBag -> NatSet
  2563. data.NatBag.toNatSet.doc : Doc
  2564. data.NatBag.toNatSet.test : [Result]
  2565. data.NatBag.union : NatBag -> NatBag -> NatBag
  2566. data.NatBag.union.doc : Doc
  2567. data.NatBag.union.test : [Result]
  2568. type data.NatMap a
  2569. data.NatMap.adjust : (a ->{g} a)
                             -> Nat
                             -> NatMap a
                             ->{g} NatMap a
  2570. data.NatMap.adjust.doc : Doc
  2571. data.NatMap.adjust.test : [Result]
  2572. data.NatMap.adjustWithKey : (Nat ->{g} a ->{g} a)
                                    -> Nat
                                    -> NatMap a
                                    ->{g} NatMap a
  2573. data.NatMap.adjustWithKey.doc : Doc
  2574. data.NatMap.adjustWithKey.test : [Result]
  2575. data.NatMap.align : NatMap a
                            -> NatMap b
                            -> NatMap (OneOrBoth a b)
  2576. data.NatMap.align.doc : Doc
  2577. data.NatMap.alignWith : (OneOrBoth a b ->{g} c)
                                -> NatMap a
                                -> NatMap b
                                ->{g} NatMap c
  2578. data.NatMap.alignWith.doc : Doc
  2579. data.NatMap.alignWithKey : (Nat
                                   ->{e} OneOrBoth a b
                                   ->{f} c)
                                   -> NatMap a
                                   -> NatMap b
                                   ->{e, f} NatMap c
  2580. data.NatMap.alignWithKey.doc : Doc
  2581. data.NatMap.alter : (Optional a ->{g} Optional a)
                            -> Nat
                            -> NatMap a
                            ->{g} NatMap a
  2582. data.NatMap.alter.doc : Doc
  2583. data.NatMap.alter.test : [Result]
  2584. data.NatMap.alterWithKey : (Nat
                                   ->{g} Optional a
                                   ->{g} Optional a)
                                   -> Nat
                                   -> NatMap a
                                   ->{g} NatMap a
  2585. data.NatMap.alterWithKey.doc : Doc
  2586. data.NatMap.alterWithKey.test : [Result]
  2587. data.NatMap.breakOffMax : NatMap a
                                  ->{Abort} ((Nat, a), NatMap a)
  2588. data.NatMap.breakOffMax.doc : Doc
  2589. data.NatMap.breakOffMax.test : [Result]
  2590. data.NatMap.breakOffMin : NatMap a
                                  ->{Abort} ((Nat, a), NatMap a)
  2591. data.NatMap.breakOffMin.doc : Doc
  2592. data.NatMap.breakOffMin.test : [Result]
  2593. data.NatMap.compareBy : (a ->{g} a ->{g} Ordering)
                                -> NatMap a
                                -> NatMap a
                                ->{g} Ordering
  2594. data.NatMap.compareBy.doc : Doc
  2595. data.NatMap.compareBy.test : [Result]
  2596. data.NatMap.contains : Nat -> NatMap a -> Boolean
  2597. data.NatMap.contains.doc : Doc
  2598. data.NatMap.delete : Nat -> NatMap a -> NatMap a
  2599. data.NatMap.delete.doc : Doc
  2600. data.NatMap.deleteMax : NatMap a ->{Abort} NatMap a
  2601. data.NatMap.deleteMax.doc : Doc
  2602. data.NatMap.deleteMin : NatMap a ->{Abort} NatMap a
  2603. data.NatMap.deleteMin.doc : Doc
  2604. data.NatMap.difference : NatMap a
                                 -> NatMap b
                                 -> NatMap a
  2605. data.NatMap.difference.doc : Doc
  2606. data.NatMap.differenceWith : (a
                                     ->{g} b
                                     ->{g} Optional a)
                                     -> NatMap a
                                     -> NatMap b
                                     ->{g} NatMap a
  2607. data.NatMap.differenceWith.doc : Doc
  2608. data.NatMap.differenceWithKey : (Nat
                                        ->{g} a
                                        ->{g} b
                                        ->{g} Optional a)
                                        -> NatMap a
                                        -> NatMap b
                                        ->{g} NatMap a
  2609. data.NatMap.differenceWithKey.doc : Doc
  2610. data.NatMap.doc : Doc
  2611. data.NatMap.empty : NatMap a
  2612. data.NatMap.empty.doc : Doc
  2613. data.NatMap.equalBy : (a ->{g} a ->{g} Boolean)
                              -> NatMap a
                              -> NatMap a
                              ->{g} Boolean
  2614. data.NatMap.equalBy.doc : Doc
  2615. data.NatMap.filter : (a ->{g} Boolean)
                             -> NatMap a
                             ->{g} NatMap a
  2616. data.NatMap.filter.doc : Doc
  2617. data.NatMap.filterWithKey : (Nat ->{g} a ->{g} Boolean)
                                    -> NatMap a
                                    ->{g} NatMap a
  2618. data.NatMap.filterWithKey.doc : Doc
  2619. data.NatMap.fold : (a ->{g} b ->{g} b)
                           -> b
                           -> NatMap a
                           ->{g} b
  2620. data.NatMap.fold.doc : Doc
  2621. data.NatMap.foldWithKey : (Nat ->{g} a ->{g} b ->{g} b)
                                  -> b
                                  -> NatMap a
                                  ->{g} b
  2622. data.NatMap.foldWithKey.doc : Doc
  2623. data.NatMap.fromList : [(Nat, a)] -> NatMap a
  2624. data.NatMap.fromList.doc : Doc
  2625. data.NatMap.fromListWith : (a ->{g} a ->{g} a)
                                   -> [(Nat, a)]
                                   ->{g} NatMap a
  2626. data.NatMap.fromListWith.doc : Doc
  2627. data.NatMap.fromListWithKey : (Nat
                                      ->{g} a
                                      ->{g} a
                                      ->{g} a)
                                      -> [(Nat, a)]
                                      ->{g} NatMap a
  2628. data.NatMap.fromListWithKey.doc : Doc
  2629. data.NatMap.fromMap : Map Nat a -> NatMap a
  2630. data.NatMap.fromMap.doc : Doc
  2631. data.NatMap.get : Nat -> NatMap a -> Optional a
  2632. data.NatMap.get.doc : Doc
  2633. data.NatMap.getAbove : Nat
                               -> NatMap v
                               -> Optional (Nat, v)
  2634. data.NatMap.getAbove.doc : Doc
  2635. data.NatMap.getAtLeast : Nat
                                 -> NatMap v
                                 -> Optional (Nat, v)
  2636. data.NatMap.getAtLeast.doc : Doc
  2637. data.NatMap.getAtMost : Nat
                                -> NatMap v
                                -> Optional (Nat, v)
  2638. data.NatMap.getAtMost.doc : Doc
  2639. data.NatMap.getBelow : Nat
                               -> NatMap v
                               -> Optional (Nat, v)
  2640. data.NatMap.getBelow.doc : Doc
  2641. data.NatMap.getMax : NatMap a ->{Abort} a
  2642. data.NatMap.getMax.doc : Doc
  2643. data.NatMap.getMin : NatMap a ->{Abort} a
  2644. data.NatMap.getMin.doc : Doc
  2645. data.NatMap.getOrAbort : Nat -> NatMap a ->{Abort} a
  2646. data.NatMap.getOrAbort.doc : Doc
  2647. data.NatMap.getOrElse : Nat -> a -> NatMap a -> a
  2648. data.NatMap.getOrElse.doc : Doc
  2649. data.NatMap.insert : Nat -> a -> NatMap a -> NatMap a
  2650. data.NatMap.insert.doc : Doc
  2651. data.NatMap.insert.nonempty : Nat
                                      -> a
                                      -> NatMap a
                                      -> NatMap.Nonempty a
  2652. data.NatMap.insert.nonempty.doc : Doc
  2653. data.NatMap.insert.nonempty.nonempty : Nat
                                               -> a
                                               -> NatMap a
                                               -> NatMap.Nonempty
                                                 a
  2654. data.NatMap.insertGetWithKey : (Nat
                                       ->{g} a
                                       ->{g} a
                                       ->{g} a)
                                       -> Nat
                                       -> a
                                       -> NatMap a
                                       ->{g} ( Optional a,
                                         NatMap.Nonempty a)
  2655. data.NatMap.insertGetWithKey.doc : Doc
  2656. data.NatMap.insertWith : (a ->{g} a ->{g} a)
                                 -> Nat
                                 -> a
                                 -> NatMap a
                                 ->{g} NatMap.Nonempty a
  2657. data.NatMap.insertWith.doc : Doc
  2658. data.NatMap.insertWithKey : (Nat
                                    ->{g} a
                                    ->{g} a
                                    ->{g} a)
                                    -> Nat
                                    -> a
                                    -> NatMap a
                                    ->{g} NatMap.Nonempty a
  2659. data.NatMap.insertWithKey.doc : Doc
  2660. data.NatMap.internal.bim : Nat
                                   -> Nat
                                   -> NatMap.Nonempty a
                                   -> NatMap.Nonempty a
                                   -> NatMap.Nonempty a
  2661. data.NatMap.internal.bin : Nat
                                   -> Nat
                                   -> NatMap a
                                   -> NatMap a
                                   -> NatMap a
  2662. data.NatMap.internal.bin.doc : Doc
  2663. data.NatMap.internal.branchMask : Nat -> Nat -> Nat
  2664. data.NatMap.internal.branchMask.doc : Doc
  2665. data.NatMap.internal.highBitMask : Nat -> Nat
  2666. data.NatMap.internal.highBitMask.doc : Doc
  2667. data.NatMap.internal.join : Nat
                                    -> NatMap.Nonempty a
                                    -> Nat
                                    -> NatMap.Nonempty a
                                    -> NatMap.Nonempty a
  2668. data.NatMap.internal.join.doc : Doc
  2669. data.NatMap.internal.mask : Nat -> Nat -> Nat
  2670. data.NatMap.internal.mask.doc : Doc
  2671. data.NatMap.internal.nomatch : Nat
                                       -> Nat
                                       -> Nat
                                       -> Boolean
  2672. data.NatMap.internal.nomatch.doc : Doc
  2673. data.NatMap.internal.shorter : Nat -> Nat -> Boolean
  2674. data.NatMap.internal.shorter.doc : Doc
  2675. data.NatMap.internal.zero : Nat -> Nat -> Boolean
  2676. data.NatMap.internal.zero.doc : Doc
  2677. data.NatMap.intersect : NatMap a -> NatMap b -> NatMap a
  2678. data.NatMap.intersect.doc : Doc
  2679. data.NatMap.intersectWith : (a ->{g} b ->{g} a)
                                    -> NatMap a
                                    -> NatMap b
                                    ->{g} NatMap a
  2680. data.NatMap.intersectWith.doc : Doc
  2681. data.NatMap.intersectWithKey : (Nat
                                       ->{g} a
                                       ->{g} b
                                       ->{g} a)
                                       -> NatMap a
                                       -> NatMap b
                                       ->{g} NatMap a
  2682. data.NatMap.intersectWithKey.doc : Doc
  2683. data.NatMap.isEmpty : NatMap a -> Boolean
  2684. data.NatMap.isEmpty.doc : Doc
  2685. data.NatMap.isProperSubmapOf : NatMap a
                                       -> NatMap a
                                       -> Boolean
  2686. data.NatMap.isProperSubmapOf.doc : Doc
  2687. data.NatMap.isProperSubmapOfBy : (a
                                         ->{g} a
                                         ->{g} Boolean)
                                         -> NatMap a
                                         -> NatMap a
                                         ->{g} Boolean
  2688. data.NatMap.isProperSubmapOfBy.doc : Doc
  2689. data.NatMap.isSubmapOf : NatMap a -> NatMap a -> Boolean
  2690. data.NatMap.isSubmapOf.doc : Doc
  2691. data.NatMap.isSubmapOfBy : (a ->{g} a ->{g} Boolean)
                                   -> NatMap a
                                   -> NatMap a
                                   ->{g} Boolean
  2692. data.NatMap.isSubmapOfBy.doc : Doc
  2693. data.NatMap.keys : NatMap a -> [Nat]
  2694. data.NatMap.keys.doc : Doc
  2695. data.NatMap.keySet : NatMap a -> NatSet
  2696. data.NatMap.keySet.doc : Doc
  2697. data.NatMap.keySet.test : [Result]
  2698. data.NatMap.lookup : Nat -> NatMap a -> Optional a
  2699. data.NatMap.map : (a ->{g} b) -> NatMap a ->{g} NatMap b
  2700. data.NatMap.map.doc : Doc
  2701. data.NatMap.mapEither : (a ->{g} Either b c)
                                -> NatMap a
                                ->{g} (NatMap b, NatMap c)
  2702. data.NatMap.mapEither.doc : Doc
  2703. data.NatMap.mapEitherWithKey : (Nat
                                       ->{g} a
                                       ->{g} Either b c)
                                       -> NatMap a
                                       ->{g} ( NatMap b,
                                         NatMap c)
  2704. data.NatMap.mapEitherWithKey.doc : Doc
  2705. data.NatMap.mapOptional : (a ->{g} Optional b)
                                  -> NatMap a
                                  ->{g} NatMap b
  2706. data.NatMap.mapOptional.doc : Doc
  2707. data.NatMap.mapOptionalWithKey : (Nat
                                         ->{g} a
                                         ->{g} Optional b)
                                         -> NatMap a
                                         ->{g} NatMap b
  2708. data.NatMap.mapOptionalWithKey.doc : Doc
  2709. data.NatMap.mapWithKey : (Nat ->{g} a ->{g} b)
                                 -> NatMap a
                                 ->{g} NatMap b
  2710. data.NatMap.mapWithKey.doc : Doc
  2711. data.NatMap.maxKey : NatMap a ->{Abort} Nat
  2712. data.NatMap.maxKey.doc : Doc
  2713. data.NatMap.maxView : NatMap a ->{Abort} (a, NatMap a)
  2714. data.NatMap.maxView.doc : Doc
  2715. data.NatMap.minKey : NatMap a ->{Abort} Nat
  2716. data.NatMap.minView : NatMap a ->{Abort} (a, NatMap a)
  2717. data.NatMap.minView.doc : Doc
  2718. data.NatMap.NatMap : Optional (NatMap.Nonempty a)
                             -> NatMap a
  2719. type data.NatMap.Nonempty a
  2720. data.NatMap.Nonempty.adjust : (a ->{g} a)
                                      -> Nat
                                      -> NatMap.Nonempty a
                                      ->{g} NatMap.Nonempty a
  2721. data.NatMap.Nonempty.adjust.doc : Doc
  2722. data.NatMap.Nonempty.adjustWithKey : (Nat
                                             ->{g} a
                                             ->{g} a)
                                             -> Nat
                                             -> NatMap.Nonempty
                                               a
                                             ->{g} NatMap.Nonempty
                                               a
  2723. data.NatMap.Nonempty.adjustWithKey.doc : Doc
  2724. data.NatMap.Nonempty.align : NatMap.Nonempty a
                                     -> NatMap.Nonempty b
                                     -> NatMap.Nonempty
                                       (OneOrBoth a b)
  2725. data.NatMap.Nonempty.align.doc : Doc
  2726. data.NatMap.Nonempty.alignWith : (OneOrBoth a b ->{g} c)
                                         -> NatMap.Nonempty a
                                         -> NatMap.Nonempty b
                                         ->{g} NatMap.Nonempty c
  2727. data.NatMap.Nonempty.alignWith.doc : Doc
  2728. data.NatMap.Nonempty.alignWithKey : (Nat
                                            ->{e} OneOrBoth a b
                                            ->{f} c)
                                            -> NatMap.Nonempty a
                                            -> NatMap.Nonempty b
                                            ->{e, f} NatMap.Nonempty
                                              c
  2729. data.NatMap.Nonempty.alignWithKey.doc : Doc
  2730. data.NatMap.Nonempty.alter : (Optional a
                                     ->{g} Optional a)
                                     -> Nat
                                     -> NatMap.Nonempty a
                                     ->{g} NatMap a
  2731. data.NatMap.Nonempty.alter.doc : Doc
  2732. data.NatMap.Nonempty.alterWithKey : (Nat
                                            ->{g} Optional a
                                            ->{g} Optional a)
                                            -> Nat
                                            -> NatMap.Nonempty a
                                            ->{g} NatMap a
  2733. data.NatMap.Nonempty.alterWithKey.doc : Doc
  2734. data.NatMap.Nonempty.breakOffMax : NatMap.Nonempty a
                                           -> ( (Nat, a),
                                             NatMap a)
  2735. data.NatMap.Nonempty.breakOffMax.doc : Doc
  2736. data.NatMap.Nonempty.breakOffMin : NatMap.Nonempty a
                                           -> ( (Nat, a),
                                             NatMap a)
  2737. data.NatMap.Nonempty.breakOffMin.doc : Doc
  2738. data.NatMap.Nonempty.compareBy : (a
                                         ->{g} a
                                         ->{g} Ordering)
                                         -> NatMap.Nonempty a
                                         -> NatMap.Nonempty a
                                         ->{g} Ordering
  2739. data.NatMap.Nonempty.compareBy.doc : Doc
  2740. data.NatMap.Nonempty.contains : Nat
                                        -> NatMap.Nonempty a
                                        -> Boolean
  2741. data.NatMap.Nonempty.contains.doc : Doc
  2742. data.NatMap.Nonempty.delete : Nat
                                      -> NatMap.Nonempty a
                                      -> NatMap a
  2743. data.NatMap.Nonempty.delete.doc : Doc
  2744. data.NatMap.Nonempty.deleteMax : NatMap.Nonempty a
                                         -> NatMap a
  2745. data.NatMap.Nonempty.deleteMax.doc : Doc
  2746. data.NatMap.Nonempty.deleteMin : NatMap.Nonempty a
                                         -> NatMap a
  2747. data.NatMap.Nonempty.deleteMin.doc : Doc
  2748. data.NatMap.Nonempty.difference : NatMap.Nonempty a
                                          -> NatMap.Nonempty b
                                          -> NatMap a
  2749. data.NatMap.Nonempty.difference.doc : Doc
  2750. data.NatMap.Nonempty.differenceWith : (a
                                              ->{g} b
                                              ->{g} Optional a)
                                              -> NatMap.Nonempty
                                                a
                                              -> NatMap.Nonempty
                                                b
                                              ->{g} NatMap a
  2751. data.NatMap.Nonempty.differenceWith.doc : Doc
  2752. data.NatMap.Nonempty.differenceWithKey : (Nat
                                                 ->{g} a
                                                 ->{g} b
                                                 ->{g} Optional
                                                   a)
                                                 -> NatMap.Nonempty
                                                   a
                                                 -> NatMap.Nonempty
                                                   b
                                                 ->{g} NatMap a
  2753. data.NatMap.Nonempty.differenceWithKey.doc : Doc
  2754. data.NatMap.Nonempty.doc : Doc
  2755. data.NatMap.Nonempty.equalBy : (a ->{g} a ->{g} Boolean)
                                       -> NatMap.Nonempty a
                                       -> NatMap.Nonempty a
                                       ->{g} Boolean
  2756. data.NatMap.Nonempty.equalBy.doc : Doc
  2757. data.NatMap.Nonempty.filter : (a ->{g} Boolean)
                                      -> NatMap.Nonempty a
                                      ->{g} NatMap a
  2758. data.NatMap.Nonempty.filter.doc : Doc
  2759. data.NatMap.Nonempty.filterWithKey : (Nat
                                             ->{g} a
                                             ->{g} Boolean)
                                             -> NatMap.Nonempty
                                               a
                                             ->{g} NatMap a
  2760. data.NatMap.Nonempty.filterWithKey.doc : Doc
  2761. data.NatMap.Nonempty.fold : (a ->{g} b ->{g} b)
                                    -> b
                                    -> NatMap.Nonempty a
                                    ->{g} b
  2762. data.NatMap.Nonempty.fold.doc : Doc
  2763. data.NatMap.Nonempty.foldMap : (b ->{g} b ->{g} b)
                                       -> (a ->{g} b)
                                       -> NatMap.Nonempty a
                                       ->{g} b
  2764. data.NatMap.Nonempty.foldMap.doc : Doc
  2765. data.NatMap.Nonempty.foldMapWithKey : (b
                                              ->{g} b
                                              ->{g} b)
                                              -> (Nat
                                              ->{g} a
                                              ->{g} b)
                                              -> NatMap.Nonempty
                                                a
                                              ->{g} b
  2766. data.NatMap.Nonempty.foldMapWithKey.doc : Doc
  2767. data.NatMap.Nonempty.foldWithKey : (Nat
                                           ->{g} a
                                           ->{g} b
                                           ->{g} b)
                                           -> b
                                           -> NatMap.Nonempty a
                                           ->{g} b
  2768. data.NatMap.Nonempty.foldWithKey.doc : Doc
  2769. data.NatMap.Nonempty.fromList : List.Nonempty (Nat, a)
                                        -> NatMap.Nonempty a
  2770. data.NatMap.Nonempty.fromList.doc : Doc
  2771. data.NatMap.Nonempty.fromListWith : (a ->{g} a ->{g} a)
                                            -> List.Nonempty
                                              (Nat, a)
                                            ->{g} NatMap.Nonempty
                                              a
  2772. data.NatMap.Nonempty.fromListWith.doc : Doc
  2773. data.NatMap.Nonempty.fromListWithKey : (Nat
                                               ->{g} a
                                               ->{g} a
                                               ->{g} a)
                                               -> List.Nonempty
                                                 (Nat, a)
                                               ->{g} NatMap.Nonempty
                                                 a
  2774. data.NatMap.Nonempty.fromListWithKey.doc : Doc
  2775. data.NatMap.Nonempty.get : Nat
                                   -> NatMap.Nonempty a
                                   -> Optional a
  2776. data.NatMap.Nonempty.get.doc : Doc
  2777. data.NatMap.Nonempty.getAbove : Nat
                                        -> NatMap.Nonempty v
                                        -> Optional (Nat, v)
  2778. data.NatMap.Nonempty.getAbove.doc : Doc
  2779. data.NatMap.Nonempty.getAtLeast : Nat
                                          -> NatMap.Nonempty v
                                          -> Optional (Nat, v)
  2780. data.NatMap.Nonempty.getAtLeast.doc : Doc
  2781. data.NatMap.Nonempty.getAtMost : Nat
                                         -> NatMap.Nonempty v
                                         -> Optional (Nat, v)
  2782. data.NatMap.Nonempty.getAtMost.doc : Doc
  2783. data.NatMap.Nonempty.getBelow : Nat
                                        -> NatMap.Nonempty v
                                        -> Optional (Nat, v)
  2784. data.NatMap.Nonempty.getBelow.doc : Doc
  2785. data.NatMap.Nonempty.getMax : NatMap.Nonempty a -> a
  2786. data.NatMap.Nonempty.getMax.doc : Doc
  2787. data.NatMap.Nonempty.getMin : NatMap.Nonempty a -> a
  2788. data.NatMap.Nonempty.getMin.doc : Doc
  2789. data.NatMap.Nonempty.getOrAbort : Nat
                                          -> NatMap.Nonempty a
                                          ->{Abort} a
  2790. data.NatMap.Nonempty.getOrAbort.doc : Doc
  2791. data.NatMap.Nonempty.getOrElse : Nat
                                         -> a
                                         -> NatMap.Nonempty a
                                         -> a
  2792. data.NatMap.Nonempty.getOrElse.doc : Doc
  2793. data.NatMap.Nonempty.insert : Nat
                                      -> a
                                      -> NatMap.Nonempty a
                                      -> NatMap.Nonempty a
  2794. data.NatMap.Nonempty.insert.doc : Doc
  2795. data.NatMap.Nonempty.insertGetWithKey : (Nat
                                                ->{g} a
                                                ->{g} a
                                                ->{g} a)
                                                -> Nat
                                                -> a
                                                -> NatMap.Nonempty
                                                  a
                                                ->{g} ( Optional
                                                  a,
                                                  NatMap.Nonempty
                                                  a)
  2796. data.NatMap.Nonempty.insertGetWithKey.doc : Doc
  2797. data.NatMap.Nonempty.insertWith : (a ->{g} a ->{g} a)
                                          -> Nat
                                          -> a
                                          -> NatMap.Nonempty a
                                          ->{g} NatMap.Nonempty
                                            a
  2798. data.NatMap.Nonempty.insertWith.doc : Doc
  2799. data.NatMap.Nonempty.insertWithKey : (Nat
                                             ->{g} a
                                             ->{g} a
                                             ->{g} a)
                                             -> Nat
                                             -> a
                                             -> NatMap.Nonempty
                                               a
                                             ->{g} NatMap.Nonempty
                                               a
  2800. data.NatMap.Nonempty.insertWithKey.doc : Doc
  2801. data.NatMap.Nonempty.intersect : NatMap.Nonempty a
                                         -> NatMap.Nonempty b
                                         -> NatMap a
  2802. data.NatMap.Nonempty.intersect.doc : Doc
  2803. data.NatMap.Nonempty.intersectWith : (a ->{g} b ->{g} a)
                                             -> NatMap.Nonempty
                                               a
                                             -> NatMap.Nonempty
                                               b
                                             ->{g} NatMap a
  2804. data.NatMap.Nonempty.intersectWith.doc : Doc
  2805. data.NatMap.Nonempty.intersectWithKey : (Nat
                                                ->{g} a
                                                ->{g} b
                                                ->{g} a)
                                                -> NatMap.Nonempty
                                                  a
                                                -> NatMap.Nonempty
                                                  b
                                                ->{g} NatMap a
  2806. data.NatMap.Nonempty.intersectWithKey.doc : Doc
  2807. data.NatMap.Nonempty.isProperSubmapOf : NatMap.Nonempty
                                                  a
                                                -> NatMap.Nonempty
                                                  a
                                                -> Boolean
  2808. data.NatMap.Nonempty.isProperSubmapOf.doc : Doc
  2809. data.NatMap.Nonempty.isProperSubmapOfBy : (a
                                                  ->{g} a
                                                  ->{g} Boolean)
                                                  -> NatMap.Nonempty
                                                    a
                                                  -> NatMap.Nonempty
                                                    a
                                                  ->{g} Boolean
  2810. data.NatMap.Nonempty.isProperSubmapOfBy.doc : Doc
  2811. data.NatMap.Nonempty.isSubmapOf : NatMap.Nonempty a
                                          -> NatMap.Nonempty a
                                          -> Boolean
  2812. data.NatMap.Nonempty.isSubmapOf.doc : Doc
  2813. data.NatMap.Nonempty.isSubmapOfBy : (a
                                            ->{g} a
                                            ->{g} Boolean)
                                            -> NatMap.Nonempty a
                                            -> NatMap.Nonempty a
                                            ->{g} Boolean
  2814. data.NatMap.Nonempty.isSubmapOfBy.doc : Doc
  2815. data.NatMap.Nonempty.keys : NatMap.Nonempty a
                                    -> List.Nonempty Nat
  2816. data.NatMap.Nonempty.keys.doc : Doc
  2817. data.NatMap.Nonempty.keySet : NatMap.Nonempty a
                                      -> NatSet.Nonempty
  2818. data.NatMap.Nonempty.keySet.doc : Doc
  2819. data.NatMap.Nonempty.map : (a ->{g} b)
                                   -> NatMap.Nonempty a
                                   ->{g} NatMap.Nonempty b
  2820. data.NatMap.Nonempty.map.doc : Doc
  2821. data.NatMap.Nonempty.mapEither : (a ->{g} Either b c)
                                         -> NatMap.Nonempty a
                                         ->{g} ( NatMap b,
                                           NatMap c)
  2822. data.NatMap.Nonempty.mapEither.doc : Doc
  2823. data.NatMap.Nonempty.mapEitherWithKey : (Nat
                                                ->{g} a
                                                ->{g} Either b c)
                                                -> NatMap.Nonempty
                                                  a
                                                ->{g} ( NatMap b,
                                                  NatMap c)
  2824. data.NatMap.Nonempty.mapEitherWithKey.doc : Doc
  2825. data.NatMap.Nonempty.mapOptional : (a ->{g} Optional b)
                                           -> NatMap.Nonempty a
                                           ->{g} NatMap b
  2826. data.NatMap.Nonempty.mapOptional.doc : Doc
  2827. data.NatMap.Nonempty.mapOptionalWithKey : (Nat
                                                  ->{g} a
                                                  ->{g} Optional
                                                    b)
                                                  -> NatMap.Nonempty
                                                    a
                                                  ->{g} NatMap b
  2828. data.NatMap.Nonempty.mapOptionalWithKey.doc : Doc
  2829. data.NatMap.Nonempty.mapWithKey : (Nat ->{g} a ->{g} b)
                                          -> NatMap.Nonempty a
                                          ->{g} NatMap.Nonempty
                                            b
  2830. data.NatMap.Nonempty.mapWithKey.doc : Doc
  2831. data.NatMap.Nonempty.maxKey : NatMap.Nonempty a -> Nat
  2832. data.NatMap.Nonempty.maxKey.doc : Doc
  2833. data.NatMap.Nonempty.maxView : NatMap.Nonempty a
                                       -> (a, NatMap a)
  2834. data.NatMap.Nonempty.maxView.doc : Doc
  2835. data.NatMap.Nonempty.minKey : NatMap.Nonempty a -> Nat
  2836. data.NatMap.Nonempty.minView : NatMap.Nonempty a
                                       -> (a, NatMap a)
  2837. data.NatMap.Nonempty.minView.doc : Doc
  2838. data.NatMap.Nonempty.NatMap.Nonempty.Bin : Nat
                                                   -> Nat
                                                   -> Nat
                                                   -> NatMap.Nonempty
                                                     a
                                                   -> NatMap.Nonempty
                                                     a
                                                   -> NatMap.Nonempty
                                                     a
  2839. data.NatMap.Nonempty.NatMap.Nonempty.Tip : Nat
                                                   -> a
                                                   -> NatMap.Nonempty
                                                     a
  2840. data.NatMap.Nonempty.nth : Nat
                                   -> NatMap.Nonempty v
                                   -> Optional (Nat, v)
  2841. data.NatMap.Nonempty.nth.doc : Doc
  2842. data.NatMap.Nonempty.nth.tests : [Result]
  2843. data.NatMap.Nonempty.partition : (a ->{g} Boolean)
                                         -> NatMap.Nonempty a
                                         ->{g} ( NatMap a,
                                           NatMap a)
  2844. data.NatMap.Nonempty.partition.doc : Doc
  2845. data.NatMap.Nonempty.partitionWithKey : (Nat
                                                ->{g} a
                                                ->{g} Boolean)
                                                -> NatMap.Nonempty
                                                  a
                                                ->{g} ( NatMap a,
                                                  NatMap a)
  2846. data.NatMap.Nonempty.partitionWithKey.doc : Doc
  2847. data.NatMap.Nonempty.randomChoice : NatMap.Nonempty v
                                            ->{Random} (Nat, v)
  2848. data.NatMap.Nonempty.randomChoice.doc : Doc
  2849. data.NatMap.Nonempty.randomChoice.test : [Result]
  2850. data.NatMap.Nonempty.randomKey : NatMap.Nonempty v
                                         ->{Random} Nat
  2851. data.NatMap.Nonempty.randomKey.doc : Doc
  2852. data.NatMap.Nonempty.randomValue : NatMap.Nonempty v
                                           ->{Random} v
  2853. data.NatMap.Nonempty.randomValue.doc : Doc
  2854. data.NatMap.Nonempty.restrict : Nat
                                        -> Nat
                                        -> NatMap.Nonempty v
                                        -> NatMap v
  2855. data.NatMap.Nonempty.restrict.doc : Doc
  2856. data.NatMap.Nonempty.restrictAbove : Nat
                                             -> NatMap.Nonempty
                                               v
                                             -> NatMap v
  2857. data.NatMap.Nonempty.restrictAbove.doc : Doc
  2858. data.NatMap.Nonempty.restrictBelow : Nat
                                             -> NatMap.Nonempty
                                               v
                                             -> NatMap v
  2859. data.NatMap.Nonempty.restrictBelow.doc : Doc
  2860. data.NatMap.Nonempty.singleton : Nat
                                         -> a
                                         -> NatMap.Nonempty a
  2861. data.NatMap.Nonempty.singleton.doc : Doc
  2862. data.NatMap.Nonempty.size : NatMap.Nonempty a -> Nat
  2863. data.NatMap.Nonempty.size.doc : Doc
  2864. data.NatMap.Nonempty.split : Nat
                                     -> NatMap.Nonempty a
                                     -> ( NatMap a,
                                       Optional a,
                                       NatMap a)
  2865. data.NatMap.Nonempty.split.doc : Doc
  2866. data.NatMap.Nonempty.submapCompareBy : (a
                                               ->{g} a
                                               ->{g} Boolean)
                                               -> NatMap.Nonempty
                                                 a
                                               -> NatMap.Nonempty
                                                 a
                                               ->{g} Optional
                                                 Ordering
  2867. data.NatMap.Nonempty.submapCompareBy.doc : Doc
  2868. data.NatMap.Nonempty.test.diff : [Result]
  2869. data.NatMap.Nonempty.test.gen : '{Gen} t
                                        -> '{Gen} NatMap.Nonempty
                                          t
  2870. data.NatMap.Nonempty.test.unionAssociative : [Result]
  2871. data.NatMap.Nonempty.test.unionCommutative : [Result]
  2872. data.NatMap.Nonempty.test.unionInsert : [Result]
  2873. data.NatMap.Nonempty.test.updateDelete : [Result]
  2874. data.NatMap.Nonempty.toList : NatMap.Nonempty a
                                      -> List.Nonempty (Nat, a)
  2875. data.NatMap.Nonempty.toList.doc : Doc
  2876. data.NatMap.Nonempty.toMap : NatMap.Nonempty a
                                     -> Map.Nonempty Nat a
  2877. data.NatMap.Nonempty.toMap.doc : Doc
  2878. data.NatMap.Nonempty.toNatMap : NatMap.Nonempty a
                                        -> NatMap a
  2879. data.NatMap.Nonempty.union : NatMap.Nonempty a
                                     -> NatMap.Nonempty a
                                     -> NatMap.Nonempty a
  2880. data.NatMap.Nonempty.union.doc : Doc
  2881. data.NatMap.Nonempty.unions : List.Nonempty
                                        (NatMap.Nonempty a)
                                      -> NatMap.Nonempty a
  2882. data.NatMap.Nonempty.unions.doc : Doc
  2883. data.NatMap.Nonempty.unionsWith : (a ->{g} a ->{g} a)
                                          -> List.Nonempty
                                            (NatMap.Nonempty a)
                                          ->{g} NatMap.Nonempty
                                            a
  2884. data.NatMap.Nonempty.unionsWith.doc : Doc
  2885. data.NatMap.Nonempty.unionWith : (a ->{g} a ->{g} a)
                                         -> NatMap.Nonempty a
                                         -> NatMap.Nonempty a
                                         ->{g} NatMap.Nonempty a
  2886. data.NatMap.Nonempty.unionWith.doc : Doc
  2887. data.NatMap.Nonempty.unionWithKey : (Nat
                                            ->{g} a
                                            ->{g} a
                                            ->{g} a)
                                            -> NatMap.Nonempty a
                                            -> NatMap.Nonempty a
                                            ->{g} NatMap.Nonempty
                                              a
  2888. data.NatMap.Nonempty.unionWithKey.doc : Doc
  2889. data.NatMap.Nonempty.update : (a ->{g} Optional a)
                                      -> Nat
                                      -> NatMap.Nonempty a
                                      ->{g} NatMap a
  2890. data.NatMap.Nonempty.update.doc : Doc
  2891. data.NatMap.Nonempty.updateGetWithKey : (Nat
                                                ->{g} a
                                                ->{g} Optional a)
                                                -> Nat
                                                -> NatMap.Nonempty
                                                  a
                                                ->{g} ( Optional
                                                  a,
                                                  NatMap a)
  2892. data.NatMap.Nonempty.updateGetWithKey.doc : Doc
  2893. data.NatMap.Nonempty.updateMax : (a ->{g} a)
                                         -> NatMap.Nonempty a
                                         ->{g} NatMap.Nonempty a
  2894. data.NatMap.Nonempty.updateMax.doc : Doc
  2895. data.NatMap.Nonempty.updateMaxWithKey : (Nat
                                                ->{g} a
                                                ->{g} a)
                                                -> NatMap.Nonempty
                                                  a
                                                ->{g} NatMap.Nonempty
                                                  a
  2896. data.NatMap.Nonempty.updateMaxWithKey.doc : Doc
  2897. data.NatMap.Nonempty.updateMin : (a ->{g} a)
                                         -> NatMap.Nonempty a
                                         ->{g} NatMap.Nonempty a
  2898. data.NatMap.Nonempty.updateMin.doc : Doc
  2899. data.NatMap.Nonempty.updateMinWithKey : (Nat
                                                ->{g} a
                                                ->{g} a)
                                                -> NatMap.Nonempty
                                                  a
                                                ->{g} NatMap.Nonempty
                                                  a
  2900. data.NatMap.Nonempty.updateMinWithKey.doc : Doc
  2901. data.NatMap.Nonempty.updateWithKey : (Nat
                                             ->{g} a
                                             ->{g} Optional a)
                                             -> Nat
                                             -> NatMap.Nonempty
                                               a
                                             ->{g} NatMap a
  2902. data.NatMap.Nonempty.updateWithKey.doc : Doc
  2903. data.NatMap.Nonempty.values : NatMap.Nonempty a
                                      -> List.Nonempty a
  2904. data.NatMap.Nonempty.values.doc : Doc
  2905. data.NatMap.nth : Nat -> NatMap v -> Optional (Nat, v)
  2906. data.NatMap.nth.doc : Doc
  2907. data.NatMap.nth.tests : [Result]
  2908. data.NatMap.partition : (a ->{g} Boolean)
                                -> NatMap a
                                ->{g} (NatMap a, NatMap a)
  2909. data.NatMap.partition.doc : Doc
  2910. data.NatMap.partitionWithKey : (Nat
                                       ->{g} a
                                       ->{g} Boolean)
                                       -> NatMap a
                                       ->{g} ( NatMap a,
                                         NatMap a)
  2911. data.NatMap.partitionWithKey.doc : Doc
  2912. data.NatMap.randomChoice : NatMap v
                                   ->{Exception, Random} ( Nat,
                                     v)
  2913. data.NatMap.randomChoice.doc : Doc
  2914. data.NatMap.randomChoice.test : [Result]
  2915. data.NatMap.randomKey : NatMap v
                                ->{Exception, Random} Nat
  2916. data.NatMap.randomKey.doc : Doc
  2917. data.NatMap.randomValue : NatMap v
                                  ->{Exception, Random} v
  2918. data.NatMap.randomValue.doc : Doc
  2919. data.NatMap.restrict : Nat
                               -> Nat
                               -> NatMap v
                               -> NatMap v
  2920. data.NatMap.restrict.doc : Doc
  2921. data.NatMap.restrictAbove : Nat -> NatMap v -> NatMap v
  2922. data.NatMap.restrictAbove.doc : Doc
  2923. data.NatMap.restrictBelow : Nat -> NatMap v -> NatMap v
  2924. data.NatMap.restrictBelow.doc : Doc
  2925. data.NatMap.singleton : Nat -> a -> NatMap.Nonempty a
  2926. data.NatMap.singleton.doc : Doc
  2927. data.NatMap.size : NatMap a -> Nat
  2928. data.NatMap.size.doc : Doc
  2929. data.NatMap.size.test : [Result]
  2930. data.NatMap.split : Nat
                            -> NatMap a
                            -> (NatMap a, Optional a, NatMap a)
  2931. data.NatMap.split.doc : Doc
  2932. data.NatMap.submapCompareBy : (a ->{g} a ->{g} Boolean)
                                      -> NatMap a
                                      -> NatMap a
                                      ->{g} Optional Ordering
  2933. data.NatMap.submapCompareBy.doc : Doc
  2934. data.NatMap.test.diff : [Result]
  2935. data.NatMap.test.gen : '{Gen} t -> '{Gen} NatMap t
  2936. data.NatMap.test.insertDelete : [Result]
  2937. data.NatMap.test.single : [Result]
  2938. data.NatMap.test.unionAssociative : [Result]
  2939. data.NatMap.test.unionCommutative : [Result]
  2940. data.NatMap.test.unionInsert : [Result]
  2941. data.NatMap.test.updateDelete : [Result]
  2942. data.NatMap.toList : NatMap a -> [(Nat, a)]
  2943. data.NatMap.toList.doc : Doc
  2944. data.NatMap.toMap : NatMap a -> Map Nat a
  2945. data.NatMap.toNonemptyList : NatMap.Nonempty a
                                     -> List.Nonempty (Nat, a)
  2946. data.NatMap.union : NatMap a -> NatMap a -> NatMap a
  2947. data.NatMap.union.doc : Doc
  2948. data.NatMap.unions : [NatMap a] -> NatMap a
  2949. data.NatMap.unions.doc : Doc
  2950. data.NatMap.unionsWith : (a ->{g} a ->{g} a)
                                 -> [NatMap a]
                                 ->{g} NatMap a
  2951. data.NatMap.unionsWith.doc : Doc
  2952. data.NatMap.unionWith : (a ->{g} a ->{g} a)
                                -> NatMap a
                                -> NatMap a
                                ->{g} NatMap a
  2953. data.NatMap.unionWith.doc : Doc
  2954. data.NatMap.unionWithKey : (Nat ->{g} a ->{g} a ->{g} a)
                                   -> NatMap a
                                   -> NatMap a
                                   ->{g} NatMap a
  2955. data.NatMap.unionWithKey.doc : Doc
  2956. data.NatMap.update : (a ->{g} Optional a)
                             -> Nat
                             -> NatMap a
                             ->{g} NatMap a
  2957. data.NatMap.update.doc : Doc
  2958. data.NatMap.updateGetWithKey : (Nat
                                       ->{g} a
                                       ->{g} Optional a)
                                       -> Nat
                                       -> NatMap a
                                       ->{g} ( Optional a,
                                         NatMap a)
  2959. data.NatMap.updateGetWithKey.doc : Doc
  2960. data.NatMap.updateMax : (a ->{g} a)
                                -> NatMap a
                                ->{g, Abort} NatMap a
  2961. data.NatMap.updateMax.doc : Doc
  2962. data.NatMap.updateMaxWithKey : (Nat ->{g} a ->{g} a)
                                       -> NatMap a
                                       ->{g, Abort} NatMap a
  2963. data.NatMap.updateMaxWithKey.doc : Doc
  2964. data.NatMap.updateMin : (a ->{g} a)
                                -> NatMap a
                                ->{g, Abort} NatMap a
  2965. data.NatMap.updateMin.doc : Doc
  2966. data.NatMap.updateMinWithKey : (Nat ->{g} a ->{g} a)
                                       -> NatMap a
                                       ->{g, Abort} NatMap a
  2967. data.NatMap.updateMinWithKey.doc : Doc
  2968. data.NatMap.updateWithKey : (Nat
                                    ->{g} a
                                    ->{g} Optional a)
                                    -> Nat
                                    -> NatMap a
                                    ->{g} NatMap a
  2969. data.NatMap.updateWithKey.doc : Doc
  2970. data.NatMap.values : NatMap a -> [a]
  2971. data.NatMap.values.doc : Doc
  2972. type data.NatSet
  2973. data.NatSet.== : NatSet -> NatSet -> Boolean
  2974. data.NatSet.all : (Nat ->{g} Boolean)
                          ->{g} NatSet
                          ->{g} Boolean
  2975. data.NatSet.all.doc : Doc
  2976. data.NatSet.all.test : [Result]
  2977. data.NatSet.alter : (Boolean ->{g} Boolean)
                            -> Nat
                            -> NatSet
                            ->{g} NatSet
  2978. data.NatSet.alter.doc : Doc
  2979. data.NatSet.alter.test : [Result]
  2980. data.NatSet.any : (Nat ->{g} Boolean)
                          ->{g} NatSet
                          ->{g} Boolean
  2981. data.NatSet.any.doc : Doc
  2982. data.NatSet.any.test : [Result]
  2983. data.NatSet.contains : Nat -> NatSet -> Boolean
  2984. data.NatSet.contains.doc : Doc
  2985. data.NatSet.contains.test : [Result]
  2986. data.NatSet.delete : Nat -> NatSet -> NatSet
  2987. data.NatSet.delete.doc : Doc
  2988. data.NatSet.deleteMax : NatSet -> NatSet
  2989. data.NatSet.deleteMax.doc : Doc
  2990. data.NatSet.deleteMax.test : [Result]
  2991. data.NatSet.deleteMin : NatSet -> NatSet
  2992. data.NatSet.deleteMin.doc : Doc
  2993. data.NatSet.deleteMin.test : [Result]
  2994. data.NatSet.difference : NatSet -> NatSet -> NatSet
  2995. data.NatSet.difference.doc : Doc
  2996. data.NatSet.difference.test : [Result]
  2997. data.NatSet.disjoint : NatSet -> NatSet -> Boolean
  2998. data.NatSet.disjoint.doc : Doc
  2999. data.NatSet.doc : Doc
  3000. data.NatSet.empty : NatSet
  3001. data.NatSet.empty.doc : Doc
  3002. data.NatSet.equals : NatSet -> NatSet -> Boolean
  3003. data.NatSet.equals.doc : Doc
  3004. data.NatSet.equals.tests.reflexive : [Result]
  3005. data.NatSet.equals.tests.symmetric : [Result]
  3006. data.NatSet.equals.tests.transitive : [Result]
  3007. data.NatSet.filter : (Nat ->{g} Boolean)
                             -> NatSet
                             ->{g} NatSet
  3008. data.NatSet.filter.doc : Doc
  3009. data.NatSet.filter.test : [Result]
  3010. data.NatSet.filterMap : (Nat ->{g} Optional Nat)
                                -> NatSet
                                ->{g} NatSet
  3011. data.NatSet.filterMap.doc : Doc
  3012. data.NatSet.filterMap.test : [Result]
  3013. data.NatSet.foldLeft : (a ->{g} Nat ->{g} a)
                               -> a
                               ->{g} NatSet
                               ->{g} a
  3014. data.NatSet.foldLeft.doc : Doc
  3015. data.NatSet.foldLeft.test : [Result]
  3016. data.NatSet.foldMap : (a ->{g} a ->{g} a)
                              -> (Nat ->{g} a)
                              -> a
                              -> NatSet
                              ->{g} a
  3017. data.NatSet.foldMap.doc : Doc
  3018. data.NatSet.foldRight : (Nat ->{g} a ->{g} a)
                                -> a
                                ->{g} NatSet
                                ->{g} a
  3019. data.NatSet.foldRight.doc : Doc
  3020. data.NatSet.foldRight.test : [Result]
  3021. data.NatSet.fromList : [Nat] -> NatSet
  3022. data.NatSet.fromList.doc : Doc
  3023. data.NatSet.getAbove : Nat -> NatSet -> Optional Nat
  3024. data.NatSet.getAbove.doc : Doc
  3025. data.NatSet.getAtLeast : Nat -> NatSet -> Optional Nat
  3026. data.NatSet.getAtLeast.doc : Doc
  3027. data.NatSet.getAtMost : Nat -> NatSet -> Optional Nat
  3028. data.NatSet.getAtMost.doc : Doc
  3029. data.NatSet.getBelow : Nat -> NatSet -> Optional Nat
  3030. data.NatSet.getBelow.doc : Doc
  3031. data.NatSet.getMax : NatSet -> Optional Nat
  3032. data.NatSet.getMax.doc : Doc
  3033. data.NatSet.getMin : NatSet -> Optional Nat
  3034. data.NatSet.getMin.doc : Doc
  3035. data.NatSet.insert : Nat -> NatSet -> NatSet
  3036. data.NatSet.insert.doc : Doc
  3037. data.NatSet.insert.nonempty : Nat
                                      -> NatSet
                                      -> NatSet.Nonempty
  3038. data.NatSet.insert.nonempty.doc : Doc
  3039. data.NatSet.insert.nonempty.nonempty : Nat
                                               -> NatSet
                                               -> NatSet.Nonempty
  3040. data.NatSet.internal.bim : Nat
                                   -> Nat
                                   -> NatSet.Nonempty
                                   -> NatSet.Nonempty
                                   -> NatSet.Nonempty
  3041. data.NatSet.internal.bin : Nat
                                   -> Nat
                                   -> NatSet
                                   -> NatSet
                                   -> NatSet
  3042. data.NatSet.internal.bin.doc : Doc
  3043. data.NatSet.internal.bitmapOf : Nat -> Nat
  3044. data.NatSet.internal.bitmapOf.doc : Doc
  3045. data.NatSet.internal.bitPred : (Nat ->{g} Boolean)
                                       -> Nat
                                       -> Nat
                                       -> Nat
                                       ->{g} Nat
  3046. data.NatSet.internal.bitPred.doc : Doc
  3047. data.NatSet.internal.foldBitsLeft : Nat
                                            -> (a
                                            ->{g} Nat
                                            ->{g} a)
                                            -> a
                                            -> Nat
                                            ->{g} a
  3048. data.NatSet.internal.foldBitsLeft.doc : Doc
  3049. data.NatSet.internal.foldBitsRight : Nat
                                             -> (Nat
                                             ->{g} a
                                             ->{g} a)
                                             -> a
                                             ->{g} Nat
                                             ->{g} a
  3050. data.NatSet.internal.foldBitsRight.doc : Doc
  3051. data.NatSet.internal.highBit : Nat -> Nat
  3052. data.NatSet.internal.highBit.doc : Doc
  3053. data.NatSet.internal.intersectBitmap : Nat
                                               -> Nat
                                               -> NatSet.Nonempty
                                               -> NatSet
  3054. data.NatSet.internal.intersectBitmap.doc : Doc
  3055. data.NatSet.internal.link : Nat
                                    -> NatSet.Nonempty
                                    -> Nat
                                    -> NatSet.Nonempty
                                    -> NatSet.Nonempty
  3056. data.NatSet.internal.link.doc : Doc
  3057. data.NatSet.internal.linkWithMask : Nat
                                            -> Nat
                                            -> NatSet.Nonempty
                                            -> NatSet.Nonempty
                                            -> NatSet.Nonempty
  3058. data.NatSet.internal.linkWithMask.doc : Doc
  3059. data.NatSet.internal.lowestBitMask : Nat -> Nat
  3060. data.NatSet.internal.lowestBitMask.doc : Doc
  3061. data.NatSet.internal.prefixOf : Nat -> Nat
  3062. data.NatSet.internal.prefixOf.doc : Doc
  3063. data.NatSet.internal.suffixOf : Nat -> Nat
  3064. data.NatSet.internal.suffixOf.doc : Doc
  3065. data.NatSet.internal.tip : Nat -> Nat -> NatSet
  3066. data.NatSet.internal.tip.doc : Doc
  3067. data.NatSet.intersect : NatSet -> NatSet -> NatSet
  3068. data.NatSet.intersect.doc : Doc
  3069. data.NatSet.intersect.test : [Result]
  3070. data.NatSet.isEmpty : NatSet -> Boolean
  3071. data.NatSet.isEmpty.doc : Doc
  3072. data.NatSet.map : (Nat ->{g} Nat) -> NatSet ->{g} NatSet
  3073. data.NatSet.map.doc : Doc
  3074. data.NatSet.map.tests.functor.homomorphism : [Result]
  3075. data.NatSet.map.tests.functor.identity : [Result]
  3076. data.NatSet.map.tests.noninjective : [Result]
  3077. data.NatSet.maxView : NatSet ->{Abort} (Nat, NatSet)
  3078. data.NatSet.maxView.doc : Doc
  3079. data.NatSet.maxView.test : [Result]
  3080. data.NatSet.minView : NatSet ->{Abort} (Nat, NatSet)
  3081. data.NatSet.minView.doc : Doc
  3082. data.NatSet.minView.test : [Result]
  3083. data.NatSet.NatSet : Optional NatSet.Nonempty -> NatSet
  3084. type data.NatSet.Nonempty
  3085. data.NatSet.Nonempty.== : NatSet.Nonempty
                                  -> NatSet.Nonempty
                                  -> Boolean
  3086. data.NatSet.Nonempty.alter : (Boolean ->{g} Boolean)
                                     -> Nat
                                     -> NatSet.Nonempty
                                     ->{g} NatSet
  3087. data.NatSet.Nonempty.alter.doc : Doc
  3088. data.NatSet.Nonempty.Bin : Nat
                                   -> Nat
                                   -> Nat
                                   -> NatSet.Nonempty
                                   -> NatSet.Nonempty
                                   -> NatSet.Nonempty
  3089. data.NatSet.Nonempty.compare : NatSet.Nonempty
                                       -> NatSet.Nonempty
                                       -> Ordering
  3090. data.NatSet.Nonempty.contains : Nat
                                        -> NatSet.Nonempty
                                        -> Boolean
  3091. data.NatSet.Nonempty.contains.doc : Doc
  3092. data.NatSet.Nonempty.delete : Nat
                                      -> NatSet.Nonempty
                                      -> NatSet
  3093. data.NatSet.Nonempty.delete.doc : Doc
  3094. data.NatSet.Nonempty.delete.test.deletedIsAbsent : [Result]
  3095. data.NatSet.Nonempty.deleteMax : NatSet.Nonempty
                                         -> NatSet
  3096. data.NatSet.Nonempty.deleteMax.doc : Doc
  3097. data.NatSet.Nonempty.deleteMin : NatSet.Nonempty
                                         -> NatSet
  3098. data.NatSet.Nonempty.deleteMin.doc : Doc
  3099. data.NatSet.Nonempty.difference : NatSet.Nonempty
                                          -> NatSet.Nonempty
                                          -> NatSet
  3100. data.NatSet.Nonempty.difference.doc : Doc
  3101. data.NatSet.Nonempty.disjoint : NatSet.Nonempty
                                        -> NatSet.Nonempty
                                        -> Boolean
  3102. data.NatSet.Nonempty.disjoint.doc : Doc
  3103. data.NatSet.Nonempty.disjoint.test : [Result]
  3104. data.NatSet.Nonempty.doc : Doc
  3105. data.NatSet.Nonempty.equals : NatSet.Nonempty
                                      -> NatSet.Nonempty
                                      -> Boolean
  3106. data.NatSet.Nonempty.equals.doc : Doc
  3107. data.NatSet.Nonempty.filter : (Nat ->{g} Boolean)
                                      -> NatSet.Nonempty
                                      ->{g} NatSet
  3108. data.NatSet.Nonempty.filter.doc : Doc
  3109. data.NatSet.Nonempty.filterMap : (Nat
                                         ->{g} Optional Nat)
                                         ->{g} NatSet.Nonempty
                                         ->{g} NatSet
  3110. data.NatSet.Nonempty.filterMap.doc : Doc
  3111. data.NatSet.Nonempty.foldLeft : (a ->{g} Nat ->{g} a)
                                        -> a
                                        ->{g} NatSet.Nonempty
                                        ->{g} a
  3112. data.NatSet.Nonempty.foldLeft.doc : Doc
  3113. data.NatSet.Nonempty.foldMap : (a ->{g} a ->{g} a)
                                       -> (Nat ->{g} a)
                                       -> NatSet.Nonempty
                                       ->{g} a
  3114. data.NatSet.Nonempty.foldMap.doc : Doc
  3115. data.NatSet.Nonempty.foldRight : (Nat ->{g} a ->{g} a)
                                         -> a
                                         ->{g} NatSet.Nonempty
                                         ->{g} a
  3116. data.NatSet.Nonempty.foldRight.doc : Doc
  3117. data.NatSet.Nonempty.fromList : List.Nonempty Nat
                                        -> NatSet.Nonempty
  3118. data.NatSet.Nonempty.fromList.doc : Doc
  3119. data.NatSet.Nonempty.getAbove : Nat
                                        -> NatSet.Nonempty
                                        -> Optional Nat
  3120. data.NatSet.Nonempty.getAbove.doc : Doc
  3121. data.NatSet.Nonempty.getAbove.test : [Result]
  3122. data.NatSet.Nonempty.getAtLeast : Nat
                                          -> NatSet.Nonempty
                                          -> Optional Nat
  3123. data.NatSet.Nonempty.getAtLeast.doc : Doc
  3124. data.NatSet.Nonempty.getAtLeast.test : [Result]
  3125. data.NatSet.Nonempty.getAtMost : Nat
                                         -> NatSet.Nonempty
                                         -> Optional Nat
  3126. data.NatSet.Nonempty.getAtMost.doc : Doc
  3127. data.NatSet.Nonempty.getAtMost.test : [Result]
  3128. data.NatSet.Nonempty.getBelow : Nat
                                        -> NatSet.Nonempty
                                        -> Optional Nat
  3129. data.NatSet.Nonempty.getBelow.doc : Doc
  3130. data.NatSet.Nonempty.getBelow.test : [Result]
  3131. data.NatSet.Nonempty.getMax : NatSet.Nonempty -> Nat
  3132. data.NatSet.Nonempty.getMax.doc : Doc
  3133. data.NatSet.Nonempty.getMax.test : [Result]
  3134. data.NatSet.Nonempty.getMin : NatSet.Nonempty -> Nat
  3135. data.NatSet.Nonempty.getMin.doc : Doc
  3136. data.NatSet.Nonempty.getMin.test : [Result]
  3137. data.NatSet.Nonempty.insert : Nat
                                      -> NatSet.Nonempty
                                      -> NatSet.Nonempty
  3138. data.NatSet.Nonempty.insert.doc : Doc
  3139. data.NatSet.Nonempty.insert.test.containsInserted : [Result]
  3140. data.NatSet.Nonempty.internal.deleteBitmap : Nat
                                                     -> Nat
                                                     -> NatSet.Nonempty
                                                     -> NatSet
  3141. data.NatSet.Nonempty.internal.deleteBitmap.doc : Doc
  3142. data.NatSet.Nonempty.internal.insertBitmap : Nat
                                                     -> Nat
                                                     -> NatSet.Nonempty
                                                     -> NatSet.Nonempty
  3143. data.NatSet.Nonempty.internal.insertBitmap.doc : Doc
  3144. data.NatSet.Nonempty.intersect : NatSet.Nonempty
                                         -> NatSet.Nonempty
                                         -> NatSet
  3145. data.NatSet.Nonempty.intersect.doc : Doc
  3146. data.NatSet.Nonempty.map : (Nat ->{g} Nat)
                                   -> NatSet.Nonempty
                                   ->{g} NatSet.Nonempty
  3147. data.NatSet.Nonempty.map.doc : Doc
  3148. data.NatSet.Nonempty.maxView : NatSet.Nonempty
                                       -> (Nat, NatSet)
  3149. data.NatSet.Nonempty.maxView.doc : Doc
  3150. data.NatSet.Nonempty.minView : NatSet.Nonempty
                                       -> (Nat, NatSet)
  3151. data.NatSet.Nonempty.minView.doc : Doc
  3152. data.NatSet.Nonempty.nth : Nat
                                   -> NatSet.Nonempty
                                   -> Optional Nat
  3153. data.NatSet.Nonempty.nth.doc : Doc
  3154. data.NatSet.Nonempty.nth.tests : [Result]
  3155. data.NatSet.Nonempty.ordering : NatSet.Nonempty
                                        -> NatSet.Nonempty
                                        -> Ordering
  3156. data.NatSet.Nonempty.partition : (Nat ->{g} Boolean)
                                         -> NatSet.Nonempty
                                         ->{g} (NatSet, NatSet)
  3157. data.NatSet.Nonempty.partition.doc : Doc
  3158. data.NatSet.Nonempty.properSubset : NatSet.Nonempty
                                            -> NatSet.Nonempty
                                            -> Boolean
  3159. data.NatSet.Nonempty.properSubset.doc : Doc
  3160. data.NatSet.Nonempty.properSuperset : NatSet.Nonempty
                                              -> NatSet.Nonempty
                                              -> Boolean
  3161. data.NatSet.Nonempty.properSuperset.doc : Doc
  3162. data.NatSet.Nonempty.randomChoice : NatSet.Nonempty
                                            ->{Random} Nat
  3163. data.NatSet.Nonempty.randomChoice.doc : Doc
  3164. data.NatSet.Nonempty.randomChoice.test : [Result]
  3165. data.NatSet.Nonempty.singleton : Nat -> NatSet.Nonempty
  3166. data.NatSet.Nonempty.size : NatSet.Nonempty -> Nat
  3167. data.NatSet.Nonempty.size.doc : Doc
  3168. data.NatSet.Nonempty.split : Nat
                                     -> NatSet.Nonempty
                                     -> (NatSet, NatSet)
  3169. data.NatSet.Nonempty.split.doc : Doc
  3170. data.NatSet.Nonempty.splitContains : Nat
                                             -> NatSet.Nonempty
                                             -> ( NatSet,
                                               Boolean,
                                               NatSet)
  3171. data.NatSet.Nonempty.splitContains.doc : Doc
  3172. data.NatSet.Nonempty.subset : NatSet.Nonempty
                                      -> NatSet.Nonempty
                                      -> Boolean
  3173. data.NatSet.Nonempty.subset.doc : Doc
  3174. data.NatSet.Nonempty.subsetCompare : NatSet.Nonempty
                                             -> NatSet.Nonempty
                                             -> Optional
                                               Ordering
  3175. data.NatSet.Nonempty.subsetCompare.doc : Doc
  3176. data.NatSet.Nonempty.superset : NatSet.Nonempty
                                        -> NatSet.Nonempty
                                        -> Boolean
  3177. data.NatSet.Nonempty.superset.doc : Doc
  3178. data.NatSet.Nonempty.Tip : Nat -> Nat -> NatSet.Nonempty
  3179. data.NatSet.Nonempty.tips : NatSet.Nonempty
                                    -> List.Nonempty
                                      NatSet.Nonempty
  3180. data.NatSet.Nonempty.tips.doc : Doc
  3181. data.NatSet.Nonempty.toList : NatSet.Nonempty
                                      -> List.Nonempty Nat
  3182. data.NatSet.Nonempty.toList.doc : Doc
  3183. data.NatSet.Nonempty.toListAscending : NatSet.Nonempty
                                               -> List.Nonempty
                                                 Nat
  3184. data.NatSet.Nonempty.toListAscending.doc : Doc
  3185. data.NatSet.Nonempty.toListDescending : NatSet.Nonempty
                                                -> List.Nonempty
                                                  Nat
  3186. data.NatSet.Nonempty.toListDescending.doc : Doc
  3187. data.NatSet.Nonempty.toNatSet : NatSet.Nonempty
                                        -> NatSet
  3188. data.NatSet.Nonempty.toNatSet.doc : Doc
  3189. data.NatSet.Nonempty.union : NatSet.Nonempty
                                     -> NatSet.Nonempty
                                     -> NatSet.Nonempty
  3190. data.NatSet.Nonempty.union.doc : Doc
  3191. data.NatSet.Nonempty.unions : List.Nonempty
                                        NatSet.Nonempty
                                      -> NatSet.Nonempty
  3192. data.NatSet.Nonempty.unions.doc : Doc
  3193. data.NatSet.ordering : NatSet -> NatSet -> Ordering
  3194. data.NatSet.ordering.doc : Doc
  3195. data.NatSet.ordering.test : [Result]
  3196. data.NatSet.partition : (Nat ->{g} Boolean)
                                -> NatSet
                                ->{g} (NatSet, NatSet)
  3197. data.NatSet.partition.doc : Doc
  3198. data.NatSet.partition.test : [Result]
  3199. data.NatSet.properSubset : NatSet -> NatSet -> Boolean
  3200. data.NatSet.properSubset.doc : Doc
  3201. data.NatSet.properSuperset : NatSet -> NatSet -> Boolean
  3202. data.NatSet.properSuperset.doc : Doc
  3203. data.NatSet.randomChoice : NatSet
                                   ->{Exception, Random} Nat
  3204. data.NatSet.randomChoice.doc : Doc
  3205. data.NatSet.randomChoice.test : [Result]
  3206. data.NatSet.singleton : Nat -> NatSet.Nonempty
  3207. data.NatSet.singleton.doc : Doc
  3208. data.NatSet.size : NatSet -> Nat
  3209. data.NatSet.size.doc : Doc
  3210. data.NatSet.size.test : [Result]
  3211. data.NatSet.split : Nat -> NatSet -> (NatSet, NatSet)
  3212. data.NatSet.split.doc : Doc
  3213. data.NatSet.split.test : [Result]
  3214. data.NatSet.splitContains : Nat
                                    -> NatSet
                                    -> (NatSet, Boolean, NatSet)
  3215. data.NatSet.splitContains.doc : Doc
  3216. data.NatSet.splitContains.test : [Result]
  3217. data.NatSet.subset : NatSet -> NatSet -> Boolean
  3218. data.NatSet.subset.doc : Doc
  3219. data.NatSet.subsetCompare : NatSet
                                    -> NatSet
                                    -> Optional Ordering
  3220. data.NatSet.subsetCompare.doc : Doc
  3221. data.NatSet.subsetCompare.test : [Result]
  3222. data.NatSet.superset : NatSet -> NatSet -> Boolean
  3223. data.NatSet.superset.doc : Doc
  3224. data.NatSet.takeMax : Nat -> NatSet -> NatSet
  3225. data.NatSet.takeMax.doc : Doc
  3226. data.NatSet.takeMin : Nat -> NatSet -> NatSet
  3227. data.NatSet.takeMin.doc : Doc
  3228. data.NatSet.tips : NatSet -> [NatSet.Nonempty]
  3229. data.NatSet.tips.doc : Doc
  3230. data.NatSet.toList : NatSet -> [Nat]
  3231. data.NatSet.toList.doc : Doc
  3232. data.NatSet.toList.test : [Result]
  3233. data.NatSet.toListAscending : NatSet -> [Nat]
  3234. data.NatSet.toListAscending.doc : Doc
  3235. data.NatSet.toListDescending : NatSet -> [Nat]
  3236. data.NatSet.toListDescending.doc : Doc
  3237. data.NatSet.toListDescending.test : [Result]
  3238. data.NatSet.union : NatSet -> NatSet -> NatSet
  3239. data.NatSet.union.doc : Doc
  3240. data.NatSet.union.test : [Result]
  3241. data.NatSet.unions : [NatSet] -> NatSet
  3242. data.NatSet.unions.doc : Doc
  3243. structural type data.OneOrBoth a b
  3244. data.OneOrBoth.Both : a -> b -> OneOrBoth a b
  3245. data.OneOrBoth.doc : Doc
  3246. data.OneOrBoth.fold : (a ->{e} c)
                              -> (b ->{f} c)
                              -> (a ->{g} b ->{h} c)
                              -> OneOrBoth a b
                              ->{e, f, g, h} c
  3247. data.OneOrBoth.fold.doc : Doc
  3248. data.OneOrBoth.isBoth : OneOrBoth a b -> Boolean
  3249. data.OneOrBoth.isBoth.doc : Doc
  3250. data.OneOrBoth.isThat : OneOrBoth a b -> Boolean
  3251. data.OneOrBoth.isThat.doc : Doc
  3252. data.OneOrBoth.isThis : OneOrBoth a b -> Boolean
  3253. data.OneOrBoth.isThis.doc : Doc
  3254. data.OneOrBoth.joinThat : (b ->{g1} b ->{g} b)
                                  -> OneOrBoth (OneOrBoth a b) b
                                  ->{g1, g} OneOrBoth a b
  3255. data.OneOrBoth.joinThat.doc : Doc
  3256. data.OneOrBoth.joinThis : (a ->{g1} a ->{g} a)
                                  -> OneOrBoth a (OneOrBoth a b)
                                  ->{g1, g} OneOrBoth a b
  3257. data.OneOrBoth.joinThis.doc : Doc
  3258. data.OneOrBoth.justBoth : OneOrBoth a b
                                  -> Optional (a, b)
  3259. data.OneOrBoth.justBoth.doc : Doc
  3260. data.OneOrBoth.justThat : OneOrBoth a b -> Optional b
  3261. data.OneOrBoth.justThat.doc : Doc
  3262. data.OneOrBoth.justThese : [OneOrBoth a b] -> [a]
  3263. data.OneOrBoth.justThese.doc : Doc
  3264. data.OneOrBoth.justThis : OneOrBoth a b -> Optional a
  3265. data.OneOrBoth.justThis.doc : Doc
  3266. data.OneOrBoth.justThose : [OneOrBoth a b] -> [b]
  3267. data.OneOrBoth.justThose.doc : Doc
  3268. data.OneOrBoth.mapBoth : (a ->{f} c)
                                 -> (b ->{g} d)
                                 -> OneOrBoth a b
                                 ->{f, g} OneOrBoth c d
  3269. data.OneOrBoth.mapBoth.doc : Doc
  3270. data.OneOrBoth.mapThat : (b ->{g} d)
                                 -> OneOrBoth a b
                                 ->{g} OneOrBoth a d
  3271. data.OneOrBoth.mapThat.doc : Doc
  3272. data.OneOrBoth.mapThis : (a ->{g} c)
                                 -> OneOrBoth a b
                                 ->{g} OneOrBoth c b
  3273. data.OneOrBoth.mapThis.doc : Doc
  3274. data.OneOrBoth.maybeThat : OneOrBoth a b -> Optional b
  3275. data.OneOrBoth.maybeThat.doc : Doc
  3276. data.OneOrBoth.maybeThis : OneOrBoth a b -> Optional a
  3277. data.OneOrBoth.maybeThis.doc : Doc
  3278. data.OneOrBoth.merge : (a ->{f} a ->{g} a)
                               -> OneOrBoth a a
                               ->{f, g} a
  3279. data.OneOrBoth.merge.doc : Doc
  3280. data.OneOrBoth.partition : [OneOrBoth a b]
                                   -> ([a], [b], [(a, b)])
  3281. data.OneOrBoth.partition.doc : Doc
  3282. data.OneOrBoth.That : b -> OneOrBoth a b
  3283. data.OneOrBoth.these : [OneOrBoth a b] -> [a]
  3284. data.OneOrBoth.these.doc : Doc
  3285. data.OneOrBoth.This : a -> OneOrBoth a b
  3286. data.OneOrBoth.those : [OneOrBoth a b] -> [b]
  3287. data.OneOrBoth.those.doc : Doc
  3288. data.OneOrBoth.toTuple : OneOrBoth a b
                                 -> a
                                 -> b
                                 -> (a, b)
  3289. data.OneOrBoth.toTuple.doc : Doc
  3290. structural type data.RoseTree a
  3291. data.RoseTree.doc : Doc
  3292. data.RoseTree.flatten : RoseTree a -> [a]
  3293. data.RoseTree.flatten.doc : Doc
  3294. data.RoseTree.flattens : [a] -> [RoseTree a] -> [a]
  3295. data.RoseTree.flattens.doc : Doc
  3296. data.RoseTree.Node : a -> [RoseTree a] -> RoseTree a
  3297. structural type data.SeqView a b
  3298. data.SeqView.doc : Doc
  3299. data.SeqView.VElem : a -> b -> SeqView a b
  3300. data.SeqView.VElem.doc : Doc
  3301. data.SeqView.VEmpty : SeqView a b
  3302. data.SeqView.VEmpty.doc : Doc
  3303. structural type data.Set a
  3304. data.Set.== : Set k -> Set k -> Boolean
  3305. data.Set.==.doc : Doc
  3306. data.Set.all : (a ->{e} Boolean) -> Set a ->{e} Boolean
  3307. data.Set.all.doc : Doc
  3308. data.Set.any : (a ->{e} Boolean) -> Set a ->{e} Boolean
  3309. data.Set.any.doc : Doc
  3310. data.Set.contains : k -> Set k -> Boolean
  3311. data.Set.contains.doc : Doc
  3312. data.Set.delete : k -> Set k -> Set k
  3313. data.Set.delete.doc : Doc
  3314. data.Set.delete.test : [Result]
  3315. data.Set.deletes : [a] -> Set a -> Set a
  3316. data.Set.deletes.doc : Doc
  3317. data.Set.deletes.test : [Result]
  3318. data.Set.difference : Set a -> Set a -> Set a
  3319. data.Set.difference.doc : Doc
  3320. data.Set.difference.test : [Result]
  3321. data.Set.doc : Doc
  3322. data.Set.elementAt : Nat -> Set a -> Optional a
  3323. data.Set.elementAt.doc : Doc
  3324. data.Set.elementAt.tests : [Result]
  3325. data.Set.empty : Set k
  3326. data.Set.empty.doc : Doc
  3327. data.Set.equals : Set k -> Set k -> Boolean
  3328. data.Set.equals.doc : Doc
  3329. data.Set.flatMap : (i ->{g} Set k) -> Set i ->{g} Set k
  3330. data.Set.flatMap.doc : Doc
  3331. data.Set.flatMap.tests.associative : [Result]
  3332. data.Set.flatMap.tests.unit : [Result]
  3333. data.Set.flatten : Set (Set k) -> Set k
  3334. data.Set.flatten.doc : Doc
  3335. data.Set.flatten.tests.associative : [Result]
  3336. data.Set.flatten.tests.unit : [Result]
  3337. data.Set.foldLeft : (b ->{e} a ->{e} b)
                            -> b
                            -> Set a
                            ->{e} b
  3338. data.Set.foldLeft.doc : Doc
  3339. data.Set.foldLeft.tests.homomorphism : [Result]
  3340. data.Set.foldRight : (a ->{e} b ->{e} b)
                             -> b
                             -> Set a
                             ->{e} b
  3341. data.Set.foldRight.doc : Doc
  3342. data.Set.foldRight.tests.homomorphism : [Result]
  3343. data.Set.fromList : [k] -> Set k
  3344. data.Set.fromList.doc : Doc
  3345. data.Set.fromText : Text -> Set Char
  3346. data.Set.fromText.doc : Doc
  3347. data.Set.inertNonempty.doc : Doc
  3348. data.Set.insert : k -> Set k -> Set k
  3349. data.Set.insert.doc : Doc
  3350. data.Set.insertNonempty : k -> Set k -> Set.Nonempty k
  3351. data.Set.insertNonempty.doc : Doc
  3352. data.Set.internal.Set : Map a () -> Set a
  3353. data.Set.internal.underlying : Set k -> Map k ()
  3354. data.Set.intersect : Set k -> Set k -> Set k
  3355. data.Set.intersect.doc : Doc
  3356. data.Set.intersects : [Set a] -> Set a
  3357. data.Set.intersects.doc : Doc
  3358. data.Set.intersects.test : [Result]
  3359. data.Set.isEmpty : Set k -> Boolean
  3360. data.Set.isEmpty.doc : Doc
  3361. data.Set.map : (a ->{e} b) -> Set a ->{e} Set b
  3362. data.Set.map.doc : Doc
  3363. data.Set.map.test : [Result]
  3364. structural type data.Set.Nonempty a
  3365. data.Set.Nonempty.== : Set.Nonempty k
                               -> Set.Nonempty k
                               -> Boolean
  3366. data.Set.Nonempty.==.doc : Doc
  3367. data.Set.Nonempty.all : (a ->{e} Boolean)
                                -> Set.Nonempty a
                                ->{e} Boolean
  3368. data.Set.Nonempty.all.doc : Doc
  3369. data.Set.Nonempty.any : (a ->{e} Boolean)
                                -> Set.Nonempty a
                                ->{e} Boolean
  3370. data.Set.Nonempty.any.doc : Doc
  3371. data.Set.Nonempty.contains : k
                                     -> Set.Nonempty k
                                     -> Boolean
  3372. data.Set.Nonempty.contains.doc : Doc
  3373. data.Set.Nonempty.delete : k -> Set.Nonempty k -> Set k
  3374. data.Set.Nonempty.delete.doc : Doc
  3375. data.Set.Nonempty.deletes : [a]
                                    -> Set.Nonempty a
                                    -> Set a
  3376. data.Set.Nonempty.deletes.doc : Doc
  3377. data.Set.Nonempty.doc : Doc
  3378. data.Set.Nonempty.elementAt : Nat
                                      -> Set.Nonempty a
                                      -> Optional a
  3379. data.Set.Nonempty.elementAt.doc : Doc
  3380. data.Set.Nonempty.equals : Set.Nonempty k
                                   -> Set.Nonempty k
                                   -> Boolean
  3381. data.Set.Nonempty.equals.doc : Doc
  3382. data.Set.Nonempty.flatMap : (i ->{g} Set.Nonempty k)
                                    -> Set.Nonempty i
                                    ->{g} Set.Nonempty k
  3383. data.Set.Nonempty.flatMap.doc : Doc
  3384. data.Set.Nonempty.flatten : Set.Nonempty
                                      (Set.Nonempty k)
                                    -> Set.Nonempty k
  3385. data.Set.Nonempty.flatten.doc : Doc
  3386. data.Set.Nonempty.foldLeft : (b ->{e} a ->{e} b)
                                     -> b
                                     -> Set.Nonempty a
                                     ->{e} b
  3387. data.Set.Nonempty.foldLeft.doc : Doc
  3388. data.Set.Nonempty.foldMap : (b ->{e} b ->{e} b)
                                    -> (a ->{e} b)
                                    -> Set.Nonempty a
                                    ->{e} b
  3389. data.Set.Nonempty.foldMap.doc : Doc
  3390. data.Set.Nonempty.foldRight : (a ->{e} b ->{e} b)
                                      -> b
                                      -> Set.Nonempty a
                                      ->{e} b
  3391. data.Set.Nonempty.foldRight.doc : Doc
  3392. data.Set.Nonempty.fromList : List.Nonempty k
                                     -> Set.Nonempty k
  3393. data.Set.Nonempty.fromList.doc : Doc
  3394. data.Set.Nonempty.fromListAnd : k
                                        -> [k]
                                        -> Set.Nonempty k
  3395. data.Set.Nonempty.fromListAnd.doc : Doc
  3396. data.Set.Nonempty.fromTextAnd : Char
                                        -> Text
                                        -> Set.Nonempty Char
  3397. data.Set.Nonempty.fromTextAnd.doc : Doc
  3398. data.Set.Nonempty.insert : k
                                   -> Set.Nonempty k
                                   -> Set.Nonempty k
  3399. data.Set.Nonempty.insert.doc : Doc
  3400. data.Set.Nonempty.internal.underlying : Set.Nonempty k
                                                -> Map.Nonempty
                                                  k ()
  3401. data.Set.Nonempty.intersect : Set.Nonempty k
                                      -> Set.Nonempty k
                                      -> Set k
  3402. data.Set.Nonempty.intersect.doc : Doc
  3403. data.Set.Nonempty.intersects : [Set.Nonempty a] -> Set a
  3404. data.Set.Nonempty.intersects.doc : Doc
  3405. data.Set.Nonempty.map : (a ->{e} b)
                                -> Set.Nonempty a
                                ->{e} Set.Nonempty b
  3406. data.Set.Nonempty.map.doc : Doc
  3407. data.Set.Nonempty.random : Set.Nonempty a ->{Random} a
  3408. data.Set.Nonempty.random.doc : Doc
  3409. data.Set.Nonempty.randomChoice : Set.Nonempty a
                                         ->{Random} a
  3410. data.Set.Nonempty.randomChoice.doc : Doc
  3411. data.Set.Nonempty.randomChoice.test : [Result]
  3412. data.Set.Nonempty.reduce : (a ->{e} a ->{e} a)
                                   -> Set.Nonempty a
                                   ->{e} a
  3413. data.Set.Nonempty.reduce.doc : Doc
  3414. data.Set.Nonempty.Set : Map.Nonempty a ()
                                -> Set.Nonempty a
  3415. data.Set.Nonempty.similarity : Set.Nonempty k
                                       -> Set.Nonempty k
                                       -> Float
  3416. data.Set.Nonempty.similarity.doc : Doc
  3417. data.Set.Nonempty.singleton : a -> Set.Nonempty a
  3418. data.Set.Nonempty.singleton.doc : Doc
  3419. data.Set.Nonempty.size : Set.Nonempty k -> Nat
  3420. data.Set.Nonempty.size.doc : Doc
  3421. data.Set.Nonempty.subset : Set.Nonempty a
                                   -> Set.Nonempty a
                                   -> Boolean
  3422. data.Set.Nonempty.subset.doc : Doc
  3423. data.Set.Nonempty.superset : Set.Nonempty a
                                     -> Set.Nonempty a
                                     -> Boolean
  3424. data.Set.Nonempty.superset.doc : Doc
  3425. data.Set.Nonempty.toList : Set.Nonempty k
                                   -> List.Nonempty k
  3426. data.Set.Nonempty.toList.doc : Doc
  3427. data.Set.Nonempty.toMap : (k ->{e} v)
                                  -> Set.Nonempty k
                                  ->{e} Map.Nonempty k v
  3428. data.Set.Nonempty.toMap.doc : Doc
  3429. data.Set.Nonempty.toSet : Set.Nonempty k -> Set k
  3430. data.Set.Nonempty.toSet.doc : Doc
  3431. data.Set.Nonempty.toText : Set.Nonempty Char -> Text
  3432. data.Set.Nonempty.toText.doc : Doc
  3433. data.Set.Nonempty.union : Set.Nonempty k
                                  -> Set.Nonempty k
                                  -> Set.Nonempty k
  3434. data.Set.Nonempty.union.doc : Doc
  3435. data.Set.Nonempty.unions : List.Nonempty
                                     (Set.Nonempty a)
                                   -> Set.Nonempty a
  3436. data.Set.Nonempty.unions.doc : Doc
  3437. data.Set.random : Set a ->{Random} Optional a
  3438. data.Set.random.doc : Doc
  3439. data.Set.randomChoice : Set a ->{Exception, Random} a
  3440. data.Set.randomChoice.doc : Doc
  3441. data.Set.randomChoice.test : [Result]
  3442. data.Set.similarity : Set k -> Set k -> Float
  3443. data.Set.similarity.doc : Doc
  3444. data.Set.singleton : a -> Set a
  3445. data.Set.singleton.doc : Doc
  3446. data.Set.singleton.test : [Result]
  3447. data.Set.size : Set k -> Nat
  3448. data.Set.size.doc : Doc
  3449. data.Set.subset : Set a -> Set a -> Boolean
  3450. data.Set.subset.doc : Doc
  3451. data.Set.superset : Set a -> Set a -> Boolean
  3452. data.Set.superset.doc : Doc
  3453. data.Set.toList : Set k -> [k]
  3454. data.Set.toList.doc : Doc
  3455. data.Set.toMap : (k ->{e} v) -> Set k ->{e} Map k v
  3456. data.Set.toMap.doc : Doc
  3457. data.Set.toText : Set Char -> Text
  3458. data.Set.toText.doc : Doc
  3459. data.Set.union : Set k -> Set k -> Set k
  3460. data.Set.union.doc : Doc
  3461. data.Set.unions : [Set a] -> Set a
  3462. data.Set.unions.doc : Doc
  3463. data.Set.unions.test : [Result]
  3464. structural ability data.Stream e
  3465. data.Stream.++ : (v1 ->{g, Stream a} v2)
                         -> (v2 ->{g, Stream a} v3)
                         -> v1
                         ->{g, Stream a} v3
  3466. data.Stream.++.doc : Doc
  3467. data.Stream.+: : a
                         -> '{g, Stream a} r
                         -> '{g, Stream a} r
  3468. data.Stream.+:.doc : Doc
  3469. data.Stream.all : (a ->{g} Boolean)
                          -> '{g, Stream a} r
                          ->{g} Boolean
  3470. data.Stream.all.doc : Doc
  3471. data.Stream.all.test : [Result]
  3472. data.Stream.any : (a ->{g} Boolean)
                          -> '{g, Stream a} r
                          ->{g} Boolean
  3473. data.Stream.any.doc : Doc
  3474. data.Stream.any.test : [Result]
  3475. data.Stream.changes : Boolean
                              -> '{g, Stream a} r
                              -> '{g, Stream a} r
  3476. data.Stream.changes.doc : Doc
  3477. data.Stream.changes.tests.multiple : [Result]
  3478. data.Stream.changes.tests.pair : [Result]
  3479. data.Stream.changes.tests.repeatSingle : [Result]
  3480. data.Stream.changes.tests.single : [Result]
  3481. data.Stream.changes! : Boolean
                               -> '{g, Stream a} r
                               ->{g, Stream a} r
  3482. data.Stream.changes!.doc : Doc
  3483. data.Stream.changesBy : (a -> a -> Boolean)
                                -> Boolean
                                -> '{g, Stream a} r
                                -> '{g, Stream a} r
  3484. data.Stream.changesBy.doc : Doc
  3485. data.Stream.changesBy! : (a -> a -> Boolean)
                                 -> Boolean
                                 -> '{g, Stream a} r
                                 ->{g, Stream a} r
  3486. data.Stream.changesBy!.doc : Doc
  3487. data.Stream.chunk : Nat
                            -> '{g, Stream a} r
                            -> '{g, Stream (List.Nonempty a)} r
  3488. data.Stream.chunk.doc : Doc
  3489. data.Stream.chunk.tests : [Result]
  3490. data.Stream.chunk! : Nat
                             -> '{g, Stream a} r
                             ->{g, Stream (List.Nonempty a)} r
  3491. data.Stream.chunk!.doc : Doc
  3492. data.Stream.collate : '{g1, Stream a} r
                              -> '{g2, Stream a} Void
                              -> '{g1, g2, Stream a} r
  3493. data.Stream.collate.doc : Doc
  3494. ability data.Stream.collate.test.Counter
  3495. data.Stream.collate.test.Counter.comma! : {Counter} ()
  3496. data.Stream.collate.test.Counter.nat! : {Counter} ()
  3497. data.Stream.collate.test.testIntersperse : [Result]
  3498. data.Stream.collate! : '{g1, Stream a} r
                               -> '{g2, Stream a} Void
                               ->{g1, g2, Stream a} r
  3499. data.Stream.collate!.doc : Doc
  3500. data.Stream.collate!.handler1 : '{g2} Void
                                        -> Request (Stream a) r
                                        ->{g2, Stream a} r
  3501. data.Stream.collate!.handler2 : a
                                        -> '{g2} r
                                        -> Request
                                          (Stream a) Void
                                        ->{g2, Stream a} r
  3502. data.Stream.collate!.handler3 : '{g2} Void
                                        -> Request (Stream a) r
                                        ->{g2, Stream a} r
  3503. data.Stream.concatMap : (a ->{e} [b])
                                -> '{e, Stream a} r
                                -> '{e, Stream b} r
  3504. data.Stream.concatMap.doc : Doc
  3505. data.Stream.concatMap! : (a ->{e} [b])
                                 -> '{e, Stream a} r
                                 ->{e, Stream b} r
  3506. data.Stream.concatMap!.doc : Doc
  3507. data.Stream.contains : a
                               -> '{g, Stream a} r
                               ->{g} Boolean
  3508. data.Stream.contains.doc : Doc
  3509. data.Stream.contains.test : [Result]
  3510. data.Stream.doc : Doc
  3511. data.Stream.drain : '{g, Stream a} r ->{g} r
  3512. data.Stream.drain.doc : Doc
  3513. data.Stream.drop : Nat
                           -> '{g, Stream a} r
                           -> '{g, Stream a} r
  3514. data.Stream.drop.doc : Doc
  3515. data.Stream.drop.test : [Result]
  3516. data.Stream.drop! : Nat
                            -> '{g, Stream a} r
                            ->{g, Stream a} r
  3517. data.Stream.drop!.doc : Doc
  3518. data.Stream.dropWhile : (a ->{e} Boolean)
                                -> '{f, Stream a} r
                                -> '{e, f, Stream a} r
  3519. data.Stream.dropWhile.doc : Doc
  3520. data.Stream.dropWhile.tests.effects : [Result]
  3521. data.Stream.dropWhile! : (a ->{e} Boolean)
                                 -> '{f, Stream a} r
                                 ->{e, f, Stream a} r
  3522. data.Stream.dropWhile!.doc : Doc
  3523. data.Stream.dropWhile!.tests.effects : [Result]
  3524. data.Stream.emit : e ->{Stream e} ()
  3525. data.Stream.emit.doc : Doc
  3526. data.Stream.emitAndReturn : a -> '{Stream a} a
  3527. data.Stream.emitAndReturn.doc : Doc
  3528. data.Stream.emitAndReturn! : a ->{Stream a} a
  3529. data.Stream.emitAndReturn!.doc : Doc
  3530. data.Stream.filter : (a ->{g} Boolean)
                             -> '{g, Stream a} r
                             -> '{g, Stream a} r
  3531. data.Stream.filter.doc : Doc
  3532. data.Stream.filter.test : [Result]
  3533. data.Stream.filter! : (a ->{g} Boolean)
                              -> '{g, Stream a} r
                              ->{g, Stream a} r
  3534. data.Stream.filter!.doc : Doc
  3535. data.Stream.filterMap : (a ->{g} Optional b)
                                -> '{g, Stream a} r
                                -> '{g, Stream b} r
  3536. data.Stream.filterMap.tests.filters : [Result]
  3537. data.Stream.filterMap.tests.identityLaw : [Result]
  3538. data.Stream.filterMap! : (a ->{g} Optional b)
                                 -> '{g, Stream a} r
                                 ->{g, Stream b} r
  3539. data.Stream.find : (a ->{g} Boolean)
                           -> '{g, Stream a} r
                           ->{g} Optional a
  3540. data.Stream.find.doc : Doc
  3541. data.Stream.find.test : [Result]
  3542. data.Stream.flatMap : (a ->{g, Stream b} any)
                              -> '{g, Stream a} r
                              -> '{g, Stream b} r
  3543. data.Stream.flatMap.doc : Doc
  3544. data.Stream.flatMap.test : [Result]
  3545. data.Stream.flatMap! : (a ->{g, Stream b} any)
                               -> '{g, Stream a} r
                               ->{g, Stream b} r
  3546. data.Stream.flatMap!.doc : Doc
  3547. data.Stream.fold : (b ->{g} a ->{g} b)
                           -> b
                           -> '{g, Stream a} r
                           ->{g} b
  3548. data.Stream.fold.doc : Doc
  3549. data.Stream.fold.test : [Result]
  3550. data.Stream.foldBalanced : (a ->{g1} b)
                                   -> b
                                   -> (b -> b ->{g2} b)
                                   -> '{g3, Stream a} r
                                   ->{g1, g2, g3} b
  3551. data.Stream.foldBalanced.doc : Doc
  3552. data.Stream.foldBalanced.test : [Result]
  3553. data.Stream.foldDelayed : (b ->{g} a ->{g} b)
                                  -> b
                                  -> '{g, Stream a} r
                                  -> '{g} b
  3554. data.Stream.foldDelayed.doc : Doc
  3555. data.Stream.foldDelayedRight : (a ->{g} b ->{g} b)
                                       -> b
                                       -> '{g, Stream a} r
                                       -> '{g} b
  3556. data.Stream.foldDelayedRight.doc : Doc
  3557. data.Stream.foldDelayedWithResult : (b ->{g} a ->{g} b)
                                            -> b
                                            -> '{g, Stream a} r
                                            -> '{g} (b, r)
  3558. data.Stream.foldDelayedWithResult.doc : Doc
  3559. data.Stream.foldRight : (a ->{g} b ->{g} b)
                                -> b
                                -> '{g, Stream a} r
                                ->{g} b
  3560. data.Stream.foldRight.doc : Doc
  3561. data.Stream.foldWithResult : (b ->{g} a ->{g} b)
                                     -> b
                                     -> '{g, Stream a} r
                                     ->{g} (b, r)
  3562. data.Stream.foldWithResult.doc : Doc
  3563. data.Stream.foldWithResult.handler : (b ->{g} a ->{g} b)
                                             -> b
                                             -> Request
                                               (Stream a) r
                                             ->{g} (b, r)
  3564. data.Stream.foldWithResult.test : [Result]
  3565. data.Stream.foreach : (a ->{g} ())
                              -> '{g, Stream a} r
                              ->{g} r
  3566. data.Stream.foreach.doc : Doc
  3567. data.Stream.from : Nat -> '{Stream Nat} a
  3568. data.Stream.from.doc : Doc
  3569. data.Stream.from! : Nat ->{Stream Nat} a
  3570. data.Stream.from!.doc : Doc
  3571. data.Stream.fromList : [a] -> '{Stream a} ()
  3572. data.Stream.fromList.doc : Doc
  3573. data.Stream.fromList! : [a] ->{Stream a} ()
  3574. data.Stream.fromList!.doc : Doc
  3575. data.Stream.head : '{g, Stream a} r ->{g} Optional a
  3576. data.Stream.head.doc : Doc
  3577. data.Stream.indexed : '{g, Stream a} r
                              -> '{g, Stream (a, Nat)} r
  3578. data.Stream.indexed.doc : Doc
  3579. data.Stream.indexed! : '{g, Stream a} r
                               ->{g, Stream (a, Nat)} r
  3580. data.Stream.indexed!.doc : Doc
  3581. data.Stream.Int.all : '{Stream Int} a
  3582. data.Stream.Int.all.doc : Doc
  3583. data.Stream.Int.from : Int -> '{Stream Int} a
  3584. data.Stream.Int.from.doc : Doc
  3585. data.Stream.Int.from! : Int ->{Stream Int} a
  3586. data.Stream.Int.from!.doc : Doc
  3587. data.Stream.Int.negatives : '{Stream Int} a
  3588. data.Stream.Int.negatives.doc : Doc
  3589. data.Stream.Int.positives : '{Stream Int} a
  3590. data.Stream.Int.positives.doc : Doc
  3591. data.Stream.Int.range : Int -> Int -> '{Stream Int} ()
  3592. data.Stream.Int.range.doc : Doc
  3593. data.Stream.Int.range! : Int
                                 ->{Stream Int} Int
                                 ->{Stream Int} ()
  3594. data.Stream.Int.range!.doc : Doc
  3595. data.Stream.interleave : '{g, Stream a} r
                                 -> '{g, Stream a} r
                                 -> '{g, Stream a} r
  3596. data.Stream.interleave.doc : Doc
  3597. data.Stream.interleave! : '{g, Stream a} r
                                  -> '{g, Stream a} r
                                  ->{g, Stream a} r
  3598. data.Stream.interleave!.doc : Doc
  3599. data.Stream.interleave!.handler : '{e} r
                                          -> Request
                                            (Stream a) r
                                          ->{e, Stream a} r
  3600. data.Stream.intersperse : a
                                  -> '{g, Stream a} r
                                  -> '{g, Stream a} r
  3601. data.Stream.intersperse.doc : Doc
  3602. data.Stream.intersperse! : a
                                   -> '{g, Stream a} r
                                   ->{g, Stream a} r
  3603. data.Stream.intersperse!.doc : Doc
  3604. data.Stream.iterate : (a ->{g} a)
                              -> a
                              -> '{g, Stream a} Void
  3605. data.Stream.iterate.doc : Doc
  3606. data.Stream.iterate.tests.ex1 : [Result]
  3607. data.Stream.iterate! : (a ->{g} a)
                               -> a
                               ->{g, Stream a} Void
  3608. data.Stream.iterate!.doc : Doc
  3609. data.Stream.map : (a ->{g} b)
                          -> '{g, Stream a} r
                          -> '{g, Stream b} r
  3610. data.Stream.map.doc : Doc
  3611. data.Stream.map.test : [Result]
  3612. data.Stream.map! : (a ->{g} b)
                           -> '{g, Stream a} r
                           ->{g, Stream b} r
  3613. data.Stream.map!.doc : Doc
  3614. data.Stream.Nat.all : '{Stream Nat} a
  3615. data.Stream.Nat.all.doc : Doc
  3616. data.Stream.pipe : '{g, Stream a} r
                           -> '{g, Ask a, Stream b} r
                           -> '{g, Stream b} r
  3617. data.Stream.pipe.doc : Doc
  3618. data.Stream.pipe! : '{g, Stream a} r
                            -> '{g, Ask a, Stream b} r
                            ->{g, Stream b} r
  3619. data.Stream.pipe!.doc : Doc
  3620. data.Stream.pipe!.handler : '{g, Stream a} r
                                    -> Request
                                      {Ask a, Stream b} r
                                    ->{g, Stream b} r
  3621. data.Stream.range : Nat -> Nat -> '{Stream Nat} ()
  3622. data.Stream.range.doc : Doc
  3623. data.Stream.range.test.emptyRange : [Result]
  3624. data.Stream.range.test.emptyRange2 : [Result]
  3625. data.Stream.range.test.listLike : [Result]
  3626. data.Stream.range.test.singletonRange : [Result]
  3627. data.Stream.range! : Nat -> Nat ->{Stream Nat} ()
  3628. data.Stream.range!.doc : Doc
  3629. data.Stream.rangeClosed : Nat -> Nat -> '{Stream Nat} ()
  3630. data.Stream.rangeClosed.doc : Doc
  3631. data.Stream.rangeClosed! : Nat -> Nat ->{Stream Nat} ()
  3632. data.Stream.rangeClosed!.doc : Doc
  3633. data.Stream.repeat : '{g} a -> '{g, Stream a} Void
  3634. data.Stream.repeat.doc : Doc
  3635. data.Stream.scan : (b ->{g} a ->{g} b)
                           -> b
                           -> '{g, Stream a} r
                           -> '{g, Stream b} r
  3636. data.Stream.scan.doc : Doc
  3637. data.Stream.scan! : (b ->{g} a ->{g} b)
                            -> b
                            -> '{g, Stream a} r
                            ->{g, Stream b} r
  3638. data.Stream.scan!.doc : Doc
  3639. data.Stream.somes : '{g, Stream (Optional a)} r
                            -> '{g, Stream a} r
  3640. data.Stream.somes.doc : Doc
  3641. data.Stream.somes! : '{g, Stream (Optional a)} r
                             ->{g, Stream a} r
  3642. data.Stream.somes!.doc : Doc
  3643. data.Stream.span : (a ->{g} Boolean)
                           -> '{g, Stream a} r
                           ->{g} ([a], '{g, Stream a} r)
  3644. data.Stream.span.doc : Doc
  3645. data.Stream.splitAt : Nat
                              -> '{g, Stream a} r
                              ->{g} ([a], '{g, Stream a} r)
  3646. data.Stream.splitAt.doc : Doc
  3647. data.Stream.tails : '{g, Stream a} r
                            -> '{g, Stream ('{Stream a, g} r)} r
  3648. data.Stream.tails.doc : Doc
  3649. data.Stream.tails! : '{g, Stream a} r
                             ->{g, Stream ('{Stream a, g} r)} r
  3650. data.Stream.tails!.doc : Doc
  3651. data.Stream.take : Nat
                           -> '{g, Stream a} t
                           -> '{g, Stream a} Optional t
  3652. data.Stream.take.doc : Doc
  3653. data.Stream.take.tests.completion : [Result]
  3654. data.Stream.take.tests.earlyTermination : [Result]
  3655. data.Stream.take.tests.pullMinimal : [Result]
  3656. data.Stream.take! : Nat
                            -> '{g, Stream a} r
                            ->{g, Stream a} Optional r
  3657. data.Stream.take!.doc : Doc
  3658. data.Stream.takeWhile : (a ->{g} Boolean)
                                -> '{g, Stream a} r
                                -> '{g, Stream a} Optional r
  3659. data.Stream.takeWhile.doc : Doc
  3660. data.Stream.takeWhile.tests.worksLikeList : [Result]
  3661. data.Stream.takeWhile! : (a ->{g} Boolean)
                                 -> '{g, Stream a} r
                                 ->{g, Stream a} Optional r
  3662. data.Stream.takeWhile!.doc : Doc
  3663. data.Stream.tap : (x ->{g1} ())
                          -> '{g2, Stream x} r
                          -> '{g1, g2, Stream x} r
  3664. data.Stream.tap.doc : Doc
  3665. data.Stream.tap! : (x ->{g1} ())
                           -> '{g2, Stream x} r
                           ->{g1, g2, Stream x} r
  3666. data.Stream.tap!.doc : Doc
  3667. data.Stream.terminated : '{g, Stream a} r
                                 -> '{g, Stream (Optional a)} r
  3668. data.Stream.terminated.doc : Doc
  3669. data.Stream.terminated.test : [Result]
  3670. data.Stream.terminated! : '{g, Stream a} r
                                  ->{g, Stream (Optional a)} r
  3671. data.Stream.terminated!.doc : Doc
  3672. data.Stream.tests.ex1 : [Result]
  3673. data.Stream.to : Nat -> '{Stream Nat} ()
  3674. data.Stream.to.doc : Doc
  3675. data.Stream.to! : Nat ->{Stream Nat} ()
  3676. data.Stream.to!.doc : Doc
  3677. data.Stream.toDelayedList : '{g, Stream a} r -> '{g} [a]
  3678. data.Stream.toDelayedList.doc : Doc
  3679. data.Stream.toDelayedList.handler : Request
                                              {Stream a} ()
                                            -> [a]
  3680. data.Stream.toDelayedList.test.bidirectional : [Result]
  3681. data.Stream.toDelayedListWithResult : '{g, Stream a} r
                                              -> '{g} ([a], r)
  3682. data.Stream.toDelayedListWithResult.doc : Doc
  3683. data.Stream.toList : '{g, Stream a} r ->{g} [a]
  3684. data.Stream.toList.doc : Doc
  3685. data.Stream.toListWithResult : '{g, Stream a} r
                                       ->{g} ([a], r)
  3686. data.Stream.toListWithResult.doc : Doc
  3687. data.Stream.trace : Text -> '{g, Stream a} r ->{g} r
  3688. data.Stream.trace.doc : Doc
  3689. data.Stream.uncons : '{g, Stream a} r
                             ->{g} Either
                               r (a, '{g, Stream a} r)
  3690. data.Stream.uncons.doc : Doc
  3691. data.Stream.uncons.tests : [Result]
  3692. data.Stream.unfold : s
                             -> (s ->{g} Optional (a, s))
                             -> '{g, Stream a} ()
  3693. data.Stream.unfold.doc : Doc
  3694. data.Stream.until : Nat -> '{Stream Nat} ()
  3695. data.Stream.until.doc : Doc
  3696. data.Stream.until! : Nat ->{Stream Nat} ()
  3697. data.Stream.until!.doc : Doc
  3698. data.Stream.window : Nat
                             -> '{g, Stream a} r
                             -> '{g, Stream [a]} r
  3699. data.Stream.window.doc : Doc
  3700. data.Stream.window! : Nat
                              -> '{g, Stream a} r
                              ->{g, Stream [a]} r
  3701. data.Stream.window!.doc : Doc
  3702. data.Stream.zip : '{g, Stream a} r
                          -> '{g, Stream b} r
                          -> '{g, Stream (a, b)} r
  3703. data.Stream.zip.doc : Doc
  3704. data.Stream.zip! : '{g, Stream a} r
                           -> '{g, Stream b} r
                           ->{g, Stream (a, b)} r
  3705. data.Stream.zip!.doc : Doc
  3706. data.Stream.zipWith : (a ->{g} b ->{g} c)
                              -> '{g, Stream a} r
                              -> '{g, Stream b} r
                              -> '{g, Stream c} r
  3707. data.Stream.zipWith.doc : Doc
  3708. data.Stream.zipWith! : (a ->{g} b ->{g} c)
                               -> '{g, Stream a} r
                               -> '{g, Stream b} r
                               ->{g, Stream c} r
  3709. data.Stream.zipWith!.doc : Doc
  3710. structural type data.Trie k v
  3711. data.Trie.doc : Doc
  3712. data.Trie.empty : Trie k v
  3713. data.Trie.empty.doc : Doc
  3714. data.Trie.fromList : [([k], v)] -> Trie k v
  3715. data.Trie.gen : '{Gen} k -> '{Gen} v -> '{Gen} Trie k v
  3716. data.Trie.gen.doc : Doc
  3717. data.Trie.head : Trie k v -> Optional v
  3718. data.Trie.head.doc : Doc
  3719. data.Trie.head.modify : (Optional v ->{𝕖} Optional v)
                                -> Trie k v
                                ->{𝕖} Trie k v
  3720. data.Trie.head.modify.doc : Doc
  3721. data.Trie.head.set : Optional v -> Trie k v -> Trie k v
  3722. data.Trie.head.set.doc : Doc
  3723. data.Trie.insert : [k] -> v -> Trie k v -> Trie k v
  3724. data.Trie.insert.doc : Doc
  3725. data.Trie.lookup : [k] -> Trie k v -> Optional v
  3726. data.Trie.lookup.doc : Doc
  3727. data.Trie.map : (v1 ->{e} v2)
                        ->{e} Trie k v1
                        ->{e} Trie k v2
  3728. data.Trie.map.doc : Doc
  3729. data.Trie.mapKeys : (k1 ->{e} k2)
                            ->{e} Trie k1 v
                            ->{e} Trie k2 v
  3730. data.Trie.mapKeys.doc : Doc
  3731. data.Trie.singleton : [k] -> v -> Trie k v
  3732. data.Trie.singleton.doc : Doc
  3733. data.Trie.tail : Trie k v -> Map k (Trie k v)
  3734. data.Trie.tail.doc : Doc
  3735. data.Trie.tail.modify : (Map k111 (Trie k111 v)
                                ->{𝕖} Map k (Trie k v))
                                -> Trie k111 v
                                ->{𝕖} Trie k v
  3736. data.Trie.tail.modify.doc : Doc
  3737. data.Trie.tail.set : Map k (Trie k v)
                             -> Trie k111 v
                             -> Trie k v
  3738. data.Trie.tail.set.doc : Doc
  3739. data.Trie.text.fromList : [(Text, v)] -> Trie Char v
  3740. data.Trie.text.fromList.doc : Doc
  3741. data.Trie.text.insert : Text
                                -> v
                                -> Trie Char v
                                -> Trie Char v
  3742. data.Trie.text.insert.doc : Doc
  3743. data.Trie.text.lookup : Text
                                -> Trie Char v
                                -> Optional v
  3744. data.Trie.text.lookup.doc : Doc
  3745. data.Trie.text.toList : Trie Char v -> [(Text, v)]
  3746. data.Trie.text.toList.doc : Doc
  3747. data.Trie.toList : Trie k v -> [([k], v)]
  3748. data.Trie.toList.doc : Doc
  3749. data.Trie.toMap : Trie k v -> Map [k] v
  3750. data.Trie.toMap.doc : Doc
  3751. data.Trie.Trie : Optional v
                         -> Map k (Trie k v)
                         -> Trie k v
  3752. data.Trie.union : Trie k v -> Trie k v -> Trie k v
  3753. data.Trie.union.doc : Doc
  3754. data.Trie.union.tests.values : [Result]
  3755. data.Trie.unionWith : (v ->{e} v ->{e} v)
                              ->{e} Trie k v
                              ->{e} Trie k v
                              ->{e} Trie k v
  3756. data.Trie.unionWith.doc : Doc
  3757. data.Trie.values : Trie k v -> [v]
  3758. data.Trie.values.doc : Doc
  3759. structural type data.Tuple a b
  3760. data.Tuple.at1 : Tuple a b -> a
  3761. data.Tuple.at1.doc : Doc
  3762. data.Tuple.at1.tests.ex1 : [Result]
  3763. data.Tuple.at2 : Tuple a (Tuple b c) -> b
  3764. data.Tuple.at2.doc : Doc
  3765. data.Tuple.at2.tests.ex1 : [Result]
  3766. data.Tuple.at3 : Tuple a (Tuple b (Tuple c d)) -> c
  3767. data.Tuple.at3.doc : Doc
  3768. data.Tuple.at3.tests.ex1 : [Result]
  3769. data.Tuple.at3.tests.ex2 : [Result]
  3770. data.Tuple.at4 : Tuple a (Tuple b (Tuple c (Tuple d e)))
                         -> d
  3771. data.Tuple.at4.doc : Doc
  3772. data.Tuple.at4.tests.ex1 : [Result]
  3773. data.Tuple.at4.tests.ex2 : [Result]
  3774. data.Tuple.bimap : (a ->{g1} b) -> (a, a) ->{g1} (b, b)
  3775. data.Tuple.bimap.doc : Doc
  3776. data.Tuple.Cons : a -> b -> Tuple a b
  3777. data.Tuple.Cons.doc : Doc
  3778. data.Tuple.doc : Doc
  3779. data.Tuple.first : (i ->{g} o)
                           -> Tuple i b
                           ->{g} Tuple o b
  3780. data.Tuple.first.doc : Doc
  3781. data.Tuple.mapLeft : (a ->{g} b) -> (a, c) ->{g} (b, c)
  3782. data.Tuple.mapLeft.doc : Doc
  3783. data.Tuple.mapPair : ((a ->{g} b), (c ->{g} d))
                             -> (a, c)
                             ->{g} (b, d)
  3784. data.Tuple.mapPair.doc : Doc
  3785. data.Tuple.mapRight : (a ->{g} b) -> (c, a) ->{g} (c, b)
  3786. data.Tuple.mapRight.doc : Doc
  3787. data.Tuple.pair : a -> b -> (a, b)
  3788. data.Tuple.pair.doc : Doc
  3789. data.Tuple.second : (i ->{g} o)
                            -> Tuple a (Tuple i b)
                            ->{g} Tuple a (Tuple o b)
  3790. data.Tuple.second.doc : Doc
  3791. data.Tuple.swap : (a, b) -> (b, a)
  3792. data.Tuple.swap.doc : Doc
  3793. data.Tuple.tests.ex1 : [Result]
  3794. data.Tuple.tests.ex2 : [Result]
  3795. Debug.tap : Text -> a -> a
  3796. Debug.tap.doc : Doc
  3797. Debug.toDebugText : a -> Text
  3798. Debug.toDebugText.doc : Doc
  3799. Debug.toDebugText.impl : a
                                 -> Optional (Either Text Text)
  3800. Debug.toDebugText.impl.doc : Doc
  3801. Debug.trace : Text -> a -> ()
  3802. Debug.trace.doc : Doc
  3803. Debug.watch : Text -> a -> a
  3804. Debug.watch.doc : Doc
  3805. type Doc
  3806. Doc.++ : Doc -> Doc -> Doc
  3807. Doc.Anchor : Text -> Doc -> Doc
  3808. Doc.Anchor.doc : Doc
  3809. Doc.Aside : Doc -> Doc
  3810. Doc.Blankline : Doc
  3811. Doc.Blockquote : Doc -> Doc
  3812. Doc.Bold : Doc -> Doc
  3813. Doc.BulletedList : [Doc] -> Doc
  3814. Doc.BulletedList.doc : Doc
  3815. Doc.Callout : Optional Doc -> Doc -> Doc
  3816. Doc.Callout.doc : Doc
  3817. Doc.Code : Doc -> Doc
  3818. Doc.codeBlock : Text -> Text -> Doc
  3819. Doc.CodeBlock : Text -> Doc -> Doc
  3820. Doc.codeBlock.doc : Doc
  3821. Doc.CodeBlock.doc : Doc
  3822. Doc.Column : [Doc] -> Doc
  3823. Doc.Column.doc : Doc
  3824. type Doc.Deprecated
  3825. Doc.Deprecated.++ : Deprecated
                            -> Deprecated
                            -> Deprecated
  3826. Doc.Deprecated.Blob : Text -> Deprecated
  3827. Doc.Deprecated.Evaluate : Link.Term -> Deprecated
  3828. Doc.Deprecated.example : Link.Term -> Deprecated
  3829. Doc.Deprecated.example.doc : Deprecated
  3830. Doc.Deprecated.Join : [Deprecated] -> Deprecated
  3831. Doc.Deprecated.Link : Link -> Deprecated
  3832. Doc.Deprecated.Signature : Link.Term -> Deprecated
  3833. Doc.Deprecated.Source : Link -> Deprecated
  3834. Doc.doc : Doc
  3835. type Doc.EmbedSvg
  3836. Doc.EmbedSvg.doc : Doc
  3837. Doc.EmbedSvg.embedSvg : Text -> Doc
  3838. Doc.EmbedSvg.EmbedSvg : Text -> EmbedSvg
  3839. Doc.EmbedSvg.embedSvg.doc : Doc
  3840. Doc.EmbedSvg.embedSvg.example : Doc
  3841. Doc.Folded : Boolean -> Doc -> Doc -> Doc
  3842. Doc.Folded.doc : Doc
  3843. type Doc.FrontMatter
  3844. Doc.FrontMatter.doc : Doc
  3845. Doc.FrontMatter.frontMatter : [(Text, Text)] -> Doc
  3846. Doc.FrontMatter.FrontMatter : [(Text, Text)]
                                      -> FrontMatter
  3847. Doc.FrontMatter.frontMatter.doc : Doc
  3848. Doc.Group : Doc -> Doc
  3849. Doc.Image : Doc -> Doc -> Optional Doc -> Doc
  3850. Doc.Italic : Doc -> Doc
  3851. Doc.Join : [Doc] -> Doc
  3852. Doc.Join.doc : Doc
  3853. type Doc.LaTeXInline
  3854. Doc.LaTeXInline.doc : Doc
  3855. Doc.LaTeXInline.laTeXInline : Doc -> Doc
  3856. Doc.LaTeXInline.LaTeXInline : Text -> LaTeXInline
  3857. Doc.LaTeXInline.laTeXInline.doc : Doc
  3858. Doc.Linebreak : Doc
  3859. type Doc.MediaSource
  3860. Doc.MediaSource.doc : Doc
  3861. Doc.MediaSource.MediaSource : Text
                                      -> Optional Text
                                      -> MediaSource
  3862. Doc.MediaSource.mimeType : MediaSource -> Optional Text
  3863. Doc.MediaSource.mimeType.doc : Doc
  3864. Doc.MediaSource.mimeType.modify : (Optional Text
                                          ->{g} Optional Text)
                                          -> MediaSource
                                          ->{g} MediaSource
  3865. Doc.MediaSource.mimeType.modify.doc : Doc
  3866. Doc.MediaSource.mimeType.set : Optional Text
                                       -> MediaSource
                                       -> MediaSource
  3867. Doc.MediaSource.mimeType.set.doc : Doc
  3868. Doc.MediaSource.sourceUrl : MediaSource -> Text
  3869. Doc.MediaSource.sourceUrl.doc : Doc
  3870. Doc.MediaSource.sourceUrl.modify : (Text ->{g} Text)
                                           -> MediaSource
                                           ->{g} MediaSource
  3871. Doc.MediaSource.sourceUrl.modify.doc : Doc
  3872. Doc.MediaSource.sourceUrl.set : Text
                                        -> MediaSource
                                        -> MediaSource
  3873. Doc.MediaSource.sourceUrl.set.doc : Doc
  3874. Doc.NamedLink : Doc -> Doc -> Doc
  3875. Doc.NumberedList : Nat -> [Doc] -> Doc
  3876. Doc.NumberedList.doc : Doc
  3877. Doc.Paragraph : [Doc] -> Doc
  3878. Doc.Paragraph.doc : Doc
  3879. Doc.Section : Doc -> [Doc] -> Doc
  3880. Doc.SectionBreak : Doc
  3881. Doc.shareSlug : Text -> Doc
  3882. Doc.shareSlug.doc : Doc
  3883. Doc.Special : SpecialForm -> Doc
  3884. Doc.Special.doc : Doc
  3885. type Doc.SpecialForm
  3886. Doc.SpecialForm.doc : Doc
  3887. Doc.SpecialForm.Embed : Any -> SpecialForm
  3888. Doc.SpecialForm.EmbedInline : Any -> SpecialForm
  3889. Doc.SpecialForm.Eval : Doc.Term -> SpecialForm
  3890. Doc.SpecialForm.EvalInline : Doc.Term -> SpecialForm
  3891. Doc.SpecialForm.Example : Nat -> Doc.Term -> SpecialForm
  3892. Doc.SpecialForm.ExampleBlock : Nat
                                       -> Doc.Term
                                       -> SpecialForm
  3893. Doc.SpecialForm.FoldedSource : [( Either Type Doc.Term,
                                         [Doc.Term])]
                                       -> SpecialForm
  3894. Doc.SpecialForm.Link : Either Type Doc.Term
                               -> SpecialForm
  3895. Doc.SpecialForm.Link.doc : Doc
  3896. Doc.SpecialForm.Signature : [Doc.Term] -> SpecialForm
  3897. Doc.SpecialForm.SignatureInline : Doc.Term
                                          -> SpecialForm
  3898. Doc.SpecialForm.Source : [( Either Type Doc.Term,
                                   [Doc.Term])]
                                 -> SpecialForm
  3899. Doc.Strikethrough : Doc -> Doc
  3900. Doc.Style : Text -> Doc -> Doc
  3901. Doc.Style.doc : Doc
  3902. Doc.Table : [[Doc]] -> Doc
  3903. type Doc.Term
  3904. Doc.term : '{g1} a -> Doc.Term
  3905. Doc.Term.doc : Doc
  3906. Doc.term.doc : Doc
  3907. Doc.Term.Term : Any -> Doc.Term
  3908. Doc.Text.doc : Doc
  3909. Doc.Tooltip : Doc -> Doc -> Doc
  3910. Doc.UntitledSection : [Doc] -> Doc
  3911. Doc.UntitledSection.doc : Doc
  3912. type Doc.Video
  3913. Doc.Video.config : Video -> [(Text, Text)]
  3914. Doc.Video.config.doc : Doc
  3915. Doc.Video.config.modify : ([(Text, Text)]
                                  ->{g} [(Text, Text)])
                                  -> Video
                                  ->{g} Video
  3916. Doc.Video.config.set : [(Text, Text)] -> Video -> Video
  3917. Doc.Video.config.set.doc : Doc
  3918. Doc.Video.doc : Doc
  3919. Doc.Video.sources : Video -> [MediaSource]
  3920. Doc.Video.sources.doc : Doc
  3921. Doc.Video.sources.modify : ([MediaSource]
                                   ->{g} [MediaSource])
                                   -> Video
                                   ->{g} Video
  3922. Doc.Video.sources.modify.doc : Doc
  3923. Doc.Video.sources.set : [MediaSource] -> Video -> Video
  3924. Doc.Video.sources.set.doc : Doc
  3925. Doc.Video.video : Text -> Text -> Doc
  3926. Doc.Video.Video : [MediaSource]
                          -> [(Text, Text)]
                          -> Video
  3927. Doc.Video.video.doc : Doc
  3928. Doc.Word : Text -> Doc
  3929. Doc.Word.doc : Doc
  3930. docs.abilitiesTutorialLink : Doc
  3931. docs.arrays : Doc
  3932. docs.basicAbilities : Doc
  3933. docs.basicDataTypes : Doc
  3934. docs.collectionTypes : Doc
  3935. docs.concurrency : Doc
  3936. docs.higherOrderFunctions : Doc
  3937. docs.inputOutput : Doc
  3938. docs.languageSupport : Doc
  3939. docs.networkAccess : Doc
  3940. docs.primitiveTypes : Doc
  3941. docs.tests : Doc
  3942. structural type Either a b
  3943. Either.bimap : (a ->{g} b)
                       -> (c ->{g} d)
                       -> Either a c
                       ->{g} Either b d
  3944. Either.bimap.doc : Doc
  3945. Either.doc : Doc
  3946. Either.flatMapRight : (a ->{g1} Either e b)
                              -> Either e a
                              ->{g1} Either e b
  3947. Either.flatMapRight.doc : Doc
  3948. Either.flattenRight : Either e (Either e a)
                              -> Either e a
  3949. Either.flattenRight.doc : Doc
  3950. Either.fold : (a ->{e} c)
                      -> (b ->{e} c)
                      -> Either a b
                      ->{e} c
  3951. Either.fold.doc : Doc
  3952. Either.isLeft : Either a b -> Boolean
  3953. Either.isLeft.doc : Doc
  3954. Either.isRight : Either a b -> Boolean
  3955. Either.isRight.doc : Doc
  3956. Either.left : Either l r -> Optional l
  3957. Either.Left : a -> Either a b
  3958. Either.left.doc : Doc
  3959. Either.Left.doc : Doc
  3960. Either.mapLeft : (a ->{𝕖} b)
                         -> Either a z
                         ->{𝕖} Either b z
  3961. Either.mapLeft.doc : Doc
  3962. Either.mapLeft.tests.ex1 : [Result]
  3963. Either.mapRight : (a ->{𝕖} b)
                          -> Either e a
                          ->{𝕖} Either e b
  3964. Either.mapRight.doc : Doc
  3965. Either.mapRight.tests.ex1 : [Result]
  3966. Either.raiseMessage : v -> Either Text a ->{Exception} a
  3967. Either.raiseMessage.doc : Doc
  3968. Either.right : Either l r -> Optional r
  3969. Either.Right : b -> Either a b
  3970. Either.Right.doc : Doc
  3971. Either.right.doc : Doc
  3972. Either.toAbort : Either a b ->{Abort} b
  3973. Either.toAbort.doc : Doc
  3974. Either.toBug : Either e a -> a
  3975. Either.toBug.doc : Doc
  3976. Either.toException : Either Failure a ->{Exception} a
  3977. Either.toException.doc : Doc
  3978. Either.toOptional : Either a b -> Optional b
  3979. Either.toOptional.doc : Doc
  3980. Either.toThrow : Either e a ->{Throw e} a
  3981. Either.toThrow.doc : Doc
  3982. Either.unwrap : Either a a -> a
  3983. Either.unwrap.doc : Doc
  3984. builtin type Float
  3985. Float.!= : Float -> Float -> Boolean
  3986. Float.* : Float -> Float -> Float
  3987. Float.+ : Float -> Float -> Float
  3988. Float.- : Float -> Float -> Float
  3989. Float./ : Float -> Float -> Float
  3990. Float.< : Float -> Float -> Boolean
  3991. Float.<= : Float -> Float -> Boolean
  3992. Float.== : Float -> Float -> Boolean
  3993. Float.> : Float -> Float -> Boolean
  3994. Float.>= : Float -> Float -> Boolean
  3995. Float.abs : Float -> Float
  3996. Float.abs.doc : Doc
  3997. Float.acos : Float -> Float
  3998. Float.acos.doc : Doc
  3999. Float.acosh : Float -> Float
  4000. Float.acosh.doc : Doc
  4001. Float.asin : Float -> Float
  4002. Float.asin.doc : Doc
  4003. Float.asinh : Float -> Float
  4004. Float.asinh.doc : Doc
  4005. Float.atan : Float -> Float
  4006. Float.atan.doc : Doc
  4007. Float.atan2 : Float -> Float -> Float
  4008. Float.atan2.doc : Doc
  4009. Float.atanh : Float -> Float
  4010. Float.atanh.doc : Doc
  4011. Float.ceiling : Float -> Float
  4012. Float.ceiling.deprecated : Float -> Int
  4013. Float.ceiling.doc : Doc
  4014. Float.ceiling.tests.adjunction : [Result]
  4015. Float.clamp : Float -> Float -> Float -> Float
  4016. Float.clamp.doc : Doc
  4017. Float.clamp.test : [Result]
  4018. Float.components : Float ->{Throw Text} (Int, Nat)
  4019. Float.components.doc : Doc
  4020. Float.cos : Float -> Float
  4021. Float.cos.doc : Doc
  4022. Float.cosh : Float -> Float
  4023. Float.cosh.doc : Doc
  4024. Float.doc : Doc
  4025. Float.e : Float
  4026. Float.e.doc : Doc
  4027. Float.emod : Float -> Float ->{Exception} Float
  4028. Float.emod.doc : Doc
  4029. Float.emod.truncatesTowardsZero : [Result]
  4030. Float.eq : Float -> Float -> Boolean
  4031. Float.eq.doc : Doc
  4032. Float.equalUpTo : Float -> Float -> Float -> Boolean
  4033. Float.equalUpTo.doc : Doc
  4034. Float.exp : Float -> Float
  4035. Float.exp.doc : Doc
  4036. Float.floor : Float -> Float
  4037. Float.floor.deprecated : Float -> Int
  4038. Float.floor.doc : Doc
  4039. Float.floor.tests.adjunction : [Result]
  4040. Float.fromHalfPrecision : Nat -> Float
  4041. Float.fromHalfPrecision.doc : Doc
  4042. Float.fromHalfPrecision.tests.largestSubnormal : [Result]
  4043. Float.fromHalfPrecision.tests.maxHalf : [Result]
  4044. Float.fromHalfPrecision.tests.negativeOne : [Result]
  4045. Float.fromHalfPrecision.tests.negativeZero : [Result]
  4046. Float.fromHalfPrecision.tests.normal : [Result]
  4047. Float.fromHalfPrecision.tests.notANumber : [Result]
  4048. Float.fromHalfPrecision.tests.positiveOne : [Result]
  4049. Float.fromHalfPrecision.tests.positiveZero : [Result]
  4050. Float.fromHalfPrecision.tests.smallestNormal : [Result]
  4051. Float.fromHalfPrecision.tests.subnormal : [Result]
  4052. Float.fromInt : Int -> Float
  4053. Float.fromInt.doc : Doc
  4054. Float.fromNat : Nat -> Float
  4055. Float.fromNat.doc : Doc
  4056. Float.fromRepresentation : Nat -> Float
  4057. Float.fromRepresentation.doc : Doc
  4058. Float.fromSinglePrecision : Nat -> Float
  4059. Float.fromSinglePrecision.doc : Doc
  4060. Float.fromSinglePrecision.tests.largestSubnormal : [Result]
  4061. Float.fromSinglePrecision.tests.maxSingle : [Result]
  4062. Float.fromSinglePrecision.tests.negativeOne : [Result]
  4063. Float.fromSinglePrecision.tests.negativeZero : [Result]
  4064. Float.fromSinglePrecision.tests.normal : [Result]
  4065. Float.fromSinglePrecision.tests.notANumber : [Result]
  4066. Float.fromSinglePrecision.tests.positiveOne : [Result]
  4067. Float.fromSinglePrecision.tests.positiveZero : [Result]
  4068. Float.fromSinglePrecision.tests.smallestNormal : [Result]
  4069. Float.fromSinglePrecision.tests.subnormal : [Result]
  4070. Float.fromText : Text -> Optional Float
  4071. Float.fromText.doc : Doc
  4072. Float.gt : Float -> Float -> Boolean
  4073. Float.gt.doc : Doc
  4074. Float.gteq : Float -> Float -> Boolean
  4075. Float.gteq.doc : Doc
  4076. Float.Infinity : Float
  4077. Float.Infinity.doc : Doc
  4078. Float.inRange : Float -> Float -> Float -> Boolean
  4079. Float.inRange.doc : Doc
  4080. Float.isInfinity : Float -> Boolean
  4081. Float.isInfinity.doc : Doc
  4082. Float.isNaN : Float -> Boolean
  4083. Float.isNaN.doc : Doc
  4084. Float.isNegativeInfinity : Float -> Boolean
  4085. Float.isNegativeInfinity.doc : Doc
  4086. Float.log : Float -> Float
  4087. Float.log.doc : Doc
  4088. Float.logBase : Float -> Float -> Float
  4089. Float.logBase.doc : Doc
  4090. Float.lt : Float -> Float -> Boolean
  4091. Float.lt.doc : Doc
  4092. Float.lteq : Float -> Float -> Boolean
  4093. Float.lteq.doc : Doc
  4094. Float.max : Float -> Float -> Float
  4095. Float.max.doc : Doc
  4096. Float.maxFloat : Float
  4097. Float.maxFloat.doc : Doc
  4098. Float.min : Float -> Float -> Float
  4099. Float.min.doc : Doc
  4100. Float.minFloat : Float
  4101. Float.minFloat.doc : Doc
  4102. Float.mod : Float -> Float ->{Exception} Float
  4103. Float.mod.doc : Doc
  4104. Float.NaN : Float
  4105. Float.NaN.doc : Doc
  4106. Float.negate : Float -> Float
  4107. Float.negate.doc : Doc
  4108. Float.NegativeInfinity : Float
  4109. Float.NegativeInfinity.doc : Doc
  4110. Float.neq : Float -> Float -> Boolean
  4111. Float.neq.doc : Doc
  4112. Float.pi : Float
  4113. Float.pi.doc : Doc
  4114. Float.pow : Float -> Float -> Float
  4115. Float.pow.doc : Doc
  4116. Float.product : [Float] -> Float
  4117. Float.product.doc : Doc
  4118. Float.rawExponent : Float -> Nat
  4119. Float.rawExponent.doc : Doc
  4120. Float.rawMantissa : Float -> Nat
  4121. Float.rawMantissa.doc : Doc
  4122. Float.reciprocal : Float -> Float
  4123. Float.reciprocal.doc : Doc
  4124. Float.round : Float -> Float
  4125. Float.round.deprecated : Float -> Int
  4126. Float.round.doc : Doc
  4127. Float.roundTo : Nat -> Float ->{Exception} Float
  4128. Float.roundTo.doc : Doc
  4129. Float.roundToWith : (Float -> Float)
                            -> Nat
                            -> Float
                            ->{Exception} Float
  4130. Float.roundToWith.doc : Doc
  4131. Float.safeEmod : Float -> Float -> Optional Float
  4132. Float.safeEmod.doc : Doc
  4133. Float.safeEmod.test : [Result]
  4134. Float.safeMod : Float -> Float -> Optional Float
  4135. Float.safeMod.doc : Doc
  4136. Float.safeMod.test : [Result]
  4137. Float.safeRoundTo : Nat -> Float -> Optional Float
  4138. Float.safeRoundTo.doc : Doc
  4139. Float.safeRoundToWith : (Float -> Float)
                                -> Nat
                                -> Float
                                -> Optional Float
  4140. Float.safeRoundToWith.doc : Doc
  4141. Float.safeRoundToWith.tests.gen : [Result]
  4142. Float.safeRoundToWith.tests.static : [Result]
  4143. Float.signBit : Float -> Nat
  4144. Float.signBit.doc : Doc
  4145. Float.sin : Float -> Float
  4146. Float.sin.doc : Doc
  4147. Float.sinh : Float -> Float
  4148. Float.sinh.doc : Doc
  4149. Float.sqrt : Float -> Float
  4150. Float.sqrt.doc : Doc
  4151. Float.sum : [Float] -> Float
  4152. Float.sum.doc : Doc
  4153. Float.tan : Float -> Float
  4154. Float.tan.doc : Doc
  4155. Float.tanh : Float -> Float
  4156. Float.tanh.doc : Doc
  4157. Float.toHalfPrecision : Float -> Nat
  4158. Float.toHalfPrecision.doc : Doc
  4159. Float.toHalfPrecision.monotonic : [Result]
  4160. Float.toHalfPrecision.tests.largestSubnormal : [Result]
  4161. Float.toHalfPrecision.tests.maxHalf : [Result]
  4162. Float.toHalfPrecision.tests.negativeOne : [Result]
  4163. Float.toHalfPrecision.tests.negativeZero : [Result]
  4164. Float.toHalfPrecision.tests.normal : [Result]
  4165. Float.toHalfPrecision.tests.notANumber : [Result]
  4166. Float.toHalfPrecision.tests.positiveOne : [Result]
  4167. Float.toHalfPrecision.tests.positiveZero : [Result]
  4168. Float.toHalfPrecision.tests.smallestNormal : [Result]
  4169. Float.toHalfPrecision.tests.subnormal : [Result]
  4170. Float.toInt : Float -> Optional Int
  4171. Float.toInt.doc : Doc
  4172. Float.toNat : Float -> Optional Nat
  4173. Float.toNat.doc : Doc
  4174. Float.toNat.tests.cornerCase : [Result]
  4175. Float.toNat.tests.roundtrip : [Result]
  4176. Float.toNat.tests.small : [Result]
  4177. Float.toRepresentation : Float -> Nat
  4178. Float.toRepresentation.doc : Doc
  4179. Float.toSinglePrecision : Float -> Nat
  4180. Float.toSinglePrecision.doc : Doc
  4181. Float.toSinglePrecision.monotonic : [Result]
  4182. Float.toSinglePrecision.tests.largestSubnormal : [Result]
  4183. Float.toSinglePrecision.tests.maxSingle : [Result]
  4184. Float.toSinglePrecision.tests.negativeOne : [Result]
  4185. Float.toSinglePrecision.tests.negativeZero : [Result]
  4186. Float.toSinglePrecision.tests.normal : [Result]
  4187. Float.toSinglePrecision.tests.notANumber : [Result]
  4188. Float.toSinglePrecision.tests.positiveOne : [Result]
  4189. Float.toSinglePrecision.tests.positiveZero : [Result]
  4190. Float.toSinglePrecision.tests.smallestNormal : [Result]
  4191. Float.toSinglePrecision.tests.subnormal : [Result]
  4192. Float.toText : Float -> Text
  4193. Float.toText.doc : Doc
  4194. Float.truncate : Float -> Float
  4195. Float.truncate.doc : Doc
  4196. Float.ulp : Float -> Float
  4197. Float.ulp.doc : Doc
  4198. Float.ulpDiff : Float -> Float -> Nat
  4199. Float.ulpDiff.doc : Doc
  4200. Float.unsafeToInt : Float -> Int
  4201. Float.unsafeToInt.doc : Doc
  4202. Float.withinULPs : Nat -> Float -> Float -> Boolean
  4203. Float.withinULPs.doc : Doc
  4204. Function.&&& : (a ->{g} b)
                       -> (a ->{h} c)
                       -> a
                       ->{g, h} (b, c)
  4205. Function.&&&.doc : Doc
  4206. Function.<< : (b ->{𝕖} c) -> (a ->{𝕖} b) -> a ->{𝕖} c
  4207. Function.<<.doc : Doc
  4208. Function.<| : (a ->{𝕖} b) -> a ->{𝕖} b
  4209. Function.<|.doc : Doc
  4210. Function.<|| : (r ->{g} a)
                       -> (r ->{e} a ->{f} b)
                       -> r
                       ->{e, f, g} b
  4211. Function.<||.doc : Doc
  4212. Function.>> : (a ->{𝕖} b) -> (b ->{𝕖} c) -> a ->{𝕖} c
  4213. Function.>>.doc : Doc
  4214. Function.andThen : (a ->{𝕖} b)
                           -> (b ->{𝕖} c)
                           -> a
                           ->{𝕖} c
  4215. Function.andThen.doc : Doc
  4216. Function.apply2 : (a ->{e} b ->{e} c)
                          -> (r ->{e} a)
                          -> (r ->{e} b)
                          -> r
                          ->{e} c
  4217. Function.apply2.doc : Doc
  4218. Function.applyAll : [a ->{e} b] -> a ->{e} [b]
  4219. Function.applyAll.doc : Doc
  4220. Function.both : (a ->{g} b)
                        -> (a ->{h} c)
                        -> a
                        ->{g, h} (b, c)
  4221. Function.both.doc : Doc
  4222. Function.compose : (b ->{𝕖} c)
                           -> (a ->{𝕖} b)
                           -> a
                           ->{𝕖} c
  4223. Function.compose.doc : Doc
  4224. Function.compose2 : (c ->{𝕖} d)
                            -> (a ->{𝕖} b ->{𝕖} c)
                            -> a
                            -> b
                            ->{𝕖} d
  4225. Function.compose2.doc : Doc
  4226. Function.compose3 : (d ->{f} e)
                            -> (a ->{g} b ->{h} c ->{i} d)
                            -> a
                            -> b
                            -> c
                            ->{f, g, h, i} e
  4227. Function.compose3.doc : Doc
  4228. Function.composeK : (b ->{e} r ->{e} c)
                            -> (a ->{e} r ->{e} b)
                            -> a
                            -> r
                            ->{e} c
  4229. Function.composeK.doc : Doc
  4230. Function.const : a -> b -> a
  4231. Function.const.doc : Doc
  4232. Function.curry : ((a, b) ->{e} c) -> a -> b ->{e} c
  4233. Function.curry.doc : Doc
  4234. Function.delay : (a ->{g} b) -> a -> '{g} b
  4235. Function.delay.doc : Doc
  4236. Function.fix : ('{e} a ->{e} a) ->{e} a
  4237. Function.fix.doc : Doc
  4238. Function.fix.examples.factorial.explicitRecursion : Nat
  4239. Function.fix.examples.factorial.fixpoint : Nat
  4240. Function.flatMap : (a -> r ->{e} b)
                           -> (r ->{e} a)
                           -> r
                           ->{e} b
  4241. Function.flatMap.doc : Doc
  4242. Function.flip : (a ->{e} b ->{e} c) -> b -> a ->{e} c
  4243. Function.flip.doc : Doc
  4244. Function.id : a -> a
  4245. Function.id.doc : Doc
  4246. Function.join : (i ->{g} i ->{h} o) -> i ->{g, h} o
  4247. Function.join.doc : Doc
  4248. Function.loopWhile : (a ->{e} (a, Boolean)) -> a ->{e} a
  4249. Function.loopWhile.doc : Doc
  4250. Function.on : (b ->{e} b ->{e} c)
                      -> (a ->{e} b)
                      -> a
                      -> a
                      ->{e} c
  4251. Function.on.doc : Doc
  4252. Function.on.examples.equalOn : Boolean
  4253. Function.tap : (a ->{g} ()) -> a ->{g} a
  4254. Function.tap.doc : Doc
  4255. Function.tap.tests.t1 : [Result]
  4256. Function.times : (a ->{e} a) -> Nat -> a ->{e} a
  4257. Function.times.doc : Doc
  4258. Function.uncurry : (a ->{e} b ->{e} c) -> (a, b) ->{e} c
  4259. Function.uncurry.doc : Doc
  4260. Function.|> : a -> (a ->{𝕖} b) ->{𝕖} b
  4261. Function.|>.doc : Doc
  4262. Function.||> : (r ->{e} a ->{f} b)
                       -> (r ->{g} a)
                       -> r
                       ->{e, f, g} b
  4263. Function.||>.doc : Doc
  4264. type GUID
  4265. GUID.doc : Doc
  4266. GUID.GUID : Bytes -> GUID
  4267. GUID.new : '{Random} GUID
  4268. GUID.new.deprecated : Text -> Text -> GUID
  4269. GUID.new.deprecated.doc : Doc
  4270. GUID.toBase16 : GUID -> Text
  4271. GUID.toBase16.doc : Doc
  4272. GUID.toBytes : GUID -> Bytes
  4273. GUID.toBytes.doc : Doc
  4274. Hash.Murmur.add : Nat -> Nat -> Nat
  4275. Hash.Murmur.add.doc : Doc
  4276. Hash.Murmur.finish : Nat -> Nat
  4277. Hash.Murmur.finish.doc : Doc
  4278. Hash.Murmur.impl.murmur_m : Nat
  4279. Hash.Murmur.impl.murmur_r : Nat
  4280. Hash.Murmur.initialSeed : Nat
  4281. Hash.Murmur.initialSeed.doc : Doc
  4282. Hash.Murmur.Readme : Doc
  4283. ignore : a -> ()
  4284. ignore.doc : Doc
  4285. builtin type Int
  4286. Int.!= : Int -> Int -> Boolean
  4287. Int.!=.doc : Doc
  4288. Int.% : Int -> Int -> Int
  4289. Int.%.doc : Doc
  4290. Int.* : Int -> Int -> Int
  4291. Int.*.doc : Doc
  4292. Int.+ : Int -> Int -> Int
  4293. Int.+.doc : Doc
  4294. Int.- : Int -> Int -> Int
  4295. Int.-.doc : Doc
  4296. Int./ : Int -> Int -> Int
  4297. Int./.doc : Doc
  4298. Int.< : Int -> Int -> Boolean
  4299. Int.<.doc : Doc
  4300. Int.<= : Int -> Int -> Boolean
  4301. Int.<=.doc : Doc
  4302. Int.== : Int -> Int -> Boolean
  4303. Int.==.doc : Doc
  4304. Int.> : Int -> Int -> Boolean
  4305. Int.>.doc : Doc
  4306. Int.>= : Int -> Int -> Boolean
  4307. Int.>=.doc : Doc
  4308. Int.abs : Int -> Nat
  4309. Int.abs.doc : Doc
  4310. Int.and : Int -> Int -> Int
  4311. Int.and.doc : Doc
  4312. Int.clamp : Int -> Int -> Int -> Int
  4313. Int.clamp.doc : Doc
  4314. Int.clamp.test : [Result]
  4315. Int.complement : Int -> Int
  4316. Int.complement.doc : Doc
  4317. Int.decrement : Int -> Int
  4318. Int.decrement.doc : Doc
  4319. Int.decrement.test : [Result]
  4320. Int.diff : Int -> Int -> Nat
  4321. Int.diff.doc : Doc
  4322. Int.div : Int -> Int -> Int
  4323. Int.div.doc : Doc
  4324. Int.div.impl : Int -> Int -> Int
  4325. Int.div.tests.galois : [Result]
  4326. Int.div.tests.range : [Result]
  4327. Int.doc : Doc
  4328. Int.ediv : Int -> Int -> Int
  4329. Int.ediv.doc : Doc
  4330. Int.ediv.tests.adjunction : [Result]
  4331. Int.emod : Int -> Int -> Nat
  4332. Int.emod.doc : Doc
  4333. Int.eq : Int -> Int -> Boolean
  4334. Int.eq.doc : Doc
  4335. Int.fromRepresentation : Nat -> Int
  4336. Int.fromRepresentation.doc : Doc
  4337. Int.fromText : Text -> Optional Int
  4338. Int.fromText.doc : Doc
  4339. Int.gcd : Int -> Int ->{Abort} Nat
  4340. Int.gcd.doc : Doc
  4341. Int.gcd.tests.commonDivisor : [Result]
  4342. Int.gcd.tests.multipleOfAnyCD : [Result]
  4343. Int.gt : Int -> Int -> Boolean
  4344. Int.gt.doc : Doc
  4345. Int.gteq : Int -> Int -> Boolean
  4346. Int.gteq.doc : Doc
  4347. Int.increment : Int -> Int
  4348. Int.increment.doc : Doc
  4349. Int.inRange : Int -> Int -> Int -> Boolean
  4350. Int.inRange.doc : Doc
  4351. Int.inRange.test : [Result]
  4352. Int.isEven : Int -> Boolean
  4353. Int.isEven.doc : Doc
  4354. Int.isNegative : Int -> Boolean
  4355. Int.isNegative.doc : Doc
  4356. Int.isOdd : Int -> Boolean
  4357. Int.isOdd.doc : Doc
  4358. Int.lcm : Int -> Int ->{Abort} Int
  4359. Int.lcm.doc : Doc
  4360. Int.leadingZeros : Int -> Nat
  4361. Int.leadingZeros.doc : Doc
  4362. Int.lt : Int -> Int -> Boolean
  4363. Int.lt.doc : Doc
  4364. Int.lteq : Int -> Int -> Boolean
  4365. Int.lteq.doc : Doc
  4366. Int.max : Int -> Int -> Int
  4367. Int.max.doc : Doc
  4368. Int.maxInt : Int
  4369. Int.maxInt.doc : Doc
  4370. Int.maxValue.doc : Doc
  4371. Int.maybeMultiply : Int -> Int ->{Abort} Int
  4372. Int.maybeMultiply.doc : Doc
  4373. Int.min : Int -> Int -> Int
  4374. Int.min.doc : Doc
  4375. Int.minInt : Int
  4376. Int.minInt.doc : Doc
  4377. Int.mod : Int -> Int -> Int
  4378. Int.mod.doc : Doc
  4379. Int.mod.test : [Result]
  4380. Int.negate : Int -> Int
  4381. Int.negate.doc : Doc
  4382. Int.neq : Int -> Int -> Boolean
  4383. Int.neq.doc : Doc
  4384. Int.or : Int -> Int -> Int
  4385. Int.or.doc : Doc
  4386. Int.popCount : Int -> Nat
  4387. Int.popCount.doc : Doc
  4388. Int.pow : Int -> Nat -> Int
  4389. Int.pow.doc : Doc
  4390. Int.product : [Int] -> Int
  4391. Int.product.doc : Doc
  4392. Int.range : Int -> Int -> [Int]
  4393. Int.range.doc : Doc
  4394. Int.range.examples.invalid.descFromNeg : [Int]
  4395. Int.range.examples.invalid.descFromPos : [Int]
  4396. Int.range.examples.valid.ascFromNeg : [Int]
  4397. Int.range.examples.valid.ascFromNeg2 : [Int]
  4398. Int.range.examples.valid.ascFromPos : [Int]
  4399. Int.range.tests.invalid.descFromNeg : [Result]
  4400. Int.range.tests.invalid.descFromPos : [Result]
  4401. Int.range.tests.valid.ascFromNeg : [Result]
  4402. Int.range.tests.valid.ascFromNeg2 : [Result]
  4403. Int.range.tests.valid.ascFromPos : [Result]
  4404. Int.rangeClosed : Int -> Int -> [Int]
  4405. Int.rangeClosed.doc : Doc
  4406. Int.safeDiv : Int -> Int -> Optional Int
  4407. Int.safeDiv.doc : Doc
  4408. Int.safeEdiv : Int -> Int -> Optional Int
  4409. Int.safeEdiv.doc : Doc
  4410. Int.safeEmod : Int -> Int -> Optional Nat
  4411. Int.safeEmod.doc : Doc
  4412. Int.safeMod : Int -> Int -> Optional Int
  4413. Int.safeMod.doc : Doc
  4414. Int.shiftLeft : Int -> Nat -> Int
  4415. Int.shiftLeft.doc : Doc
  4416. Int.shiftRight : Int -> Nat -> Int
  4417. Int.shiftRight.doc : Doc
  4418. Int.shiftRightL : Int -> Nat -> Int
  4419. Int.shiftRightL.doc : Doc
  4420. Int.signum : Int -> Int
  4421. Int.signum.doc : Doc
  4422. Int.sum : [Int] -> Int
  4423. Int.sum.doc : Doc
  4424. Int.toFloat : Int -> Float
  4425. Int.toFloat.doc : Doc
  4426. Int.toNat : Int -> Optional Nat
  4427. Int.toNat.doc : Doc
  4428. Int.toRepresentation : Int -> Nat
  4429. Int.toRepresentation.doc : Doc
  4430. Int.toText : Int -> Text
  4431. Int.toText.doc : Doc
  4432. Int.toTextBase : Nat -> Int -> Optional Text
  4433. Int.toTextBase.doc : Doc
  4434. Int.trailingZeros : Int -> Nat
  4435. Int.trailingZeros.doc : Doc
  4436. Int.truncate0 : Int -> Nat
  4437. Int.truncate0.doc : Doc
  4438. Int.xor : Int -> Int -> Int
  4439. Int.xor.doc : Doc
  4440. builtin type IO
  4441. IO.arrayOf : a -> Nat ->{IO} mutable.Array {IO} a
  4442. IO.arrayOf.doc : Doc
  4443. IO.byteArray : Nat ->{IO} mutable.ByteArray {IO}
  4444. IO.byteArray.doc : Doc
  4445. IO.byteArrayOf : Nat
                         -> Nat
                         ->{IO} mutable.ByteArray {IO}
  4446. IO.byteArrayOf.doc : Doc
  4447. IO.byteArrayOf.test : '{IO, Exception} [Result]
  4448. IO.catchAll : '{IO, Exception} a ->{IO} Either Failure a
  4449. IO.catchAll.doc : Doc
  4450. IO.catchAll.tests.catchArithmeticFailure : '{IO,
                                                   Exception} [Result]
  4451. IO.catchAll.tests.catchBug : '{IO, Exception} [Result]
  4452. IO.concurrent.fork : '{IO} () ->{IO} ThreadId
  4453. IO.concurrent.fork.doc : Doc
  4454. IO.concurrent.fork.impl : '{IO} a ->{IO} ThreadId
  4455. IO.concurrent.fork_ : '{IO} () ->{IO} ()
  4456. IO.concurrent.fork_.doc : Doc
  4457. IO.concurrent.kill : ThreadId ->{IO, Exception} ()
  4458. IO.concurrent.kill.doc : Doc
  4459. IO.concurrent.kill.impl : ThreadId
                                  ->{IO} Either Failure ()
  4460. builtin type IO.concurrent.MVar
  4461. IO.concurrent.MVar.doc : Doc
  4462. IO.concurrent.MVar.isEmpty : MVar a ->{IO} Boolean
  4463. IO.concurrent.MVar.isEmpty.doc : Doc
  4464. IO.concurrent.MVar.modify : MVar a
                                    -> (a
                                    ->{IO, Exception} (a, b))
                                    ->{IO, Exception} b
  4465. IO.concurrent.MVar.modify.doc : Doc
  4466. IO.concurrent.MVar.new : a ->{IO} MVar a
  4467. IO.concurrent.MVar.new.doc : Doc
  4468. IO.concurrent.MVar.newEmpty : '{IO} MVar a
  4469. IO.concurrent.MVar.newEmpty.doc : Doc
  4470. IO.concurrent.MVar.put : MVar a
                                 -> a
                                 ->{IO, Exception} ()
  4471. IO.concurrent.MVar.put.doc : Doc
  4472. IO.concurrent.MVar.put.impl : MVar a
                                      -> a
                                      ->{IO} Either Failure ()
  4473. IO.concurrent.MVar.read : MVar a ->{IO, Exception} a
  4474. IO.concurrent.MVar.read.doc : Doc
  4475. IO.concurrent.MVar.read.impl : MVar a
                                       ->{IO} Either Failure a
  4476. IO.concurrent.MVar.swap : MVar a
                                  -> a
                                  ->{IO, Exception} a
  4477. IO.concurrent.MVar.swap.doc : Doc
  4478. IO.concurrent.MVar.swap.impl : MVar a
                                       -> a
                                       ->{IO} Either Failure a
  4479. IO.concurrent.MVar.take : MVar a ->{IO, Exception} a
  4480. IO.concurrent.MVar.take.doc : Doc
  4481. IO.concurrent.MVar.take.impl : MVar a
                                       ->{IO} Either Failure a
  4482. IO.concurrent.MVar.tryModify : MVar a
                                       -> (a
                                       ->{IO, Exception} (a, b))
                                       ->{IO, Exception} Optional
                                         b
  4483. IO.concurrent.MVar.tryModify.doc : Doc
  4484. IO.concurrent.MVar.tryPut : MVar a
                                    -> a
                                    ->{IO, Exception} Boolean
  4485. IO.concurrent.MVar.tryPut.doc : Doc
  4486. IO.concurrent.MVar.tryPut.impl : MVar a
                                         -> a
                                         ->{IO} Either
                                           Failure Boolean
  4487. IO.concurrent.MVar.tryRead : MVar a
                                     ->{IO, Exception} Optional
                                       a
  4488. IO.concurrent.MVar.tryRead.doc : Doc
  4489. IO.concurrent.MVar.tryRead.impl : MVar a
                                          ->{IO} Either
                                            Failure (Optional a)
  4490. IO.concurrent.MVar.tryTake : MVar a ->{IO} Optional a
  4491. IO.concurrent.MVar.tryTake.doc : Doc
  4492. builtin type IO.concurrent.Promise
  4493. IO.concurrent.Promise.doc : Doc
  4494. IO.concurrent.Promise.new : '{IO} Promise a
  4495. IO.concurrent.Promise.new.doc : Doc
  4496. IO.concurrent.Promise.read : Promise a ->{IO} a
  4497. IO.concurrent.Promise.read.doc : Doc
  4498. IO.concurrent.Promise.tryRead : Promise a
                                        ->{IO} Optional a
  4499. IO.concurrent.Promise.tryRead.doc : Doc
  4500. IO.concurrent.Promise.write : Promise a
                                      -> a
                                      ->{IO} Boolean
  4501. IO.concurrent.Promise.write.doc : Doc
  4502. IO.concurrent.Promise.write_ : Promise a -> a ->{IO} ()
  4503. IO.concurrent.Promise.write_.doc : Doc
  4504. IO.concurrent.sleep : Duration ->{IO, Exception} ()
  4505. IO.concurrent.sleep.doc : Doc
  4506. IO.concurrent.sleepMicroseconds : Nat
                                          ->{IO, Exception} ()
  4507. IO.concurrent.sleepMicroseconds.doc : Doc
  4508. IO.concurrent.sleepMicroseconds.examples.ex1 : '{IO,
                                                       Exception} ()
  4509. IO.concurrent.sleepMicroseconds.impl : Nat
                                               ->{IO} Either
                                                 Failure ()
  4510. builtin type IO.concurrent.STM
  4511. IO.concurrent.STM.atomically : '{STM} a ->{IO} a
  4512. IO.concurrent.STM.atomically.doc : Doc
  4513. IO.concurrent.STM.atomically.doc.example : '{IO} Nat
  4514. IO.concurrent.STM.doc : Doc
  4515. IO.concurrent.STM.docs.glossary.FIFO : Doc
  4516. IO.concurrent.STM.docs.glossary.FIFO.content : Doc
  4517. IO.concurrent.STM.retry : '{STM} a
  4518. IO.concurrent.STM.retry.doc : Doc
  4519. IO.concurrent.STM.retry.doc.example : '{IO} Nat
  4520. type IO.concurrent.STM.STMFailure
  4521. IO.concurrent.STM.STMFailure.doc : Doc
  4522. type IO.concurrent.STM.TMap a
  4523. IO.concurrent.STM.TMap.contains : Bytes
                                          -> TMap a
                                          ->{STM} Boolean
  4524. IO.concurrent.STM.TMap.contains.doc : Doc
  4525. IO.concurrent.STM.TMap.delete : Bytes
                                        -> TMap a
                                        ->{STM} ()
  4526. IO.concurrent.STM.TMap.delete.doc : Doc
  4527. IO.concurrent.STM.TMap.doc : Doc
  4528. IO.concurrent.STM.TMap.empty : '{STM} TMap a
  4529. IO.concurrent.STM.TMap.empty.doc : Doc
  4530. type IO.concurrent.STM.TMap.impl.F a
  4531. IO.concurrent.STM.TMap.impl.F.doc : Doc
  4532. IO.concurrent.STM.TMap.impl.F.Empty : F a
  4533. IO.concurrent.STM.TMap.impl.F.Many : TMap a -> F a
  4534. IO.concurrent.STM.TMap.impl.F.One : Bytes -> a -> F a
  4535. IO.concurrent.STM.TMap.insert : Bytes
                                        -> a
                                        -> TMap a
                                        ->{STM} ()
  4536. IO.concurrent.STM.TMap.insert.doc : Doc
  4537. IO.concurrent.STM.TMap.insert.impl : Nat
                                             -> Bytes
                                             -> a
                                             -> TMap a
                                             ->{STM} ()
  4538. IO.concurrent.STM.TMap.lookup : Bytes
                                        -> TMap a
                                        ->{STM} Optional a
  4539. IO.concurrent.STM.TMap.lookup.doc : Doc
  4540. IO.concurrent.STM.TMap.tests.insertsAndDeletes : '{IO} [Result]
  4541. IO.concurrent.STM.TMap.tests.insertsAndDeletes.doc : Doc
  4542. IO.concurrent.STM.TMap.TMap : TVar (Optional a)
                                      -> [TVar (F a)]
                                      -> TMap a
  4543. type IO.concurrent.STM.TQueue a
  4544. IO.concurrent.STM.TQueue.boundedEnqueue : Nat
                                                  -> a
                                                  -> TQueue a
                                                  ->{STM} ()
  4545. IO.concurrent.STM.TQueue.boundedEnqueue.doc : Doc
  4546. IO.concurrent.STM.TQueue.dequeue : TQueue a ->{STM} a
  4547. IO.concurrent.STM.TQueue.dequeue.doc : Doc
  4548. IO.concurrent.STM.TQueue.dequeueNonce : TQueue a
                                                ->{STM} Nat
  4549. IO.concurrent.STM.TQueue.dequeueNonce.doc : Doc
  4550. IO.concurrent.STM.TQueue.doc : Doc
  4551. IO.concurrent.STM.TQueue.elements : TQueue a ->{STM} [a]
  4552. IO.concurrent.STM.TQueue.elements.doc : Doc
  4553. IO.concurrent.STM.TQueue.empty : '{STM} TQueue a
  4554. IO.concurrent.STM.TQueue.empty.doc : Doc
  4555. IO.concurrent.STM.TQueue.enqueue : a
                                           -> TQueue a
                                           ->{STM} ()
  4556. IO.concurrent.STM.TQueue.enqueue.doc : Doc
  4557. IO.concurrent.STM.TQueue.enqueueAll : [a]
                                              -> TQueue a
                                              ->{STM} ()
  4558. IO.concurrent.STM.TQueue.enqueueAll.doc : Doc
  4559. IO.concurrent.STM.TQueue.fromList : [a] ->{STM} TQueue a
  4560. IO.concurrent.STM.TQueue.fromList.doc : Doc
  4561. IO.concurrent.STM.TQueue.peek : TQueue a ->{STM} a
  4562. IO.concurrent.STM.TQueue.peek.doc : Doc
  4563. IO.concurrent.STM.TQueue.pushback : a
                                            -> TQueue a
                                            ->{STM} ()
  4564. IO.concurrent.STM.TQueue.pushback.doc : Doc
  4565. IO.concurrent.STM.TQueue.size : TQueue a ->{STM} Nat
  4566. IO.concurrent.STM.TQueue.size.doc : Doc
  4567. IO.concurrent.STM.TQueue.tests.ex1 : '{IO} [Result]
  4568. IO.concurrent.STM.TQueue.TQueue : TVar [a]
                                          -> TVar Nat
                                          -> TQueue a
  4569. IO.concurrent.STM.TQueue.tryBoundedEnqueue : Nat
                                                     -> a
                                                     -> TQueue a
                                                     ->{STM} Boolean
  4570. IO.concurrent.STM.TQueue.tryBoundedEnqueue.doc : Doc
  4571. IO.concurrent.STM.TQueue.tryBoundedEnqueueAll : Nat
                                                        -> [a]
                                                        -> TQueue
                                                          a
                                                        ->{STM} Boolean
  4572. IO.concurrent.STM.TQueue.tryBoundedEnqueueAll.doc : Doc
  4573. IO.concurrent.STM.TQueue.tryDequeue : TQueue a
                                              ->{STM} Optional a
  4574. IO.concurrent.STM.TQueue.tryDequeue.doc : Doc
  4575. IO.concurrent.STM.TQueue.tryPeek : TQueue a
                                           ->{STM} Optional a
  4576. IO.concurrent.STM.TQueue.tryPeek.doc : Doc
  4577. builtin type IO.concurrent.ThreadId
  4578. IO.concurrent.ThreadId.doc : Doc
  4579. IO.concurrent.ThreadId.toText : ThreadId -> Text
  4580. IO.concurrent.ThreadId.toText.doc : Doc
  4581. type IO.concurrent.ThreadKilledFailure
  4582. structural type IO.concurrent.TMVar a
  4583. IO.concurrent.TMVar.doc : Doc
  4584. IO.concurrent.TMVar.isEmpty : TMVar a ->{STM} Boolean
  4585. IO.concurrent.TMVar.isEmpty.doc : Doc
  4586. IO.concurrent.TMVar.new : a ->{STM} TMVar a
  4587. IO.concurrent.TMVar.new.doc : Doc
  4588. IO.concurrent.TMVar.newEmpty : '{STM} TMVar a
  4589. IO.concurrent.TMVar.newEmpty.doc : Doc
  4590. IO.concurrent.TMVar.newEmptyIO : '{IO} TMVar a
  4591. IO.concurrent.TMVar.newEmptyIO.doc : Doc
  4592. IO.concurrent.TMVar.newIO : a ->{IO} TMVar a
  4593. IO.concurrent.TMVar.newIO.doc : Doc
  4594. IO.concurrent.TMVar.put : TMVar a -> a ->{STM} ()
  4595. IO.concurrent.TMVar.put.doc : Doc
  4596. IO.concurrent.TMVar.read : TMVar a ->{STM} a
  4597. IO.concurrent.TMVar.read.doc : Doc
  4598. IO.concurrent.TMVar.swap : TMVar a -> a ->{STM} a
  4599. IO.concurrent.TMVar.swap.doc : Doc
  4600. IO.concurrent.TMVar.take : TMVar a ->{STM} a
  4601. IO.concurrent.TMVar.take.doc : Doc
  4602. IO.concurrent.TMVar.TMVar : TVar (Optional a) -> TMVar a
  4603. IO.concurrent.TMVar.tryPut : TMVar a
                                     -> a
                                     ->{STM} Boolean
  4604. IO.concurrent.TMVar.tryPut.doc : Doc
  4605. IO.concurrent.TMVar.tryRead : TMVar a ->{STM} Optional a
  4606. IO.concurrent.TMVar.tryRead.doc : Doc
  4607. IO.concurrent.TMVar.tryTake : TMVar a ->{STM} Optional a
  4608. IO.concurrent.TMVar.tryTake.doc : Doc
  4609. builtin type IO.concurrent.TVar
  4610. IO.concurrent.TVar.doc : Doc
  4611. IO.concurrent.TVar.modify : TVar a
                                    -> (a ->{STM} a)
                                    ->{STM} ()
  4612. IO.concurrent.TVar.modify.doc : Doc
  4613. IO.concurrent.TVar.new : a ->{STM} TVar a
  4614. IO.concurrent.TVar.new.doc : Doc
  4615. IO.concurrent.TVar.newIO : a ->{IO} TVar a
  4616. IO.concurrent.TVar.newIO.doc : Doc
  4617. IO.concurrent.TVar.read : TVar a ->{STM} a
  4618. IO.concurrent.TVar.read.doc : Doc
  4619. IO.concurrent.TVar.readIO : TVar a ->{IO} a
  4620. IO.concurrent.TVar.readIO.doc : Doc
  4621. IO.concurrent.TVar.state : TVar s
                                   -> (s ->{e} (a, s))
                                   ->{e, STM} a
  4622. IO.concurrent.TVar.state.doc : Doc
  4623. IO.concurrent.TVar.swap : TVar a -> a ->{STM} a
  4624. IO.concurrent.TVar.swap.doc : Doc
  4625. IO.concurrent.TVar.write : TVar a -> a ->{STM} ()
  4626. IO.concurrent.TVar.write.doc : Doc
  4627. IO.console.printLine : Text ->{IO, Exception} ()
  4628. IO.console.printLine.doc : Doc
  4629. IO.console.readLine : '{IO, Exception} Text
  4630. IO.console.readLine.doc : Doc
  4631. type IO.deprecated.EpochTime
  4632. IO.deprecated.EpochTime.doc : Doc
  4633. IO.deprecated.EpochTime.EpochTime : Nat -> EpochTime
  4634. IO.deprecated.systemTime : '{IO, Exception} EpochTime
  4635. IO.deprecated.systemTime.doc : Doc
  4636. IO.deprecated.systemTime.impl : '{IO} Either Failure Nat
  4637. IO.deprecated.systemTimeMicroseconds : '{IO} Int
  4638. IO.deprecated.systemTimeMicroseconds.doc : Doc
  4639. IO.deprecated.systemTimeMicroseconds.impl : '{IO} Int
  4640. IO.doc : Doc
  4641. IO.Error.EOF.doc : Doc
  4642. type IO.Failure
  4643. type IO.Failure.ArithmeticFailure
  4644. IO.Failure.ArithmeticFailure.doc : Doc
  4645. IO.Failure.doc : Doc
  4646. IO.Failure.Failure : Type -> Text -> Any -> Failure
  4647. IO.Failure.failureType : Failure -> Type
  4648. IO.Failure.failureType.doc : Doc
  4649. IO.Failure.message : Failure -> Text
  4650. IO.Failure.message.doc : Doc
  4651. type IO.Failure.MiscFailure
  4652. IO.Failure.payload : Failure -> Any
  4653. IO.Failure.payload.doc : Doc
  4654. type IO.Failure.RuntimeFailure
  4655. IO.Failure.RuntimeFailure.doc : Doc
  4656. type IO.FilePath
  4657. IO.FilePath./ : FilePath -> Text -> FilePath
  4658. IO.FilePath./.doc : Doc
  4659. IO.FilePath.appendFile : FilePath
                                 -> Bytes
                                 ->{IO, Exception} ()
  4660. IO.FilePath.appendFile.doc : Doc
  4661. IO.FilePath.appendFileUtf8 : FilePath
                                     -> Text
                                     ->{IO, Exception} ()
  4662. IO.FilePath.appendFileUtf8.doc : Doc
  4663. IO.FilePath.createDirectory : FilePath
                                      ->{IO, Exception} ()
  4664. IO.FilePath.createDirectory.deprecated : Text
                                                 ->{IO,
                                                 Exception} ()
  4665. IO.FilePath.createDirectory.doc : Doc
  4666. IO.FilePath.createDirectory.impl : Text
                                           ->{IO} Either
                                             Failure ()
  4667. IO.FilePath.createTempDirectory : FilePath
                                          ->{IO, Exception} FilePath
  4668. IO.FilePath.createTempDirectory.doc : Doc
  4669. IO.FilePath.createTempDirectory.impl : Text
                                               ->{IO} Either
                                                 Failure Text
  4670. IO.FilePath.directoryContents : FilePath
                                        ->{IO, Exception} [FilePath]
  4671. IO.FilePath.directoryContents.doc : Doc
  4672. IO.FilePath.directoryContents.impl : Text
                                             ->{IO} Either
                                               Failure [Text]
  4673. IO.FilePath.directoryContents.texts : FilePath
                                              ->{IO, Exception} [Text]
  4674. IO.FilePath.doc : Doc
  4675. IO.FilePath.exists : FilePath ->{IO, Exception} Boolean
  4676. IO.FilePath.exists.deprecated : Text
                                        ->{IO, Exception} Boolean
  4677. IO.FilePath.exists.doc : Doc
  4678. IO.FilePath.exists.impl : Text
                                  ->{IO} Either Failure Boolean
  4679. type IO.FilePath.FileMode
  4680. IO.FilePath.FileMode.Append : FileMode
  4681. IO.FilePath.FileMode.doc : Doc
  4682. IO.FilePath.FileMode.Read : FileMode
  4683. IO.FilePath.FileMode.ReadWrite : FileMode
  4684. IO.FilePath.FileMode.Write : FileMode
  4685. IO.FilePath.FilePath : Text -> FilePath
  4686. IO.FilePath.getCurrentDirectory : '{IO, Exception} FilePath
  4687. IO.FilePath.getCurrentDirectory.deprecated : '{IO,
                                                     Exception} Text
  4688. IO.FilePath.getCurrentDirectory.doc : Doc
  4689. IO.FilePath.getCurrentDirectory.impl : '{IO} Either
                                                 Failure Text
  4690. IO.FilePath.getSize : FilePath ->{IO, Exception} Nat
  4691. IO.FilePath.getSize.deprecated : Text
                                         ->{IO, Exception} Nat
  4692. IO.FilePath.getSize.doc : Doc
  4693. IO.FilePath.getSize.impl : Text
                                   ->{IO} Either Failure Nat
  4694. IO.FilePath.getTempDirectory : '{IO, Exception} FilePath
  4695. IO.FilePath.getTempDirectory.deprecated : '{IO,
                                                  Exception} Text
  4696. IO.FilePath.getTempDirectory.doc : Doc
  4697. IO.FilePath.getTempDirectory.impl : '{IO} Either
                                              Failure Text
  4698. IO.FilePath.getTimestamp : FilePath
                                   ->{IO, Exception} Instant
  4699. IO.FilePath.getTimestamp.deprecated.v1 : Text
                                                 ->{IO,
                                                 Exception} Nat
  4700. IO.FilePath.getTimestamp.deprecated.v1.doc : Doc
  4701. IO.FilePath.getTimestamp.deprecated.v2 : FilePath
                                                 ->{IO,
                                                 Exception} EpochTime
  4702. IO.FilePath.getTimestamp.deprecated.v2.doc : Doc
  4703. IO.FilePath.getTimeStamp.doc : Doc
  4704. IO.FilePath.getTimestamp.impl : Text
                                        ->{IO} Either
                                          Failure Nat
  4705. IO.FilePath.isDirectory : FilePath
                                  ->{IO, Exception} Boolean
  4706. IO.FilePath.isDirectory.deprecated : Text
                                             ->{IO, Exception} Boolean
  4707. IO.FilePath.isDirectory.doc : Doc
  4708. IO.FilePath.isDirectory.impl : Text
                                       ->{IO} Either
                                         Failure Boolean
  4709. IO.FilePath.open : FilePath
                           -> FileMode
                           ->{IO, Exception} Handle
  4710. IO.FilePath.open.deprecated : Text
                                      -> FileMode
                                      ->{IO, Exception} Handle
  4711. IO.FilePath.open.doc : Doc
  4712. IO.FilePath.open.impl : Text
                                -> FileMode
                                ->{IO} Either Failure Handle
  4713. IO.FilePath.readFile : FilePath ->{IO, Exception} Bytes
  4714. IO.FilePath.readFile.doc : Doc
  4715. IO.FilePath.readFileUtf8 : FilePath
                                   ->{IO, Exception} Text
  4716. IO.FilePath.readFileUtf8.doc : Doc
  4717. IO.FilePath.removeDirectory : FilePath
                                      ->{IO, Exception} ()
  4718. IO.FilePath.removeDirectory.deprecated : Text
                                                 ->{IO,
                                                 Exception} ()
  4719. IO.FilePath.removeDirectory.doc : Doc
  4720. IO.FilePath.removeDirectory.impl : Text
                                           ->{IO} Either
                                             Failure ()
  4721. IO.FilePath.removeFile : FilePath ->{IO, Exception} ()
  4722. IO.FilePath.removeFile.deprecated : Text
                                            ->{IO, Exception} ()
  4723. IO.FilePath.removeFile.doc : Doc
  4724. IO.FilePath.removeFile.impl : Text
                                      ->{IO} Either Failure ()
  4725. IO.FilePath.renameDirectory : FilePath
                                      -> FilePath
                                      ->{IO, Exception} ()
  4726. IO.FilePath.renameDirectory.deprecated : Text
                                                 -> Text
                                                 ->{IO,
                                                 Exception} ()
  4727. IO.FilePath.renameDirectory.doc : Doc
  4728. IO.FilePath.renameDirectory.impl : Text
                                           -> Text
                                           ->{IO} Either
                                             Failure ()
  4729. IO.FilePath.renameFile : FilePath
                                 -> FilePath
                                 ->{IO, Exception} ()
  4730. IO.FilePath.renameFile.deprecated : Text
                                            -> Text
                                            ->{IO, Exception} ()
  4731. IO.FilePath.renameFile.doc : Doc
  4732. IO.FilePath.renameFile.impl : Text
                                      -> Text
                                      ->{IO} Either Failure ()
  4733. IO.FilePath.setCurrentDirectory : FilePath
                                          ->{IO, Exception} ()
  4734. IO.FilePath.setCurrentDirectory.deprecated : Text
                                                     ->{IO,
                                                     Exception} ()
  4735. IO.FilePath.setCurrentDirectory.doc : Doc
  4736. IO.FilePath.setCurrentDirectory.impl : Text
                                               ->{IO} Either
                                                 Failure ()
  4737. IO.FilePath.toText : FilePath -> Text
  4738. IO.FilePath.toText.doc : Doc
  4739. IO.FilePath.writeFile : FilePath
                                -> Bytes
                                ->{IO, Exception} ()
  4740. IO.FilePath.writeFile.doc : Doc
  4741. IO.FilePath.writeFileUtf8 : FilePath
                                    -> Text
                                    ->{IO, Exception} ()
  4742. IO.FilePath.writeFileUtf8.doc : Doc
  4743. IO.getArgs : '{IO, Exception} [Text]
  4744. IO.getArgs.doc : Doc
  4745. IO.getArgs.impl : '{IO} Either Failure [Text]
  4746. IO.getEnv : Text ->{IO, Exception} Text
  4747. IO.getEnv.doc : Doc
  4748. IO.getEnv.impl : Text ->{IO} Either Failure Text
  4749. builtin type IO.Handle
  4750. type IO.Handle.BufferMode
  4751. IO.Handle.BufferMode.BlockBuffering : BufferMode
  4752. IO.Handle.BufferMode.doc : Doc
  4753. IO.Handle.BufferMode.LineBuffering : BufferMode
  4754. IO.Handle.BufferMode.NoBuffering : BufferMode
  4755. IO.Handle.BufferMode.SizedBlockBuffering : Nat
                                                   -> BufferMode
  4756. IO.Handle.close : Handle ->{IO, Exception} ()
  4757. IO.Handle.close.doc : Doc
  4758. IO.Handle.close.impl : Handle ->{IO} Either Failure ()
  4759. IO.Handle.doc : Doc
  4760. IO.Handle.getAllBytes : Handle ->{IO, Exception} Bytes
  4761. IO.Handle.getAllBytes.doc : Doc
  4762. IO.Handle.getAllText : Handle ->{IO, Exception} Text
  4763. IO.Handle.getAllText.doc : Doc
  4764. IO.Handle.getBuffering : Handle
                                 ->{IO, Exception} BufferMode
  4765. IO.Handle.getBuffering.doc : Doc
  4766. IO.Handle.getBuffering.impl : Handle
                                      ->{IO} Either
                                        Failure BufferMode
  4767. IO.Handle.getBytes : Handle
                             -> Nat
                             ->{IO, Exception} Bytes
  4768. IO.Handle.getBytes.doc : Doc
  4769. IO.Handle.getBytes.impl : Handle
                                  -> Nat
                                  ->{IO} Either Failure Bytes
  4770. IO.Handle.getChar : Handle ->{IO, Exception} Char
  4771. IO.Handle.getChar.doc : Doc
  4772. IO.Handle.getChar.impl : Handle
                                 ->{IO} Either Failure Char
  4773. IO.Handle.getContents : Handle ->{IO, Exception} Bytes
  4774. IO.Handle.getContents.doc : Doc
  4775. IO.Handle.getEcho : Handle ->{IO, Exception} Boolean
  4776. IO.Handle.getEcho.doc : Doc
  4777. IO.Handle.getEcho.impl : Handle
                                 ->{IO} Either Failure Boolean
  4778. IO.Handle.getLine : Handle ->{IO, Exception} Text
  4779. IO.Handle.getLine.doc : Doc
  4780. IO.Handle.getLine.impl : Handle
                                 ->{IO} Either Failure Text
  4781. IO.Handle.getPosition : Handle ->{IO, Exception} Nat
  4782. IO.Handle.getPosition.doc : Doc
  4783. IO.Handle.getPosition.impl : Handle
                                     ->{IO} Either Failure Nat
  4784. IO.Handle.getSomeBytes : Handle
                                 -> Nat
                                 ->{IO, Exception} Bytes
  4785. IO.Handle.getSomeBytes.doc : Doc
  4786. IO.Handle.getSomeBytes.impl : Handle
                                      -> Nat
                                      ->{IO} Either
                                        Failure Bytes
  4787. IO.Handle.getText : Handle ->{IO, Exception} Text
  4788. IO.Handle.getText.doc : Doc
  4789. IO.Handle.isEOF : Handle ->{IO, Exception} Boolean
  4790. IO.Handle.isEOF.doc : Doc
  4791. IO.Handle.isEOF.impl : Handle
                               ->{IO} Either Failure Boolean
  4792. IO.Handle.isOpen : Handle ->{IO, Exception} Boolean
  4793. IO.Handle.isOpen.doc : Doc
  4794. IO.Handle.isOpen.impl : Handle
                                ->{IO} Either Failure Boolean
  4795. IO.Handle.isReadable : Handle ->{IO} Boolean
  4796. IO.Handle.isReadable.doc : Doc
  4797. IO.Handle.isSeekable : Handle ->{IO, Exception} Boolean
  4798. IO.Handle.isSeekable.doc : Doc
  4799. IO.Handle.isSeekable.impl : Handle
                                    ->{IO} Either
                                      Failure Boolean
  4800. IO.Handle.position : Handle ->{IO, Exception} Nat
  4801. IO.Handle.position.doc : Doc
  4802. IO.Handle.putBytes : Handle
                             -> Bytes
                             ->{IO, Exception} ()
  4803. IO.Handle.putBytes.doc : Doc
  4804. IO.Handle.putBytes.impl : Handle
                                  -> Bytes
                                  ->{IO} Either Failure ()
  4805. IO.Handle.putLine : Handle -> Text ->{IO, Exception} ()
  4806. IO.Handle.putLine.doc : Doc
  4807. IO.Handle.putText : Handle -> Text ->{IO, Exception} ()
  4808. IO.Handle.putText.doc : Doc
  4809. IO.Handle.ready : Handle ->{IO, Exception} Boolean
  4810. IO.Handle.ready.doc : Doc
  4811. IO.Handle.ready.impl : Handle
                               ->{IO} Either Failure Boolean
  4812. IO.Handle.readyAndAble : Handle ->{IO} Boolean
  4813. IO.Handle.readyAndAble.doc : Doc
  4814. IO.Handle.seek : Handle
                         -> SeekMode
                         -> Int
                         ->{IO, Exception} ()
  4815. IO.Handle.seek.doc : Doc
  4816. IO.Handle.seek.impl : Handle
                              -> SeekMode
                              -> Int
                              ->{IO} Either Failure ()
  4817. type IO.Handle.SeekMode
  4818. IO.Handle.SeekMode.AbsoluteSeek : SeekMode
  4819. IO.Handle.SeekMode.doc : Doc
  4820. IO.Handle.SeekMode.RelativeSeek : SeekMode
  4821. IO.Handle.SeekMode.SeekFromEnd : SeekMode
  4822. IO.Handle.setBuffering : Handle
                                 -> BufferMode
                                 ->{IO, Exception} ()
  4823. IO.Handle.setBuffering.doc : Doc
  4824. IO.Handle.setBuffering.impl : Handle
                                      -> BufferMode
                                      ->{IO} Either Failure ()
  4825. IO.Handle.setEcho : Handle
                            -> Boolean
                            ->{IO, Exception} ()
  4826. IO.Handle.setEcho.doc : Doc
  4827. IO.Handle.setEcho.impl : Handle
                                 -> Boolean
                                 ->{IO} Either Failure ()
  4828. type IO.Handle.Std
  4829. IO.Handle.std : Std -> Handle
  4830. IO.Handle.std.doc : Doc
  4831. IO.Handle.Std.doc : Doc
  4832. IO.Handle.Std.StdErr : Std
  4833. IO.Handle.Std.StdErr.doc : Doc
  4834. IO.Handle.Std.StdIn : Std
  4835. IO.Handle.Std.StdIn.doc : Doc
  4836. IO.Handle.Std.StdOut : Std
  4837. IO.Handle.Std.StdOut.doc : Doc
  4838. IO.Handle.stdErr : Handle
  4839. IO.Handle.stdErr.doc : Doc
  4840. IO.Handle.stdIn : Handle
  4841. IO.Handle.stdIn.doc : Doc
  4842. IO.Handle.stdOut : Handle
  4843. IO.Handle.stdOut.doc : Doc
  4844. IO.Handle.toText : Handle -> Text
  4845. IO.Handle.toText.doc : Doc
  4846. type IO.IOFailure
  4847. IO.IOFailure.doc : Doc
  4848. type IO.net.Connection
  4849. IO.net.Connection.accept : ListeningServerSocket
                                   ->{IO, Exception} Connection
  4850. IO.net.Connection.accept.doc : Doc
  4851. IO.net.Connection.client : HostName
                                   -> Port
                                   ->{IO, Exception} Connection
  4852. IO.net.Connection.client.doc : Doc
  4853. IO.net.Connection.close : Connection
                                  ->{IO, Exception} ()
  4854. IO.net.Connection.close.doc : Doc
  4855. IO.net.Connection.closer : Connection
                                   -> '{IO, Exception} ()
  4856. IO.net.Connection.closer.doc : Doc
  4857. IO.net.Connection.closer.modify : ('{IO, Exception} ()
                                          ->{g} '{IO, Exception} ())
                                          -> Connection
                                          ->{g} Connection
  4858. IO.net.Connection.closer.set : '{IO, Exception} ()
                                       -> Connection
                                       -> Connection
  4859. IO.net.Connection.Connection : (Bytes
                                       ->{IO, Exception} ())
                                       -> '{IO, Exception} Bytes
                                       -> '{IO, Exception} ()
                                       -> Connection
  4860. IO.net.Connection.doc : Doc
  4861. IO.net.Connection.receive : Connection
                                    ->{IO, Exception} Bytes
  4862. IO.net.Connection.receive.doc : Doc
  4863. IO.net.Connection.receiver : Connection
                                     -> '{IO, Exception} Bytes
  4864. IO.net.Connection.receiver.doc : Doc
  4865. IO.net.Connection.receiver.modify : ('{IO, Exception} Bytes
                                            ->{g} '{IO,
                                            Exception} Bytes)
                                            -> Connection
                                            ->{g} Connection
  4866. IO.net.Connection.receiver.modify.doc : Doc
  4867. IO.net.Connection.receiver.set : '{g, IO, Exception} Bytes
                                         -> Connection
                                         -> Connection
  4868. IO.net.Connection.receiver.set.doc : Doc
  4869. IO.net.Connection.send : Connection
                                 -> Bytes
                                 ->{IO, Exception} ()
  4870. IO.net.Connection.send.doc : Doc
  4871. IO.net.Connection.send.modify : ((Bytes
                                        ->{IO, Exception} ())
                                        ->{g} Bytes
                                        ->{IO, Exception} ())
                                        -> Connection
                                        ->{g} Connection
  4872. IO.net.Connection.send.modify.doc : Doc
  4873. IO.net.Connection.send.set : (Bytes
                                     ->{IO, Exception} ())
                                     -> Connection
                                     -> Connection
  4874. IO.net.Connection.send.set.doc : Doc
  4875. IO.net.Connection.sizedSocket : Nat
                                        -> Socket
                                        ->{IO, Exception} Connection
  4876. IO.net.Connection.sizedSocket.doc : Doc
  4877. IO.net.Connection.socket : Socket -> Connection
  4878. IO.net.Connection.socket.doc : Doc
  4879. IO.net.Connection.tls : HostName
                                -> Port
                                ->{IO, Exception} Connection
  4880. IO.net.Connection.tls.deprecated : TlsSocket
                                           -> Connection
  4881. IO.net.Connection.tls.deprecated.doc : Doc
  4882. IO.net.Connection.tls.doc : Doc
  4883. IO.net.Connection.tls.fromSocket : Socket
                                           -> HostName
                                           ->{IO, Exception} Connection
  4884. IO.net.Connection.tls.fromSocket.doc : Doc
  4885. IO.net.Connection.tls.fromSocketWithConfig : ClientConfig
                                                     -> Socket
                                                     ->{IO,
                                                     Exception} Connection
  4886. IO.net.Connection.tls.fromSocketWithConfig.doc : Doc
  4887. IO.net.Connection.tls.withConfig : HostName
                                           -> Port
                                           -> ClientConfig
                                           ->{IO, Exception} Connection
  4888. IO.net.Connection.tls.withConfig.doc : Doc
  4889. type IO.net.HostName
  4890. IO.net.HostName.doc : Doc
  4891. IO.net.HostName.HostName : Text -> HostName
  4892. IO.net.HostName.toText : HostName -> Text
  4893. IO.net.HostName.toText.doc : Doc
  4894. type IO.net.Port
  4895. IO.net.Port.doc : Doc
  4896. IO.net.Port.number : Nat -> Port
  4897. IO.net.Port.number.doc : Doc
  4898. IO.net.Port.Port : Text -> Port
  4899. IO.net.Port.toText : Port -> Text
  4900. IO.net.Port.toText.doc : Doc
  4901. IO.net.README : Doc
  4902. builtin type IO.net.Socket
  4903. IO.net.Socket.accept : ListeningServerSocket
                               ->{IO, Exception} Socket
  4904. IO.net.Socket.accept.doc : Doc
  4905. IO.net.Socket.accept.impl : Socket
                                    ->{IO} Either Failure Socket
  4906. IO.net.Socket.accept.raw : Socket
                                   ->{IO, Exception} Socket
  4907. IO.net.Socket.accept.raw.doc : Doc
  4908. type IO.net.Socket.BoundServerSocket
  4909. IO.net.Socket.BoundServerSocket.BoundServerSocket : Socket
                                                            -> BoundServerSocket
  4910. IO.net.Socket.BoundServerSocket.doc : Doc
  4911. IO.net.Socket.client : HostName
                               -> Port
                               ->{IO, Exception} Socket
  4912. IO.net.Socket.client.deprecated : Text
                                          -> Text
                                          ->{IO, Exception} Socket
  4913. IO.net.Socket.client.doc : Doc
  4914. IO.net.Socket.client.impl : Text
                                    -> Text
                                    ->{IO} Either Failure Socket
  4915. IO.net.Socket.close : Socket ->{IO, Exception} ()
  4916. IO.net.Socket.close.doc : Doc
  4917. IO.net.Socket.close.impl : Socket
                                   ->{IO} Either Failure ()
  4918. IO.net.Socket.doc : Doc
  4919. IO.net.Socket.listen : BoundServerSocket
                               ->{IO, Exception} ListeningServerSocket
  4920. IO.net.Socket.listen.doc : Doc
  4921. IO.net.Socket.listen.impl : Socket
                                    ->{IO} Either Failure ()
  4922. IO.net.Socket.listen.raw : Socket ->{IO, Exception} ()
  4923. IO.net.Socket.listen.raw.doc : Doc
  4924. type IO.net.Socket.ListeningServerSocket
  4925. IO.net.Socket.ListeningServerSocket.doc : Doc
  4926. IO.net.Socket.ListeningServerSocket.ListeningServerSocket : Socket
                                                                    -> ListeningServerSocket
  4927. IO.net.Socket.port : Socket ->{IO, Exception} Port
  4928. IO.net.Socket.port.doc : Doc
  4929. IO.net.Socket.port.impl : Socket
                                  ->{IO} Either Failure Nat
  4930. IO.net.Socket.portNumber : Socket ->{IO, Exception} Nat
  4931. IO.net.Socket.portNumber.doc : Doc
  4932. IO.net.Socket.receive : Socket ->{IO, Exception} Bytes
  4933. IO.net.Socket.receive.doc : Doc
  4934. IO.net.Socket.receiveAtMost : Socket
                                      -> Nat
                                      ->{IO, Exception} Bytes
  4935. IO.net.Socket.receiveAtMost.doc : Doc
  4936. IO.net.Socket.receiveAtMost.impl : Socket
                                           -> Nat
                                           ->{IO} Either
                                             Failure Bytes
  4937. IO.net.Socket.send : Socket
                             -> Bytes
                             ->{IO, Exception} ()
  4938. IO.net.Socket.send.doc : Doc
  4939. IO.net.Socket.send.impl : Socket
                                  -> Bytes
                                  ->{IO} Either Failure ()
  4940. IO.net.Socket.server : Optional HostName
                               -> Port
                               ->{IO, Exception} BoundServerSocket
  4941. IO.net.Socket.server.deprecated : Optional Text
                                          -> Text
                                          ->{IO, Exception} Socket
  4942. IO.net.Socket.server.doc : Doc
  4943. IO.net.Socket.server.impl : Optional Text
                                    -> Text
                                    ->{IO} Either Failure Socket
  4944. IO.net.Socket.server.raw : Optional HostName
                                   -> Port
                                   ->{IO, Exception} Socket
  4945. IO.net.Socket.server.raw.doc : Doc
  4946. IO.net.Socket.toText : Socket -> Text
  4947. IO.net.Socket.toText.doc : Doc
  4948. type IO.net.Socket.UnboundServerSocket
  4949. IO.net.Socket.UnboundServerSocket.doc : Doc
  4950. IO.net.Socket.UnboundServerSocket.UnboundServerSocket : Socket
                                                                -> UnboundServerSocket
  4951. builtin type IO.net.Tls
  4952. builtin type IO.net.Tls.Cipher
  4953. IO.net.Tls.Cipher.doc : Doc
  4954. builtin type IO.net.Tls.ClientConfig
  4955. IO.net.Tls.ClientConfig.certificates.set : [SignedCert]
                                                   -> ClientConfig
                                                   -> ClientConfig
  4956. IO.net.Tls.ClientConfig.certificates.set.doc : Doc
  4957. IO.net.Tls.ClientConfig.default : HostName
                                          -> Text
                                          -> ClientConfig
  4958. IO.net.Tls.ClientConfig.default.doc : Doc
  4959. IO.net.Tls.ClientConfig.default.impl : Text
                                               -> Bytes
                                               -> ClientConfig
  4960. IO.net.Tls.ClientConfig.doc : Doc
  4961. IO.net.Tls.decodeCert : Bytes
                                -> Either Failure SignedCert
  4962. IO.net.Tls.decodeCert.doc : Doc
  4963. IO.net.Tls.decodeCert.impl : Bytes
                                     -> Either
                                       Failure SignedCert
  4964. IO.net.Tls.decodePrivateKey : Bytes -> [Tls.PrivateKey]
  4965. IO.net.Tls.decodePrivateKey.doc : Doc
  4966. IO.net.Tls.doc : Doc
  4967. IO.net.Tls.encodeCert : SignedCert -> Bytes
  4968. IO.net.Tls.encodeCert.doc : Doc
  4969. IO.net.Tls.encodePrivateKey : Tls.PrivateKey -> Bytes
  4970. IO.net.Tls.encodePrivateKey.doc : Doc
  4971. IO.net.Tls.handshake : Tls ->{IO, Exception} TlsSocket
  4972. IO.net.Tls.handshake.doc : Doc
  4973. IO.net.Tls.handshake.impl : Tls ->{IO} Either Failure ()
  4974. IO.net.Tls.newClient : ClientConfig
                               -> Socket
                               ->{IO, Exception} Tls
  4975. IO.net.Tls.newClient.doc : Doc
  4976. IO.net.Tls.newClient.impl : ClientConfig
                                    -> Socket
                                    ->{IO} Either Failure Tls
  4977. IO.net.Tls.newServer : ServerConfig
                               -> Socket
                               ->{IO, Exception} Tls
  4978. IO.net.Tls.newServer.doc : Doc
  4979. IO.net.Tls.newServer.impl : ServerConfig
                                    -> Socket
                                    ->{IO} Either Failure Tls
  4980. builtin type IO.net.Tls.PrivateKey
  4981. IO.net.Tls.PrivateKey.doc : Doc
  4982. builtin type IO.net.Tls.ServerConfig
  4983. IO.net.Tls.ServerConfig.certificates.set : [SignedCert]
                                                   -> ServerConfig
                                                   -> ServerConfig
  4984. IO.net.Tls.ServerConfig.certificates.set.doc : Doc
  4985. IO.net.Tls.ServerConfig.ciphers.set : [Cipher]
                                              -> ServerConfig
                                              -> ServerConfig
  4986. IO.net.Tls.ServerConfig.ciphers.set.doc : Doc
  4987. IO.net.Tls.ServerConfig.default : [SignedCert]
                                          -> Tls.PrivateKey
                                          -> ServerConfig
  4988. IO.net.Tls.ServerConfig.default.doc : Doc
  4989. IO.net.Tls.ServerConfig.doc : Doc
  4990. IO.net.Tls.ServerConfig.versions.set : [Version]
                                               -> ServerConfig
                                               -> ServerConfig
  4991. IO.net.Tls.ServerConfig.versions.set.doc : Doc
  4992. builtin type IO.net.Tls.SignedCert
  4993. IO.net.Tls.SignedCert.doc : Doc
  4994. IO.net.Tls.terminate : Tls ->{IO, Exception} ()
  4995. IO.net.Tls.terminate.doc : Doc
  4996. IO.net.Tls.terminate.impl : Tls ->{IO} Either Failure ()
  4997. type IO.net.Tls.TlsFailure
  4998. IO.net.Tls.TlsFailure.doc : Doc
  4999. type IO.net.Tls.TlsSocket
  5000. IO.net.Tls.TlsSocket.doc : Doc
  5001. IO.net.Tls.TlsSocket.receive : TlsSocket
                                       ->{IO, Exception} Bytes
  5002. IO.net.Tls.TlsSocket.receive.doc : Doc
  5003. IO.net.Tls.TlsSocket.receive.impl : Tls
                                            ->{IO} Either
                                              Failure Bytes
  5004. IO.net.Tls.TlsSocket.send : TlsSocket
                                    -> Bytes
                                    ->{IO, Exception} ()
  5005. IO.net.Tls.TlsSocket.send.doc : Doc
  5006. IO.net.Tls.TlsSocket.send.impl : Tls
                                         -> Bytes
                                         ->{IO} Either
                                           Failure ()
  5007. IO.net.Tls.TlsSocket.terminate : TlsSocket
                                         ->{IO, Exception} ()
  5008. IO.net.Tls.TlsSocket.terminate.doc : Doc
  5009. IO.net.Tls.TlsSocket.terminate_ : TlsSocket ->{IO} ()
  5010. IO.net.Tls.TlsSocket.terminate_.doc : Doc
  5011. IO.net.Tls.TlsSocket.TlsSocket : Tls -> TlsSocket
  5012. builtin type IO.net.Tls.Version
  5013. IO.net.Tls.Version.doc : Doc
  5014. type IO.net.URI
  5015. type IO.net.URI.Authority
  5016. IO.net.URI.authority : URI -> Optional Authority
  5017. IO.net.URI.Authority.Authority : Optional UserInfo
                                         -> HostName
                                         -> Optional Port
                                         -> Authority
  5018. IO.net.URI.Authority.doc : Doc
  5019. IO.net.URI.Authority.fromHost : HostName -> Authority
  5020. IO.net.URI.Authority.host : Authority -> HostName
  5021. IO.net.URI.Authority.host.modify : (HostName
                                           ->{g} HostName)
                                           -> Authority
                                           ->{g} Authority
  5022. IO.net.URI.Authority.host.set : HostName
                                        -> Authority
                                        -> Authority
  5023. IO.net.URI.authority.modify : (Optional Authority
                                      ->{g} Optional Authority)
                                      -> URI
                                      ->{g} URI
  5024. IO.net.URI.Authority.port : Authority -> Optional Port
  5025. IO.net.URI.Authority.port.modify : (Optional Port
                                           ->{g} Optional Port)
                                           -> Authority
                                           ->{g} Authority
  5026. IO.net.URI.Authority.port.set : Optional Port
                                        -> Authority
                                        -> Authority
  5027. IO.net.URI.authority.set : Optional Authority
                                   -> URI
                                   -> URI
  5028. IO.net.URI.Authority.toText : Authority -> Text
  5029. IO.net.URI.Authority.toText.tests : [Result]
  5030. IO.net.URI.Authority.userInfo : Authority
                                        -> Optional UserInfo
  5031. IO.net.URI.Authority.userInfo.modify : (Optional
                                                 UserInfo
                                               ->{g} Optional
                                                 UserInfo)
                                               -> Authority
                                               ->{g} Authority
  5032. IO.net.URI.Authority.userInfo.set : Optional UserInfo
                                            -> Authority
                                            -> Authority
  5033. IO.net.URI.doc : Doc
  5034. IO.net.URI.encode.percent.char.special : Char -> Text
  5035. IO.net.URI.escape : Text -> Text
  5036. IO.net.URI.escapeChar : Char -> Text
  5037. IO.net.URI.escapeQuery : Text -> Text
  5038. IO.net.URI.escapeQueryChar : Char -> Text
  5039. IO.net.URI.forceHostAndPort : URI -> Authority
  5040. type IO.net.URI.Fragment
  5041. IO.net.URI.fragment : URI -> Fragment
  5042. IO.net.URI.fragment.doc : Doc
  5043. IO.net.URI.Fragment.empty : Fragment
  5044. IO.net.URI.Fragment.Fragment : Text -> Fragment
  5045. IO.net.URI.Fragment.toText : Fragment -> Text
  5046. IO.net.URI.fragmentText : URI -> Text
  5047. IO.net.URI.fragmentText.doc : Doc
  5048. IO.net.URI.fromPath : Path -> URI
  5049. IO.net.URI.host : URI -> HostName
  5050. IO.net.URI.http : URI -> URI
  5051. IO.net.URI.https : URI -> URI
  5052. type IO.net.URI.Method
  5053. IO.net.URI.Method.CONNECT : Method
  5054. IO.net.URI.Method.DELETE : Method
  5055. IO.net.URI.Method.GET : Method
  5056. IO.net.URI.Method.HEAD : Method
  5057. IO.net.URI.Method.OPTIONS : Method
  5058. IO.net.URI.Method.PATCH : Method
  5059. IO.net.URI.Method.POST : Method
  5060. IO.net.URI.Method.PUT : Method
  5061. IO.net.URI.Method.TRACE : Method
  5062. IO.net.URI.parse : Text ->{Exception} URI
  5063. IO.net.URI.parse.unquotePercentEncoded : Text
                                                 ->{Exception} Text
  5064. IO.net.URI.parse.unquotePercentEncoded.doc : Doc
  5065. IO.net.URI.parse.unquotePercentEncoded.impl : Text
                                                      -> Either
                                                        Text
                                                        Text
  5066. IO.net.URI.parse.unquotePercentEncoded.impl.tests : [Result]
  5067. IO.net.URI.parse.unquotePercentEncodedPlus : Text
                                                     ->{Exception} Text
  5068. IO.net.URI.parse.unquotePercentEncodedPlus.doc : Doc
  5069. IO.net.URI.parse.unquotePercentEncodedPlus.impl : Text
                                                          -> Either
                                                            Text
                                                            Text
  5070. IO.net.URI.parse.unquotePercentEncodedPlus.impl.doc : Doc
  5071. IO.net.URI.parse.unquotePercentEncodedPlus.impl.tests : [Result]
  5072. IO.net.URI.parse._internal.parseAuthority : Text
                                                    -> Text
                                                    -> Text
                                                    ->{Abort} Optional
                                                      Authority
  5073. IO.net.URI.parse._internal.parseFragment : Text
                                                   ->{Abort} Fragment
  5074. IO.net.URI.parse._internal.parsePath : Text
                                               ->{Abort} Path
  5075. IO.net.URI.parse._internal.parsePort : Text
                                               ->{Abort} Optional
                                                 Port
  5076. IO.net.URI.parse._internal.parseQuery : Text
                                                ->{Abort} Query
  5077. IO.net.URI.parse._internal.parseQuery.tests.percentPlusIsPlus : [Result]
  5078. IO.net.URI.parse._internal.parseQuery.tests.plusIsSpace : [Result]
  5079. IO.net.URI.parse._internal.parseUserInfo : Text
                                                   ->{Abort} Optional
                                                     UserInfo
  5080. IO.net.URI.parse._internal.renderPercentEncoded : Text
                                                          ->{Abort} Text
  5081. type IO.net.URI.ParseError
  5082. IO.net.URI.parseOptional : Text -> Optional URI
  5083. IO.net.URI.parseOrBug : Text -> URI
  5084. type IO.net.URI.Path
  5085. IO.net.URI.path : URI -> Path
  5086. IO.net.URI.Path.++ : Path -> Path -> Path
  5087. IO.net.URI.Path./ : Path -> Text -> Path
  5088. IO.net.URI.Path./.doc : Doc
  5089. IO.net.URI.Path.doc : Doc
  5090. IO.net.URI.Path.encode : Path -> Bytes
  5091. IO.net.URI.Path.encode.char : Char -> Text
  5092. IO.net.URI.Path.encode.char.test : [Result]
  5093. IO.net.URI.Path.encode.segment : Text -> Bytes
  5094. IO.net.URI.Path.fromText : Text ->{Exception} Path
  5095. IO.net.URI.path.modify : (Path ->{g} Path)
                                 -> URI
                                 ->{g} URI
  5096. IO.net.URI.Path.Path : [Text] -> Path
  5097. IO.net.URI.Path.root : Path
  5098. IO.net.URI.Path.segments : Path -> [Text]
  5099. IO.net.URI.Path.segments.modify : ([Text] ->{g} [Text])
                                          -> Path
                                          ->{g} Path
  5100. IO.net.URI.Path.segments.set : [Text] -> Path -> Path
  5101. IO.net.URI.path.set : Path -> URI -> URI
  5102. IO.net.URI.Path.slash.tests : [Result]
  5103. IO.net.URI.Path.toText : Path -> Text
  5104. IO.net.URI.Path.toUnescapedText : Path -> Text
  5105. IO.net.URI.Path.toUnescapedText.doc : Doc
  5106. IO.net.URI.pattern.alphaNum : Pattern Text
  5107. IO.net.URI.pattern.authority : IPattern
                                         (And
                                           (And Capture Capture)
                                           Capture)
                                         Text
  5108. IO.net.URI.pattern.dash : Pattern Text
  5109. IO.net.URI.pattern.decOctet : Pattern Text
  5110. IO.net.URI.pattern.decOctet.tests : [Result]
  5111. IO.net.URI.pattern.fragment : IPattern Capture Text
  5112. IO.net.URI.pattern.h16 : Pattern Text
  5113. IO.net.URI.pattern.heirPart : IPattern
                                        (And
                                          (And
                                            (And Capture Capture)
                                            Capture)
                                          Capture)
                                        Text
  5114. IO.net.URI.pattern.host : IPattern Capture Text
  5115. IO.net.URI.pattern.ipLiteral : Pattern Text
  5116. IO.net.URI.pattern.ipv4Address : Pattern Text
  5117. IO.net.URI.pattern.ipv4Address.tests : [Result]
  5118. IO.net.URI.pattern.ipv6Address : Pattern Text
  5119. IO.net.URI.pattern.ipvFuture : Pattern Text
  5120. IO.net.URI.pattern.ls32 : Pattern Text
  5121. IO.net.URI.pattern.path : Pattern Text
  5122. IO.net.URI.pattern.pathAbEmpty : Pattern Text
  5123. IO.net.URI.pattern.pathAbsolute : Pattern Text
  5124. IO.net.URI.pattern.pathEmpty : Pattern Text
  5125. IO.net.URI.pattern.pathNoscheme : Pattern Text
  5126. IO.net.URI.pattern.pathRootless : Pattern Text
  5127. IO.net.URI.pattern.pchar : Pattern Text
  5128. IO.net.URI.pattern.percentEncoded : Pattern Text
  5129. IO.net.URI.pattern.period : Pattern Text
  5130. IO.net.URI.pattern.port : IPattern Capture Text
  5131. IO.net.URI.pattern.query : IPattern Capture Text
  5132. IO.net.URI.pattern.regName : Pattern Text
  5133. IO.net.URI.pattern.scheme : IPattern Capture Text
  5134. IO.net.URI.pattern.segment : Pattern Text
  5135. IO.net.URI.pattern.segmentNz : Pattern Text
  5136. IO.net.URI.pattern.segmentNzNc : Pattern Text
  5137. IO.net.URI.pattern.subDelims : Pattern Text
  5138. IO.net.URI.pattern.tilde : Pattern Text
  5139. IO.net.URI.pattern.underscore : Pattern Text
  5140. IO.net.URI.pattern.unreserved : Pattern Text
  5141. IO.net.URI.pattern.uri : IPattern
                                   (And
                                     (And
                                       (And
                                         Capture
                                         (And
                                           (And
                                             (And
                                               Capture Capture)
                                             Capture)
                                           Capture))
                                       Capture)
                                     Capture)
                                   Text
  5142. IO.net.URI.pattern.userInfo : IPattern Capture Text
  5143. IO.net.URI.port : URI -> Optional Port
  5144. IO.net.URI.port.doc : Doc
  5145. IO.net.URI.portOr80 : URI -> Port
  5146. IO.net.URI.portOr80.doc : Doc
  5147. type IO.net.URI.Query
  5148. IO.net.URI.query : URI -> RawQuery
  5149. IO.net.URI.Query.& : Query -> (Text, Text) -> Query
  5150. IO.net.URI.Query.addParam : Text
                                    -> Text
                                    -> Query
                                    -> Query
  5151. IO.net.URI.Query.doc : Doc
  5152. IO.net.URI.Query.empty : Query
  5153. IO.net.URI.Query.encode.char : Text -> Text
  5154. IO.net.URI.Query.encode.charX : Char -> Text
  5155. IO.net.URI.Query.encode.impl : Boolean -> Query -> Text
  5156. IO.net.URI.Query.encode.test : [Result]
  5157. IO.net.URI.Query.encode.test.double.simple : [Result]
  5158. IO.net.URI.Query.encode.test.empty : [Result]
  5159. IO.net.URI.Query.encode.test.single.simple : [Result]
  5160. IO.net.URI.Query.example.exampleQuery : Query
  5161. IO.net.URI.Query.fromRawQuery : RawQuery
                                        -> Optional Query
  5162. IO.net.URI.Query.getParam : Text -> Query -> [Text]
  5163. IO.net.URI.Query.Query : Map Text [Text] -> Query
  5164. IO.net.URI.Query.singleton : Text -> Text -> Query
  5165. IO.net.URI.Query.tests.addParamOrder : [Result]
  5166. IO.net.URI.Query.toMap : Query -> Map Text [Text]
  5167. IO.net.URI.Query.toMap.doc : Doc
  5168. IO.net.URI.Query.toRawQuery : Query -> RawQuery
  5169. IO.net.URI.Query.toText : Query -> Text
  5170. IO.net.URI.Query.union : Query -> Query -> Query
  5171. type IO.net.URI.RawQuery
  5172. IO.net.URI.RawQuery.doc : Doc
  5173. IO.net.URI.RawQuery.empty : RawQuery
  5174. IO.net.URI.RawQuery.empty.doc : Doc
  5175. IO.net.URI.RawQuery.encode : RawQuery -> Text
  5176. IO.net.URI.RawQuery.encode.tests : [Result]
  5177. IO.net.URI.RawQuery.encode.tests.double.simple : [Result]
  5178. IO.net.URI.RawQuery.encodePairs : [Char] -> Text
  5179. IO.net.URI.RawQuery.encodeRaw.char : Char -> Text
  5180. IO.net.URI.RawQuery.encodeRaw.text : Text -> Text
  5181. IO.net.URI.RawQuery.fromQuery : Query -> RawQuery
  5182. IO.net.URI.RawQuery.modify : (RawQuery ->{g} RawQuery)
                                     -> URI
                                     ->{g} URI
  5183. IO.net.URI.RawQuery.RawQuery : Text -> RawQuery
  5184. IO.net.URI.RawQuery.toQuery : RawQuery -> Optional Query
  5185. IO.net.URI.RawQuery.toText : RawQuery -> Text
  5186. type IO.net.URI.Scheme
  5187. IO.net.URI.scheme : URI -> Scheme
  5188. IO.net.URI.Scheme.defaultPort : Scheme
                                        ->{Throw Text} Nat
  5189. IO.net.URI.Scheme.empty : Scheme
  5190. IO.net.URI.Scheme.http : Scheme
  5191. IO.net.URI.Scheme.http.doc : Doc
  5192. IO.net.URI.Scheme.https : Scheme
  5193. IO.net.URI.Scheme.https.doc : Doc
  5194. IO.net.URI.scheme.modify : (Scheme ->{g} Scheme)
                                   -> URI
                                   ->{g} URI
  5195. IO.net.URI.Scheme.Scheme : Text -> Scheme
  5196. IO.net.URI.scheme.set : Scheme -> URI -> URI
  5197. IO.net.URI.Scheme.toText : Scheme -> Text
  5198. IO.net.URI.Scheme.toText.tests : [Result]
  5199. IO.net.URI.tests.testEmptyFragment : [Result]
  5200. IO.net.URI.tests.testPathDecode : [Result]
  5201. IO.net.URI.tests.testPathToText : [Result]
  5202. IO.net.URI.tests.testQueryParams : [Result]
  5203. IO.net.URI.tests.testUriRoundTrip : [Result]
  5204. IO.net.URI.toText : URI -> Text
  5205. IO.net.URI.toText.tests.complicatedUri : [Result]
  5206. IO.net.URI.toText.tests.unisonDocs : [Result]
  5207. IO.net.URI.toText.tests.unisonDocs.unisonDocs : URI
  5208. IO.net.URI.toUnescapedText : URI -> Text
  5209. IO.net.URI.toUnescapedText.doc : Doc
  5210. IO.net.URI.URI : Scheme
                         -> Optional Authority
                         -> Path
                         -> RawQuery
                         -> Fragment
                         -> URI
  5211. type IO.net.URI.UserInfo
  5212. IO.net.URI.UserInfo.UserInfo : Text -> UserInfo
  5213. IO.net.URI.withHost : Text -> URI -> URI
  5214. IO.net.URI.withQuery : RawQuery -> URI -> URI
  5215. builtin type IO.Process
  5216. IO.Process.call : Text -> [Text] ->{IO} Nat
  5217. IO.Process.call.doc : Doc
  5218. IO.Process.doc : Doc
  5219. IO.Process.exitCode : Process ->{IO} Optional Nat
  5220. IO.Process.exitCode.doc : Doc
  5221. IO.Process.kill : Process ->{IO} ()
  5222. IO.Process.kill.doc : Doc
  5223. IO.Process.start : Text
                           -> [Text]
                           ->{IO} ( Handle,
                             Handle,
                             Handle,
                             Process)
  5224. IO.Process.start.doc : Doc
  5225. IO.Process.wait : Process ->{IO} Nat
  5226. IO.Process.wait.doc : Doc
  5227. IO.randomBytes : Nat ->{IO} Bytes
  5228. IO.randomBytes.doc : Doc
  5229. IO.randomNat : '{IO} Nat
  5230. IO.randomNat.doc : Doc
  5231. IO.Raw.array : Nat ->{IO} mutable.Array.Raw {IO} a
  5232. IO.Raw.array.doc : Doc
  5233. IO.Raw.arrayOf : a
                         -> Nat
                         ->{IO} mutable.Array.Raw {IO} a
  5234. IO.Raw.arrayOf.doc : Doc
  5235. IO.Raw.byteArray : Nat ->{IO} mutable.ByteArray.Raw {IO}
  5236. IO.Raw.byteArray.doc : Doc
  5237. IO.Raw.byteArrayOf : Nat
                             -> Nat
                             ->{IO} mutable.ByteArray.Raw {IO}
  5238. IO.Raw.byteArrayOf.doc : Doc
  5239. IO.ref : a ->{IO} Ref {IO} a
  5240. IO.ref.atomically : Ref {IO} a -> (a -> (a, b)) ->{IO} b
  5241. IO.ref.atomically.doc : Doc
  5242. IO.ref.cas : Ref {IO} a -> Ticket a -> a ->{IO} Boolean
  5243. IO.ref.cas.doc : Doc
  5244. IO.ref.cas.examples.getAndIncrement : Ref {IO} Nat
                                              ->{IO} Nat
  5245. IO.ref.cas.examples.getAndIncrement2 : Ref {IO} Nat
                                               ->{IO} Nat
  5246. IO.ref.cas.examples.printAndIncrement : Ref {IO} Nat
                                                ->{IO,
                                                Exception} ()
  5247. IO.ref.doc : Doc
  5248. IO.ref.modify : Ref {IO} a -> (a -> a) ->{IO} ()
  5249. IO.ref.modify.doc : Doc
  5250. IO.ref.readForCas : Ref {IO} a ->{IO} Ticket a
  5251. IO.ref.readForCas.doc : Doc
  5252. builtin type IO.ref.Ticket
  5253. IO.ref.Ticket.doc : Doc
  5254. IO.ref.Ticket.read : Ticket a -> a
  5255. IO.ref.Ticket.read.doc : Doc
  5256. IO.thawArray : data.Array a ->{IO} mutable.Array {IO} a
  5257. IO.thawArray.doc : Doc
  5258. IO.thawByteArray : data.ByteArray
                           ->{IO} mutable.ByteArray {IO}
  5259. IO.thawByteArray.doc : Doc
  5260. IO.tryEval : '{IO, Exception} a ->{IO, Exception} a
  5261. IO.tryEval.doc : Doc
  5262. IO.tryEval.impl : '{IO} a ->{IO, Exception} a
  5263. type IPattern n a
  5264. IPattern.++ : IPattern n a
                      -> IPattern m a
                      -> IPattern (And n m) a
  5265. IPattern.++.doc : Doc
  5266. IPattern.+: : Pattern a -> IPattern n a -> IPattern n a
  5267. IPattern.+:.doc : Doc
  5268. IPattern.:+ : IPattern n a -> Pattern a -> IPattern n a
  5269. IPattern.:+.doc : Doc
  5270. IPattern.<|> : IPattern n a
                       -> IPattern n a
                       -> IPattern n a
  5271. IPattern.<|>.doc : Doc
  5272. type IPattern.And l r
  5273. IPattern.And.doc : Doc
  5274. type IPattern.Capture
  5275. IPattern.capture : Pattern a -> IPattern Capture a
  5276. IPattern.capture.doc : Doc
  5277. IPattern.Capture.doc : Doc
  5278. IPattern.colonplusdoc : Doc
  5279. IPattern.doc : Doc
  5280. IPattern.IPattern : Pattern a -> IPattern n a
  5281. IPattern.ordoc : Doc
  5282. IPattern.pluscolondoc : Doc
  5283. IPattern.plusplusdoc : Doc
  5284. IPattern.run : IPattern n a -> a -> Optional ([a], a)
  5285. IPattern.run.doc : Doc
  5286. LICENSE : License
  5287. LICENSE.doc : Doc
  5288. LocalDate.ordering : LocalDate -> LocalDate -> Ordering
  5289. LocalDate.ordering.doc : Doc
  5290. LocalDateTime.ordering : LocalDateTime
                                 -> LocalDateTime
                                 -> Ordering
  5291. LocalDateTime.ordering.doc : Doc
  5292. LocalTime.ordering : LocalTime -> LocalTime -> Ordering
  5293. LocalTime.ordering.doc : Doc
  5294. type math.ArithmeticException
  5295. math.ArithmeticException.dividedByZero : '{Exception} r
  5296. math.ArithmeticException.DividedByZero : ArithmeticException
  5297. math.ArithmeticException.dividedByZero.doc : Doc
  5298. math.ArithmeticException.doc : Doc
  5299. math.ArithmeticException.negativeInfinity : '{Exception} r
  5300. math.ArithmeticException.negativeInfinity.doc : Doc
  5301. math.ArithmeticException.NegativeInfinityNotAllowed : ArithmeticException
  5302. math.ArithmeticException.notANumber : '{Exception} r
  5303. math.ArithmeticException.NotANumber : ArithmeticException
  5304. math.ArithmeticException.notANumber.doc : Doc
  5305. math.ArithmeticException.overflow : '{Exception} r
  5306. math.ArithmeticException.Overflow : ArithmeticException
  5307. math.ArithmeticException.overflow.doc : Doc
  5308. math.ArithmeticException.positiveInfinity : '{Exception} r
  5309. math.ArithmeticException.positiveInfinity.doc : Doc
  5310. math.ArithmeticException.PositiveInfinityNotAllowed : ArithmeticException
  5311. math.ArithmeticException.underflow : '{Exception} r
  5312. math.ArithmeticException.Underflow : ArithmeticException
  5313. math.ArithmeticException.underflow.doc : Doc
  5314. type math.Natural
  5315. math.Natural.* : Natural -> Natural -> Natural
  5316. math.Natural.+ : Natural -> Natural -> Natural
  5317. math.Natural.- : Natural -> Natural -> Natural
  5318. math.Natural./ : Natural
                         -> Natural
                         ->{Exception} Natural
  5319. math.Natural.< : Natural -> Natural -> Boolean
  5320. math.Natural.<= : Natural -> Natural -> Boolean
  5321. math.Natural.== : Natural -> Natural -> Boolean
  5322. math.Natural.> : Natural -> Natural -> Boolean
  5323. math.Natural.>= : Natural -> Natural -> Boolean
  5324. math.Natural.div : Natural
                           -> Natural
                           ->{Exception} Natural
  5325. math.Natural.div.aborting : Natural
                                    -> Natural
                                    ->{Abort} Natural
  5326. math.Natural.div.aborting.doc : Doc
  5327. math.Natural.divMod : Natural
                              -> Natural
                              ->{Exception} (Natural, Natural)
  5328. math.Natural.divMod.aborting : Natural
                                       -> Natural
                                       ->{Abort} ( Natural,
                                         Natural)
  5329. math.Natural.divMod.aborting.doc : Doc
  5330. math.Natural.divMod.doc : Doc
  5331. math.Natural.doc : Doc
  5332. math.Natural.docs.arithmetic : Doc
  5333. math.Natural.docs.constructing : Doc
  5334. math.Natural.docs.converting : Doc
  5335. math.Natural.docs.relations : Doc
  5336. math.Natural.eq : Natural -> Natural -> Boolean
  5337. math.Natural.eq.doc : Doc
  5338. math.Natural.fromNat : Nat -> Natural
  5339. math.Natural.fromNat.doc : Doc
  5340. math.Natural.gt : Natural -> Natural -> Boolean
  5341. math.Natural.gt.doc : Doc
  5342. math.natural.gt.doc : Doc
  5343. math.Natural.gte.doc.doc : Doc
  5344. math.Natural.gteq : Natural -> Natural -> Boolean
  5345. math.Natural.internal.bitMask : Nat
  5346. math.Natural.internal.bitWidth : Nat
  5347. math.Natural.internal.digits : Natural
                                       -> List.Nonempty Nat
  5348. math.Natural.internal.divImpl : Natural
                                        -> Natural
                                        ->{Abort} ( Natural,
                                          Natural)
  5349. math.Natural.internal.fromNats : [Nat] -> Natural
  5350. math.Natural.internal.mkNatural : [Nat] -> Natural
  5351. math.Natural.internal.Natural : List.Nonempty Nat
                                        -> Natural
  5352. math.Natural.internal.normalize : Natural -> Natural
  5353. math.Natural.internal.radix : Nat
  5354. math.Natural.isZero : Natural -> Boolean
  5355. math.Natural.isZero.doc : Doc
  5356. math.Natural.lt : Natural -> Natural -> Boolean
  5357. math.Natural.lt.doc : Doc
  5358. math.Natural.lte.doc : Doc
  5359. math.natural.lte.doc : Doc
  5360. math.Natural.lteq : Natural -> Natural -> Boolean
  5361. math.Natural.maybeDiv : Natural
                                -> Natural
                                -> Optional Natural
  5362. math.Natural.maybeDiv.doc : Doc
  5363. math.Natural.maybeDivMod : Natural
                                   -> Natural
                                   -> Optional
                                     (Natural, Natural)
  5364. math.Natural.maybeDivMod.doc : Doc
  5365. math.Natural.maybeMod : Natural
                                -> Natural
                                -> Optional Natural
  5366. math.Natural.maybeMod.doc : Doc
  5367. math.Natural.mod : Natural
                           -> Natural
                           ->{Exception} Natural
  5368. math.Natural.mod.aborting : Natural
                                    -> Natural
                                    ->{Abort} Natural
  5369. math.Natural.mod.aborting.doc : Doc
  5370. math.Natural.mod.doc : Doc
  5371. math.Natural.one : Natural
  5372. math.Natural.one.doc : Doc
  5373. math.Natural.parse : Nat -> Text -> Optional Natural
  5374. math.Natural.parse.deprecated : Text
                                        -> Nat
                                        -> Optional Natural
  5375. math.Natural.parse.deprecated.doc : Doc
  5376. math.Natural.parse.doc : Doc
  5377. math.Natural.parse.tests.roundtrip : [Result]
  5378. math.Natural.parse! : Nat -> Text ->{Abort} Natural
  5379. math.Natural.parse!.deprecated : Text
                                         -> Nat
                                         ->{Abort} Natural
  5380. math.Natural.parse!.deprecated.doc : Doc
  5381. math.Natural.parse!.doc : Doc
  5382. math.Natural.parse!.tests.roundtrip : [Result]
  5383. math.Natural.pow : Natural -> Nat -> Natural
  5384. math.Natural.pow.doc : Doc
  5385. math.Natural.pow.tests.powerOfOne : [Result]
  5386. math.Natural.pow.tests.powerOfPower : [Result]
  5387. math.Natural.pow.tests.powerOfProduct : [Result]
  5388. math.Natural.pow.tests.powerOfZero : [Result]
  5389. math.Natural.pow.tests.product : [Result]
  5390. math.Natural.pow.tests.quotient : [Result]
  5391. math.Natural.shiftLeft : Natural -> Nat -> Natural
  5392. math.Natural.shiftLeft.doc : Doc
  5393. math.Natural.tests.additionAssociative : [Result]
  5394. math.Natural.tests.additionCommutative : [Result]
  5395. math.Natural.tests.additionZero : [Result]
  5396. math.Natural.tests.distributiveLaw : [Result]
  5397. math.Natural.tests.gen.natural : '{Gen} Natural
  5398. math.Natural.tests.multiplicationAssociative : [Result]
  5399. math.Natural.tests.multiplicationCommutative : [Result]
  5400. math.Natural.tests.multiplicationZero : [Result]
  5401. math.Natural.tests.subtraction : [Result]
  5402. math.Natural.tests.subtractLeftAdjoint : [Result]
  5403. math.Natural.tests.zeroDivisors : [Result]
  5404. math.Natural.toDecimalText : Natural -> Text
  5405. math.Natural.toDecimalText.doc : Doc
  5406. math.Natural.toHex : Natural -> Text
  5407. math.Natural.toHex.doc : Doc
  5408. math.Natural.toMaybeNat : Natural -> Optional Nat
  5409. math.Natural.toMaybeNat.doc : Doc
  5410. math.Natural.toNat : Natural ->{Exception} Nat
  5411. math.Natural.toNat.doc : Doc
  5412. math.Natural.toNat.tests.roundtrip : [Result]
  5413. math.Natural.toText : Nat -> Natural -> Optional Text
  5414. math.Natural.toText.deprecated : Natural
                                         -> Nat
                                         -> Optional Text
  5415. math.Natural.toText.deprecated.doc : Doc
  5416. math.Natural.toText.doc : Doc
  5417. math.Natural.toText! : Nat -> Natural ->{Abort} Text
  5418. math.Natural.toText!.deprecated : Natural
                                          -> Nat
                                          ->{Abort} Text
  5419. math.Natural.toText!.deprecated.doc : Doc
  5420. math.Natural.toText!.doc : Doc
  5421. math.Natural.zero : Natural
  5422. math.Natural.zero.doc : Doc
  5423. math.Natural.^ : Natural -> Nat -> Natural
  5424. type metadata.Author
  5425. metadata.Author.Author : GUID -> Text -> Author
  5426. metadata.Author.doc : Doc
  5427. metadata.Author.guid : Author -> GUID
  5428. metadata.Author.guid.doc : Doc
  5429. metadata.Author.guid.modify : (GUID ->{𝕖} GUID)
                                      -> Author
                                      ->{𝕖} Author
  5430. metadata.Author.guid.modify.doc : Doc
  5431. metadata.Author.guid.set : GUID -> Author -> Author
  5432. metadata.Author.guid.set.doc : Doc
  5433. metadata.Author.name : Author -> Text
  5434. metadata.Author.name.doc : Doc
  5435. metadata.Author.name.modify : (Text ->{𝕖} Text)
                                      -> Author
                                      ->{𝕖} Author
  5436. metadata.Author.name.modify.doc : Doc
  5437. metadata.Author.name.set : Text -> Author -> Author
  5438. metadata.Author.name.set.doc : Doc
  5439. metadata.Author.toCopyrightHolder : Author
                                            -> CopyrightHolder
  5440. metadata.Author.toCopyrightHolder.doc : Doc
  5441. metadata.authors.andriypalamarchuk : Author
  5442. metadata.authors.andriypalamarchuk.guid : GUID
  5443. metadata.authors.anovstrup : Author
  5444. metadata.authors.anovstrup.guid : GUID
  5445. metadata.authors.aryairani : Author
  5446. metadata.authors.aryairani.guid : GUID
  5447. metadata.authors.atacratic : Author
  5448. metadata.authors.atacratic.guid : GUID
  5449. metadata.authors.ceedubs : Author
  5450. metadata.authors.ceedubs.guid : GUID
  5451. metadata.authors.chiroptical : Author
  5452. metadata.authors.chiroptical.guid : GUID
  5453. metadata.authors.chrispenner : Author
  5454. metadata.authors.chrispenner.guid : GUID
  5455. metadata.authors.daanleijen : Author
  5456. metadata.authors.daanleijen.guid : GUID
  5457. metadata.authors.dariooddenino : Author
  5458. metadata.authors.dariooddenino.guid : GUID
  5459. metadata.authors.dolio : Author
  5460. metadata.authors.dolio.guid : GUID
  5461. metadata.authors.emiflake : Author
  5462. metadata.authors.emiflake.guid : GUID
  5463. metadata.authors.fabianböller : Author
  5464. metadata.authors.fabianböller.guid : GUID
  5465. metadata.authors.gerardfinol : Author
  5466. metadata.authors.gerardfinol.guid : GUID
  5467. metadata.authors.hagl : Author
  5468. metadata.authors.hagl.guid : GUID
  5469. metadata.authors.heathermiller : Author
  5470. metadata.authors.heathermiller.guid : GUID
  5471. metadata.authors.iamevn : Author
  5472. metadata.authors.iamevn.guid : GUID
  5473. metadata.authors.jamessully : Author
  5474. metadata.authors.jamessully.guid : GUID
  5475. metadata.authors.johanwinther : Author
  5476. metadata.authors.johanwinther.guid : GUID
  5477. metadata.authors.jskripsky : Author
  5478. metadata.authors.jskripsky.guid : GUID
  5479. metadata.authors.justjoheinz : Author
  5480. metadata.authors.justjoheinz.guid : GUID
  5481. metadata.authors.katefulton : Author
  5482. metadata.authors.katefulton.guid : GUID
  5483. metadata.authors.loewenheim : Author
  5484. metadata.authors.loewenheim.guid : GUID
  5485. metadata.authors.oleggrenrus : Author
  5486. metadata.authors.oleggrenrus.guid : GUID
  5487. metadata.authors.pchiusano : Author
  5488. metadata.authors.pchiusano.guid : GUID
  5489. metadata.authors.pete_ts : Author
  5490. metadata.authors.pete_ts.guid : GUID
  5491. metadata.authors.pragdave : Author
  5492. metadata.authors.pragdave.guid : GUID
  5493. metadata.authors.rlmark : Author
  5494. metadata.authors.rlmark.guid : GUID
  5495. metadata.authors.runarorama : Author
  5496. metadata.authors.runarorama.doc : Doc
  5497. metadata.authors.runarorama.guid : GUID
  5498. metadata.authors.simonhøjberg : Author
  5499. metadata.authors.simonhøjberg.guid : GUID
  5500. metadata.authors.stew : Author
  5501. metadata.authors.stew.guid : GUID
  5502. metadata.authors.systemfw : Author
  5503. metadata.authors.systemfw.guid : GUID
  5504. metadata.authors.thomasschilling : Author
  5505. metadata.authors.thomasschilling.guid : GUID
  5506. metadata.authors.unisoncomputing.guid : GUID
  5507. metadata.authors.universityofglasgow : Author
  5508. metadata.authors.universityofglasgow.guid : GUID
  5509. metadata.authors.vanev : Author
  5510. metadata.authors.vanev.guid : GUID
  5511. metadata.authors.zenhack : Author
  5512. metadata.authors.zenhack.guid : GUID
  5513. type metadata.CopyrightHolder
  5514. metadata.CopyrightHolder.CopyrightHolder : GUID
                                                   -> Text
                                                   -> CopyrightHolder
  5515. metadata.CopyrightHolder.doc : Doc
  5516. metadata.CopyrightHolder.guid : CopyrightHolder -> GUID
  5517. metadata.CopyrightHolder.guid.doc : Doc
  5518. metadata.CopyrightHolder.guid.modify : (GUID ->{𝕖} GUID)
                                               -> CopyrightHolder
                                               ->{𝕖} CopyrightHolder
  5519. metadata.CopyrightHolder.guid.modify.doc : Doc
  5520. metadata.CopyrightHolder.guid.set : GUID
                                            -> CopyrightHolder
                                            -> CopyrightHolder
  5521. metadata.CopyrightHolder.guid.set.doc : Doc
  5522. metadata.CopyrightHolder.name : CopyrightHolder -> Text
  5523. metadata.CopyrightHolder.name.doc : Doc
  5524. metadata.CopyrightHolder.name.modify : (Text ->{𝕖} Text)
                                               -> CopyrightHolder
                                               ->{𝕖} CopyrightHolder
  5525. metadata.CopyrightHolder.name.modify.doc : Doc
  5526. metadata.CopyrightHolder.name.set : Text
                                            -> CopyrightHolder
                                            -> CopyrightHolder
  5527. metadata.CopyrightHolder.name.set.doc : Doc
  5528. metadata.copyrightHolders.andriypalamarchuk : CopyrightHolder
  5529. metadata.copyrightHolders.anovstrup : CopyrightHolder
  5530. metadata.copyrightHolders.atacratic : CopyrightHolder
  5531. metadata.copyrightHolders.ceedubs : CopyrightHolder
  5532. metadata.copyrightHolders.chiroptical : CopyrightHolder
  5533. metadata.copyrightHolders.chrispenner : CopyrightHolder
  5534. metadata.copyrightHolders.daanleijen : CopyrightHolder
  5535. metadata.copyrightHolders.dariooddenino : CopyrightHolder
  5536. metadata.copyrightHolders.emiflake : CopyrightHolder
  5537. metadata.copyrightHolders.fabianböller : CopyrightHolder
  5538. metadata.copyrightHolders.gerardfinol : CopyrightHolder
  5539. metadata.copyrightHolders.hagl : CopyrightHolder
  5540. metadata.copyrightHolders.iamevn : CopyrightHolder
  5541. metadata.copyrightHolders.jamessully : CopyrightHolder
  5542. metadata.copyrightHolders.johanwinther : CopyrightHolder
  5543. metadata.copyrightHolders.jskripsky : CopyrightHolder
  5544. metadata.copyrightHolders.justjoheinz : CopyrightHolder
  5545. metadata.copyrightHolders.katefulton : CopyrightHolder
  5546. metadata.copyrightHolders.pete_ts : CopyrightHolder
  5547. metadata.copyrightHolders.pragdave : CopyrightHolder
  5548. metadata.copyrightHolders.stew : CopyrightHolder
  5549. metadata.copyrightHolders.systemfw : CopyrightHolder
  5550. metadata.copyrightHolders.thomasschilling : CopyrightHolder
  5551. metadata.copyrightHolders.unisoncomputing : CopyrightHolder
  5552. metadata.copyrightHolders.universityofglasgow : CopyrightHolder
  5553. metadata.copyrightHolders.vanev : CopyrightHolder
  5554. metadata.copyrightHolders.zenhack : CopyrightHolder
  5555. type metadata.IsPropagated
  5556. metadata.isPropagated : IsPropagated
  5557. metadata.IsPropagated.doc : Doc
  5558. metadata.IsPropagated.IsPropagated : IsPropagated
  5559. type metadata.IsTest
  5560. metadata.isTest : IsTest
  5561. metadata.IsTest.IsTest : IsTest
  5562. type metadata.License
  5563. metadata.License.copyrightHolders : License
                                            -> [CopyrightHolder]
  5564. metadata.License.copyrightHolders.doc : Doc
  5565. metadata.License.copyrightHolders.modify : ([CopyrightHolder]
                                                   ->{𝕖} [CopyrightHolder])
                                                   -> License
                                                   ->{𝕖} License
  5566. metadata.License.copyrightHolders.modify.doc : Doc
  5567. metadata.License.copyrightHolders.set : [CopyrightHolder]
                                                -> License
                                                -> License
  5568. metadata.License.copyrightHolders.set.doc : Doc
  5569. metadata.License.doc : Doc
  5570. metadata.License.License : [CopyrightHolder]
                                   -> [Year]
                                   -> LicenseType
                                   -> License
  5571. metadata.License.licenseType : License -> LicenseType
  5572. metadata.License.licenseType.doc : Doc
  5573. metadata.License.licenseType.modify : (LicenseType
                                              ->{𝕖} LicenseType)
                                              -> License
                                              ->{𝕖} License
  5574. metadata.License.licenseType.modify.doc : Doc
  5575. metadata.License.licenseType.set : LicenseType
                                           -> License
                                           -> License
  5576. metadata.License.licenseType.set.doc : Doc
  5577. metadata.License.toDoc : License -> Doc
  5578. metadata.License.toDoc.doc : Doc
  5579. metadata.License.years : License -> [Year]
  5580. metadata.License.years.doc : Doc
  5581. metadata.License.years.modify : ([Year] ->{𝕖} [Year])
                                        -> License
                                        ->{𝕖} License
  5582. metadata.License.years.modify.doc : Doc
  5583. metadata.License.years.set : [Year]
                                     -> License
                                     -> License
  5584. metadata.License.years.set.doc : Doc
  5585. metadata.licenses.anovstrup.bsd2_2020 : License
  5586. metadata.licenses.anovstrup.bsd2_2020.doc : Doc
  5587. metadata.licenses.anovstrup.bsd3_2020 : License
  5588. metadata.licenses.anovstrup.bsd3_2020.doc : Doc
  5589. metadata.licenses.anovstrup.mit_2020 : License
  5590. metadata.licenses.anovstrup.mit_2020.doc : Doc
  5591. metadata.licenses.atacratic.mit_2020 : License
  5592. metadata.licenses.ceedubs2020 : License
  5593. metadata.licenses.ceedubs2020.doc : Doc
  5594. metadata.licenses.chiroptical.mit_2022 : License
  5595. metadata.licenses.chiroptical.mit_2022.doc : Doc
  5596. metadata.licenses.chrispenner : License
  5597. metadata.licenses.chrispenner.doc : Doc
  5598. metadata.licenses.dariooddenino.dariooddenino2020 : License
  5599. metadata.licenses.dariooddenino.dariooddenino2020.doc : Doc
  5600. metadata.licenses.datamapinternal : License
  5601. metadata.licenses.datamapinternal.doc : Doc
  5602. metadata.licenses.emiflake_mit_2020 : License
  5603. metadata.licenses.emiflake_mit_2020.doc : Doc
  5604. metadata.licenses.fböller2020 : License
  5605. metadata.licenses.fböller2020.doc : Doc
  5606. metadata.licenses.hagl2021 : License
  5607. metadata.licenses.hagl2021.doc : Doc
  5608. metadata.licenses.iamevn : License
  5609. metadata.licenses.iamevn.doc : Doc
  5610. metadata.licenses.jamessully : License
  5611. metadata.licenses.jamessully.doc : Doc
  5612. metadata.licenses.johanwinther2023 : License
  5613. metadata.licenses.jskripsky2023 : License
  5614. metadata.licenses.justjoheinz : License
  5615. metadata.licenses.katefulton2021 : License
  5616. metadata.licenses.katefulton2021.doc : Doc
  5617. metadata.licenses.pete_ts.bsd2_2020 : License
  5618. metadata.licenses.pete_ts.bsd2_2020.doc : Doc
  5619. metadata.licenses.pete_ts.bsd3_2020 : License
  5620. metadata.licenses.pete_ts.bsd3_2020.doc : Doc
  5621. metadata.licenses.pete_ts.mit_2020 : License
  5622. metadata.licenses.pete_ts.mit_2020.doc : Doc
  5623. metadata.licenses.unisoncomputing2020 : License
  5624. metadata.licenses.unisoncomputing2020.doc : Doc
  5625. metadata.licenses.unisoncomputing2021 : License
  5626. metadata.licenses.unisoncomputing2021.doc : Doc
  5627. metadata.licenses.unisoncomputing2022 : License
  5628. metadata.licenses.unisoncomputing2022.doc : Doc
  5629. metadata.licenses.unisoncomputing2023 : License
  5630. metadata.licenses.unisoncomputing2023.doc : Doc
  5631. metadata.licenses.zenhack2020 : License
  5632. metadata.licenses.zenhack2020.doc : Doc
  5633. type metadata.LicenseType
  5634. metadata.LicenseType.doc : Doc
  5635. metadata.LicenseType.LicenseType : Doc -> LicenseType
  5636. metadata.licenseTypes.allRightsReserved : LicenseType
  5637. metadata.licenseTypes.allRightsReserved.doc : Doc
  5638. metadata.licenseTypes.bsd2 : LicenseType
  5639. metadata.licenseTypes.bsd2.doc : Doc
  5640. metadata.licenseTypes.bsd3 : LicenseType
  5641. metadata.licenseTypes.bsd3.doc : Doc
  5642. metadata.licenseTypes.cc0 : LicenseType
  5643. metadata.licenseTypes.cc0.doc : Doc
  5644. metadata.licenseTypes.cc0.text : Doc
  5645. metadata.licenseTypes.mit : LicenseType
  5646. metadata.licenseTypes.mit.doc : Doc
  5647. metadata.unassignedGuids.guid3 : GUID
  5648. metadata.unassignedGuids.guid4 : GUID
  5649. metadata.unassignedGuids.guid5 : GUID
  5650. metadata.unassignedGuids.guid6 : GUID
  5651. metadata.unassignedGuids.guid8 : GUID
  5652. type metadata.Year
  5653. metadata.Year.doc : Doc
  5654. metadata.Year.toText : Year -> Text
  5655. metadata.Year.toText.doc : Doc
  5656. metadata.Year.Year : Nat -> Year
  5657. structural type mutable.Array g a
  5658. mutable.Array.copy : Nat
                             -> Nat
                             -> Nat
                             -> mutable.Array g a
                             -> mutable.Array g a
                             ->{g, Exception} ()
  5659. mutable.Array.copy.doc : Doc
  5660. mutable.Array.copy.tests.doesCopy : [Result]
  5661. mutable.Array.copy.tests.doesNotCopyPastEndOfDestinationArray : [Result]
  5662. mutable.Array.copy.tests.doesNotCopyPastEndOfSourceArray : [Result]
  5663. mutable.Array.doc : Doc
  5664. mutable.Array.drop! : Nat
                              -> mutable.Array g a
                              ->{Exception} mutable.Array g a
  5665. mutable.Array.drop!.doc : Doc
  5666. mutable.Array.dropEnd! : Nat
                                 -> mutable.Array g a
                                 ->{Exception} mutable.Array g a
  5667. mutable.Array.dropEnd!.doc : Doc
  5668. mutable.Array.fill : Nat
                             -> a
                             ->{Scope s} mutable.Array
                               {Scope s} a
  5669. mutable.Array.fill.doc : Doc
  5670. mutable.Array.freeze : mutable.Array g a
                               ->{g} data.Array a
  5671. mutable.Array.freeze.doc : Doc
  5672. mutable.Array.freeze! : mutable.Array g a
                                ->{g} data.Array a
  5673. mutable.Array.freeze!.doc : Doc
  5674. mutable.Array.MArr : Nat
                             -> Nat
                             -> mutable.Array.Raw g a
                             -> mutable.Array g a
  5675. mutable.Array.MArr.doc : Doc
  5676. mutable.Array.mutable.Array.fromList : [a]
                                               ->{Scope s} mutable.Array
                                                 {Scope s} a
  5677. mutable.Array.mutable.Array.fromList.doc : Doc
  5678. mutable.Array.of : x
                           -> Nat
                           ->{Scope s} mutable.Array {Scope s} x
  5679. mutable.Array.of.doc : Doc
  5680. builtin type mutable.Array.Raw
  5681. mutable.Array.Raw.copyTo! : mutable.Array.Raw g a
                                    -> Nat
                                    -> mutable.Array.Raw g a
                                    -> Nat
                                    -> Nat
                                    ->{g, Exception} ()
  5682. mutable.Array.Raw.copyTo!.doc : Doc
  5683. mutable.Array.Raw.doc : Doc
  5684. mutable.Array.Raw.freeze : mutable.Array.Raw g a
                                   -> Nat
                                   -> Nat
                                   ->{g} data.Array.Raw a
  5685. mutable.Array.Raw.freeze.doc : Doc
  5686. mutable.Array.Raw.freeze! : mutable.Array.Raw g a
                                    ->{g} data.Array.Raw a
  5687. mutable.Array.Raw.freeze!.doc : Doc
  5688. mutable.Array.Raw.read : mutable.Array.Raw g a
                                 -> Nat
                                 ->{g, Exception} a
  5689. mutable.Array.Raw.read.doc : Doc
  5690. mutable.Array.Raw.size : mutable.Array.Raw g a -> Nat
  5691. mutable.Array.Raw.size.doc : Doc
  5692. mutable.Array.Raw.write : mutable.Array.Raw g a
                                  -> Nat
                                  -> a
                                  ->{g, Exception} ()
  5693. mutable.Array.Raw.write.doc : Doc
  5694. mutable.Array.read : mutable.Array g a
                             -> Nat
                             ->{g, Exception} a
  5695. mutable.Array.read.doc : Doc
  5696. mutable.Array.resize : Nat
                               -> a
                               -> mutable.Array {Scope s} a
                               ->{Exception, Scope s} mutable.Array
                                 {Scope s} a
  5697. mutable.Array.resize.doc : Doc
  5698. mutable.Array.resize.impl : (∀ x.
                                      x
                                      -> Nat
                                      ->{g} mutable.Array g x)
                                    -> Nat
                                    -> a
                                    -> mutable.Array g a
                                    ->{g, Exception} mutable.Array
                                      g a
  5699. mutable.Array.resizeIO : Nat
                                 -> a
                                 -> mutable.Array IO a
                                 ->{IO, Exception} mutable.Array
                                   IO a
  5700. mutable.Array.resizeIO.doc : Doc
  5701. mutable.Array.size : mutable.Array g a -> Nat
  5702. mutable.Array.size.doc : Doc
  5703. mutable.Array.slice! : Nat
                               -> Nat
                               -> mutable.Array g a
                               ->{Exception} mutable.Array g a
  5704. mutable.Array.slice!.doc : Doc
  5705. mutable.Array.write : mutable.Array g a
                              -> Nat
                              -> a
                              ->{g, Exception} ()
  5706. mutable.Array.write.doc : Doc
  5707. structural type mutable.ByteArray g
  5708. mutable.ByteArray.doc : Doc
  5709. mutable.ByteArray.drop! : Nat
                                  -> mutable.ByteArray g
                                  ->{Exception} mutable.ByteArray
                                    g
  5710. mutable.ByteArray.drop!.doc : Doc
  5711. mutable.ByteArray.dropEnd! : Nat
                                     -> mutable.ByteArray g
                                     ->{Exception} mutable.ByteArray
                                       g
  5712. mutable.ByteArray.dropEnd!.doc : Doc
  5713. mutable.ByteArray.freeze : mutable.ByteArray g
                                   ->{g} data.ByteArray
  5714. mutable.ByteArray.freeze.doc : Doc
  5715. mutable.ByteArray.freeze! : mutable.ByteArray g
                                    ->{g} data.ByteArray
  5716. mutable.ByteArray.freeze!.doc : Doc
  5717. mutable.ByteArray.MBArr : Nat
                                  -> Nat
                                  -> mutable.ByteArray.Raw g
                                  -> mutable.ByteArray g
  5718. builtin type mutable.ByteArray.Raw
  5719. mutable.ByteArray.Raw.copyTo! : mutable.ByteArray.Raw g
                                        -> Nat
                                        -> mutable.ByteArray.Raw
                                          g
                                        -> Nat
                                        -> Nat
                                        ->{g, Exception} ()
  5720. mutable.ByteArray.Raw.copyTo!.doc : Doc
  5721. mutable.ByteArray.Raw.doc : Doc
  5722. mutable.ByteArray.Raw.freeze : mutable.ByteArray.Raw g
                                       -> Nat
                                       -> Nat
                                       ->{g} data.ByteArray.Raw
  5723. mutable.ByteArray.Raw.freeze.doc : Doc
  5724. mutable.ByteArray.Raw.freeze! : mutable.ByteArray.Raw g
                                        ->{g} data.ByteArray.Raw
  5725. mutable.ByteArray.Raw.freeze!.doc : Doc
  5726. mutable.ByteArray.Raw.read16be : mutable.ByteArray.Raw g
                                         -> Nat
                                         ->{g, Exception} Nat
  5727. mutable.ByteArray.Raw.read16be.doc : Doc
  5728. mutable.ByteArray.Raw.read24be : mutable.ByteArray.Raw g
                                         -> Nat
                                         ->{g, Exception} Nat
  5729. mutable.ByteArray.Raw.read24be.doc : Doc
  5730. mutable.ByteArray.Raw.read32be : mutable.ByteArray.Raw g
                                         -> Nat
                                         ->{g, Exception} Nat
  5731. mutable.ByteArray.Raw.read32be.doc : Doc
  5732. mutable.ByteArray.Raw.read40be : mutable.ByteArray.Raw g
                                         -> Nat
                                         ->{g, Exception} Nat
  5733. mutable.ByteArray.Raw.read40be.doc : Doc
  5734. mutable.ByteArray.Raw.read64be : mutable.ByteArray.Raw g
                                         -> Nat
                                         ->{g, Exception} Nat
  5735. mutable.ByteArray.Raw.read64be.doc : Doc
  5736. mutable.ByteArray.Raw.read8 : mutable.ByteArray.Raw g
                                      -> Nat
                                      ->{g, Exception} Nat
  5737. mutable.ByteArray.Raw.read8.doc : Doc
  5738. mutable.ByteArray.Raw.size : mutable.ByteArray.Raw g
                                     -> Nat
  5739. mutable.ByteArray.Raw.size.doc : Doc
  5740. mutable.ByteArray.Raw.write16be : mutable.ByteArray.Raw
                                            g
                                          -> Nat
                                          -> Nat
                                          ->{g, Exception} ()
  5741. mutable.ByteArray.Raw.write16be.doc : Doc
  5742. mutable.ByteArray.Raw.write32be : mutable.ByteArray.Raw
                                            g
                                          -> Nat
                                          -> Nat
                                          ->{g, Exception} ()
  5743. mutable.ByteArray.Raw.write32be.doc : Doc
  5744. mutable.ByteArray.Raw.write64be : mutable.ByteArray.Raw
                                            g
                                          -> Nat
                                          -> Nat
                                          ->{g, Exception} ()
  5745. mutable.ByteArray.Raw.write64be.doc : Doc
  5746. mutable.ByteArray.Raw.write8 : mutable.ByteArray.Raw g
                                       -> Nat
                                       -> Nat
                                       ->{g, Exception} ()
  5747. mutable.ByteArray.Raw.write8.doc : Doc
  5748. mutable.ByteArray.read8 : mutable.ByteArray g
                                  -> Nat
                                  ->{g, Exception} Nat
  5749. mutable.ByteArray.read8.doc : Doc
  5750. mutable.ByteArray.size : mutable.ByteArray g -> Nat
  5751. mutable.ByteArray.size.doc : Doc
  5752. mutable.ByteArray.slice! : Nat
                                   -> Nat
                                   -> mutable.ByteArray g
                                   ->{Exception} mutable.ByteArray
                                     g
  5753. mutable.ByteArray.slice!.doc : Doc
  5754. mutable.ByteArray.write16be : mutable.ByteArray g
                                      -> Nat
                                      -> Nat
                                      ->{g, Exception} ()
  5755. mutable.ByteArray.write16be.doc : Doc
  5756. mutable.ByteArray.write32be : mutable.ByteArray g
                                      -> Nat
                                      -> Nat
                                      ->{g, Exception} ()
  5757. mutable.ByteArray.write32be.doc : Doc
  5758. mutable.ByteArray.write64be : mutable.ByteArray g
                                      -> Nat
                                      -> Nat
                                      ->{g, Exception} ()
  5759. mutable.ByteArray.write64be.doc : Doc
  5760. mutable.ByteArray.write8 : mutable.ByteArray g
                                   -> Nat
                                   -> Nat
                                   ->{g, Exception} ()
  5761. mutable.ByteArray.write8.doc : Doc
  5762. builtin type mutable.Ref
  5763. mutable.Ref.doc : Doc
  5764. mutable.Ref.modify.deprecated : Ref g a
                                        -> (a ->{h} a)
                                        ->{g, h} ()
  5765. mutable.Ref.modify.deprecated.doc : Doc
  5766. mutable.Ref.read : Ref g a ->{g} a
  5767. mutable.Ref.read.doc : Doc
  5768. mutable.Ref.write : Ref g a -> a ->{g} ()
  5769. mutable.Ref.write.doc : Doc
  5770. builtin type mutable.Scope
  5771. mutable.Scope.arrayOf : a
                                -> Nat
                                ->{Scope s} mutable.Array
                                  {Scope s} a
  5772. mutable.Scope.arrayOf.doc : Doc
  5773. mutable.Scope.byteArray : Nat
                                  ->{Scope s} mutable.ByteArray
                                    {Scope s}
  5774. mutable.Scope.byteArray.doc : Doc
  5775. mutable.Scope.byteArrayOf : Nat
                                    -> Nat
                                    ->{Scope s} mutable.ByteArray
                                      {Scope s}
  5776. mutable.Scope.byteArrayOf.doc : Doc
  5777. mutable.Scope.byteArrayOf.test : [Result]
  5778. mutable.Scope.doc : Doc
  5779. mutable.Scope.Raw.array : Nat
                                  ->{Scope s} mutable.Array.Raw
                                    (Scope s) a
  5780. mutable.Scope.Raw.array.doc : Doc
  5781. mutable.Scope.Raw.arrayOf : a
                                    -> Nat
                                    ->{Scope s} mutable.Array.Raw
                                      (Scope s) a
  5782. mutable.Scope.Raw.arrayOf.doc : Doc
  5783. mutable.Scope.Raw.byteArray : Nat
                                      ->{Scope s} mutable.ByteArray.Raw
                                        (Scope s)
  5784. mutable.Scope.Raw.byteArray.doc : Doc
  5785. mutable.Scope.Raw.byteArrayOf : Nat
                                        -> Nat
                                        ->{Scope s} mutable.ByteArray.Raw
                                          (Scope s)
  5786. mutable.Scope.Raw.bytearrayOf.doc : Doc
  5787. mutable.Scope.ref : a ->{Scope s} Ref {Scope s} a
  5788. mutable.Scope.ref.doc : Doc
  5789. mutable.Scope.ref.modify : Ref {Scope s} a
                                   -> (a ->{g} a)
                                   ->{g, Scope s} ()
  5790. mutable.Scope.ref.modify.doc : Doc
  5791. mutable.Scope.run : (∀ s. '{g, Scope s} r) ->{g} r
  5792. mutable.Scope.run.doc : Doc
  5793. mutable.Scope.thawArray : data.Array a
                                  ->{Scope s} mutable.Array
                                    {Scope s} a
  5794. mutable.Scope.thawArray.doc : Doc
  5795. mutable.Scope.thawByteArray : data.ByteArray
                                      ->{Scope s} mutable.ByteArray
                                        {Scope s}
  5796. mutable.Scope.thawByteArray.doc : Doc
  5797. builtin type Nat
  5798. Nat.!= : Nat -> Nat -> Boolean
  5799. Nat.!=.doc : Doc
  5800. Nat.% : Nat -> Nat -> Nat
  5801. Nat.%.doc : Doc
  5802. Nat.* : Nat -> Nat -> Nat
  5803. Nat.*.doc : Doc
  5804. Nat.+ : Nat -> Nat -> Nat
  5805. Nat.+.doc : Doc
  5806. Nat.- : Nat -> Nat -> Nat
  5807. Nat.-.doc : Doc
  5808. Nat.-.tests.leftAdjoint : [Result]
  5809. Nat./ : Nat -> Nat -> Nat
  5810. Nat./.doc : Doc
  5811. Nat.< : Nat -> Nat -> Boolean
  5812. Nat.<.doc : Doc
  5813. Nat.<= : Nat -> Nat -> Boolean
  5814. Nat.<=.doc : Doc
  5815. Nat.== : Nat -> Nat -> Boolean
  5816. Nat.==.doc : Doc
  5817. Nat.> : Nat -> Nat -> Boolean
  5818. Nat.>.doc : Doc
  5819. Nat.>= : Nat -> Nat -> Boolean
  5820. Nat.>=.doc : Doc
  5821. Nat.and : Nat -> Nat -> Nat
  5822. Nat.and.doc : Doc
  5823. Nat.bit : Nat -> Nat -> Nat
  5824. Nat.bit.doc : Doc
  5825. Nat.changeBit : Nat -> Boolean -> Nat -> Nat
  5826. Nat.changeBit.doc : Doc
  5827. Nat.changeBit.tests : [Result]
  5828. Nat.choose : Nat -> Nat -> Nat
  5829. Nat.choose.doc : Doc
  5830. Nat.choose.tests.test1 : [Result]
  5831. Nat.clamp : Nat -> Nat -> Nat -> Nat
  5832. Nat.clamp.doc : Doc
  5833. Nat.clamp.test : [Result]
  5834. Nat.clearBit : Nat -> Nat -> Nat
  5835. Nat.clearBit.doc : Doc
  5836. Nat.complement : Nat -> Nat
  5837. Nat.complement.doc : Doc
  5838. Nat.decrement : Nat -> Nat
  5839. Nat.decrement.doc : Doc
  5840. Nat.decrement.test : [Result]
  5841. Nat.deprecated.findLowestZero : (Nat ->{e} Int)
                                        -> Nat
                                        -> Nat
                                        ->{e} Nat
  5842. Nat.deprecated.findLowestZero.doc : Doc
  5843. Nat.diff : Nat -> Nat -> Nat
  5844. Nat.diff.doc : Doc
  5845. Nat.div : Nat -> Nat -> Nat
  5846. Nat.div.doc : Doc
  5847. Nat.doc : Doc
  5848. Nat.dropBits : Nat -> Nat -> Nat
  5849. Nat.dropBits.doc : Doc
  5850. Nat.eq : Nat -> Nat -> Boolean
  5851. Nat.eq.doc : Doc
  5852. Nat.factorial : Nat -> Natural
  5853. Nat.factorial.doc : Doc
  5854. Nat.factorial.tests.test1 : [Result]
  5855. Nat.flipBit : Nat -> Nat -> Nat
  5856. Nat.flipBit.doc : Doc
  5857. Nat.flipEndian : Nat -> Nat
  5858. Nat.flipEndian.doc : Doc
  5859. Nat.fromBytesBigEndian : Bytes ->{Abort} Nat
  5860. Nat.fromBytesBigEndian.doc : Doc
  5861. Nat.fromBytesLittleEndian : Bytes ->{Abort} Nat
  5862. Nat.fromBytesLittleEndian.doc : Doc
  5863. Nat.fromHex : Text -> Optional Nat
  5864. Nat.fromHex.doc : Doc
  5865. Nat.fromInt : Int -> Optional Nat
  5866. Nat.fromInt.doc : Doc
  5867. Nat.fromText : Text -> Optional Nat
  5868. Nat.fromText.doc : Doc
  5869. Nat.fromTextOrFail : Text ->{Exception} Nat
  5870. Nat.fromTextOrFail.doc : Doc
  5871. Nat.gcd : Nat -> Nat ->{Abort} Nat
  5872. Nat.gcd.doc : Doc
  5873. Nat.gcd.tests.commonDivisor : [Result]
  5874. Nat.gcd.tests.multipleOfAnyCD : [Result]
  5875. Nat.gt : Nat -> Nat -> Boolean
  5876. Nat.gt.doc : Doc
  5877. Nat.gteq : Nat -> Nat -> Boolean
  5878. Nat.gteq.doc : Doc
  5879. Nat.increment : Nat -> Nat
  5880. Nat.increment.doc : Doc
  5881. Nat.inRange : Nat -> Nat -> Nat -> Boolean
  5882. Nat.inRange.doc : Doc
  5883. Nat.inRange.test : [Result]
  5884. Nat.isEven : Nat -> Boolean
  5885. Nat.isEven.doc : Doc
  5886. Nat.isOdd : Nat -> Boolean
  5887. Nat.isOdd.doc : Doc
  5888. Nat.isPrefixOf : Nat -> Nat -> Boolean
  5889. Nat.isPrefixOf.doc : Doc
  5890. Nat.isSetBit : Nat -> Nat -> Boolean
  5891. Nat.isSetBit.doc : Doc
  5892. Nat.isSuffixOf : Nat -> Nat -> Boolean
  5893. Nat.isSuffixOf.doc : Doc
  5894. Nat.lcm : Nat -> Nat ->{Abort} Nat
  5895. Nat.lcm.doc : Doc
  5896. Nat.leadingOnes : Nat -> Nat
  5897. Nat.leadingOnes.doc : Doc
  5898. Nat.leadingOnes.tests : [Result]
  5899. Nat.leadingZeros : Nat -> Nat
  5900. Nat.leadingZeros.doc : Doc
  5901. Nat.lsfr : Nat -> Nat
  5902. Nat.lsfr.doc : Doc
  5903. Nat.lt : Nat -> Nat -> Boolean
  5904. Nat.lt.doc : Doc
  5905. Nat.lteq : Nat -> Nat -> Boolean
  5906. Nat.lteq.doc : Doc
  5907. Nat.max : Nat -> Nat -> Nat
  5908. Nat.max.doc : Doc
  5909. Nat.maxNat : Nat
  5910. Nat.maxNat.doc : Doc
  5911. Nat.maybeMultiply : Nat -> Nat ->{Abort} Nat
  5912. Nat.maybeMultiply.doc : Doc
  5913. Nat.min : Nat -> Nat -> Nat
  5914. Nat.min.doc : Doc
  5915. Nat.mod : Nat -> Nat -> Nat
  5916. Nat.mod.doc : Doc
  5917. Nat.modExp : Nat -> Nat -> Nat -> Nat
  5918. Nat.modExp.doc : Doc
  5919. Nat.modExp.tests : [Result]
  5920. Nat.msb : Nat -> Optional Nat
  5921. Nat.msb.doc : Doc
  5922. Nat.msb.test : [Result]
  5923. Nat.neq : Nat -> Nat -> Boolean
  5924. Nat.neq.doc : Doc
  5925. Nat.onesComplementSum : Nat -> Nat -> Nat -> Nat
  5926. Nat.onesComplementSum.doc : Doc
  5927. Nat.or : Nat -> Nat -> Nat
  5928. Nat.or.doc : Doc
  5929. Nat.popCount : Nat -> Nat
  5930. Nat.popCount.doc : Doc
  5931. Nat.popCount.test : [Result]
  5932. Nat.pow : Nat -> Nat -> Nat
  5933. Nat.pow.doc : Doc
  5934. Nat.product : [Nat] -> Nat
  5935. Nat.product.doc : Doc
  5936. Nat.range : Nat -> Nat -> [Nat]
  5937. Nat.range.doc : Doc
  5938. Nat.rangeClosed : Nat -> Nat -> [Nat]
  5939. Nat.rangeClosed.doc : Doc
  5940. Nat.reverseBits : Nat -> Nat
  5941. Nat.reverseBits.doc : Doc
  5942. Nat.reverseBits.test.hom : [Result]
  5943. Nat.reverseBits.test.iso : [Result]
  5944. Nat.search : (Nat ->{e} Int)
                     -> Nat
                     -> Nat
                     ->{e} Optional Nat
  5945. Nat.search.doc : Doc
  5946. Nat.setBit : Nat -> Nat -> Nat
  5947. Nat.setBit.doc : Doc
  5948. Nat.shiftLeft : Nat -> Nat -> Nat
  5949. Nat.shiftLeft.doc : Doc
  5950. Nat.shiftRight : Nat -> Nat -> Nat
  5951. Nat.shiftRight.doc : Doc
  5952. Nat.subtractToInt : Nat -> Nat -> Int
  5953. Nat.subtractToInt.doc : Doc
  5954. Nat.subtractToInt.impl : Nat -> Nat -> Int
  5955. Nat.sum : [Nat] -> Nat
  5956. Nat.sum.doc : Doc
  5957. Nat.takeLeftBits : Nat -> Nat -> Nat
  5958. Nat.takeLeftBits.doc : Doc
  5959. Nat.takeLeftBits.test : [Result]
  5960. Nat.takeRightBits : Nat -> Nat -> Nat
  5961. Nat.takeRightBits.doc : Doc
  5962. Nat.takeRightBits.test : [Result]
  5963. Nat.toBytesBigEndian : Nat -> Bytes
  5964. Nat.toBytesBigEndian.doc : Doc
  5965. Nat.toBytesBigEndian.test.ex1 : [Result]
  5966. Nat.toBytesLittleEndian : Nat -> Bytes
  5967. Nat.toBytesLittleEndian.doc : Doc
  5968. Nat.toBytesLittleEndian.test.ex1 : [Result]
  5969. Nat.toBytesLittleEndian.test.prop : [Result]
  5970. Nat.toFloat : Nat -> Float
  5971. Nat.toFloat.doc : Doc
  5972. Nat.toInt : Nat -> Int
  5973. Nat.toInt.doc : Doc
  5974. Nat.toText : Nat -> Text
  5975. Nat.toText.doc : Doc
  5976. Nat.toTextBase : Nat -> Nat -> Optional Text
  5977. Nat.toTextBase.doc : Doc
  5978. Nat.trailingZeros : Nat -> Nat
  5979. Nat.trailingZeros.doc : Doc
  5980. Nat.twosComplement : Nat -> Nat
  5981. Nat.twosComplement.doc : Doc
  5982. Nat.xor : Nat -> Nat -> Nat
  5983. Nat.xor.doc : Doc
  5984. OffsetDateTime.ordering : OffsetDateTime
                                  -> OffsetDateTime
                                  -> Ordering
  5985. OffsetTime.ordering : OffsetTime
                              -> OffsetTime
                              -> Ordering
  5986. structural type Optional a
  5987. Optional.<*> : Optional (a ->{g} b)
                       -> Optional a
                       ->{g} Optional b
  5988. Optional.<*>.doc : Doc
  5989. Optional.apply : Optional (a ->{g} b)
                         -> Optional a
                         ->{g} Optional b
  5990. Optional.apply.doc : Doc
  5991. Optional.compareBy : (a ->{g2} a ->{g1} Ordering)
                             -> Optional a
                             -> Optional a
                             ->{g2, g1} Ordering
  5992. Optional.compareBy.doc : Doc
  5993. Optional.contains : a -> Optional a -> Boolean
  5994. Optional.contains.doc : Doc
  5995. Optional.deprecated.mapOptional : (a ->{g} Optional b)
                                          -> [a]
                                          ->{g} [b]
  5996. Optional.deprecated.mapOptional.doc : Doc
  5997. Optional.doc : Doc
  5998. Optional.exists : (a ->{g} Boolean)
                          -> Optional a
                          ->{g} Boolean
  5999. Optional.exists.doc : Doc
  6000. Optional.filter : (a ->{g} Boolean)
                          -> Optional a
                          ->{g} Optional a
  6001. Optional.filter.doc : Doc
  6002. Optional.flatMap : (a ->{𝕖} Optional b)
                           -> Optional a
                           ->{𝕖} Optional b
  6003. Optional.flatten : Optional (Optional a) -> Optional a
  6004. Optional.flatten.doc : Doc
  6005. Optional.fold : '{g} b
                        -> (a ->{g} b)
                        -> Optional a
                        ->{g} b
  6006. Optional.fold.doc : Doc
  6007. Optional.forAll : (a ->{g} Boolean)
                          -> Optional a
                          ->{g} Boolean
  6008. Optional.forAll.doc : Doc
  6009. Optional.foreach : (a ->{g} ()) -> Optional a ->{g} ()
  6010. Optional.foreach.doc : Doc
  6011. Optional.getOrBug : msg -> Optional a -> a
  6012. Optional.getOrBug.doc : Doc
  6013. Optional.getOrElse : a -> Optional a -> a
  6014. Optional.getOrElse.doc : Doc
  6015. Optional.getOrElse' : '{e} a -> Optional a ->{e} a
  6016. Optional.getOrElse'.doc : Doc
  6017. Optional.isNone : Optional a -> Boolean
  6018. Optional.isNone.doc : Doc
  6019. Optional.isSome : Optional a -> Boolean
  6020. Optional.isSome.doc : Doc
  6021. Optional.map : (a ->{𝕖} b)
                       -> Optional a
                       ->{𝕖} Optional b
  6022. Optional.map.doc : Doc
  6023. Optional.map2 : (a ->{𝕖} b ->{𝕖} c)
                        -> Optional a
                        -> Optional b
                        ->{𝕖} Optional c
  6024. Optional.map2.doc : Doc
  6025. Optional.None : Optional a
  6026. Optional.None.doc : Doc
  6027. Optional.note : e -> Optional a ->{Throw e} a
  6028. Optional.note.doc : Doc
  6029. Optional.orElse : Optional a -> Optional a -> Optional a
  6030. Optional.orElse.doc : Doc
  6031. Optional.Some : a -> Optional a
  6032. Optional.Some.doc : Doc
  6033. Optional.toAbort : Optional a ->{Abort} a
  6034. Optional.toException : Text
                               -> Type
                               -> Optional a
                               ->{Exception} a
  6035. Optional.toException.doc : Doc
  6036. Optional.toGenericException : Optional a ->{Exception} a
  6037. Optional.toGenericException.doc : Doc
  6038. Optional.toGenericExceptionWith : Text
                                          -> b
                                          -> Optional a
                                          ->{Exception} a
  6039. Optional.toGenericExceptionWith.doc : Doc
  6040. Optional.toList : Optional a -> [a]
  6041. Optional.toList.doc : Doc
  6042. Optional.toList.tests.roundtrip : [Result]
  6043. Optional.unzip : Optional (a, b)
                         -> (Optional a, Optional b)
  6044. Optional.unzip.doc : Doc
  6045. Optional.zip : Optional a
                       -> Optional b
                       -> Optional (a, b)
  6046. Optional.zip.doc : Doc
  6047. type Ordering
  6048. Ordering.andThen : Ordering -> Ordering -> Ordering
  6049. Ordering.andThen.doc : Doc
  6050. Ordering.andThen.example.ex1 : Ordering
  6051. Ordering.doc : Doc
  6052. Ordering.eqBy : (a ->{f} b ->{g} Ordering)
                        -> a
                        -> b
                        ->{f, g} Boolean
  6053. Ordering.eqBy.doc : Doc
  6054. Ordering.Equal : Ordering
  6055. Ordering.Equal.doc : Doc
  6056. Ordering.Greater : Ordering
  6057. Ordering.gtBy : (a ->{g2} a ->{g1} Ordering)
                        -> a
                        -> a
                        ->{g2, g1} Boolean
  6058. Ordering.gtBy.doc : Doc
  6059. Ordering.gteqBy : (a ->{g2} a ->{g1} Ordering)
                          -> a
                          -> a
                          ->{g2, g1} Boolean
  6060. Ordering.gteqBy.doc : Doc
  6061. Ordering.inverse : Ordering -> Ordering
  6062. Ordering.inverse.doc : Doc
  6063. Ordering.Less : Ordering
  6064. Ordering.list.orderingBy : (a -> a ->{g} Ordering)
                                   -> [a]
                                   -> [a]
                                   ->{g} Ordering
  6065. Ordering.list.orderingBy.doc : Doc
  6066. Ordering.list.orderingBy.tests : [Result]
  6067. Ordering.ltBy : (a ->{g2} a ->{g1} Ordering)
                        -> a
                        -> a
                        ->{g2, g1} Boolean
  6068. Ordering.ltBy.doc : Doc
  6069. Ordering.lteqBy : (a ->{g2} a ->{g1} Ordering)
                          -> a
                          -> a
                          ->{g2, g1} Boolean
  6070. Ordering.lteqBy.doc : Doc
  6071. Ordering.maxBy : (a ->{g2} a ->{g1} Ordering)
                         -> a
                         -> a
                         ->{g2, g1} a
  6072. Ordering.maxBy.doc : Doc
  6073. Ordering.medianOf3By : (a ->{g2} a ->{g1} Ordering)
                               -> a
                               -> a
                               -> a
                               ->{g2, g1} a
  6074. Ordering.medianOf3By.doc : Doc
  6075. Ordering.medianOf3By.test : [Result]
  6076. Ordering.minBy : (a ->{g2} a ->{g1} Ordering)
                         -> a
                         -> a
                         ->{g2, g1} a
  6077. Ordering.minBy.doc : Doc
  6078. Ordering.pair.orderingBy : (a -> a ->{g2} Ordering)
                                   -> (b -> b ->{g} Ordering)
                                   -> (a, b)
                                   -> (a, b)
                                   ->{g, g2} Ordering
  6079. Ordering.pair.orderingBy.doc : Doc
  6080. Ordering.pair.orderingBy.tests : [Result]
  6081. builtin type Pattern
  6082. Pattern.+ : Pattern a -> Pattern a -> Pattern a
  6083. Pattern.+.doc : Doc
  6084. Pattern.capture : Pattern a -> Pattern a
  6085. Pattern.capture.doc : Doc
  6086. Pattern.captureAs : a -> Pattern a -> Pattern a
  6087. Pattern.captureAs.doc : Doc
  6088. Pattern.captures : Pattern t -> t -> [t]
  6089. Pattern.captures.doc : Doc
  6090. Pattern.doc : Doc
  6091. Pattern.drop : Pattern t -> t -> t
  6092. Pattern.drop.doc : Doc
  6093. Pattern.empty : Pattern a
  6094. Pattern.empty.doc : Doc
  6095. Pattern.isMatch : Pattern a -> a -> Boolean
  6096. Pattern.isMatch.doc : Doc
  6097. Pattern.join : [Pattern a] -> Pattern a
  6098. Pattern.join.doc : Doc
  6099. Pattern.many : Pattern a -> Pattern a
  6100. Pattern.many.doc : Doc
  6101. Pattern.oneOf : List.Nonempty (Pattern a) -> Pattern a
  6102. Pattern.oneOf.doc : Doc
  6103. Pattern.optional : Pattern a -> Pattern a
  6104. Pattern.optional.doc : Doc
  6105. Pattern.or : Pattern a -> Pattern a -> Pattern a
  6106. Pattern.or.doc : Doc
  6107. Pattern.replicate : Nat -> Nat -> Pattern a -> Pattern a
  6108. Pattern.replicate.doc : Doc
  6109. Pattern.run : Pattern a -> a -> Optional ([a], a)
  6110. Pattern.run.doc : Doc
  6111. Pattern.sepMany : Pattern a -> Pattern a -> Pattern a
  6112. Pattern.sepMany.doc : Doc
  6113. Pattern.sepSome : Pattern a -> Pattern a -> Pattern a
  6114. Pattern.sepSome.doc : Doc
  6115. Pattern.some : Pattern a -> Pattern a
  6116. Pattern.some.doc : Doc
  6117. structural type Pretty txt
  6118. type Pretty.Annotated w txt
  6119. Pretty.Annotated.Append : w
                                  -> [Annotated w txt]
                                  -> Annotated w txt
  6120. Pretty.Annotated.doc : Doc
  6121. Pretty.Annotated.Empty : Annotated w txt
  6122. Pretty.Annotated.Group : w
                                 -> Annotated w txt
                                 -> Annotated w txt
  6123. Pretty.Annotated.Indent : w
                                  -> Annotated w txt
                                  -> Annotated w txt
                                  -> Annotated w txt
                                  -> Annotated w txt
  6124. Pretty.Annotated.Lit : w -> txt -> Annotated w txt
  6125. Pretty.Annotated.OrElse : w
                                  -> Annotated w txt
                                  -> Annotated w txt
                                  -> Annotated w txt
  6126. Pretty.Annotated.Table : w
                                 -> [[Annotated w txt]]
                                 -> Annotated w txt
  6127. Pretty.Annotated.Wrap : w
                                -> Annotated w txt
                                -> Annotated w txt
  6128. Pretty.append : Pretty txt -> Pretty txt -> Pretty txt
  6129. Pretty.append.doc : Doc
  6130. Pretty.doc : Doc
  6131. Pretty.empty : Pretty txt
  6132. Pretty.empty.doc : Doc
  6133. Pretty.get : Pretty txt -> Annotated () txt
  6134. Pretty.get.doc : Doc
  6135. Pretty.group : Pretty txt -> Pretty txt
  6136. Pretty.group.doc : Doc
  6137. Pretty.indent : Pretty txt -> Pretty txt -> Pretty txt
  6138. Pretty.indent.doc : Doc
  6139. Pretty.indent' : Pretty txt
                         -> Pretty txt
                         -> Pretty txt
                         -> Pretty txt
  6140. Pretty.indent'.doc : Doc
  6141. Pretty.join : [Pretty txt] -> Pretty txt
  6142. Pretty.join.doc : Doc
  6143. Pretty.lit : txt -> Pretty txt
  6144. Pretty.lit.doc : Doc
  6145. Pretty.map : (txt ->{g} txt2)
                     -> Pretty txt
                     ->{g} Pretty txt2
  6146. Pretty.map.doc : Doc
  6147. Pretty.orElse : Pretty txt -> Pretty txt -> Pretty txt
  6148. Pretty.orElse.doc : Doc
  6149. Pretty.Pretty : Annotated () txt -> Pretty txt
  6150. Pretty.sepBy : Pretty txt -> [Pretty txt] -> Pretty txt
  6151. Pretty.sepBy.doc : Doc
  6152. Pretty.table : [[Pretty txt]] -> Pretty txt
  6153. Pretty.table.doc : Doc
  6154. Pretty.wrap : Pretty txt -> Pretty txt
  6155. Pretty.wrap.doc : Doc
  6156. README : Doc
  6157. builtin type reflection.Code
  6158. reflection.Code.cache_ : [(Link.Term, Code)]
                                 ->{IO} [Link.Term]
  6159. reflection.Code.cache_.doc : Doc
  6160. reflection.Code.dependencies : Code -> [Link.Term]
  6161. reflection.Code.dependencies.doc : Doc
  6162. reflection.Code.deserialize : Bytes ->{Exception} Code
  6163. reflection.Code.deserialize.doc : Doc
  6164. reflection.Code.deserialize.impl : Bytes
                                           -> Either Text Code
  6165. reflection.Code.deserialize.impl.doc : Doc
  6166. reflection.Code.doc : Doc
  6167. reflection.Code.doc.snippets.unisonTerm : Doc
  6168. reflection.Code.isMissing : Link.Term ->{IO} Boolean
  6169. reflection.Code.isMissing.doc : Doc
  6170. reflection.Code.lookup : Link.Term ->{IO} Optional Code
  6171. reflection.Code.lookup.doc : Doc
  6172. reflection.Code.serialize : Code -> Bytes
  6173. reflection.Code.serialize.doc : Doc
  6174. reflection.Code.validateLinks : [(Link.Term, Code)]
                                        ->{Exception} Either
                                          [Link.Term]
                                          [Link.Term]
  6175. reflection.Code.validateLinks.doc : Doc
  6176. type reflection.Link
  6177. reflection.Link.doc : Doc
  6178. builtin type reflection.Link.Term
  6179. reflection.Link.Term : Link.Term -> Link
  6180. reflection.Link.Term.doc : Doc
  6181. reflection.Link.Term.toText : Link.Term -> Text
  6182. reflection.Link.Term.toText.doc : Doc
  6183. builtin type reflection.Link.Type
  6184. reflection.Link.Type : Type -> Link
  6185. reflection.Link.Type.doc : Doc
  6186. type reflection.RewriteCase a b
  6187. reflection.RewriteCase.RewriteCase : a
                                             -> b
                                             -> RewriteCase a b
  6188. type reflection.Rewrites a
  6189. reflection.Rewrites.doc : Doc
  6190. reflection.Rewrites.examples.eitherToOptional : e1
                                                        -> a1
                                                        -> Rewrites
                                                          ( RewriteTerm
                                                            (Either
                                                              e1
                                                              b1)
                                                            (Optional
                                                              a5),
                                                            RewriteTerm
                                                            (Either
                                                              a4
                                                              a1)
                                                            (Optional
                                                              a1),
                                                            RewriteCase
                                                            (Either
                                                              e1
                                                              b)
                                                            (Optional
                                                              a3),
                                                            RewriteCase
                                                            (Either
                                                              a2
                                                              a1)
                                                            (Optional
                                                              a1),
                                                            RewriteSignature
                                                            (Either
                                                              e
                                                              a)
                                                            (Optional
                                                              a))
  6191. reflection.Rewrites.examples.eitherToOptional.doc : Doc
  6192. reflection.Rewrites.examples.etaReduce : (i ->{g} o)
                                                 -> Rewrites
                                                   (Tuple
                                                     (RewriteTerm
                                                       (i
                                                       ->{g, g1} o)
                                                       (i
                                                       ->{g} o))
                                                     ())
  6193. reflection.Rewrites.examples.etaReduce.doc : Doc
  6194. reflection.Rewrites.examples.optionalToEither : ∀ _e a1 a5 b a4 a3 a2 a e.
                                                          _e
                                                          -> a1
                                                          -> Rewrites
                                                            ( RewriteTerm
                                                              (Optional
                                                                a5)
                                                              (Either
                                                                _e
                                                                b),
                                                              RewriteTerm
                                                              (Optional
                                                                a1)
                                                              (Either
                                                                a4
                                                                a1),
                                                              RewriteCase
                                                              (Optional
                                                                a1)
                                                              (Either
                                                                a3
                                                                a1),
                                                              RewriteCase
                                                              (Either
                                                                a2
                                                                a1)
                                                              (Optional
                                                                a1),
                                                              RewriteSignature
                                                              (Optional
                                                                a)
                                                              (Either
                                                                e
                                                                a))
  6195. reflection.Rewrites.examples.optionalToEither.doc : Doc
  6196. reflection.Rewrites.examples.useIncrement : Nat
                                                    -> Rewrites
                                                      (Tuple
                                                        (RewriteTerm
                                                          Nat
                                                          Nat)
                                                        ())
  6197. reflection.Rewrites.examples.useIncrement.doc : Doc
  6198. reflection.Rewrites.Rewrites : a -> Rewrites a
  6199. type reflection.RewriteSignature a b
  6200. reflection.RewriteSignature.RewriteSignature : (a
                                                       -> b
                                                       -> ())
                                                       -> RewriteSignature
                                                         a b
  6201. type reflection.RewriteTerm a b
  6202. reflection.RewriteTerm.RewriteTerm : a
                                             -> b
                                             -> RewriteTerm a b
  6203. reflection.validateSandboxed.deprecated : [Link.Term]
                                                  -> a
                                                  -> Boolean
  6204. reflection.validateSandboxed.deprecated.doc : Doc
  6205. builtin type reflection.Value
  6206. reflection.Value.dependencies : Value -> [Link.Term]
  6207. reflection.Value.dependencies.doc : Doc
  6208. reflection.Value.deserialize : Bytes ->{Exception} Value
  6209. reflection.Value.deserialize.doc : Doc
  6210. reflection.Value.deserialize.impl : Bytes
                                            -> Either Text Value
  6211. reflection.Value.deserialize.impl.doc : Doc
  6212. reflection.Value.doc : Doc
  6213. reflection.Value.load : Value
                                ->{IO} Either [Link.Term] a
  6214. reflection.Value.load.doc : Doc
  6215. reflection.Value.serialize : Value -> Bytes
  6216. reflection.Value.serialize.doc : Doc
  6217. reflection.Value.validateSandboxed : [Link.Term]
                                             -> Value
                                             ->{IO} Either
                                               [Link.Term]
                                               [Link.Term]
  6218. reflection.Value.validateSandboxed.doc : Doc
  6219. reflection.Value.validateSandboxed.example : '{IO} Either
                                                       [Link.Term]
                                                       [Link.Term]
  6220. reflection.Value.value : a -> Value
  6221. reflection.Value.value.doc : Doc
  6222. ReleaseNotes : Doc
  6223. Stream.toArray : '{g, Stream b} ()
                         ->{g, Exception} data.Array b
  6224. Stream.toArray.doc : Doc
  6225. syntax.docAside : Doc -> Doc
  6226. syntax.docBlockquote : Doc -> Doc
  6227. syntax.docBold : Doc -> Doc
  6228. syntax.docBulletedList : [Doc] -> Doc
  6229. syntax.docBulletedList.doc : Doc
  6230. syntax.docCallout : Optional Doc -> Doc -> Doc
  6231. syntax.docCallout.doc : Doc
  6232. syntax.docCode : Doc -> Doc
  6233. syntax.docCodeBlock : Text -> Text -> Doc
  6234. syntax.docCodeBlock.doc : Doc
  6235. syntax.docColumn : [Doc] -> Doc
  6236. syntax.docColumn.doc : Doc
  6237. syntax.docEmbedAnnotation : tm -> Doc.Term
  6238. syntax.docEmbedAnnotations : tms -> tms
  6239. syntax.docEmbedSignatureLink : '{g1} t -> Doc.Term
  6240. syntax.docEmbedTermLink : '{g1} t -> Either a Doc.Term
  6241. syntax.docEmbedTermLink.doc : Doc
  6242. syntax.docEmbedTypeLink : typ -> Either typ b
  6243. syntax.docEmbedTypeLink.doc : Doc
  6244. syntax.docEval : 'a -> Doc
  6245. syntax.docEval.doc : Doc
  6246. syntax.docEvalInline : 'a -> Doc
  6247. syntax.docEvalInline.doc : Doc
  6248. syntax.docExample : Nat -> '{g1} t -> Doc
  6249. syntax.docExample.doc : Doc
  6250. syntax.docExampleBlock : Nat -> '{g1} t -> Doc
  6251. syntax.docExampleBlock.doc : Doc
  6252. syntax.docFoldedSource : [( Either Type Doc.Term,
                                   [Doc.Term])]
                                 -> Doc
  6253. syntax.docFoldedSource.doc : Doc
  6254. syntax.docFormatConsole : Doc
                                  -> Pretty
                                    (Either
                                      SpecialForm ConsoleText)
  6255. syntax.docGroup : Doc -> Doc
  6256. syntax.docItalic : Doc -> Doc
  6257. syntax.docJoin : [Doc] -> Doc
  6258. syntax.docJoin.doc : Doc
  6259. syntax.docLink : Either Type Doc.Term -> Doc
  6260. syntax.docLink.doc : Doc
  6261. syntax.docNamedLink : Doc -> Doc -> Doc
  6262. syntax.docNumberedList : Nat -> [Doc] -> Doc
  6263. syntax.docNumberedList.doc : Doc
  6264. syntax.docParagraph : [Doc] -> Doc
  6265. syntax.docParagraph.doc : Doc
  6266. syntax.docSection : Doc -> [Doc] -> Doc
  6267. syntax.docSignature : [Doc.Term] -> Doc
  6268. syntax.docSignature.doc : Doc
  6269. syntax.docSignatureInline : Doc.Term -> Doc
  6270. syntax.docSource : [(Either Type Doc.Term, [Doc.Term])]
                           -> Doc
  6271. syntax.docSource.doc : Doc
  6272. syntax.docSourceElement : link
                                  -> annotations
                                  -> (link, annotations)
  6273. syntax.docStrikethrough : Doc -> Doc
  6274. syntax.docTable : [[Doc]] -> Doc
  6275. syntax.docTable.doc : Doc
  6276. syntax.docTooltip : Doc -> Doc -> Doc
  6277. syntax.docTransclude : d -> d
  6278. syntax.docTransclude.doc : Doc
  6279. syntax.docUntitledSection : [Doc] -> Doc
  6280. syntax.docUntitledSection.doc : Doc
  6281. syntax.docVerbatim : Doc -> Doc
  6282. syntax.docVerbatim.doc : Doc
  6283. syntax.docWord : Text -> Doc
  6284. syntax.docWord.doc : Doc
  6285. type system.ANSI.Color
  6286. system.ANSI.Color.Black : Color
  6287. system.ANSI.Color.Blue : Color
  6288. system.ANSI.Color.BrightBlack : Color
  6289. system.ANSI.Color.BrightBlue : Color
  6290. system.ANSI.Color.BrightCyan : Color
  6291. system.ANSI.Color.BrightGreen : Color
  6292. system.ANSI.Color.BrightMagenta : Color
  6293. system.ANSI.Color.BrightRed : Color
  6294. system.ANSI.Color.BrightWhite : Color
  6295. system.ANSI.Color.BrightYellow : Color
  6296. system.ANSI.Color.Cyan : Color
  6297. system.ANSI.Color.doc : Doc
  6298. system.ANSI.Color.Green : Color
  6299. system.ANSI.Color.Magenta : Color
  6300. system.ANSI.Color.Red : Color
  6301. system.ANSI.Color.White : Color
  6302. system.ANSI.Color.Yellow : Color
  6303. type system.ConsoleText
  6304. system.ConsoleText.Background : Color
                                        -> ConsoleText
                                        -> ConsoleText
  6305. system.ConsoleText.Bold : ConsoleText -> ConsoleText
  6306. system.ConsoleText.doc : Doc
  6307. system.ConsoleText.Foreground : Color
                                        -> ConsoleText
                                        -> ConsoleText
  6308. system.ConsoleText.Invert : ConsoleText -> ConsoleText
  6309. system.ConsoleText.Plain : Text -> ConsoleText
  6310. system.ConsoleText.Underline : ConsoleText
                                       -> ConsoleText
  6311. test.arbitrary.floats : Nat ->{Each, Random} Float
  6312. test.arbitrary.floats.doc : Doc
  6313. test.arbitrary.ints : Nat ->{Each, Random} Int
  6314. test.arbitrary.ints.doc : Doc
  6315. test.arbitrary.nats : Nat ->{Each, Random} Nat
  6316. test.arbitrary.nats.doc : Doc
  6317. test.arbitrary.unspecialFloats : Nat
                                         ->{Each, Random} Float
  6318. test.arbitrary.unspecialFloats.doc : Doc
  6319. test.assert : Boolean -> e -> a -> a
  6320. test.assert.doc : Doc
  6321. test.assertEquals : a -> a -> Boolean
  6322. test.assertEquals.doc : Doc
  6323. test.check : Boolean -> [Result]
  6324. test.deprecated.check' : Boolean -> Test
  6325. structural type test.deprecated.Domain a
  6326. test.deprecated.Domain.boolean : Domain Boolean
  6327. test.deprecated.Domain.ints : Domain Int
  6328. test.deprecated.Domain.Large : Weighted a -> Domain a
  6329. test.deprecated.Domain.lift2 : (a -> b -> c)
                                       -> Domain a
                                       -> Domain b
                                       -> Domain c
  6330. test.deprecated.Domain.lists : Domain [()]
  6331. test.deprecated.Domain.listsOf : Domain a -> Domain [a]
  6332. test.deprecated.Domain.map : (a -> b)
                                     -> Domain a
                                     -> Domain b
  6333. test.deprecated.Domain.nats : Domain Nat
  6334. test.deprecated.Domain.pairs : Domain a -> Domain (a, a)
  6335. test.deprecated.Domain.sample : Nat -> Domain a -> [a]
  6336. test.deprecated.Domain.Small : [a] -> Domain a
  6337. test.deprecated.Domain.smallSize : Nat
  6338. test.deprecated.Domain.tuples : Domain a
                                        -> Domain b
                                        -> Domain (Tuple a b)
  6339. test.deprecated.Domain.weighted : Domain a -> Weighted a
  6340. test.deprecated.forAll : Nat
                                 -> Domain a
                                 -> (a ->{e} Boolean)
                                 ->{e} [Result]
  6341. structural ability test.deprecated.Gen
  6342. test.deprecated.Gen.append : '{Gen} a
                                     -> '{Gen} a
                                     -> '{Gen} a
  6343. test.deprecated.Gen.append.doc : Doc
  6344. test.deprecated.Gen.append.examples.ex1 : [Nat]
  6345. test.deprecated.Gen.append.examples.ex2 : [Nat]
  6346. test.deprecated.gen.atLeastOne : '{Gen} a
                                         -> '{Gen} List.Nonempty
                                           a
  6347. test.deprecated.gen.atLeastOne.doc : Doc
  6348. test.deprecated.gen.atLeastOneDistinct : '{Gen} a
                                                 -> '{Gen} List.Nonempty
                                                   a
  6349. test.deprecated.gen.atLeastOneDistinct.doc : Doc
  6350. test.deprecated.gen.boolean : '{Gen} Boolean
  6351. test.deprecated.gen.boolean.doc : Doc
  6352. test.deprecated.gen.Char.alpha : '{Gen} Char
  6353. test.deprecated.gen.Char.alpha.doc : Doc
  6354. test.deprecated.gen.Char.alpha.sampled : [Char]
  6355. test.deprecated.gen.Char.ascii : '{Gen} Char
  6356. test.deprecated.gen.Char.ascii.doc : Doc
  6357. test.deprecated.gen.Char.ascii.sampled : [Char]
  6358. test.deprecated.gen.Char.asciiNonPrintable : '{Gen} Char
  6359. test.deprecated.gen.Char.asciiNonPrintable.doc : Doc
  6360. test.deprecated.gen.Char.asciiNonPrintable.sampled : [Char]
  6361. test.deprecated.gen.Char.asciiPrintable : '{Gen} Char
  6362. test.deprecated.gen.Char.asciiPrintable.doc : Doc
  6363. test.deprecated.gen.Char.asciiPrintable.sampled : [Char]
  6364. test.deprecated.gen.Char.digit : '{Gen} Char
  6365. test.deprecated.gen.Char.digit.doc : Doc
  6366. test.deprecated.gen.Char.digit.sampled : [Char]
  6367. test.deprecated.gen.Char.hexDigit : '{Gen} Char
  6368. test.deprecated.gen.Char.hexDigit.doc : Doc
  6369. test.deprecated.gen.Char.hexDigit.sampled : [Char]
  6370. test.deprecated.gen.Char.lower : '{Gen} Char
  6371. test.deprecated.gen.Char.lower.doc : Doc
  6372. test.deprecated.gen.Char.lower.sampled : [Char]
  6373. test.deprecated.gen.Char.upper : '{Gen} Char
  6374. test.deprecated.gen.Char.upper.doc : Doc
  6375. test.deprecated.gen.Char.upper.sampled : [Char]
  6376. test.deprecated.Gen.cost : Nat -> '{Gen} a -> '{Gen} a
  6377. test.deprecated.Gen.cost.doc : Doc
  6378. test.deprecated.gen.distinctListOf : '{Gen} a
                                             -> '{Gen} [a]
  6379. test.deprecated.gen.distinctListOf.doc : Doc
  6380. test.deprecated.Gen.doc : Doc
  6381. test.deprecated.gen.either : '{Gen} a
                                     -> '{Gen} b
                                     -> '{Gen} Either a b
  6382. test.deprecated.gen.either.doc : Doc
  6383. test.deprecated.gen.either.test : [Result]
  6384. test.deprecated.gen.empty : '{Gen} a
  6385. test.deprecated.gen.empty.doc : Doc
  6386. test.deprecated.gen.float : '{Gen} Float
  6387. test.deprecated.gen.float.doc : Doc
  6388. test.deprecated.gen.functions.logic : '{Gen} (Boolean
                                              -> Boolean
                                              -> Boolean)
  6389. test.deprecated.gen.functions.logic.doc : Doc
  6390. test.deprecated.gen.functions.someOrNone : (a ->{g} b)
                                                   -> b
                                                   -> '{Gen} (Optional
                                                     a
                                                   ->{g} Optional
                                                     b)
  6391. test.deprecated.gen.functions.someOrNone.doc : Doc
  6392. test.deprecated.gen.functions.yesNo : '{Gen} (Boolean
                                              -> Boolean)
  6393. test.deprecated.gen.functions.yesNo.doc : Doc
  6394. test.deprecated.gen.int : '{Gen} Int
  6395. test.deprecated.gen.int.doc : Doc
  6396. test.deprecated.gen.listOf : '{Gen} a -> '{Gen} [a]
  6397. test.deprecated.gen.listOf.doc : Doc
  6398. test.deprecated.gen.mapOf : '{Gen} k
                                    -> '{Gen} v
                                    -> '{Gen} Map k v
  6399. test.deprecated.gen.mapOf.doc : Doc
  6400. test.deprecated.gen.nat : '{Gen} Nat
  6401. test.deprecated.gen.nat.doc : Doc
  6402. test.deprecated.gen.natIn : Nat -> Nat -> '{Gen} Nat
  6403. test.deprecated.gen.natIn.doc : Doc
  6404. test.deprecated.gen.natInOrder : '{Gen} Nat
  6405. test.deprecated.gen.natInOrder.doc : Doc
  6406. test.deprecated.gen.nonzeroNat : '{Gen} Nat
  6407. test.deprecated.gen.nonzeroNat.doc : Doc
  6408. test.deprecated.gen.normalFloat : '{Gen} Float
  6409. test.deprecated.gen.normalFloat.doc : Doc
  6410. test.deprecated.gen.oneOf : [a] -> '{Gen} a
  6411. test.deprecated.gen.oneOf.doc : Doc
  6412. test.deprecated.gen.optional : '{Gen} a
                                       -> '{Gen} Optional a
  6413. test.deprecated.gen.optional.doc : Doc
  6414. test.deprecated.gen.optional.test : [Result]
  6415. test.deprecated.gen.pairOf : '{Gen} a
                                     -> '{Gen} b
                                     -> '{Gen} (a, b)
  6416. test.deprecated.gen.pairOf.doc : Doc
  6417. test.deprecated.gen.pick : ['{Gen} a] -> '{Gen} a
  6418. test.deprecated.gen.pick.doc : Doc
  6419. test.deprecated.gen.positiveInt : '{Gen} Int
  6420. test.deprecated.gen.positiveInt.doc : Doc
  6421. test.deprecated.Gen.runGen : '{g, Gen} a ->{g, Abort} a
  6422. test.deprecated.Gen.runGen.doc : Doc
  6423. test.deprecated.Gen.sample : Weighted a ->{Gen} a
  6424. test.deprecated.Gen.sample.doc : Doc
  6425. test.deprecated.gen.setOf : '{Gen} a -> '{Gen} Set a
  6426. test.deprecated.gen.setOf.doc : Doc
  6427. test.deprecated.Gen.take : Nat
                                   -> '{e, Gen} t
                                   -> '{e, Gen} t
  6428. test.deprecated.Gen.take.doc : Doc
  6429. test.deprecated.gen.Text.ascii : '{Gen} Text
  6430. test.deprecated.gen.Text.ascii.doc : Doc
  6431. test.deprecated.gen.Text.asciiPrintable : '{Gen} Text
  6432. test.deprecated.gen.Text.asciiPrintable.doc : Doc
  6433. test.deprecated.Gen.toWeighted : '{e, Gen} a
                                         ->{e} Weighted a
  6434. test.deprecated.Gen.toWeighted.doc : Doc
  6435. test.deprecated.internals.v1.foldReport : (Trie
                                                    Text Status
                                                  ->{e} r)
                                                  -> Report
                                                  ->{e} r
  6436. test.deprecated.internals.v1.foldScope : ([Text]
                                                 ->{𝕖} r)
                                                 -> Labels
                                                 ->{𝕖} r
  6437. test.deprecated.internals.v1.foldStatus : r
                                                  -> (Success
                                                  ->{𝕖} r)
                                                  -> (Success
                                                  ->{𝕖} r)
                                                  -> r
                                                  -> Status
                                                  ->{𝕖} r
  6438. test.deprecated.internals.v1.foldSuccess : (Nat ->{𝕖} r)
                                                   -> r
                                                   -> Success
                                                   ->{𝕖} r
  6439. test.deprecated.internals.v1.Scope.cons : Text
                                                  -> Labels
                                                  -> Labels
  6440. test.deprecated.internals.v1.Status.combine : Status
                                                      -> Status
                                                      -> Status
  6441. test.deprecated.internals.v1.Status.pending : Status
                                                      -> Status
  6442. test.deprecated.internals.v1.Success.combine : Success
                                                       -> Success
                                                       -> Success
  6443. test.deprecated.internals.v1.Test.failed : Test
  6444. test.deprecated.internals.v1.Test.failedWith : Text
                                                       -> Test
  6445. test.deprecated.internals.v1.Test.finished : Status
                                                     -> Test
  6446. test.deprecated.internals.v1.Test.forAll' : Nat
                                                    -> Domain a
                                                    -> (a
                                                    ->{e} Boolean)
                                                    ->{e} Test
  6447. test.deprecated.internals.v1.Test.label.deprecated : Text
                                                             -> Test
                                                             -> Test
  6448. type test.deprecated.internals.v1.Test.Labels
  6449. test.deprecated.internals.v1.Test.Labels.Labels : [Text]
                                                          -> Labels
  6450. test.deprecated.internals.v1.Test.modifyScope : (Labels
                                                        -> Labels)
                                                        -> Test
                                                        -> Test
  6451. test.deprecated.internals.v1.Test.modifyStatus : (Status
                                                         -> Status)
                                                         -> Test
                                                         -> Test
  6452. test.deprecated.internals.v1.Test.passed : Test
  6453. test.deprecated.internals.v1.Test.passedUnexpectedly : Test
  6454. test.deprecated.internals.v1.Test.passedWith : Text
                                                       -> Test
  6455. test.deprecated.internals.v1.Test.pending : Test -> Test
  6456. test.deprecated.internals.v1.Test.provedUnexpectedly : Test
  6457. test.deprecated.internals.v1.Test.provedWith : Text
                                                       -> Test
  6458. structural type test.deprecated.internals.v1.Test.Report
  6459. test.deprecated.internals.v1.Test.report : Test
                                                   -> Report
  6460. test.deprecated.internals.v1.Test.Report.combine : Report
                                                           -> Report
                                                           -> Report
  6461. test.deprecated.internals.v1.Test.Report.empty : Report
  6462. test.deprecated.internals.v1.Test.Report.Report : Trie
                                                            Text
                                                            Status
                                                          -> Report
  6463. test.deprecated.internals.v1.Test.Report.toCLIResult : Report
                                                               -> [Result]
  6464. test.deprecated.internals.v1.Test.run : Test -> [Result]
  6465. structural type test.deprecated.internals.v1.Test.Status
  6466. test.deprecated.internals.v1.Test.Status.Expected : Success
                                                            -> Status
  6467. test.deprecated.internals.v1.Test.Status.Failed : Status
  6468. test.deprecated.internals.v1.Test.Status.Pending : Status
  6469. test.deprecated.internals.v1.Test.Status.Unexpected : Success
                                                              -> Status
  6470. structural type test.deprecated.internals.v1.Test.Success
  6471. test.deprecated.internals.v1.Test.Success.Passed : Nat
                                                           -> Success
  6472. test.deprecated.internals.v1.Test.Success.Proved : Success
  6473. test.deprecated.laws.absorption : '{Gen} a
                                          -> (a ->{e} a ->{e} a)
                                          -> (a ->{e} a ->{e} a)
                                          ->{e, Gen} Test
  6474. test.deprecated.laws.absorption.doc : Doc
  6475. test.deprecated.laws.adjoint : '{Gen} o
                                       -> (o ->{g1} o ->{g2} t)
                                       -> (o ->{g3} o ->{g4} o)
                                       -> (o ->{g5} o ->{g6} o)
                                       ->{g1,
                                       g2,
                                       g3,
                                       g4,
                                       g5,
                                       g6,
                                       Gen} Test
  6476. test.deprecated.laws.adjoint.doc : Doc
  6477. test.deprecated.laws.associative : '{Gen} a
                                           -> (a
                                           ->{e} a
                                           ->{e} a)
                                           ->{e, Gen} Test
  6478. test.deprecated.laws.associative.doc : Doc
  6479. test.deprecated.laws.commutative : '{Gen} a
                                           -> (a
                                           ->{e} a
                                           ->{e} b)
                                           ->{e, Gen} Test
  6480. test.deprecated.laws.commutative.doc : Doc
  6481. test.deprecated.laws.distributive : '{Gen} a
                                            -> (a
                                            ->{e} a
                                            ->{e} a)
                                            -> (a
                                            ->{e} a
                                            ->{e} a)
                                            ->{e, Gen} Test
  6482. test.deprecated.laws.distributive.doc : Doc
  6483. test.deprecated.laws.homomorphism : '{Gen} a
                                            -> (a ->{e} b)
                                            -> (a
                                            ->{e} a
                                            ->{e} a)
                                            -> (b
                                            ->{e} b
                                            ->{e} b)
                                            ->{e, Gen} Test
  6484. test.deprecated.laws.homomorphism.doc : Doc
  6485. test.deprecated.laws.idempotence : '{Gen} a
                                           -> (a
                                           ->{e} a
                                           ->{e} a)
                                           ->{e, Gen} Test
  6486. test.deprecated.laws.idempotence.doc : Doc
  6487. test.deprecated.laws.lattice : '{Gen} a
                                       -> (a ->{e} a ->{e} a)
                                       -> (a ->{e} a ->{e} a)
                                       ->{e, Gen} Test
  6488. test.deprecated.laws.lattice.doc : Doc
  6489. test.deprecated.laws.reflexive : '{Gen} a
                                         -> (a
                                         ->{e} a
                                         ->{e} Boolean)
                                         ->{e, Gen} Test
  6490. test.deprecated.laws.reflexive.doc : Doc
  6491. test.deprecated.laws.transitive : '{Gen} a
                                          -> (a
                                          ->{e} a
                                          ->{e} Boolean)
                                          ->{e, Gen} Test
  6492. test.deprecated.laws.transitive.doc : Doc
  6493. test.deprecated.prove : '{e, Gen} Test ->{e} [Result]
  6494. test.deprecated.prove.doc : Doc
  6495. test.deprecated.run : Test -> [Result]
  6496. test.deprecated.run.doc : Doc
  6497. test.deprecated.runAll : [Test] -> [Result]
  6498. test.deprecated.runAll.doc : Doc
  6499. test.deprecated.runs : Nat
                               -> '{e, Gen} Test
                               ->{e} [Result]
  6500. test.deprecated.runs.doc : Doc
  6501. test.deprecated.sample : Nat -> '{e, Gen} a ->{e} [a]
  6502. test.deprecated.sample.doc : Doc
  6503. structural type test.deprecated.Test
  6504. test.deprecated.Test.both : Test -> Test -> Test
  6505. test.deprecated.Test.both.doc : Doc
  6506. test.deprecated.Test.expect : Boolean -> Test
  6507. test.deprecated.Test.expect.doc : Doc
  6508. test.deprecated.Test.fail : Test
  6509. test.deprecated.Test.fail.doc : Doc
  6510. test.deprecated.Test.failWith : Text -> Test
  6511. test.deprecated.Test.failWith.doc : Doc
  6512. test.deprecated.Test.label.deprecated : Text
                                                -> Test
                                                -> Test
  6513. test.deprecated.Test.label.deprecated.doc : Doc
  6514. test.deprecated.Test.ok : Test
  6515. test.deprecated.Test.ok.doc : Doc
  6516. test.deprecated.Test.okWith : Text -> Test
  6517. test.deprecated.Test.okWith.doc : Doc
  6518. test.deprecated.Test.pass : Nat -> Test
  6519. test.deprecated.Test.pass.doc : Doc
  6520. test.deprecated.Test.proved : Test
  6521. test.deprecated.Test.proved.doc : Doc
  6522. test.deprecated.Test.provedWith : Text -> Test
  6523. test.deprecated.Test.provedWith.doc : Doc
  6524. test.deprecated.Test.Test : (Labels -> Report) -> Test
  6525. test.deprecated.Test.tests : [Test] -> Test
  6526. test.deprecated.Test.unexpected.ok : Test
  6527. test.deprecated.Test.unexpected.ok.doc : Doc
  6528. test.deprecated.Test.unexpected.proven : Test
  6529. test.deprecated.Test.unexpected.proven.doc : Doc
  6530. test.deprecated.verifyAndIgnore : '{g,
                                          Exception,
                                          Each,
                                          Random,
                                          Label} a
                                          ->{g} [Result]
  6531. test.deprecated.verifyAndIgnore.doc : Doc
  6532. test.deprecated.verifyWithSeedAndIgnore : Nat
                                                  -> '{g,
                                                  Exception,
                                                  Each,
                                                  Random,
                                                  Label} a
                                                  ->{g} [Result]
  6533. test.deprecated.verifyWithSeedAndIgnore.doc : Doc
  6534. test.ensure : Boolean ->{Exception} ()
  6535. test.ensure.doc : Doc
  6536. test.ensureEqual : a -> a ->{Exception} ()
  6537. test.ensureEqual.doc : Doc
  6538. test.ensureGreater : x -> x ->{Exception} ()
  6539. test.ensureGreater.doc : Doc
  6540. test.ensureGreaterOrEqual : x -> x ->{Exception} ()
  6541. test.ensureGreaterOrEqual.doc : Doc
  6542. test.ensureLess : x -> x ->{Exception} ()
  6543. test.ensureLess.doc : Doc
  6544. test.ensureLessOrEqual : x -> x ->{Exception} ()
  6545. test.ensureLessOrEqual.doc : Doc
  6546. test.ensureNotEqual : a -> a ->{Exception} ()
  6547. test.ensureNotEqual.doc : Doc
  6548. test.ensureWith : a -> Boolean ->{Exception} ()
  6549. test.ensureWith.doc : Doc
  6550. test.ensuring : '{g} Boolean ->{g, Exception} ()
  6551. test.ensuring.doc : Doc
  6552. test.ensuringWith : Text
                            -> a
                            -> '{g} Boolean
                            ->{g, Exception} ()
  6553. test.ensuringWith.doc : Doc
  6554. test.laws.abelianGroup : '{Each, Random} t
                                 -> (t ->{e} t ->{e1} t)
                                 -> t
                                 -> (t ->{e2} t)
                                 ->{e2,
                                 e1,
                                 e,
                                 Exception,
                                 Each,
                                 Random,
                                 Label} ()
  6555. test.laws.abelianGroup.doc : Doc
  6556. test.laws.absorption : '{Each, Random} a
                               -> (a ->{e} a ->{e} a)
                               -> (a ->{e} a ->{e} a)
                               ->{e,
                               Exception,
                               Each,
                               Random,
                               Label} ()
  6557. test.laws.absorption.doc : Doc
  6558. test.laws.associativity : '{Each, Random} a
                                  -> (a ->{e} a ->{e} a)
                                  ->{e,
                                  Exception,
                                  Each,
                                  Random,
                                  Label} ()
  6559. test.laws.associativity.doc : Doc
  6560. test.laws.commutativity : '{Each, Random} a
                                  -> (a ->{e} a ->{e} a)
                                  ->{e,
                                  Exception,
                                  Each,
                                  Random,
                                  Label} ()
  6561. test.laws.commutativity.doc : Doc
  6562. test.laws.distributivity : '{Each, Random} a
                                   -> (a ->{e} a ->{e} a)
                                   -> (a ->{e} a ->{e} a)
                                   ->{e,
                                   Exception,
                                   Each,
                                   Random,
                                   Label} ()
  6563. test.laws.distributivity.doc : Doc
  6564. test.laws.group : '{Each, Random} t
                          -> (t ->{e} t ->{e1} t)
                          -> t
                          -> (t ->{e2} t)
                          ->{e2,
                          e1,
                          e,
                          Exception,
                          Each,
                          Random,
                          Label} ()
  6565. test.laws.group.doc : Doc
  6566. test.laws.homomorphism : '{Each, Random} a
                                 -> (a ->{e} a ->{e} a)
                                 -> (b ->{e} b ->{e} b)
                                 -> (a ->{e} b)
                                 ->{e,
                                 Exception,
                                 Each,
                                 Random,
                                 Label} ()
  6567. test.laws.homomorphism.doc : Doc
  6568. test.laws.idempotence : '{Each, Random} a
                                -> (a ->{e} a)
                                ->{e,
                                Exception,
                                Each,
                                Random,
                                Label} ()
  6569. test.laws.idempotence.doc : Doc
  6570. test.laws.identity : '{Each, Random} a
                             -> (a ->{e} a ->{e} a)
                             -> a
                             ->{e,
                             Exception,
                             Each,
                             Random,
                             Label} ()
  6571. test.laws.identity.doc : Doc
  6572. test.laws.involutive : '{Each, Random} a
                               -> (a ->{e} a)
                               ->{e,
                               Exception,
                               Each,
                               Random,
                               Label} ()
  6573. test.laws.involutive.doc : Doc
  6574. test.laws.lattice : '{Each, Random} a
                            -> (a ->{e} a ->{e} a)
                            -> (a ->{e} a ->{e} a)
                            ->{e,
                            Exception,
                            Each,
                            Random,
                            Label} ()
  6575. test.laws.lattice.doc : Doc
  6576. test.laws.monoid : '{Each, Random} t
                           -> (t ->{e} t ->{e1} t)
                           -> t
                           ->{e1,
                           e,
                           Exception,
                           Each,
                           Random,
                           Label} ()
  6577. test.laws.monoid.doc : Doc
  6578. test.laws.reflexivity : '{Each, Random} a
                                -> (a ->{e} a ->{e} Boolean)
                                ->{e,
                                Exception,
                                Each,
                                Random,
                                Label} ()
  6579. test.laws.reflexivity.doc : Doc
  6580. test.laws.ring : '{Each, Random} t
                         -> (t ->{e4} t ->{e3} t)
                         -> t
                         -> (t ->{e2} t)
                         -> (t ->{e1} t ->{e} t)
                         -> t
                         ->{e4,
                         e3,
                         e2,
                         e1,
                         e,
                         Exception,
                         Each,
                         Random,
                         Label} ()
  6581. test.laws.ring.doc : Doc
  6582. test.laws.transitivity : '{Each, Random} a
                                 -> (a ->{e} a ->{e} Boolean)
                                 ->{e,
                                 Exception,
                                 Each,
                                 Random,
                                 Label} ()
  6583. test.laws.transitivity.doc : Doc
  6584. test.raiseFailure : Text -> a ->{Exception} x
  6585. test.raiseFailure.doc : Doc
  6586. type test.Result
  6587. test.Result.doc : Doc
  6588. test.Result.Fail : Text -> Result
  6589. test.Result.Fail.doc : Doc
  6590. test.Result.firstFailure : [Result] -> Text
  6591. test.Result.firstFailure.doc : Doc
  6592. test.Result.isOk : Result -> Boolean
  6593. test.Result.isOk.doc : Doc
  6594. test.Result.Ok : Text -> Result
  6595. test.Result.Ok.doc : Doc
  6596. test.Result.text : Result -> Text
  6597. test.Result.text.doc : Doc
  6598. type test.TestFailure
  6599. test.TestFailure.doc : Doc
  6600. test.verify : '{g, Exception, Each, Random, Label} ()
                      ->{g} [Result]
  6601. test.verify.doc : Doc
  6602. test.verifyWithSeed : Nat
                              -> '{g,
                              Exception,
                              Each,
                              Random,
                              Label} ()
                              ->{g} [Result]
  6603. test.verifyWithSeed.doc : Doc
  6604. tests.catchArithmeticFailure : '{IO, Exception} [Result]
  6605. tests.catchBug : '{IO, Exception} [Result]
  6606. tests.catchKill : '{IO, Exception} [Result]
  6607. builtin type Text
  6608. Text.!= : Text -> Text -> Boolean
  6609. Text.!=.doc : Doc
  6610. Text.++ : Text -> Text -> Text
  6611. Text.< : Text -> Text -> Boolean
  6612. Text.<.doc : Doc
  6613. Text.<= : Text -> Text -> Boolean
  6614. Text.<=.doc : Doc
  6615. Text.== : Text -> Text -> Boolean
  6616. Text.==.doc : Doc
  6617. Text.> : Text -> Text -> Boolean
  6618. Text.>.doc : Doc
  6619. Text.>= : Text -> Text -> Boolean
  6620. Text.>=.doc : Doc
  6621. Text.alignCenterWith : Nat -> Char -> Text -> Text
  6622. Text.alignCenterWith.doc : Doc
  6623. Text.alignCenterWith.test : [Result]
  6624. Text.alignLeftWith : Nat -> Char -> Text -> Text
  6625. Text.alignLeftWith.doc : Doc
  6626. Text.alignRightWith : Nat -> Char -> Text -> Text
  6627. Text.alignRightWith.doc : Doc
  6628. Text.allSplits : Text -> [(Text, Text)]
  6629. Text.allSplits.doc : Doc
  6630. Text.break : (Char ->{g} Boolean)
                     -> Text
                     ->{g} (Text, Text)
  6631. Text.break.doc : Doc
  6632. Text.captureAll : Pattern Text -> Text -> [Text]
  6633. Text.captureAll.doc : Doc
  6634. Text.captureAllWith : ([Text] ->{g} a)
                              -> Pattern Text
                              -> Text
                              ->{g} [a]
  6635. Text.captureAllWith.doc : Doc
  6636. Text.capturePatternsWith : [( ([Text] ->{g} a),
                                     Pattern Text)]
                                   -> Text
                                   ->{g} [a]
  6637. Text.capturePatternsWith.doc : Doc
  6638. Text.charAt : Nat -> Text -> Optional Char
  6639. Text.charAt.doc : Doc
  6640. Text.charAt.tests : [Result]
  6641. Text.chunk : Nat -> Text -> [Text]
  6642. Text.chunk.doc : Doc
  6643. Text.codePoints : Text -> [Nat]
  6644. Text.codePoints.doc : Doc
  6645. Text.cons : Char -> Text -> Text
  6646. Text.cons.doc : Doc
  6647. Text.cons.tests : [Result]
  6648. Text.contains : Text -> Text -> Boolean
  6649. Text.contains.doc : Doc
  6650. Text.crlfToLf : Text -> Text
  6651. Text.crlfToLf.doc : Doc
  6652. Text.doc : Doc
  6653. Text.drop : Nat -> Text -> Text
  6654. Text.drop.doc : Doc
  6655. Text.dropRightWhile : (Char ->{g} Boolean)
                              -> Text
                              ->{g} Text
  6656. Text.dropRightWhile.doc : Doc
  6657. Text.dropUntil : (Char ->{e} Boolean) -> Text ->{e} Text
  6658. Text.dropUntil.doc : Doc
  6659. Text.dropWhile : (Char ->{g} Boolean) -> Text ->{g} Text
  6660. Text.dropWhile.doc : Doc
  6661. Text.empty : Text
  6662. Text.empty.doc : Doc
  6663. Text.endsWith : Text -> Text -> Boolean
  6664. Text.endsWith.doc : Doc
  6665. Text.eq : Text -> Text -> Boolean
  6666. Text.eq.doc : Doc
  6667. Text.filter : (Char ->{g} Boolean) -> Text ->{g} Text
  6668. Text.filter.doc : Doc
  6669. Text.findFirst : Class -> Text -> (Text, Text)
  6670. Text.findFirst.doc : Doc
  6671. Text.findFirstIndex : Class -> Text -> Nat
  6672. Text.findFirstIndex.doc : Doc
  6673. Text.findLast : Class -> Text -> (Text, Text)
  6674. Text.findLast.doc : Doc
  6675. Text.findLastIndex : Class -> Text -> Nat
  6676. Text.findLastIndex.doc : Doc
  6677. Text.flatMap : (Char ->{g} Text) -> Text ->{g} Text
  6678. Text.flatMap.doc : Doc
  6679. Text.flatMapRight : (Char ->{g} Text) -> Text ->{g} Text
  6680. Text.flatMapRight.doc : Doc
  6681. Text.fromAscii : Bytes -> Text
  6682. Text.fromAscii.doc : Doc
  6683. Text.fromCharList : [Char] -> Text
  6684. Text.fromCharList.doc : Doc
  6685. Text.fromSet : Set Char -> Text
  6686. Text.fromSet.doc : Doc
  6687. Text.fromUtf8 : Bytes ->{Exception} Text
  6688. Text.fromUtf8.doc : Doc
  6689. Text.fromUtf8.impl : Bytes -> Either Failure Text
  6690. Text.fromUtf8.partial : Bytes
                                ->{Exception} (Text, Bytes)
  6691. Text.fromUtf8.partial.doc : Doc
  6692. Text.fromUtf8.partial.tests : [Result]
  6693. Text.fromUtf8.stream : '{g, Stream Bytes} r
                               -> '{g, Exception, Stream Text} r
  6694. Text.fromUtf8.stream.doc : Doc
  6695. Text.fromUtf8.stream.tests.invalidUtf8 : [Result]
  6696. Text.fromUtf8.stream.tests.success : [Result]
  6697. Text.fromUtf8.stream! : '{g, Stream Bytes} r
                                ->{g, Exception, Stream Text} r
  6698. Text.fromUtf8.stream!.doc : Doc
  6699. Text.gt : Text -> Text -> Boolean
  6700. Text.gt.doc : Doc
  6701. Text.gteq : Text -> Text -> Boolean
  6702. Text.gteq.doc : Doc
  6703. Text.head : Text -> Optional Char
  6704. Text.head.doc : Doc
  6705. Text.head.tests : [Result]
  6706. Text.indexOf : Text -> Text -> Optional Nat
  6707. Text.indexOf.doc : Doc
  6708. Text.indexOf.tests.infix : [Result]
  6709. Text.isEmpty : Text -> Boolean
  6710. Text.isEmpty.doc : Doc
  6711. Text.join : Text -> [Text] -> Text
  6712. Text.join.doc : Doc
  6713. Text.join.tests.ex1 : [Result]
  6714. Text.leftPad : Nat -> Text -> Text -> Text
  6715. Text.leftPad.doc : Doc
  6716. Text.lfToCrlf : Text -> Text
  6717. Text.lfToCrlf.doc : Doc
  6718. Text.lines : Text -> [Text]
  6719. Text.lines.doc : Doc
  6720. Text.lines.tests.empty : [Result]
  6721. Text.lines.tests.leading : [Result]
  6722. Text.lines.tests.multi : [Result]
  6723. Text.lines.tests.single : [Result]
  6724. Text.lines.tests.trailing : [Result]
  6725. Text.lt : Text -> Text -> Boolean
  6726. Text.lt.doc : Doc
  6727. Text.lteq : Text -> Text -> Boolean
  6728. Text.lteq.doc : Doc
  6729. Text.map : (Char ->{g} Char) -> Text ->{g} Text
  6730. Text.map.doc : Doc
  6731. Text.neq : Text -> Text -> Boolean
  6732. Text.neq.doc : Doc
  6733. Text.nonempty : Text -> Optional Text
  6734. Text.nonempty.doc : Doc
  6735. Text.patterns.anyChar : Pattern Text
  6736. Text.patterns.anyChar.doc : Doc
  6737. Text.patterns.anyChar.test : [Result]
  6738. Text.patterns.asciiLetter : Pattern Text
  6739. Text.patterns.asciiLetter.doc : Doc
  6740. Text.patterns.asciiLetter.test : [Result]
  6741. Text.patterns.captureWithin : Text
                                      -> Text
                                      -> Pattern Text
  6742. Text.patterns.captureWithin.doc : Doc
  6743. Text.patterns.char : Class -> Pattern Text
  6744. Text.patterns.char.doc : Doc
  6745. Text.patterns.char.tests.alphanumeric : [Result]
  6746. Text.patterns.char.tests.and : [Result]
  6747. Text.patterns.char.tests.not : [Result]
  6748. Text.patterns.char.tests.or : [Result]
  6749. Text.patterns.charIn : [Char] -> Pattern Text
  6750. Text.patterns.charIn.doc : Doc
  6751. Text.patterns.charRange : Char -> Char -> Pattern Text
  6752. Text.patterns.charRange.doc : Doc
  6753. Text.patterns.chars : Text -> Pattern Text
  6754. Text.patterns.chars.doc : Doc
  6755. Text.patterns.charUntil : Class -> Text -> Pattern Text
  6756. Text.patterns.charUntil.doc : Doc
  6757. Text.patterns.digit : Pattern Text
  6758. Text.patterns.digit.doc : Doc
  6759. Text.patterns.eof : Pattern Text
  6760. Text.patterns.eof.doc : Doc
  6761. Text.patterns.hexDigit : Pattern Text
  6762. Text.patterns.hexDigit.doc : Doc
  6763. Text.patterns.isFullMatch : Pattern Text
                                    -> Text
                                    -> Boolean
  6764. Text.patterns.isFullMatch.doc : Doc
  6765. Text.patterns.letter : Pattern Text
  6766. Text.patterns.letter.doc : Doc
  6767. Text.patterns.literal : Text -> Pattern Text
  6768. Text.patterns.literal.doc : Doc
  6769. Text.patterns.notCharIn : [Char] -> Pattern Text
  6770. Text.patterns.notCharIn.doc : Doc
  6771. Text.patterns.notCharRange : Char
                                     -> Char
                                     -> Pattern Text
  6772. Text.patterns.notCharRange.doc : Doc
  6773. Text.patterns.notChars : Text -> Pattern Text
  6774. Text.patterns.notChars.doc : Doc
  6775. Text.patterns.punctuation : Pattern Text
  6776. Text.patterns.punctuation.doc : Doc
  6777. Text.patterns.space : Pattern Text
  6778. Text.patterns.space.doc : Doc
  6779. Text.patterns.wordChar : Pattern Text
  6780. Text.patterns.wordChar.doc : Doc
  6781. Text.repeat : Nat -> Text -> Text
  6782. Text.repeat.doc : Doc
  6783. Text.replaceAll : Text -> Text -> Text -> Text
  6784. Text.replaceAll.doc : Doc
  6785. Text.replaceAll.tests : [Result]
  6786. Text.reverse : Text -> Text
  6787. Text.reverse.doc : Doc
  6788. Text.reverse.tests.homomorphism : [Result]
  6789. Text.reverse.tests.isomorphism : [Result]
  6790. Text.segmentBy : (Char ->{e} Boolean)
                         -> Text
                         ->{e} [Text]
  6791. Text.segmentBy.doc : Doc
  6792. Text.size : Text -> Nat
  6793. Text.size.doc : Doc
  6794. Text.slice : Nat -> Nat -> Text -> Text
  6795. Text.slice.doc : Doc
  6796. Text.slice.tests.example1 : [Result]
  6797. Text.slice.tests.example2 : [Result]
  6798. Text.slice.tests.largeEnd : [Result]
  6799. Text.slice.tests.largeStart : [Result]
  6800. Text.snoc : Text -> Char -> Text
  6801. Text.snoc.doc : Doc
  6802. Text.split : Char -> Text -> [Text]
  6803. Text.split.doc : Doc
  6804. Text.split.examples.ex1 : [Text]
  6805. Text.split.examples.ex2 : [Text]
  6806. Text.split.test : [Result]
  6807. Text.splitAt : Nat -> Text -> (Text, Text)
  6808. Text.splitAt.doc : Doc
  6809. Text.splitOn : Class -> Text -> [Text]
  6810. Text.splitOn.doc : Doc
  6811. Text.splitOnNewline : Text -> [Text]
  6812. Text.splitOnNewline.doc : Doc
  6813. Text.splitOnPattern : Pattern Text -> Text -> [Text]
  6814. Text.splitOnPattern.doc : Doc
  6815. Text.splitOnText : Text -> Text -> [Text]
  6816. Text.splitOnText.doc : Doc
  6817. Text.startsWith : Text -> Text -> Boolean
  6818. Text.startsWith.doc : Doc
  6819. Text.startsWith.tests.isPrefix : [Result]
  6820. Text.substitute : ([Text] ->{g} Text)
                          -> Pattern Text
                          -> Text
                          ->{g} Text
  6821. Text.substitute.doc : Doc
  6822. Text.substituteAll : Pattern Text
                             -> ([Text] ->{g} Text)
                             -> Text
                             ->{g} Text
  6823. Text.substituteAll.doc : Doc
  6824. Text.substituteMany : ([Text] ->{g} Text)
                              -> Pattern Text
                              -> Text
                              ->{g} Text
  6825. Text.substituteMany.doc : Doc
  6826. Text.take : Nat -> Text -> Text
  6827. Text.take.doc : Doc
  6828. Text.takeRightWhile : (Char ->{g} Boolean)
                              -> Text
                              ->{g} Text
  6829. Text.takeRightWhile.doc : Doc
  6830. Text.takeUntil : (Char ->{e} Boolean) -> Text ->{e} Text
  6831. Text.takeUntil.doc : Doc
  6832. Text.takeWhile : (Char ->{e} Boolean) -> Text ->{e} Text
  6833. Text.takeWhile.doc : Doc
  6834. Text.takeWhile.tests.allMatch : [Result]
  6835. Text.takeWhile.tests.isLongestPrefix : [Result]
  6836. Text.takeWhile.tests.isPrefix : [Result]
  6837. Text.toBag : Text -> Bag Char
  6838. Text.toBag.doc : Doc
  6839. Text.toCharList : Text -> [Char]
  6840. Text.toCharList.doc : Doc
  6841. Text.toDoc : Text -> Doc
  6842. Text.toDoc.doc : Doc
  6843. Text.toInt : Text -> Optional Int
  6844. Text.toInt.doc : Doc
  6845. Text.toLowercase : Text -> Text
  6846. Text.toLowercase.doc : Doc
  6847. Text.toNat : Text -> Optional Nat
  6848. Text.toNat.doc : Doc
  6849. Text.toSet : Text -> Set Char
  6850. Text.toSet.doc : Doc
  6851. Text.toStream : Text ->{Stream Char} ()
  6852. Text.toStream.doc : Doc
  6853. Text.toUppercase : Text -> Text
  6854. Text.toUppercase.doc : Doc
  6855. Text.toUtf8 : Text -> Bytes
  6856. Text.toUtf8.doc : Doc
  6857. Text.trim : Text -> Text
  6858. Text.trim.doc : Doc
  6859. Text.trim.tests.all : [Result]
  6860. Text.trim.tests.edges : [Result]
  6861. Text.trim.tests.none : [Result]
  6862. Text.uncons : Text -> Optional (Char, Text)
  6863. Text.uncons.doc : Doc
  6864. Text.uncons.tests : [Result]
  6865. Text.unlines : [Text] -> Text
  6866. Text.unlines.doc : Doc
  6867. Text.unlines.roundtrip : [Result]
  6868. Text.unlines.tests.empty : [Result]
  6869. Text.unlines.tests.leading : [Result]
  6870. Text.unlines.tests.multi : [Result]
  6871. Text.unlines.tests.single : [Result]
  6872. Text.unlines.tests.trailing : [Result]
  6873. Text.unsnoc : Text -> Optional (Text, Char)
  6874. Text.unsnoc.doc : Doc
  6875. Text.unwords : [Text] -> Text
  6876. Text.unwords.doc : Doc
  6877. Text.unwords.test : [Result]
  6878. Text.words : Text -> [Text]
  6879. Text.words.doc : Doc
  6880. Text.words.test : [Result]
  6881. time.Clock.internals.monotonic.impl : '{IO} Either
                                                Failure TimeSpec
  6882. time.Clock.internals.processCPUTime.impl : '{IO} Either
                                                     Failure
                                                     TimeSpec
  6883. time.Clock.internals.realtime.impl : '{IO} Either
                                               Failure TimeSpec
  6884. time.Clock.internals.systemTimeZone.impl : Int
                                                   ->{IO} ( Int,
                                                     Nat,
                                                     Text)
  6885. time.Clock.internals.threadCPUTime.impl : '{IO} Either
                                                    Failure
                                                    TimeSpec
  6886. builtin type time.Clock.internals.TimeSpec
  6887. time.Clock.internals.TimeSpec.nsec : TimeSpec -> Nat
  6888. time.Clock.internals.TimeSpec.sec : TimeSpec -> Int
  6889. time.Clock.monotonic : '{IO, Exception} Duration
  6890. time.Clock.monotonic.doc : Doc
  6891. time.Clock.processCPUTime : '{IO, Exception} Duration
  6892. time.Clock.processCPUTime.doc : Doc
  6893. time.Clock.realtime : '{IO, Exception} Instant
  6894. time.Clock.realtime.doc : Doc
  6895. time.Clock.threadCPUTime : '{IO, Exception} Duration
  6896. time.Clock.threadCPUTime.doc : Doc
  6897. time.Clock.timeSinceEpoch : '{IO, Exception} Duration
  6898. time.Clock.timeSinceEpoch.doc : Doc
  6899. type time.DayOfWeek
  6900. time.DayOfWeek.daysSinceSat : DayOfWeek -> Nat
  6901. time.DayOfWeek.daysSinceSat.doc : Doc
  6902. time.DayOfWeek.doc : Doc
  6903. time.DayOfWeek.Fri : DayOfWeek
  6904. time.DayOfWeek.fromName : Text -> Optional DayOfWeek
  6905. time.DayOfWeek.fromName.doc : Doc
  6906. time.DayOfWeek.isWeekday : DayOfWeek -> Boolean
  6907. time.DayOfWeek.isWeekday.doc : Doc
  6908. time.DayOfWeek.isWeekend : DayOfWeek -> Boolean
  6909. time.DayOfWeek.isWeekend.doc : Doc
  6910. time.DayOfWeek.Mon : DayOfWeek
  6911. time.DayOfWeek.name : DayOfWeek -> Text
  6912. time.DayOfWeek.name.doc : Doc
  6913. time.DayOfWeek.next : DayOfWeek -> DayOfWeek
  6914. time.DayOfWeek.next.doc : Doc
  6915. time.DayOfWeek.number : Nat -> DayOfWeek
  6916. time.DayOfWeek.number.doc : Doc
  6917. time.DayOfWeek.previous : DayOfWeek -> DayOfWeek
  6918. time.DayOfWeek.previous.doc : Doc
  6919. time.DayOfWeek.Sat : DayOfWeek
  6920. time.DayOfWeek.shortName : DayOfWeek -> Text
  6921. time.DayOfWeek.shortName.doc : Doc
  6922. time.DayOfWeek.Sun : DayOfWeek
  6923. time.DayOfWeek.Thu : DayOfWeek
  6924. time.DayOfWeek.Tue : DayOfWeek
  6925. time.DayOfWeek.Wed : DayOfWeek
  6926. type time.Duration
  6927. time.Duration.!= : Duration -> Duration -> Boolean
  6928. time.Duration.* : Int -> Duration -> Duration
  6929. time.Duration.*.doc : Doc
  6930. time.Duration.+ : Duration -> Duration -> Duration
  6931. time.Duration.+.doc : Doc
  6932. time.Duration.- : Duration -> Duration -> Duration
  6933. time.Duration.-.doc : Doc
  6934. time.Duration./ : Duration -> Int -> Duration
  6935. time.Duration./.doc : Doc
  6936. time.Duration.< : Duration -> Duration -> Boolean
  6937. time.Duration.<.doc : Doc
  6938. time.Duration.<= : Duration -> Duration -> Boolean
  6939. time.Duration.<=.doc : Doc
  6940. time.Duration.== : Duration -> Duration -> Boolean
  6941. time.Duration.> : Duration -> Duration -> Boolean
  6942. time.Duration.>.doc : Doc
  6943. time.Duration.>= : Duration -> Duration -> Boolean
  6944. time.Duration.>=.doc : Doc
  6945. time.Duration.abs : Duration -> Duration
  6946. time.Duration.abs.doc : Doc
  6947. time.Duration.asDays : Duration -> Float
  6948. time.Duration.asDays.doc : Doc
  6949. time.Duration.asHours : Duration -> Float
  6950. time.Duration.asHours.doc : Doc
  6951. time.Duration.asJulianYears : Duration -> Float
  6952. time.Duration.asJulianYears.doc : Doc
  6953. time.Duration.asMicroseconds : Duration -> Float
  6954. time.Duration.asMicroseconds.doc : Doc
  6955. time.Duration.asMilliseconds : Duration -> Float
  6956. time.Duration.asMilliseconds.doc : Doc
  6957. time.Duration.asMinutes : Duration -> Float
  6958. time.Duration.asMinutes.doc : Doc
  6959. time.Duration.asNanoseconds : Duration -> Int
  6960. time.Duration.asNanoseconds.doc : Doc
  6961. time.Duration.asSeconds : Duration -> Float
  6962. time.Duration.asSeconds.doc : Doc
  6963. time.Duration.asSeconds.tests.test1 : [Result]
  6964. time.Duration.asWeeks : Duration -> Float
  6965. time.Duration.asWeeks.doc : Doc
  6966. time.Duration.asYears : Duration -> Float
  6967. time.Duration.asYears.doc : Doc
  6968. time.Duration.averageMonth : Duration
  6969. time.Duration.averageMonth.doc : Doc
  6970. time.Duration.averageMonths : Int -> Duration
  6971. time.Duration.averageMonths.doc : Doc
  6972. time.Duration.averageYear : Duration
  6973. time.Duration.averageYear.doc : Doc
  6974. time.Duration.averageYears : Int -> Duration
  6975. time.Duration.averageYears.doc : Doc
  6976. time.Duration.between : Instant -> Instant -> Duration
  6977. time.Duration.between.doc : Doc
  6978. time.Duration.compare : Duration -> Duration -> Ordering
  6979. time.Duration.compare.doc : Doc
  6980. time.Duration.countDays : Duration -> Int
  6981. time.Duration.countDays.doc : Doc
  6982. time.Duration.countHours : Duration -> Int
  6983. time.Duration.countHours.doc : Doc
  6984. time.Duration.countJulianYears : Duration -> Int
  6985. time.Duration.countJulianYears.doc : Doc
  6986. time.Duration.countMicroseconds : Duration -> Int
  6987. time.Duration.countMicroseconds.doc : Doc
  6988. time.Duration.countMilliseconds : Duration -> Int
  6989. time.Duration.countMilliseconds.doc : Doc
  6990. time.Duration.countMinutes : Duration -> Int
  6991. time.Duration.countMinutes.doc : Doc
  6992. time.Duration.countSeconds : Duration -> Int
  6993. time.Duration.countSeconds.doc : Doc
  6994. time.Duration.countWeeks : Duration -> Int
  6995. time.Duration.countWeeks.doc : Doc
  6996. time.Duration.countYears : Duration -> Int
  6997. time.Duration.countYears.doc : Doc
  6998. time.Duration.day : Duration
  6999. time.Duration.day.doc : Doc
  7000. time.Duration.days : Int -> Duration
  7001. time.Duration.days.doc : Doc
  7002. time.Duration.div : Duration -> Int -> Duration
  7003. time.Duration.div.doc : Doc
  7004. time.Duration.doc : Doc
  7005. time.Duration.fortnight : Duration
  7006. time.Duration.fortnight.doc : Doc
  7007. time.Duration.hour : Duration
  7008. time.Duration.hour.doc : Doc
  7009. time.Duration.hours : Int -> Duration
  7010. time.Duration.hours.doc : Doc
  7011. time.Duration.internal.Duration : Int -> Nat -> Duration
  7012. time.Duration.isNegative : Duration -> Boolean
  7013. time.Duration.isNegative.doc : Doc
  7014. time.Duration.isZero : Duration -> Boolean
  7015. time.Duration.isZero.doc : Doc
  7016. time.Duration.julianYear : Duration
  7017. time.Duration.julianYear.doc : Doc
  7018. time.Duration.julianYears : Int -> Duration
  7019. time.Duration.julianYears.doc : Doc
  7020. time.Duration.maxDuration : Duration
  7021. time.Duration.maxDuration.doc : Doc
  7022. time.Duration.microsecond : Duration
  7023. time.Duration.microsecond.doc : Doc
  7024. time.Duration.microseconds : Int -> Duration
  7025. time.Duration.microseconds.doc : Doc
  7026. time.Duration.millisecond : Duration
  7027. time.Duration.millisecond.doc : Doc
  7028. time.Duration.milliseconds : Int -> Duration
  7029. time.Duration.milliseconds.doc : Doc
  7030. time.Duration.minDuration : Duration
  7031. time.Duration.minDuration.doc : Doc
  7032. time.Duration.minute : Duration
  7033. time.Duration.minute.doc : Doc
  7034. time.Duration.minutes : Int -> Duration
  7035. time.Duration.minutes.doc : Doc
  7036. time.Duration.mod : Duration
                            -> Duration
                            ->{Exception} Duration
  7037. time.Duration.mod.doc : Doc
  7038. time.Duration.nanosComponent : Duration -> Nat
  7039. time.Duration.nanosComponent.doc : Doc
  7040. time.Duration.nanosecond : Duration
  7041. time.Duration.nanosecond.doc : Doc
  7042. time.Duration.nanoseconds : Int -> Duration
  7043. time.Duration.nanoseconds.doc : Doc
  7044. time.Duration.negate : Duration -> Duration
  7045. time.Duration.negate.doc : Doc
  7046. time.Duration.second : Duration
  7047. time.Duration.second.doc : Doc
  7048. time.Duration.seconds : Int -> Duration
  7049. time.Duration.seconds.doc : Doc
  7050. time.Duration.setNanos : Duration -> Nat -> Duration
  7051. time.Duration.setNanos.doc : Doc
  7052. time.Duration.setSeconds : Duration -> Int -> Duration
  7053. time.Duration.setSeconds.doc : Doc
  7054. time.Duration.tests.divNotTruncate.nn : [Result]
  7055. time.Duration.tests.divNotTruncate.np : [Result]
  7056. time.Duration.tests.divNotTruncate.pn : [Result]
  7057. time.Duration.tests.divNotTruncate.pp : [Result]
  7058. time.Duration.toText : Duration -> Text
  7059. time.Duration.toText.doc : Doc
  7060. time.Duration.week : Duration
  7061. time.Duration.week.doc : Doc
  7062. time.Duration.weeks : Int -> Duration
  7063. time.Duration.weeks.doc : Doc
  7064. time.Duration.zero : Duration
  7065. time.Duration.zero.doc : Doc
  7066. type time.Instant
  7067. time.Instant.!= : Instant -> Instant -> Boolean
  7068. time.Instant.+ : Instant -> Duration -> Instant
  7069. time.Instant.+.doc : Doc
  7070. time.Instant.- : Instant -> Duration -> Instant
  7071. time.Instant.-.doc : Doc
  7072. time.Instant.< : Instant -> Instant -> Boolean
  7073. time.Instant.<.doc : Doc
  7074. time.Instant.<= : Instant -> Instant -> Boolean
  7075. time.Instant.<=.doc : Doc
  7076. time.Instant.== : Instant -> Instant -> Boolean
  7077. time.Instant.==.doc : Doc
  7078. time.Instant.> : Instant -> Instant -> Boolean
  7079. time.Instant.>.doc : Doc
  7080. time.Instant.>= : Instant -> Instant -> Boolean
  7081. time.Instant.>=.doc : Doc
  7082. time.Instant.addDuration : Instant
                                   -> Duration
                                   -> Instant
  7083. time.Instant.addDuration.doc : Doc
  7084. time.Instant.addYears : Instant -> Int -> Instant
  7085. time.Instant.addYears.doc : Doc
  7086. time.Instant.atOffset : Instant
                                -> UTCOffset
                                -> OffsetDateTime
  7087. time.Instant.atOffset.doc : Doc
  7088. time.Instant.atUTC : Instant -> OffsetDateTime
  7089. time.Instant.atUTC.doc : Doc
  7090. time.Instant.ceiling : Duration
                               -> Instant
                               ->{Exception} Instant
  7091. time.Instant.ceiling.doc : Doc
  7092. time.Instant.compare : Instant -> Instant -> Ordering
  7093. time.Instant.compare.doc : Doc
  7094. time.Instant.doc : Doc
  7095. time.Instant.epoch : Instant
  7096. time.Instant.epoch.doc : Doc
  7097. time.Instant.floor : Duration
                             -> Instant
                             ->{Exception} Instant
  7098. time.Instant.floor.doc : Doc
  7099. time.Instant.fromEpochMicroseconds : Int -> Instant
  7100. time.Instant.fromEpochMicroseconds.doc : Doc
  7101. time.Instant.fromEpochMilliseconds : Int -> Instant
  7102. time.Instant.fromEpochMilliseconds.doc : Doc
  7103. time.Instant.fromEpochNanoseconds : Int -> Instant
  7104. time.Instant.fromEpochNanoseconds.doc : Doc
  7105. time.Instant.fromEpochSeconds : Int -> Instant
  7106. time.Instant.fromEpochSeconds.doc : Doc
  7107. time.Instant.fromIso8601 : Text -> Optional Instant
  7108. time.Instant.fromIso8601.doc : Doc
  7109. time.Instant.internal.dayOfYearToMonthAndDay : Boolean
                                                       -> Nat
                                                       -> ( Nat,
                                                         Nat)
  7110. time.Instant.internal.dayOfYearToMonthAndDay.doc : Doc
  7111. time.Instant.internal.Instant : Int -> Nat -> Instant
  7112. time.Instant.microsecondsSinceEpoch : Instant -> Int
  7113. time.Instant.microsecondsSinceEpoch.doc : Doc
  7114. time.Instant.millisecondsSinceEpoch : Instant -> Int
  7115. time.Instant.millisecondsSinceEpoch.doc : Doc
  7116. time.Instant.nanosecondOfSecond : Instant -> Nat
  7117. time.Instant.nanosecondOfSecond.doc : Doc
  7118. time.Instant.nanosecondOfSecond.modify : (Nat ->{g} Nat)
                                                 -> Instant
                                                 ->{g} Instant
  7119. time.Instant.nanosecondOfSecond.modify.doc : Doc
  7120. time.Instant.nanosecondOfSecond.set : Nat
                                              -> Instant
                                              -> Instant
  7121. time.Instant.nanosecondOfSecond.set.doc : Doc
  7122. time.Instant.nanosecondsSinceEpoch : Instant -> Int
  7123. time.Instant.nanosecondsSinceEpoch.doc : Doc
  7124. time.Instant.now : '{IO, Exception} Instant
  7125. time.Instant.now.doc : Doc
  7126. time.Instant.round : Duration
                             -> Instant
                             ->{Exception} Instant
  7127. time.Instant.round.doc : Doc
  7128. time.Instant.secondsSinceEpoch : Instant -> Int
  7129. time.Instant.secondsSinceEpoch.doc : Doc
  7130. time.Instant.secondsSinceEpoch.modify : (Int ->{g} Int)
                                                -> Instant
                                                ->{g} Instant
  7131. time.Instant.secondsSinceEpoch.modify.doc : Doc
  7132. time.Instant.secondsSinceEpoch.set : Int
                                             -> Instant
                                             -> Instant
  7133. time.Instant.secondsSinceEpoch.set.doc : Doc
  7134. time.Instant.subtractDuration : Instant
                                        -> Duration
                                        -> Instant
  7135. time.Instant.subtractDuration.doc : Doc
  7136. time.Instant.timeSinceEpoch : Instant -> Duration
  7137. time.Instant.timeSinceEpoch.doc : Doc
  7138. time.Instant.toBasicISO8601 : Instant -> Text
  7139. time.Instant.toBasicISO8601.doc : Doc
  7140. time.Instant.toRFC1123 : Instant -> Text
  7141. time.Instant.toRFC1123.doc : Doc
  7142. time.Instant.toRFC2822 : Instant -> Text
  7143. time.Instant.toRFC2822.doc : Doc
  7144. time.Instant.toText : Instant -> Text
  7145. time.Instant.toText.doc : Doc
  7146. time.Instant.truncateToCenturies : Instant -> Instant
  7147. time.Instant.truncateToCenturies.doc : Doc
  7148. time.Instant.truncateToDays : Instant -> Instant
  7149. time.Instant.truncateToDays.doc : Doc
  7150. time.Instant.truncateToHours : Instant -> Instant
  7151. time.Instant.truncateToHours.doc : Doc
  7152. time.Instant.truncateToMicroseconds : Instant -> Instant
  7153. time.Instant.truncateToMicroseconds.doc : Doc
  7154. time.Instant.truncateToMillennia : Instant -> Instant
  7155. time.Instant.truncateToMillennia.doc : Doc
  7156. time.Instant.truncateToMilliseconds : Instant -> Instant
  7157. time.Instant.truncateToMilliseconds.doc : Doc
  7158. time.Instant.truncateToMinutes : Instant -> Instant
  7159. time.Instant.truncateToMinutes.doc : Doc
  7160. time.Instant.truncateToSeconds : Instant -> Instant
  7161. time.Instant.truncateToSeconds.doc : Doc
  7162. time.Instant.truncateToYears : Instant -> Instant
  7163. time.Instant.truncateToYears.doc : Doc
  7164. time.isLeapYear : Int -> Boolean
  7165. time.isLeapYear.doc : Doc
  7166. type time.LocalDate
  7167. time.LocalDate.!= : LocalDate -> LocalDate -> Boolean
  7168. time.LocalDate.!=.doc : Doc
  7169. time.LocalDate.+ : LocalDate -> Int -> LocalDate
  7170. time.LocalDate.+.doc : Doc
  7171. time.LocalDate.- : LocalDate -> LocalDate -> Int
  7172. time.LocalDate.-.doc : Doc
  7173. time.LocalDate.< : LocalDate -> LocalDate -> Boolean
  7174. time.LocalDate.<.doc : Doc
  7175. time.LocalDate.<= : LocalDate -> LocalDate -> Boolean
  7176. time.LocalDate.<=.doc : Doc
  7177. time.LocalDate.== : LocalDate -> LocalDate -> Boolean
  7178. time.LocalDate.==.doc : Doc
  7179. time.LocalDate.> : LocalDate -> LocalDate -> Boolean
  7180. time.LocalDate.>.doc : Doc
  7181. time.LocalDate.>= : LocalDate -> LocalDate -> Boolean
  7182. time.LocalDate.>=.doc : Doc
  7183. time.LocalDate.addDuration : LocalDate
                                     -> Duration
                                     -> LocalDate
  7184. time.LocalDate.addDuration.doc : Doc
  7185. time.LocalDate.atTime : LocalDate
                                -> LocalTime
                                -> LocalDateTime
  7186. time.LocalDate.atTime.doc : Doc
  7187. time.LocalDate.current : '{IO, Exception} LocalDate
  7188. time.LocalDate.current.doc : Doc
  7189. time.LocalDate.day : LocalDate -> Nat
  7190. time.LocalDate.day.doc : Doc
  7191. time.LocalDate.day.modify : (Nat ->{g} Nat)
                                    -> LocalDate
                                    ->{g} LocalDate
  7192. time.LocalDate.day.set : Nat -> LocalDate -> LocalDate
  7193. time.LocalDate.day.set.doc : Doc
  7194. time.LocalDate.dayOfWeek : LocalDate -> DayOfWeek
  7195. time.LocalDate.dayOfWeek.doc : Doc
  7196. time.LocalDate.doc : Doc
  7197. time.LocalDate.duration : LocalDate
                                  -> LocalDate
                                  -> Duration
  7198. time.LocalDate.format : Text -> LocalDate -> Text
  7199. time.LocalDate.format.doc : Doc
  7200. time.LocalDate.format.test : [Result]
  7201. time.LocalDate.fromBasicISO8601 : Text
                                          -> Optional LocalDate
  7202. time.LocalDate.fromBasicISO8601.doc : Doc
  7203. time.LocalDate.fromIso8601 : Text -> Optional LocalDate
  7204. time.LocalDate.fromIso8601.doc : Doc
  7205. time.LocalDate.fromRFC7231 : Text
                                     ->{Exception} LocalDate
  7206. time.LocalDate.fromRFC7231.doc : Doc
  7207. time.LocalDate.LocalDate : Int
                                   -> Nat
                                   -> Nat
                                   -> LocalDate
  7208. time.LocalDate.month : LocalDate -> Nat
  7209. time.LocalDate.month.doc : Doc
  7210. time.LocalDate.month.modify : (Nat ->{g} Nat)
                                      -> LocalDate
                                      ->{g} LocalDate
  7211. time.LocalDate.month.set : Nat -> LocalDate -> LocalDate
  7212. time.LocalDate.month.set.doc : Doc
  7213. time.LocalDate.range : LocalDate
                               -> LocalDate
                               -> [LocalDate]
  7214. time.LocalDate.range.doc : Doc
  7215. time.LocalDate.range.test : [Result]
  7216. time.LocalDate.tests.comparison : [Result]
  7217. time.LocalDate.toBasicISO8601 : LocalDate -> Text
  7218. time.LocalDate.toBasicISO8601.doc : Doc
  7219. time.LocalDate.toText : LocalDate -> Text
  7220. time.LocalDate.toText.doc : Doc
  7221. time.LocalDate.year : LocalDate -> Int
  7222. time.LocalDate.year.doc : Doc
  7223. time.LocalDate.year.modify : (Int ->{g} Int)
                                     -> LocalDate
                                     ->{g} LocalDate
  7224. time.LocalDate.year.set : Int -> LocalDate -> LocalDate
  7225. time.LocalDate.year.set.doc : Doc
  7226. type time.LocalDateTime
  7227. time.LocalDateTime.!= : LocalDateTime
                                -> LocalDateTime
                                -> Boolean
  7228. time.LocalDateTime.!=.doc : Doc
  7229. time.LocalDateTime.< : LocalDateTime
                               -> LocalDateTime
                               -> Boolean
  7230. time.LocalDateTime.<.doc : Doc
  7231. time.LocalDateTime.<= : LocalDateTime
                                -> LocalDateTime
                                -> Boolean
  7232. time.LocalDateTime.<=.doc : Doc
  7233. time.LocalDateTime.== : LocalDateTime
                                -> LocalDateTime
                                -> Boolean
  7234. time.LocalDateTime.==.doc : Doc
  7235. time.LocalDateTime.> : LocalDateTime
                               -> LocalDateTime
                               -> Boolean
  7236. time.LocalDateTime.>.doc : Doc
  7237. time.LocalDateTime.>= : LocalDateTime
                                -> LocalDateTime
                                -> Boolean
  7238. time.LocalDateTime.>=.doc : Doc
  7239. time.LocalDateTime.addDuration : LocalDateTime
                                         -> Duration
                                         -> LocalDateTime
  7240. time.LocalDateTime.addDuration.doc : Doc
  7241. time.LocalDateTime.atOffset : LocalDateTime
                                      -> UTCOffset
                                      -> OffsetDateTime
  7242. time.LocalDateTime.atOffset.doc : Doc
  7243. time.LocalDateTime.atStartOfDay : LocalDate
                                          -> LocalDateTime
  7244. time.LocalDateTime.atStartOfDay.doc : Doc
  7245. time.LocalDateTime.current : '{IO, Exception} LocalDateTime
  7246. time.LocalDateTime.current.doc : Doc
  7247. time.LocalDateTime.date : LocalDateTime -> LocalDate
  7248. time.LocalDateTime.date.doc : Doc
  7249. time.LocalDateTime.date.modify : (LocalDate
                                         ->{g} LocalDate)
                                         -> LocalDateTime
                                         ->{g} LocalDateTime
  7250. time.LocalDateTime.date.modify.doc : Doc
  7251. time.LocalDateTime.date.set : LocalDate
                                      -> LocalDateTime
                                      -> LocalDateTime
  7252. time.LocalDateTime.date.set.doc : Doc
  7253. time.LocalDateTime.dayOfWeek : LocalDateTime
                                       -> DayOfWeek
  7254. time.LocalDateTime.dayOfWeek.doc : Doc
  7255. time.LocalDateTime.doc : Doc
  7256. time.LocalDateTime.format : Text
                                    -> LocalDateTime
                                    -> Text
  7257. time.LocalDateTime.format.doc : Doc
  7258. time.LocalDateTime.format.test : [Result]
  7259. time.LocalDateTime.fromIso8601 : Text
                                         -> Optional
                                           LocalDateTime
  7260. time.LocalDateTime.fromIso8601.doc : Doc
  7261. time.LocalDateTime.fromRFC7231 : Text
                                         ->{Exception} LocalDateTime
  7262. time.LocalDateTime.fromRFC7231.doc : Doc
  7263. time.LocalDateTime.LocalDateTime : LocalDate
                                           -> LocalTime
                                           -> LocalDateTime
  7264. time.LocalDateTime.tests.comparison : [Result]
  7265. time.LocalDateTime.time : LocalDateTime -> LocalTime
  7266. time.LocalDateTime.time.doc : Doc
  7267. time.LocalDateTime.time.modify : (LocalTime
                                         ->{g} LocalTime)
                                         -> LocalDateTime
                                         ->{g} LocalDateTime
  7268. time.LocalDateTime.time.modify.doc : Doc
  7269. time.LocalDateTime.time.set : LocalTime
                                      -> LocalDateTime
                                      -> LocalDateTime
  7270. time.LocalDateTime.time.set.doc : Doc
  7271. time.LocalDateTime.toBasicISO8601 : LocalDateTime
                                            -> Text
  7272. time.LocalDateTime.toBasicISO8601.doc : Doc
  7273. time.LocalDateTime.toRFC1123AtGMT : LocalDateTime
                                            -> Text
  7274. time.LocalDateTime.toRFC1123AtGMT.doc : Doc
  7275. time.LocalDateTime.toText : LocalDateTime -> Text
  7276. time.LocalDateTime.toText.doc : Doc
  7277. type time.LocalTime
  7278. time.LocalTime.!= : LocalTime -> LocalTime -> Boolean
  7279. time.LocalTime.!=.doc : Doc
  7280. time.LocalTime.< : LocalTime -> LocalTime -> Boolean
  7281. time.LocalTime.<.doc : Doc
  7282. time.LocalTime.<= : LocalTime -> LocalTime -> Boolean
  7283. time.LocalTime.<=.doc : Doc
  7284. time.LocalTime.== : LocalTime -> LocalTime -> Boolean
  7285. time.LocalTime.==.doc : Doc
  7286. time.LocalTime.> : LocalTime -> LocalTime -> Boolean
  7287. time.LocalTime.>.doc : Doc
  7288. time.LocalTime.>= : LocalTime -> LocalTime -> Boolean
  7289. time.LocalTime.>=.doc : Doc
  7290. time.LocalTime.addDuration : LocalTime
                                     -> Duration
                                     -> LocalTime
  7291. time.LocalTime.addDuration.doc : Doc
  7292. time.LocalTime.atOffset : LocalTime
                                  -> UTCOffset
                                  -> OffsetTime
  7293. time.LocalTime.atOffset.doc : Doc
  7294. time.LocalTime.comparison : [Result]
  7295. time.LocalTime.current : '{IO, Exception} LocalTime
  7296. time.LocalTime.current.doc : Doc
  7297. time.LocalTime.doc : Doc
  7298. time.LocalTime.fromBasicISO8601 : Text
                                          -> Optional LocalTime
  7299. time.LocalTime.fromBasicISO8601.doc : Doc
  7300. time.LocalTime.fromIso8601 : Text -> Optional LocalTime
  7301. time.LocalTime.fromIso8601.doc : Doc
  7302. time.LocalTime.fromRFC7231 : Text
                                     ->{Exception} LocalTime
  7303. time.LocalTime.fromRFC7231.doc : Doc
  7304. time.LocalTime.hour : LocalTime -> Nat
  7305. time.LocalTime.hour.doc : Doc
  7306. time.LocalTime.hour.modify : (Nat ->{g} Nat)
                                     -> LocalTime
                                     ->{g} LocalTime
  7307. time.LocalTime.hour.modify.doc : Doc
  7308. time.LocalTime.hour.set : Nat -> LocalTime -> LocalTime
  7309. time.LocalTime.hour.set.doc : Doc
  7310. time.LocalTime.LocalTime : Nat
                                   -> Nat
                                   -> Nat
                                   -> Nat
                                   -> LocalTime
  7311. time.LocalTime.minute : LocalTime -> Nat
  7312. time.LocalTime.minute.doc : Doc
  7313. time.LocalTime.minute.modify : (Nat ->{g} Nat)
                                       -> LocalTime
                                       ->{g} LocalTime
  7314. time.LocalTime.minute.modify.doc : Doc
  7315. time.LocalTime.minute.set : Nat
                                    -> LocalTime
                                    -> LocalTime
  7316. time.LocalTime.minute.set.doc : Doc
  7317. time.LocalTime.nanosecond : LocalTime -> Nat
  7318. time.LocalTime.nanosecond.modify : (Nat ->{g} Nat)
                                           -> LocalTime
                                           ->{g} LocalTime
  7319. time.LocalTime.nanosecond.modify.doc : Doc
  7320. time.LocalTime.nanosecond.set : Nat
                                        -> LocalTime
                                        -> LocalTime
  7321. time.LocalTime.nanosecond.set.doc : Doc
  7322. time.LocalTime.second : LocalTime -> Nat
  7323. time.LocalTime.second.doc : Doc
  7324. time.LocalTime.second.modify : (Nat ->{g} Nat)
                                       -> LocalTime
                                       ->{g} LocalTime
  7325. time.LocalTime.second.modify.doc : Doc
  7326. time.LocalTime.second.set : Nat
                                    -> LocalTime
                                    -> LocalTime
  7327. time.LocalTime.second.set.doc : Doc
  7328. time.LocalTime.toBasicISO8601 : LocalTime -> Text
  7329. time.LocalTime.toBasicISO8601.doc : Doc
  7330. time.LocalTime.toText : LocalTime -> Text
  7331. time.LocalTime.toText.doc : Doc
  7332. time.monthLengths : Boolean -> List.Nonempty Nat
  7333. time.monthLengths.doc : Doc
  7334. time.monthNames : [Text]
  7335. time.monthNamesShort : [Text]
  7336. structural type time.OffsetDateTime
  7337. time.OffsetDateTime.!= : OffsetDateTime
                                 -> OffsetDateTime
                                 -> Boolean
  7338. time.OffsetDateTime.!=.doc : Doc
  7339. time.OffsetDateTime.< : OffsetDateTime
                                -> OffsetDateTime
                                -> Boolean
  7340. time.OffsetDateTime.<.doc : Doc
  7341. time.OffsetDateTime.<= : OffsetDateTime
                                 -> OffsetDateTime
                                 -> Boolean
  7342. time.OffsetDateTime.<=.doc : Doc
  7343. time.OffsetDateTime.== : OffsetDateTime
                                 -> OffsetDateTime
                                 -> Boolean
  7344. time.OffsetDateTime.==.doc : Doc
  7345. time.OffsetDateTime.> : OffsetDateTime
                                -> OffsetDateTime
                                -> Boolean
  7346. time.OffsetDateTime.>.doc : Doc
  7347. time.OffsetDateTime.>= : OffsetDateTime
                                 -> OffsetDateTime
                                 -> Boolean
  7348. time.OffsetDateTime.>=.doc : Doc
  7349. time.OffsetDateTime.addDuration : OffsetDateTime
                                          -> Duration
                                          -> OffsetDateTime
  7350. time.OffsetDateTime.addDuration.doc : Doc
  7351. time.OffsetDateTime.convertOffset : UTCOffset
                                            -> OffsetDateTime
                                            -> OffsetDateTime
  7352. time.OffsetDateTime.convertOffset.doc : Doc
  7353. time.OffsetDateTime.current : '{IO, Exception} OffsetDateTime
  7354. time.OffsetDateTime.current.doc : Doc
  7355. time.OffsetDateTime.date : OffsetDateTime -> LocalDate
  7356. time.OffsetDateTime.date.doc : Doc
  7357. time.OffsetDateTime.dayOfWeek : OffsetDateTime
                                        -> DayOfWeek
  7358. time.OffsetDateTime.dayOfWeek.doc : Doc
  7359. time.OffsetDateTime.doc : Doc
  7360. time.OffsetDateTime.fromInstant : Instant
                                          -> UTCOffset
                                          -> OffsetDateTime
  7361. time.OffsetDateTime.fromInstant.doc : Doc
  7362. time.OffsetDateTime.fromIso8601 : Text
                                          -> Optional
                                            OffsetDateTime
  7363. time.OffsetDateTime.fromIso8601.doc : Doc
  7364. time.OffsetDateTime.fromRFC1123 : Text
                                          ->{Exception} OffsetDateTime
  7365. time.OffsetDateTime.fromRFC1123.doc : Doc
  7366. time.OffsetDateTime.fromRFC1123.test : [Result]
  7367. time.OffsetDateTime.fromRFC2822 : Text
                                          ->{Exception} OffsetDateTime
  7368. time.OffsetDateTime.fromRFC2822.doc : Doc
  7369. time.OffsetDateTime.fromRFC2822.test : [Result]
  7370. time.OffsetDateTime.fromTimeAndDate : OffsetTime
                                              -> LocalDate
                                              -> OffsetDateTime
  7371. time.OffsetDateTime.fromTimeAndDate.doc : Doc
  7372. time.OffsetDateTime.localDateTime : OffsetDateTime
                                            -> LocalDateTime
  7373. time.OffsetDateTime.localDateTime.doc : Doc
  7374. time.OffsetDateTime.offset : OffsetDateTime -> UTCOffset
  7375. time.OffsetDateTime.offset.doc : Doc
  7376. time.OffsetDateTime.OffsetDateTime : UTCOffset
                                             -> LocalDateTime
                                             -> OffsetDateTime
  7377. time.OffsetDateTime.ordering.doc : Doc
  7378. time.OffsetDateTime.tests.comparison : [Result]
  7379. time.OffsetDateTime.timeOfDay : OffsetDateTime
                                        -> OffsetTime
  7380. time.OffsetDateTime.timeOfDay.doc : Doc
  7381. time.OffsetDateTime.toBasicISO8601 : OffsetDateTime
                                             -> Text
  7382. time.OffsetDateTime.toBasicISO8601.doc : Doc
  7383. time.OffsetDateTime.toInstant : OffsetDateTime
                                        -> Instant
  7384. time.OffsetDateTime.toInstant.doc : Doc
  7385. time.OffsetDateTime.toInstant.tests.rountrip : [Result]
  7386. time.OffsetDateTime.toRFC1123 : OffsetDateTime -> Text
  7387. time.OffsetDateTime.toRFC1123.doc : Doc
  7388. time.OffsetDateTime.toRFC2822 : OffsetDateTime -> Text
  7389. time.OffsetDateTime.toRFC2822.doc : Doc
  7390. time.OffsetDateTime.toText : OffsetDateTime -> Text
  7391. time.OffsetDateTime.toText.doc : Doc
  7392. time.OffsetDateTime.toUTC : OffsetDateTime
                                    -> OffsetDateTime
  7393. time.OffsetDateTime.toUTC.doc : Doc
  7394. time.OffsetDateTime.toUTCLocal : OffsetDateTime
                                         -> LocalDateTime
  7395. time.OffsetDateTime.toUTCLocal.doc : Doc
  7396. type time.OffsetTime
  7397. time.OffsetTime.!= : OffsetTime -> OffsetTime -> Boolean
  7398. time.OffsetTime.!=.doc : Doc
  7399. time.OffsetTime.< : OffsetTime -> OffsetTime -> Boolean
  7400. time.OffsetTime.<.doc : Doc
  7401. time.OffsetTime.<= : OffsetTime -> OffsetTime -> Boolean
  7402. time.OffsetTime.<=.doc : Doc
  7403. time.OffsetTime.== : OffsetTime -> OffsetTime -> Boolean
  7404. time.OffsetTime.==.doc : Doc
  7405. time.OffsetTime.> : OffsetTime -> OffsetTime -> Boolean
  7406. time.OffsetTime.>.doc : Doc
  7407. time.OffsetTime.>= : OffsetTime -> OffsetTime -> Boolean
  7408. time.OffsetTime.>=.doc : Doc
  7409. time.OffsetTime.addDuration : OffsetTime
                                      -> Duration
                                      -> OffsetTime
  7410. time.OffsetTime.addDuration.doc : Doc
  7411. time.OffsetTime.doc : Doc
  7412. time.OffsetTime.offset : OffsetTime -> UTCOffset
  7413. time.OffsetTime.offset.doc : Doc
  7414. time.OffsetTime.offset.modify : (UTCOffset
                                        ->{g} UTCOffset)
                                        -> OffsetTime
                                        ->{g} OffsetTime
  7415. time.OffsetTime.offset.set : UTCOffset
                                     -> OffsetTime
                                     -> OffsetTime
  7416. time.OffsetTime.offset.set.doc : Doc
  7417. time.OffsetTime.OffsetTime : UTCOffset
                                     -> LocalTime
                                     -> OffsetTime
  7418. time.OffsetTime.ordering.doc : Doc
  7419. time.OffsetTime.tests.comparison : [Result]
  7420. time.OffsetTime.time : OffsetTime -> LocalTime
  7421. time.OffsetTime.time.doc : Doc
  7422. time.OffsetTime.time.modify : (LocalTime
                                      ->{g} LocalTime)
                                      -> OffsetTime
                                      ->{g} OffsetTime
  7423. time.OffsetTime.time.set : LocalTime
                                   -> OffsetTime
                                   -> OffsetTime
  7424. time.OffsetTime.time.set.doc : Doc
  7425. time.OffsetTime.toText : OffsetTime -> Text
  7426. time.patterns.asctimeFormat : Pattern Text
  7427. time.patterns.asctimeFormat.doc : Doc
  7428. time.patterns.asctimeFormat.test : [Result]
  7429. time.patterns.iso8601Date : Pattern Text
  7430. time.patterns.iso8601DateTime : Pattern Text
  7431. time.patterns.iso8601LocalDateTime : Pattern Text
  7432. time.patterns.iso8601LocalTime : Pattern Text
  7433. time.patterns.iso8601Time : Pattern Text
  7434. time.patterns.iso8601Timezone : Pattern Text
  7435. time.patterns.rfc2822DateTime : Pattern Text
  7436. time.patterns.rfc2822DateTime.doc : Doc
  7437. time.patterns.rfc2822Offset : Pattern Text
  7438. time.patterns.rfc2822Offset.doc : Doc
  7439. time.patterns.rfc7231Date : Pattern Text
  7440. time.patterns.rfc7231Date.doc : Doc
  7441. time.patterns.rfc7231DateTime : Pattern Text
  7442. time.patterns.rfc7231DateTime.doc : Doc
  7443. time.patterns.rfc7231DateTime.test850 : [Result]
  7444. time.patterns.rfc7231DateTime.testIMF : [Result]
  7445. time.patterns.rfc7231Time : Pattern Text
  7446. time.patterns.rfc7231Time.doc : Doc
  7447. time.README : Doc
  7448. type time.TimeZone
  7449. time.TimeZone.currentTimeZone : '{IO, Exception} TimeZone
  7450. time.TimeZone.currentTimeZone.doc : Doc
  7451. time.TimeZone.doc : Doc
  7452. time.TimeZone.getTimeZone : Instant ->{IO} TimeZone
  7453. time.TimeZone.getTimeZone.doc : Doc
  7454. time.TimeZone.name : TimeZone -> Text
  7455. time.TimeZone.name.modify : (Text ->{g} Text)
                                    -> TimeZone
                                    ->{g} TimeZone
  7456. time.TimeZone.name.set : Text -> TimeZone -> TimeZone
  7457. time.TimeZone.offset : TimeZone -> UTCOffset
  7458. time.TimeZone.offset.modify : (UTCOffset
                                      ->{g} UTCOffset)
                                      -> TimeZone
                                      ->{g} TimeZone
  7459. time.TimeZone.offset.set : UTCOffset
                                   -> TimeZone
                                   -> TimeZone
  7460. time.TimeZone.summerOnly : TimeZone -> Boolean
  7461. time.TimeZone.summerOnly.modify : (Boolean
                                          ->{g} Boolean)
                                          -> TimeZone
                                          ->{g} TimeZone
  7462. time.TimeZone.summerOnly.set : Boolean
                                       -> TimeZone
                                       -> TimeZone
  7463. time.TimeZone.TimeZone : UTCOffset
                                 -> Boolean
                                 -> Text
                                 -> TimeZone
  7464. time.TimeZone.toDuration : TimeZone -> Duration
  7465. time.TimeZone.toDuration.doc : Doc
  7466. type time.UTCOffset
  7467. time.UTCOffset.addHours : Nat -> UTCOffset -> UTCOffset
  7468. time.UTCOffset.addHours.doc : Doc
  7469. time.UTCOffset.addHours.flipped : UTCOffset
                                          -> Nat
                                          -> UTCOffset
  7470. time.UTCOffset.addHours.flipped.doc : Doc
  7471. time.UTCOffset.addMinutes : Nat
                                    -> UTCOffset
                                    -> UTCOffset
  7472. time.UTCOffset.addMinutes.doc : Doc
  7473. time.UTCOffset.currentOffset : '{IO, Exception} UTCOffset
  7474. time.UTCOffset.currentOffset.doc : Doc
  7475. time.UTCOffset.doc : Doc
  7476. time.UTCOffset.fromBasicISO8601 : Text
                                          -> Optional UTCOffset
  7477. time.UTCOffset.fromBasicISO8601.doc : Doc
  7478. time.UTCOffset.fromHours : Int -> UTCOffset
  7479. time.UTCOffset.fromHours.doc : Doc
  7480. time.UTCOffset.fromIso8601 : Text -> Optional UTCOffset
  7481. time.UTCOffset.fromIso8601.doc : Doc
  7482. time.UTCOffset.fromMinutes : Int -> UTCOffset
  7483. time.UTCOffset.fromMinutes.doc : Doc
  7484. time.UTCOffset.fromRFC2822 : Text
                                     ->{Exception} UTCOffset
  7485. time.UTCOffset.fromRFC2822.doc : Doc
  7486. time.UTCOffset.getOffset : Instant ->{IO} UTCOffset
  7487. time.UTCOffset.getOffset.doc : Doc
  7488. time.UTCOffset.isNegative : UTCOffset -> Boolean
  7489. time.UTCOffset.isNegative.doc : Doc
  7490. time.UTCOffset.offsetHours : UTCOffset -> Int
  7491. time.UTCOffset.offsetHours.doc : Doc
  7492. time.UTCOffset.offsetMinutes : UTCOffset -> Nat
  7493. time.UTCOffset.offsetMinutes.doc : Doc
  7494. time.UTCOffset.offsetNamed.ADT : UTCOffset
  7495. time.UTCOffset.offsetNamed.AKDT : UTCOffset
  7496. time.UTCOffset.offsetNamed.AKST : UTCOffset
  7497. time.UTCOffset.offsetNamed.ART : UTCOffset
  7498. time.UTCOffset.offsetNamed.AST : UTCOffset
  7499. time.UTCOffset.offsetNamed.BRST : UTCOffset
  7500. time.UTCOffset.offsetNamed.BRT : UTCOffset
  7501. time.UTCOffset.offsetNamed.BST : UTCOffset
  7502. time.UTCOffset.offsetNamed.CDT : UTCOffset
  7503. time.UTCOffset.offsetNamed.CEST : UTCOffset
  7504. time.UTCOffset.offsetNamed.CET : UTCOffset
  7505. time.UTCOffset.offsetNamed.CST : UTCOffset
  7506. time.UTCOffset.offsetNamed.DST : UTCOffset
  7507. time.UTCOffset.offsetNamed.EAT : UTCOffset
  7508. time.UTCOffset.offsetNamed.EDT : UTCOffset
  7509. time.UTCOffset.offsetNamed.EEST : UTCOffset
  7510. time.UTCOffset.offsetNamed.EET : UTCOffset
  7511. time.UTCOffset.offsetNamed.EST : UTCOffset
  7512. time.UTCOffset.offsetNamed.GMT : UTCOffset
  7513. time.UTCOffset.offsetNamed.GST : UTCOffset
  7514. time.UTCOffset.offsetNamed.HST : UTCOffset
  7515. time.UTCOffset.offsetNamed.IDLE : UTCOffset
  7516. time.UTCOffset.offsetNamed.IDLW : UTCOffset
  7517. time.UTCOffset.offsetNamed.IST : UTCOffset
  7518. time.UTCOffset.offsetNamed.JST : UTCOffset
  7519. time.UTCOffset.offsetNamed.MDT : UTCOffset
  7520. time.UTCOffset.offsetNamed.MSD : UTCOffset
  7521. time.UTCOffset.offsetNamed.MSK : UTCOffset
  7522. time.UTCOffset.offsetNamed.MST : UTCOffset
  7523. time.UTCOffset.offsetNamed.NDT : UTCOffset
  7524. time.UTCOffset.offsetNamed.NZDT : UTCOffset
  7525. time.UTCOffset.offsetNamed.NZST : UTCOffset
  7526. time.UTCOffset.offsetNamed.NZT : UTCOffset
  7527. time.UTCOffset.offsetNamed.PDT : UTCOffset
  7528. time.UTCOffset.offsetNamed.PKT : UTCOffset
  7529. time.UTCOffset.offsetNamed.PST : UTCOffset
  7530. time.UTCOffset.offsetNamed.SLT : UTCOffset
  7531. time.UTCOffset.offsetNamed.SST : UTCOffset
  7532. time.UTCOffset.offsetNamed.UTC : UTCOffset
  7533. time.UTCOffset.offsetNamed.WAT : UTCOffset
  7534. time.UTCOffset.offsetNamed.WET : UTCOffset
  7535. time.UTCOffset.offsetNamed.WIB : UTCOffset
  7536. time.UTCOffset.offsetNamed.WST : UTCOffset
  7537. time.UTCOffset.subtractHours : Nat
                                       -> UTCOffset
                                       -> UTCOffset
  7538. time.UTCOffset.subtractHours.doc : Doc
  7539. time.UTCOffset.subtractHours.flipped : UTCOffset
                                               -> Nat
                                               -> UTCOffset
  7540. time.UTCOffset.subtractHours.flipped.doc : Doc
  7541. time.UTCOffset.subtractMinutes : Nat
                                         -> UTCOffset
                                         -> UTCOffset
  7542. time.UTCOffset.subtractMinutes.doc : Doc
  7543. time.UTCOffset.toBasicISO8601 : UTCOffset -> Text
  7544. time.UTCOffset.toBasicISO8601.doc : Doc
  7545. time.UTCOffset.toDuration : UTCOffset -> Duration
  7546. time.UTCOffset.toDuration.doc : Doc
  7547. time.UTCOffset.toHours : UTCOffset -> Float
  7548. time.UTCOffset.toHours.doc : Doc
  7549. time.UTCOffset.toMinutes : UTCOffset -> Int
  7550. time.UTCOffset.toMinutes.doc : Doc
  7551. time.UTCOffset.toMinutes.modify : (Int ->{g} Int)
                                          -> UTCOffset
                                          ->{g} UTCOffset
  7552. time.UTCOffset.toMinutes.modify.doc : Doc
  7553. time.UTCOffset.toMinutes.set : Int
                                       -> UTCOffset
                                       -> UTCOffset
  7554. time.UTCOffset.toRFC2822 : UTCOffset -> Text
  7555. time.UTCOffset.toRFC2822.doc : Doc
  7556. time.UTCOffset.toText : UTCOffset -> Text
  7557. time.UTCOffset.toText.doc : Doc
  7558. time.UTCOffset.utc : Int -> UTCOffset
  7559. time.UTCOffset.utc.doc : Doc
  7560. time.UTCOffset.UTCOffset : Int -> UTCOffset
  7561. todo : a -> b
  7562. todo.doc : Doc
  7563. structural type Unit
  7564. Unit.doc : Doc
  7565. Unit.Unit : ()
  7566. Universal.!== : a -> a -> Boolean
  7567. Universal.!==.doc : Doc
  7568. Universal.=== : a -> a -> Boolean
  7569. Universal.===.doc : Doc
  7570. Universal.compare : a -> a -> Int
  7571. Universal.compare.doc : Doc
  7572. Universal.compareOn : (a ->{e} x)
                              -> a
                              -> a
                              ->{e} Ordering
  7573. Universal.compareOn.doc : Doc
  7574. Universal.eq : a -> a -> Boolean
  7575. Universal.eq.doc : Doc
  7576. Universal.gt : a -> a -> Boolean
  7577. Universal.gt.doc : Doc
  7578. Universal.gteq : a -> a -> Boolean
  7579. Universal.gteq.doc : Doc
  7580. Universal.lt : a -> a -> Boolean
  7581. Universal.lt.doc : Doc
  7582. Universal.lteq : a -> a -> Boolean
  7583. Universal.lteq.doc : Doc
  7584. Universal.max : a -> a -> a
  7585. Universal.max.doc : Doc
  7586. Universal.max.tests.absorption : [Result]
  7587. Universal.max.tests.associative : [Result]
  7588. Universal.max.tests.commutative : [Result]
  7589. Universal.max.tests.distributesOverMin : [Result]
  7590. Universal.max.tests.idempotent : [Result]
  7591. Universal.max.tests.partialOrder : [Result]
  7592. Universal.min : a -> a -> a
  7593. Universal.min.doc : Doc
  7594. Universal.min.tests.absorption : [Result]
  7595. Universal.min.tests.associative : [Result]
  7596. Universal.min.tests.commutative : [Result]
  7597. Universal.min.tests.distributesOverMax : [Result]
  7598. Universal.min.tests.idempotent : [Result]
  7599. Universal.min.tests.partialOrder : [Result]
  7600. Universal.murmurHash : a -> Nat
  7601. Universal.murmurHash.doc : Doc
  7602. Universal.neq : a -> a -> Boolean
  7603. Universal.neq.doc : Doc
  7604. Universal.ordering : a -> a -> Ordering
  7605. Universal.ordering.doc : Doc
  7606. Universal.ordering.rewriteToCompare : x
                                              -> x
                                              -> lt
                                              -> lt
                                              -> lt
                                              -> Rewrites
                                                ( RewriteTerm
                                                  lt lt,
                                                  RewriteTerm
                                                  lt lt,
                                                  RewriteTerm
                                                  lt lt,
                                                  RewriteTerm
                                                  lt lt)
  7607. Universal.ordering.rewriteToCompare.doc : Doc
  7608. unsafe.coerceAbilities : (a ->{e1} b) -> a -> b
  7609. unsafe.coerceAbilities.doc : Doc
  7610. structural type Void
  7611. Void.absurd : Void -> a
  7612. Void.absurd.doc : Doc
  7613. Void.absurdly : '{e} Void ->{e} a
  7614. Void.absurdly.doc : Doc
  7615. Void.doc : Doc
```

## Code style conventions

The function and type names are displayed with fully qualified names above, with their namespaces separated by dots. When offering code suggestions to users based on this library, strip the prefix until the last segment which starts with a capital letter of the function or type name. For example, `data.List.map` should be suggested as `List.map` and `data.Map` should be suggested as `Map`.
