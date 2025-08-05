# Core Operations: Add, Remove, Update, Access

## Part 1: The Audition - Accessing Songs by Position

**_The Power of Direct Access_**

Just like Alex's organized songbook, arrays provide instant access to any element when you know its position (index). This is one of the most fundamental and powerful array operations.

```js
// Alex's current setlist for the audition
const alexsSetlist = [
  "Wonderwall", // index 0 - opening song
  "Hotel California", // index 1 - crowd pleaser
  "Blackbird", // index 2 - acoustic showcase
  "Sweet Child O' Mine", // index 3 - rock anthem
  "Hallelujah", // index 4 - emotional closer
];

// Marcus wants to hear the third song (index 2)
const requestedSong = alexsSetlist[2];
console.log(`Now playing: ${requestedSong}`); // "Now playing: Blackbird"

// Alex can instantly access any song
const openingSong = alexsSetlist[0]; // "Wonderwall"
const closingSong = alexsSetlist[4]; // "Hallelujah"
const totalSongs = alexsSetlist.length; // 5
```

> "I learned that organizing songs by position makes everything O(1) time complexity - no matter if I have 5 songs or 500 songs, finding a specific position always takes the same amount of time."

## Why Position-Based Access is Lightning Fast

"Well," Alex explains, strumming a chord, "imagine if I had to search through every song one by one until I found the right one. With 100 songs, I might have to check 50 songs on average. But with position-based access, I jump directly to song #3 - boom, done!"

```js
// Efficient: Direct access by position (O(1))
const song = setlist[2]; // Always instant, regardless of setlist size

// Inefficient: Searching through everything (O(n))
function findSongByTitle(setlist, title) {
  for (let i = 0; i < setlist.length; i++) {
    if (setlist[i] === title) {
      return i; // Might have to check every song!
    }
  }
  return -1;
}
```

**_⏱️ Alex's First Challenge!_**

```js
function getSongAtPosition(setlist, position) {
  // Return the song at the given position
  // Check if position is within bounds
  if (position >= 0 && position < setlist.length) {
    return setlist[position];
  } else {
    // Handle invalid positions gracefully
    return "Invalid position";
  }
}

const alexsSetlist = [
  "Wonderwall",
  "Hotel California",
  "Blackbird",
  "Free Bird",
];
console.log("Song at position 2:", getSongAtPosition(alexsSetlist, 2)); // Blackbird
console.log("Song at position 10:", getSongAtPosition(alexsSetlist, 10)); // Invalid position
```

## Part 2: The Rehearsal - Updating Songs in the Setlist

**_The Art of Song Substitution(Update)_**

```js
// Alex's original setlist
let rehearsalSetlist = [
  "Wonderwall",
  "Hotel California",
  "Blackbird", // Marcus wants this changed
  "Sweet Child O' Mine",
  "Hallelujah",
];

console.log("Original setlist:", rehearsalSetlist);

// Update the third song (index 2) based on Marcus's feedback
rehearsalSetlist[2] = "Don't Stop Believin'";

console.log("Updated setlist:", rehearsalSetlist);
// ["Wonderwall", "Hotel California", "Don't Stop Believin'", "Sweet Child O' Mine", "Hallelujah"]

// Alex can update any position instantly
rehearsalSetlist[0] = "Come As You Are"; // New opener
rehearsalSetlist[4] = "Bohemian Rhapsody"; // Epic closer

console.log("Final rehearsal setlist:", rehearsalSetlist);
```

> "That's the beauty of O(1) update operations. I can replace any song in any position without affecting the others. It's like having numbered slots - I just swap out what's in slot #3."

**_Why Updates Are So Efficient_**

> "Think of it like a jukebox," Alex explains to a curious customer. "Each song has a specific slot number. When I want to change song #3, I don't have to move songs #1, #2, #4, or #5. I just replace what's in that exact slot."

