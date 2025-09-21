Project Specification: Sky Castle (A Text Adventure)**

**1. Game Title:** Sky Castle

**2. Genre:** Text Adventure / Interactive Fiction

**3. Platform:** Command Line Interface (CLI) - Python

**4. Core Concept:** A young boy embarks on a quest through a fantastical, cloud-borne castle, inspired by the lyrics of "Just the Two of Us," to find his lost father. The castle is a labyrinth of whimsical rooms, emotional resonance, and challenging puzzles, all designed around themes of memory, love, patience, and connection.

**5. Player Character:** A boy (unnamed, or player-named upon request), determined to find his father.

**6. Core Gameplay Loop:**
    *   **Explore:** Navigate through various rooms of the Sky Castle.
    *   **Observe:** `look` around rooms for descriptions, items, and hints. `look [item]` to inspect specific objects.
    *   **Interact:** `take` items, `drop` items, and `use` items to solve puzzles.
    *   **Solve Puzzles:** Use items and environmental clues to overcome obstacles that block progression or reveal new paths.
    *   **Progress Narrative:** Each solved puzzle or key action moves the player closer to finding their father and understanding the castle's secrets.

**7. Key Features:**

*   **Text-Based Interface:** All interaction is via text input and output.
*   **Whimsical Colored Text:** Use of `colorama` or similar library for legible, aesthetically pleasing, and thematically appropriate colored text output to enhance immersion.
*   **Inventory System:** Players can `take` items from rooms, `drop` items into current rooms, and view their `inventory` at any time.
*   **Non-linear Exploration:** Multiple paths and puzzles will be available from central points, allowing players to tackle challenges in various sequences. Room exits can be conditional (e.g., locked until a puzzle is solved).
*   **Event-Driven "Time":** No real-time clock. "Time" (e.g., "morning," "night," seasons) advances only upon the completion of specific puzzles or significant game events, impacting environmental states (e.g., a "morning" event might make dewdrops appear). This avoids constant pressure and allows players to explore at their own pace.
*   **Persistent Game State:** The state of rooms (items present, puzzles solved, exits unlocked) will persist as the player moves.
*   **Winning Condition:** Successfully locating and reuniting with the father in the final room (Sky-High Summit).

**8. Technical Requirements (Python):**

*   **Modular Design:** Separate components for rooms, items, player, parser, and game logic.
*   **Data Structures:**
    *   **`Room` objects:** Store description, items present, exits (with conditions), and puzzle states.
    *   **`Item` objects:** Store name, description, and properties (e.g., `is_collectible`, `is_usable`).
    *   **`Player` object:** Store current location, inventory, and potentially a list of solved puzzles or flags.
*   **Command Parser:** Robustly handle player input and map it to game actions (e.g., `go north`, `take crystal`).
*   **Text Formatting:** Integration with `colorama` (or similar) for colored output.
*   **Game Loop:** Continuously process player input, update game state, and display output.

**9. Game World & Narrative Elements:**

*   **Setting:** The Sky Castle – a fantastical, cloud-borne structure built from dreams and memories. Its architecture and atmosphere are constantly shifting, reflecting the lyrical inspirations.
*   **Central Conflict:** The father is lost within the castle's depths or has become absorbed in its creation, and the son must find him. The "lost" aspect could be metaphorical, e.g., he's deeply engrossed in a complex project, and the son needs to complete a final piece to reach him.
*   **Themes:** Love, perseverance, shared dreams, understanding, emotional maturity, making good use of time/effort ("wasted water's all that is").
*   **Climax:** Reunion at the Sky-High Summit, symbolizing the fulfillment of their shared "castle in the sky."

**10. Initial Room & Puzzle Concepts (from Brainstorming):**

*   **Crystal Atrium:**
    *   **Description:** Grand entrance, walls of shimmering crystal with "raindrops."
    *   **Item:** `Tuning Fork` (initially hidden or found in another room).
    *   **Puzzle:** Use `Tuning Fork` to resonate crystals, revealing a hidden path or opening an exit.
    *   **Exits:** To Rainbow Gallery, Wasted Waterworks, (potentially) Father's Study.
