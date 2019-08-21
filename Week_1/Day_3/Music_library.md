# Music library


Input looks like the following:
```
const library = {
  tracks: { t01: { id: "t01",
    name: "Code Monkey",
    artist: "Jonathan Coulton",
    album: "Thing a Week Three" },
  t02: { id: "t02",
    name: "Model View Controller",
    artist: "James Dempsey",
    album: "WWDC 2003"},
  t03: { id: "t03",
    name: "Four Thirty-Three",
    artist: "John Cage",
    album: "Woodstock 1952"}
  },
  playlists: { p01: { id: "p01",
    name: "Coding Music",
    tracks: ["t01", "t02"]
  },
  p02: { id: "p02",
    name: "Other Playlist",
    tracks: ["t03"]
  }
  }
};
```

We can make this more readable by adding whitespace:
```
const library = {
  tracks: { 
    t01: { 
      id: "t01",
      name: "Code Monkey",
      artist: "Jonathan Coulton",
      album: "Thing a Week Three" },
    
    t02: { 
      id: "t02",
      name: "Model View Controller",
      artist: "James Dempsey",
      album: "WWDC 2003"},
    
    t03: { 
      id: "t03",
      name: "Four Thirty-Three",
      artist: "John Cage",
      album: "Woodstock 1952"}
  },
  
  
  playlists: { 
    p01: {
      id: "p01",
      name: "Coding Music",
      tracks: ["t01", "t02"]
    },

    p02: { 
      id: "p02",
      name: "Other Playlist",
      tracks: ["t03"]
    }
  }
};
```

Since `playlists` and `tracks` are objects themselves, you can loop through them with a `for-in` loop, like this:
```
for (let key in library.playlists) {...}
for (let key in library.tracks) {...}
```

This will give you the key of each item. Looping through `playlists`, for example, will set the `key` variable to `p01` then `p02` because those are the keys in   `playlists`.

```
//Playlists object in library
playlists: { 
  p01: {
    id: "p01",
    name: "Coding Music",
    tracks: ["t01", "t02"]
  },

  p02: { 
    id: "p02",
    name: "Other Playlist",
    tracks: ["t03"]
  }
}
```

Since you now have the key, you can directly access the values in the `playlists` object.

```
library.playlists[key].name
```
```
library.playlists[key].tracks

//since tracks is an array, you can access it even further
library.playlists[key].tracks[0]
library.playlists[key].tracks[1]
...
```