```js
// Multiple updates - all O(1) operations
function customizeSetlist(setlist, preferences) {
  // Each update is instant, regardless of setlist size
  if (preferences.wantsRock) {
    setlist[0] = "Thunderstruck"; // O(1)
  }

  if (preferences.wantsAcoustic) {
    setlist[2] = "Tears in Heaven"; // O(1)
  }

  if (preferences.wantsClassic) {
    setlist[4] = "Stairway to Heaven"; // O(1)
  }

  return setlist;
}

// Alex can customize any setlist instantly
let customSet = ["Song 1", "Song 2", "Song 3", "Song 4", "Song 5"];
customizeSetlist(customSet, { wantsRock: true, wantsClassic: true });
console.log(customSet);
```

**_⏱️ Alex's Rehearsal Challenge!_**

```js
function updateSetlistBasedOnFeedback(setlist, updates) {
  // Loop through each key in the updates object (these are indices as strings)
  for (let index in updates) {
    // Ensure the index is within the bounds of the setlist array
    if (index >= 0 && index < setlist.length) {
      // Apply the update: replace the song at this index with the new one from feedback
      setlist[index] = updates[index];
    }
  }

  // Return the modified setlist (this step is optional if you're modifying in place)
  return setlist;
}

let performanceSet = ["Song A", "Song B", "Song C", "Song D"];
const feedback = { 0: "Thunderstruck", 2: "Don't Stop Believin'" };
updateSetlistBasedOnFeedback(performanceSet, feedback);
console.log("Updated setlist:", performanceSet);
```

## Part 3: The First Performance - Adding New Songs to the Repertoire

**_Adding Songs to the End - The Encore Approach_**

```js
// Alex's current performance setlist
let tonightSetlist = [
  "Come As You Are",
  "Hotel California",
  "Don't Stop Believin'",
  "Sweet Child O' Mine",
];

// Adding an encore song to the end (most common and efficient)
tonightSetlist.push("Free Bird");
console.log("With encore:", tonightSetlist);
// ["Come As You Are", "Hotel California", "Don't Stop Believin'", "Sweet Child O' Mine", "Free Bird"]

// Alex can add multiple encore songs
tonightSetlist.push("Stairway to Heaven", "Bohemian Rhapsody");
console.log("Extended encore:", tonightSetlist);
```

> "Adding to the end is O(1) time complexity," Alex explains to a fellow musician in the audience. "It's like adding another page to the back of my songbook - quick and doesn't disturb anything else."

**_Adding Songs to the Beginning - The Grand Opening_**

```js
// Adding a new opening song
let dynamicSetlist = [
  "Hotel California",
  "Don't Stop Believin'",
  "Sweet Child O' Mine",
];

// Add a powerful opener to the beginning
dynamicSetlist.unshift("Thunderstruck");
console.log("With new opener:", dynamicSetlist);
// ["Thunderstruck", "Hotel California", "Don't Stop Believin'", "Sweet Child O' Mine"]

// Alex can add multiple opening songs
let grandOpening = ["Intro Jam"];
grandOpening.unshift("Sound Check", "Welcome Speech");
console.log("Grand opening sequence:", grandOpening);
// ["Sound Check", "Welcome Speech", "Intro Jam"]
```

> "But here's the thing," Alex notes, adjusting their guitar strap, "adding to the beginning is O(n) time complexity. Every song after the new opener has to 'shift down' one position in my setlist. With a small setlist, no problem. But imagine if I had 100 songs - they'd all have to move!"

**_Adding Songs in the Middle - The Perfect Transition_**

```js
// Current high-energy sequence
let energySetlist = [
  "Thunderstruck",
  "Sweet Child O' Mine", // Too intense back-to-back
  "Free Bird",
];

// Insert a mellow song between the rock anthems
energySetlist.splice(1, 0, "Tears in Heaven");
console.log("With transition song:", energySetlist);
// ["Thunderstruck", "Tears in Heaven", "Sweet Child O' Mine", "Free Bird"]

// Alex can insert multiple transition songs
let flowSetlist = ["Rock Song 1", "Rock Song 2"];
flowSetlist.splice(1, 0, "Acoustic Ballad", "Jazz Interlude");
console.log("Improved flow:", flowSetlist);
// ["Rock Song 1", "Acoustic Ballad", "Jazz Interlude", "Rock Song 2"]
```