*   **Rainbow Gallery:**
    *   **Description:** Stained-glass panels, missing parts of the rainbow spectrum.
    *   **Item:** `Pocket Mirror / Prism` (to be found).
    *   **Puzzle:** Position `Pocket Mirror/Prism` to complete the rainbow, unlocking a gate or revealing a clue.
    *   **Exits:** To Crystal Atrium, Father's Study.
*   **Wasted Waterworks:**
    *   **Description:** Cavernous chamber with strong but misdirected water flow, barren earth.
    *   **Item:** `Seed of Unity` (to be found).
    *   **Puzzle:** Divert water flow using an environmental control or direct the `Seed of Unity` into the flow to fertilize a previously barren spot, making a unique flower grow and opening a path.
    *   **Exits:** To Crystal Atrium, Garden of Patience.
*   **Garden of Patience:**
    *   **Description:** Beautiful but dormant garden, perhaps with intricate mechanisms that suggest a need for timing.
    *   **Item:** A small `Stone of Observation` (perhaps provides hints).
    *   **Puzzle:** The `Seed of Unity` (from Waterworks) needs to be planted here. "Time" (event completion) must pass for it to bloom, revealing an item or opening an exit.
    *   **Exits:** To Wasted Waterworks, Dawning Outlook.
*   **Father's Study/Memory Alcove:**
    *   **Description:** A cluttered room with personal effects, notes, and incomplete blueprints.
    *   **Items:** `Fragmented Blueprint Piece 1`, `Father's Journal` (containing hints or a riddle).
    *   **Puzzle:** Decipher a riddle from the `Father's Journal` or piece together `Fragmented Blueprint` to unlock a hidden compartment or reveal the location of another key item.
    *   **Exits:** To Rainbow Gallery, (potentially) Dawning Outlook.
*   **Dawning Outlook/Morning Dew Glade:**
    *   **Description:** A high, serene glade that is misty and becomes vibrant with the rising sun.
    *   **Item:** `Empty Dewdrop Vial`.
    *   **Puzzle:** The "morning" event (triggered by a previous puzzle) must occur. Use the `Empty Dewdrop Vial` to collect `Morning Dew` which is a key ingredient for a later puzzle.
    *   **Exits:** To Garden of Patience, Sky-High Summit.
*   **Sky-High Summit/Grand Workshop (Final Room):**
    *   **Description:** The unfinished pinnacle of the castle, a grand workshop with scattered tools, and a magnificent view.
    *   **Items:** `Fragmented Blueprint Piece 2`, `Father's Final Note`.
    *   **Puzzle:** Present or assemble all collected `Fragmented Blueprint Pieces` here. This reveals the father, perhaps engrossed in completing the ultimate `Castle in the Sky` project.
    *   **Exits:** To Dawning Outlook (initially, until father is found).

**11. Player Commands (Initial Set):**

*   `go [north/south/east/west/up/down/roomname]`
*   `look` (provides room description)
*   `look [itemname]` (provides item description)
*   `take [itemname]`
*   `drop [itemname]`
*   `inventory` or `i`
*   `use [itemname]` (interact with an item, context-sensitive)
*   `help` (lists available commands)
*   `quit`

---

Song Lyrics

I see the crystal raindrops fall
And the beauty of it all
Is when the sun comes shining through
To make those rainbows in my mind
When I think of you sometime
And I wanna spend some time with you

Just the two of us, we can make it if we try
Just the two of us (Just the two of us)
Just the two of us, building castles in the sky
Just the two of us, you and I

We look for love, no time for tears
Wasted water's all that is
And it don't make no flowers grow
Good things might come to those who wait
Not for those who wait too late
We gotta go for all we know

Just the two of us, we can make it if we try
Just the two of us (Just the two of us)
Just the two of us, building them castles in the sky
Just the two of us, you and I

I hear the crystal raindrops fall
On the window down the hall
And it becomes the morning dew
And darling when the morning comes
And I see the morning sun
I wanna be the one with you

Just the two of us, we can make it if we try
Just the two of us (Just the two of us)
Just the two of us, building big castles way on high
Just the two of us, you and I

(Just the two of us) We can make it, just the two of us
Let's get it together baby (yeah)
(Just the two of us) Just the two of us
(We can make it, just the two of us)
