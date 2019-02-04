# javascript-no-escape-game
Maze game created with just JavaScript.  Initial version built over a weekend, but will add to it over time (see ToDos).  Purposely made some design choices and coding choices to show off some of the later ecmaScript options (there are easier ways to do some of this, for sure).

Hosted: [Site](http://www.shaylershepherd.com/noescape/index.html)

## Revision Log
### February 2nd/3rd, 2019
- Switch to Static Map ~ Initial designs had the game moving sideways at a constant rate (depending on difficulty) and all routes visible similar to the side-scrolling "Game & Watch" handheld that I played as a kid.  This would add a lot of complexity for redrawing the maze with every tick and then having to manage moving the character.  Also items wouldn't make as much sense for what I'd had planned.  Decided to stick to a static map but having extensive items and multiple difficulties to offset it being less static.  

- Added Lighting Mechanic ~ To add some difficulty to the game, and a bit of themeing, decided to limit visibility of map.  Items will be able to extend the range of vision, but it starts out pretty small.  Did a [rough test](http://shaylershepherd.com/images/escape_lighting_01.PNG) of background/border/opacity to see if it would work.  Will have to change how the player and positioning is done though as now the "player" might just be an abs positioned overlay on top of the map and the maze knows where you are based on positioning.

- Replace Nested Binary Array with Nested Object Array ~ The nested binary array "Map" will still be required to build the level, but it should be replaced with a class-based nested object array.  This will be much more extendable in the future and when the randomly generated levels are implemented (and the binary map won't be required at all) it will require almost no changing.

## ToDos
- Items ~ Each level should have randomly generated items spread throughout for use on the map.  This includes an item to break through a single wall of the maze, an item to double the "light" being created (through incresting the size of radial gradient), an item that inverts the whole maze (simple invert of the top/left walls being drawn), and an item to remove the "darkness" for 1 second (possibly more, depending on balancing).

- UI Update ~ The interface isn't complete and to have both theming and controls for game.

- Randomly Generated Levels ~ The game currently relies on statically created maps, but can have random mazes.  To ensure that the randomly generated maps are completable, I will create a generated route to the end first...and then create the walls around it randomly.  This will also provide a function to test whether any given map is completable.  Definitely some trial and error needed to keep it fun and make sure the mazes are completable.  

- Sound ~ There should be a very light positive sound when the player moves, a slight negative sound when the player can't move in a direction, and a victory sound when the level is done.  Will simply use my own recording whatnot to get these sounds and avoid copyright infringment issues.