> "Inserting in the middle is also O(n) time complexity," Alex explains to Marcus during the break. "When I insert 'Tears in Heaven' at position 1, both 'Sweet Child O' Mine' and 'Free Bird' have to shift to make room. The more songs after the insertion point, the more shifting required."

**_Understanding the Performance Trade-offs_**

```js
// Fast additions - use these when possible
function efficientSongManagement() {
  let setlist = ["Song 1", "Song 2", "Song 3"];

  // Adding to end - always fast (O(1))
  setlist.push("Encore Song"); // Instant!
  setlist.push("Final Song"); // Still instant!

  return setlist;
}

// Slower additions - use sparingly during busy performances
function carefulSongManagement() {
  let setlist = ["Song 1", "Song 2", "Song 3"];

  // Adding to beginning - gets slower with more songs (O(n))
  setlist.unshift("New Opener"); // Shifts everything

  // Adding to middle - also gets slower (O(n))
  setlist.splice(2, 0, "Transition"); // Shifts some songs

  return setlist;
}
```

**_⏱️ Alex's Performance Challenge!_**

```js
//Task: Create a function that adds songs using the most efficient method based on position

function addSongStrategically(setlist, song, position) {
  // If position is "end", append the song to the end (O(1))
  if (position === "end") {
    setlist.push(song);
  }
  // If position is "beginning", add the song to the start (O(n))
  else if (position === "beginning") {
    setlist.unshift(song);
  }
  // If position is a number, insert the song at that index using splice (O(n))
  else if (
    typeof position === "number" &&
    position >= 0 &&
    position <= setlist.length
  ) {
    setlist.splice(position, 0, song); // Insert at the given index without removing anything
  }
  // Handle invalid position inputs
  else {
    console.warn(`Invalid position "${position}". Song not added.`);
  }

  // Return the updated setlist (optional since we're mutating in place)
  return setlist;
}

let strategicSet = ["Hotel California", "Sweet Child O' Mine"];
addSongStrategically(strategicSet, "Thunderstruck", "beginning");
addSongStrategically(strategicSet, "Free Bird", "end");
addSongStrategically(strategicSet, "Wonderwall", 2);
console.log("Strategic setlist:", strategicSet);
```

## Part 4: The Late Night Set - Removing Songs from the Repertoire

**_Removing the Last Song - The Quick Exit_**

```js
// Alex's current setlist with a song that didn't work
let lateNightSet = [
  "Thunderstruck",
  "Hotel California",
  "Don't Stop Believin'",
  "Experimental Jazz Fusion", // This one confused the crowd
];

// Remove the last song (most efficient removal)
let removedSong = lateNightSet.pop();
console.log(`Removed: ${removedSong}`); // "Removed: Experimental Jazz Fusion"
console.log("Updated setlist:", lateNightSet); // Ends with "Don't Stop Believin'" now

// Alex can quickly remove multiple songs from the end
let extendedSet = ["Song 1", "Song 2", "Song 3", "Song 4", "Song 5"];
let lastTwo = [extendedSet.pop(), extendedSet.pop()];
console.log("Removed songs:", lastTwo); // ["Song 5", "Song 4"]
console.log("Shortened set:", extendedSet); // ["Song 1", "Song 2", "Song 3"]
```

> "Removing from the end is O(1) time complexity," Alex notes while tuning their guitar. "It's like tearing off the last page of my songbook - quick, clean, and doesn't affect anything else."

**_Removing the First Song - The New Beginning_**

