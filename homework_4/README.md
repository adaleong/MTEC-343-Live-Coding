I used the piano patch to create a twinkle twinkle inspired song, I used rhythms to create effects in the music.

final code:
```
// ᓚᘏᗢ
cpm (120/4)
$: note("e5 e5 e5 e5 c6 c6 c6 c6 g6 g6 g6 g6 f5 f5 f5 f5").s("piano").ply("<1 2 3 4>").gain(.15)
$: note("c a f e d e f g").s("piano")
$: note("f c [~ e] f").ply("<1 2 3>").s("piano")
$: note("c3 e3 g3 f3").s("piano")
$: note(`<
[c6 c6 g6 g6] 
[c6 - g6 -]
[f6 e6 d6 e6]
[d6 - e6 -]
[c6 - - -]
>`).s("piano").room(2).roomsize(2).gain(3)
$: note(`<
[c7 c6 c7 c6 - c7 c6 -]
[c7 - c7 - - c7 - -]
[- - - - - - - -] 
[c7 c7 c7 c7 c7 c7 c7 c7]
[- - - - - - - -] 
[- - - - - - - -] 
[- - - - - - - -]
[g7 g7 g7 g7 g7 g7 g7 g7]
[- - - - - - - -] 
[c7 c6 c7 c6 - c7 c6 -]
[c7 - c7 - - c7 - -]
[c7 c6 c7 c6 - c7 c6 -]
[c7 - c7 - - c7 - -]
>`).s("piano").gain(2)
```