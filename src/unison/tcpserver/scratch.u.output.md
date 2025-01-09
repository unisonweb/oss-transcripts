# Tcpserver

This library provides a simplified interface for writing TCP servers in Unison. Using the
Tcp.serve function, you can write a TCP server in just a few lines of code. The library takes care of multithreading and connection lifecycle management for you.

## Library contents list

``` ucm
@unison/tcpserver/main> pull.without-history @unison/tcpserver/releases/1.0.1

  Downloaded 12735 entities.

  ✅

  Successfully updated @unison/tcpserver/main from
  @unison/tcpserver/releases/1.0.1.

@unison/tcpserver/main> find

  1.  concurrently : '{IO, Exception} () ->{IO} Promise ()
  2.  concurrently.doc : Doc
  3.  concurrently.example : '{IO} ()
  4.  examples.echoClient : '{IO, Exception} ()
  5.  examples.echoClientServer : '{IO} ()
  6.  examples.echoServer : '{IO, Exception} ()
  7.  README : Doc
  8.  ReleaseNotes : Doc
  9.  Tcp.acceptFork : ListeningServerSocket
                       -> (Socket ->{IO, Exception} a)
                       ->{IO, Exception} ThreadId
  10. Tcp.acceptFork.doc : Doc
  11. Tcp.examples.echoClient : '{IO, Exception} ()
  12. Tcp.examples.echoClientServer : '{IO} ()
  13. Tcp.examples.echoServer : '{IO, Exception} ()
  14. Tcp.listen : Optional HostName
                   -> Port
                   -> (ListeningServerSocket
                   ->{IO, Exception} a)
                   ->{IO, Exception} a
  15. Tcp.listen.doc : Doc
  16. Tcp.README : Doc
  17. Tcp.ReleaseNotes : Doc
  18. Tcp.serve : Optional HostName
                  -> Port
                  -> (Socket ->{IO, Exception} ())
                  ->{IO, Exception} ()
  19. Tcp.serve.doc : Doc
  20. Tcp.up.base.abilities.Exception.logAndCrash : '{g,
                                                    IO,
                                                    Exception} a
                                                    ->{g, IO} a
  21. Tcp.up.base.abilities.Exception.logAndCrash.doc : Doc
  22. Tcp.up.base.abilities.Exception.logAndIgnore : '{g,
                                                     IO,
                                                     Exception} a
                                                     ->{g, IO} ()
  23. Tcp.up.base.abilities.Exception.logAndIgnore.doc : Doc
  24. Tls.acceptFork : ServerConfig
                       -> ListeningServerSocket
                       -> (TlsSocket ->{g} t)
                       ->{IO, Exception} ThreadId
  25. Tls.acceptFork.doc : Doc
  26. Tls.acceptTls : ServerConfig
                      -> ListeningServerSocket
                      ->{IO, Exception} (Tls, Socket)
  27. Tls.acceptTls.doc : Doc
  28. Tls.connect : ClientConfig
                    -> HostName
                    -> Port
                    -> (TlsSocket ->{IO, Exception} a)
                    ->{IO, Exception} a
  29. Tls.connect.doc : Doc
  30. Tls.connectTls : ClientConfig
                       -> HostName
                       -> Port
                       ->{IO, Exception} (Tls, Socket)
  31. Tls.connectTls.doc : Doc
  32. Tls.serve : ServerConfig
                  -> Optional HostName
                  -> Port
                  -> (TlsSocket ->{IO, Exception} ())
                  ->{IO, Exception} ()
  33. Tls.serve.doc : Doc
  34. Tls.useTls : (TlsSocket ->{IO, Exception} a)
                   -> Tls
                   ->{IO, Exception} a
  35. Tls.useTls.doc : Doc
  36. Tls.useTlsThenCloseFork : (TlsSocket -> o)
                                -> Tls
                                -> Socket
                                ->{IO} ThreadId
  37. up.base.abilities.Exception.logAndCrash : '{g,
                                                IO,
                                                Exception} a
                                                ->{g, IO} a
  38. up.base.abilities.Exception.logAndCrash.doc : Doc
  39. up.base.abilities.Exception.logAndIgnore : '{g,
                                                 IO,
                                                 Exception} a
                                                 ->{g, IO} ()
  40. up.base.abilities.Exception.logAndIgnore.doc : Doc
```

## Code examples

``` ucm
@unison/tcpserver/main> edit 1-5000

  ☝️

  I added 31 definitions to the top of scratch.u

  You can edit them there, then run `update` to replace the
  definitions currently in this namespace.
```