```js
// Current setlist with a weak opener
let crowdSetlist = [
  "Slow Ballad", // Not working for this energetic crowd
  "Thunderstruck",
  "Sweet Child O' Mine",
  "Free Bird",
];

// Remove the first song and let "Thunderstruck" be the opener
let oldOpener = crowdSetlist.shift();
console.log(`Removed opener: ${oldOpener}`); // "Removed opener: Slow Ballad"
console.log("New setlist:", crowdSetlist); // Now starts with "Thunderstruck"

// The crowd immediately perks up with the new opener!
console.log(`New opener: ${crowdSetlist[0]}`); // "New opener: Thunderstruck"
```

> "But removing from the beginning is O(n) time complexity," Alex explains to a curious bartender. "When I remove 'Slow Ballad', every other song has to 'shift up' one position. 'Thunderstruck' moves from position 1 to position 0, and so on."

**_Removing Songs from the Middle - The Perfect Edit_**

```js
// Setlist with an awkward middle section
let flowSetlist = [
  "Thunderstruck",
  "Hotel California",
  "Polka Medley", // This kills the rock vibe
  "Country Roads", // This too - wrong genre
  "Sweet Child O' Mine",
  "Free Bird",
];

// Remove the two songs that break the flow
let removedSongs = flowSetlist.splice(2, 2);
console.log("Removed awkward section:", removedSongs); // ["Polka Medley", "Country Roads"]
console.log("Improved flow:", flowSetlist);
// ["Thunderstruck", "Hotel California", "Sweet Child O' Mine", "Free Bird"]

// Now the rock energy flows perfectly!
```

> "Removing from the middle is also O(n) time complexity," Alex explains while adjusting their amp. "When I remove those two songs at positions 2 and 3, 'Sweet Child O' Mine' and 'Free Bird' have to shift left to fill the gaps."

**_Strategic Removal Decisions_**

> "It's all about understanding the trade-offs:"

```js
// Efficient removals - use when possible
function quickSetlistEdits() {
  let setlist = ["Song 1", "Song 2", "Song 3", "Song 4"];

  // Remove from end - always fast (O(1))
  let lastSong = setlist.pop(); // Instant removal

  return { setlist, removed: lastSong };
}

// Slower removals - use when necessary for artistic reasons
function carefulSetlistEdits() {
  let setlist = ["Weak Opener", "Song 2", "Bad Transition", "Song 4"];

  // Remove from beginning - slower but sometimes necessary (O(n))
  let badOpener = setlist.shift(); // All songs shift left

  // Remove from middle - also slower but improves flow (O(n))
  let badTransition = setlist.splice(1, 1)[0]; // Some songs shift left

  return { setlist, removed: [badOpener, badTransition] };
}

// Alex's performance philosophy
console.log("Quick edits for efficiency, careful edits for artistry!");
```

**_⏱️ Alex's Late Night Challenge!_**

```js
//Task: Create a function that removes songs using the most efficient method

function removeSongStrategically(setlist, position) {
  // If position is "end", remove the last song using pop (O(1))
  if (position === "end") {
    return setlist.pop();
  }

  // If position is "beginning", remove the first song using shift (O(n))
  else if (position === "beginning") {
    return setlist.shift();
  }

  // If position is a valid number, remove the song at that index using splice (O(n))
  else if (
    typeof position === "number" &&
    position >= 0 &&
    position < setlist.length
  ) {
    // splice returns an array of removed items, so we return the first (and only) element
    return setlist.splice(position, 1)[0];
  }

  // If position is invalid, return undefined and optionally log a warning
  else {
    console.warn(`Invalid position "${position}". No song removed.`);
    return undefined;
  }
}

let removalSet = [
  "Thunderstruck",
  "Hotel California",
  "Wonderwall",
  "Free Bird",
];
console.log("Removed from end:", removeSongStrategically(removalSet, "end"));
console.log(
  "Removed from beginning:",
  removeSongStrategically(removalSet, "beginning")
);
console.log("Removed from position 1:", removeSongStrategically(removalSet, 1));
console.log("Final setlist:", removalSet);
```

