servant-db-elm-auth example applet*

*I mean "applet" to be "a small application".  Not "applet" from 90s java.

# Rationale

I had written very little haskell and no elm before starting this.

While there are numerous helpful examples on `servant`, `servant-elm`, 
`servant-auth`, and even examples stiching them all up together, I found it 
quite difficult to learn from them without seeing a step by step example.  
When one is new to Servant (and Elm.  And Haskell) it is just too much to 
absorb all at once.  

Therefore I set out to create such a step-by-step example.  
This has the added bonus of revealing to myself what I do and do not actually
understand.

# How it works

This repo contains four sub-projects in sequence; the next project adds 
functionality to the last for one and only one new topic.  The code
implementing the new functionality is commented with my understanding of 
what it does and how it works.  The sub-projects are:

1. _A-servant-start_: Basic RESTful server implement in Haskell/servant.
2. _B-postgres-data_: Servant API endpoints that talk to a database.
3. _C-small-elm-app_: An Elm app that talks to the API we created, where the 
   necessary requests and decoders are generated by `servant-elm`
4. _D-cookie-logins_: Authentication on the same servant REST API.

Each sub-project contains a README summarizing how to start the applet and
what has changed since the last one.

Beware! There is some cargo-cult programming in each sub-project, simply
because I did not fully understand the examples I learned from.

Admittedly, it would be neater if I could direct the user to a specific git 
commit of the project instead.  But that would take far too much care in my 
git commits (or far more git-fu) than I am able to produce. 

# System requirements

You should have ghc installed.  And configured to use with your favourite editor.
You should also have stack installed.

# Acknowledgements

Many thanks to `alp` and `phaazon` on the #servant IRC channel for informative 
discussions.  

I also learned by reading the following examples: (Add github links)

1. https://github.com/mchaver/servant-auth-and-elm-example
2. https://github.com/mattjbray/servant-elm-example-app
3. https://rundis.github.io/blog/2015/haskell_elm_spa_part1.html
4. https://github.com/rtfeldman/elm-spa-example

# TODO 

Doubtless there are many things that I could have done better, if I were a wiser
and more experienced haskeller.  Therefore I ask the reader to send me suggestions.

I think that how you deal with stateful and effectful code is more important to 
a project than what framework or even language you're using.  Discussions with
@lexi-lambda have lead me to believe that "mtl-style" provides a coherent way of
handling such code and making it testable.  I consider my this applet incomplete
(and my haskell-servant-elm learning) until it includes some testable logic.

@lexi-lambda's mtl example is at https://github.com/lexi-lambda/mtl-style-example