## Part 5: The Encore - Finding Songs in the Repertoire

**_Finding Songs by Title - The Search Mission_**

```js
// Alex's full repertoire for tonight
const fullRepertoire = [
  "Thunderstruck",
  "Hotel California",
  "Don't Stop Believin'",
  "Sweet Child O' Mine",
  "Wonderwall",
  "Stairway to Heaven",
  "Free Bird",
  "Bohemian Rhapsody",
];

// Customer requests "Wonderwall"
const wonderwallPosition = fullRepertoire.indexOf("Wonderwall");
if (wonderwallPosition !== -1) {
  console.log(`Found Wonderwall at position ${wonderwallPosition}!`); // Position 4
  console.log("Playing it next!");
} else {
  console.log("Sorry, I don't know that song yet.");
}

// Multiple requests coming in
const requests = ["Stairway to Heaven", "Smoke on the Water", "Free Bird"];
requests.forEach((song) => {
  const position = fullRepertoire.indexOf(song);
  if (position !== -1) {
    console.log(`✓ I can play ${song} (position ${position})`);
  } else {
    console.log(`✗ I don't know ${song} yet`);
  }
});
```

> "Finding songs by title is O(n) time complexity," Alex explains to an aspiring musician in the crowd. "In the worst case, I might have to check every song in my repertoire until I find the one you requested - or discover I don't know it."

**_Finding Songs by Characteristics - The Advanced Search_**

```js
// Alex's repertoire with song characteristics
const detailedRepertoire = [
  { title: "Thunderstruck", genre: "rock", tempo: "fast", mood: "energetic" },
  {
    title: "Hotel California",
    genre: "rock",
    tempo: "medium",
    mood: "mysterious",
  },
  {
    title: "Wonderwall",
    genre: "alternative",
    tempo: "medium",
    mood: "nostalgic",
  },
  {
    title: "Tears in Heaven",
    genre: "ballad",
    tempo: "slow",
    mood: "emotional",
  },
  { title: "At Last", genre: "jazz", tempo: "slow", mood: "romantic" },
];

// Find a song perfect for slow dancing
const slowDanceSong = detailedRepertoire.find(
  (song) =>
    song.tempo === "slow" &&
    (song.mood === "romantic" || song.mood === "emotional")
);

if (slowDanceSong) {
  console.log(`Perfect for slow dancing: ${slowDanceSong.title}`);
  // "Perfect for slow dancing: At Last"
} else {
  console.log("Let me learn some romantic ballads!");
}

// Find all rock songs for an energetic set
const rockSongs = detailedRepertoire.filter((song) => song.genre === "rock");
console.log(
  "Rock songs available:",
  rockSongs.map((song) => song.title)
);
// ["Thunderstruck", "Hotel California"]
```

> "Advanced searching is also O(n) time complexity," Alex notes while setting up for the next song. "I have to examine each song's characteristics until I find what matches your criteria."

**_Building a Smart Song Finder_**

```js
class SongFinder {
  constructor(repertoire) {
    this.repertoire = repertoire;
  }

  // Find song by exact title (O(n))
  findByTitle(title) {
    const index = this.repertoire.findIndex(
      (song) => song.title.toLowerCase() === title.toLowerCase()
    );
    return index !== -1
      ? { song: this.repertoire[index], position: index }
      : null;
  }

  // Find songs by genre (O(n))
  findByGenre(genre) {
    return this.repertoire.filter(
      (song) => song.genre.toLowerCase() === genre.toLowerCase()
    );
  }

  // Find songs by mood (O(n))
  findByMood(mood) {
    return this.repertoire.filter(
      (song) => song.mood.toLowerCase() === mood.toLowerCase()
    );
  }

  // Smart search - find songs matching multiple criteria (O(n))
  smartSearch(criteria) {
    return this.repertoire.filter((song) => {
      return Object.keys(criteria).every(
        (key) =>
          song[key] && song[key].toLowerCase() === criteria[key].toLowerCase()
      );
    });
  }

  // Get random song for inspiration (O(1))
  getRandomSong() {
    const randomIndex = Math.floor(Math.random() * this.repertoire.length);
    return this.repertoire[randomIndex];
  }
}

// Alex uses their new song finder
const alexsFinder = new SongFinder(detailedRepertoire);

// Handle various requests efficiently
console.log("Looking for Wonderwall:", alexsFinder.findByTitle("wonderwall"));
console.log("All ballads:", alexsFinder.findByGenre("ballad"));
console.log("Energetic songs:", alexsFinder.findByMood("energetic"));
console.log(
  "Slow rock songs:",
  alexsFinder.smartSearch({ genre: "rock", tempo: "slow" })
);
console.log("Random inspiration:", alexsFinder.getRandomSong());
```

**_⏱️ Alex's Encore Challenge!_**

```js
function findSongsForRequest(repertoire, criteria) {
  // Use filter to return only songs where all criteria match
  return repertoire.filter((song) => {
    // Check every key in the criteria object
    for (let key in criteria) {
      // If the song doesn't match the current criterion, exclude it
      if (song[key] !== criteria[key]) {
        return false;
      }
    }
    // If all criteria match, include the song
    return true;
  });
}

const alexsRepertoire = [
  { title: "Thunderstruck", genre: "rock", mood: "energetic" },
  { title: "Hotel California", genre: "rock", mood: "mysterious" },
  { title: "Wonderwall", genre: "alternative", mood: "nostalgic" },
  { title: "Tears in Heaven", genre: "ballad", mood: "emotional" },
];

console.log(
  "Rock songs:",
  findSongsForRequest(alexsRepertoire, { genre: "rock" })
);
console.log(
  "Energetic rock:",
  findSongsForRequest(alexsRepertoire, { genre: "rock", mood: "energetic" })
);
```

## Alex's Musical Mastery: The Four Core Operations

**_🎯 The Four Pillars of Array Mastery_**

1. Access by Index - The Instant Lookup (O(1))
   "When someone asks for 'the third song,' I can find it instantly."

```js
const song = setlist[2]; // Always instant, regardless of setlist size
```

2. Update Elements - The Perfect Substitution (O(1))
   "Swapping one song for another in a specific position is lightning-fast."

```js
setlist[2] = "New Song"; // Instant replacement, no shifting required
```

3. Add Elements - The Strategic Expansion
   - To End (O(1)): "Adding encore songs is always fast"
   - To Beginning/Middle (O(n)): "Powerful but requires shifting other songs"

```js
setlist.push("Encore"); // Fast addition
setlist.unshift("New Opener"); // Slower but sometimes necessary
setlist.splice(2, 0, "Interlude"); // Strategic insertion
```

4. Remove Elements - The Artistic Edit
   - From End (O(1)): "Dropping the last song is effortless"
   - From Beginning/Middle (O(n)): "Sometimes needed for better flow"

```js
setlist.pop(); // Quick removal
setlist.shift(); // Slower but improves opening
setlist.splice(2, 1); // Strategic removal for better flow
```

5. Find Elements - The Request Handler (O(n))
   "Searching through my repertoire to fulfill audience requests."

```js
const position = setlist.indexOf("Wonderwall"); // Find by exact match
const song = setlist.find((s) => s.mood === "romantic"); // Find by criteria
```

**_🎸 Alex's Performance Philosophy_**

1. Use O(1) operations (access, update, end additions/removals) during busy performances when speed matters most
2. Use O(n) operations (beginning/middle modifications, searching) strategically when the artistic benefit outweighs the performance cost
3. Design your setlist structure to favor the operations you'll use most frequently
4. Batch similar operations when possible to minimize disruption
