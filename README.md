# Software Construction - Behind the App: Thinking Like Software Engineers

**Course:** Software Construction   

**Assignment Type:** Mobile application analysis 

**Group Members:** Rebecca Alinda., Anna Akumu., Namaganda Wakabi Precious., Odongkara Oscar., Joseph Mukama

**Selected App:** Spotify  

This README contains our group's complete submission for Assignment 1. We analyzed Spotify, a music streaming app we all use frequently for discovering and listening to music, podcasts, and more.

## 1. App Overview

**What problem does this app solve?**  
1. Relation to Copyright, spotify provides legal, licensed access to music, reducing illegal copying. Artists and record labels are paid for streams, which protects copyright ownership. By making music easy and affordable to access, Spotify helps prevent copyright infringement.
2. Centralizing Music Genres, before Spotify, music was spread across platforms like HowBizz for local Ugandan music, Tubidy for international pop and hip-hop, and Boomplay for African genres. Spotify brought all these genres into one platform, making music easier to find and enjoy in one place.
3. 
**Who are its primary users?
1. Music enthusiasts within a specific age range(most preferably youth).
2. Music artists and producers looking to sell their music.


## 2. Core Features

List 5–7 key features of Spotify (based on current app experience):

1. User authentication/The login and registration.
2. The search button: There is no way to get quick access to most of the stored playlists and albums minus using the search button.
3. Offline Downloads: Permits saving content for offline use, emphasizing data storage strategies for reliability.
4. Lyrics Display(Real-Time Synced): Shows timed lyrics during playback, a feature that ties UI with timing algorithms.
5. Personalized Recommendations: Made for You sections like Daily Mixes, Discover Weekly, and Release Radar based on listening history.
6. Creation and management of playlists: Create, edit, share, and collaborate on playlists; add/remove tracks.
7. Streaming Playback & Controls 


## Part B: Thinking Behind the Scenes

**Feature 1: User authentication/The login and registration.**
 - Likely software components involved:
 - User Interface (UI)
     Login screen with options:
        Continue with email
        Continue with phone number
        Continue with Google
     If email is selected → user is taken to an email and password screen
     If phone number is selected → user is taken to a screen to enter phone number
     If Google is selected → user is shown a list of Google accounts to choose from
     This shows how the app guides the user step-by-step.
  - Business Logic
      Determines which login option the user selected
      Validates email/password or phone number
      Handles Google authentication flow
      Creates a secure user session after successful login
  - Network / APIs
      Communicates with Spotify authentication servers
      Uses Google authentication APIs for “Continue with Google”
      Sends and verifies login credentials
  - Data Storage
      Stores authentication tokens locally on the device
      Stores user account data securely on Spotify servers
  - It requires internet, if there is no internet then the authentication process will not go through.
  - If the network is slow or unavailable:
      Login pages may not load
      Verification may fail
      User cannot access their account

Feature 2: The search button   
- Likely software components involved:  
  - User Interface (UI): Top search bar with autocomplete suggestions, category tabs (Songs, Artists, Albums, Playlists, Podcasts), grid/list of results with album art, titles, and play buttons.
  - Business logic: Processes user query, applies ranking (popularity + personal history), generates autocomplete suggestions, filters by content type.
  - Network / APIs: Calls Spotify’s Search API (and Browse API for suggestions), fetches real-time metadata and images.
  - Data storage: Local cache of recent searches and suggestions for faster loading.

- Does it require Internet? Yes (for full results and suggestions).
- If Network Slow/Unavailable: Results load slowly or fail to appear; app falls back to cached searches or shows “No internet connection” message. Local library search may still work partially.

Feature 3: Offline Downloads
- Likely software components involved:  
  - User Interface (UI): Download toggle buttons on songs/albums/playlists, progress indicators, “Downloads” section in Your Library.
  - Business logic: Manages download queue, handles DRM encryption/decryption, checks download expiration, prioritizes based on user preferences. 
  - Network / APIs: Initial API calls to authorize and fetch content from Spotify’s content delivery network (CDN). 
  - Data storage: Encrypted audio files stored in app’s secure local storage (device file system).

- Does it require Internet? Yes to download; No to play downloaded content.
- If Network Slow/Unavailable: Downloads pause or fail; already downloaded content remains playable without issues.

Feature 4: Lyrics Display(Real-Time Synced) 
- Likely software components involved:  
  - User Interface (UI): Scrollable lyrics panel below the player, current line highlighted and auto-scrolling, “Lyrics not available” fallback.
  - Business logic: Syncs lyrics timestamps with current playback position, handles language selection, karaoke-style highlighting.
  - Network / APIs: Fetches timed lyrics data from Spotify’s lyrics service or third-party partners (e.g., Musixmatch).
  - Data storage: Temporary cache of recently viewed lyrics on device.

- Does it require Internet? Yes for initial fetch; cached lyrics may work offline.
- If Network Slow/Unavailable: Lyrics fail to load or appear delayed/out-of-sync; app shows “Lyrics unavailable” or static text.

Feature 5: Personalized Recommendations.
 - Likely software components involved:
   - UI: Carousels and lists like "Discover Weekly."
   - Business Logic: Machine learning models to analyze listening patterns and suggest content.
   - Network/APIs: APIs to send user data and receive recommendation responses from servers.
   - Data Storage: Local storage for user preferences; cloud for aggregated data.

- Does it require Internet? Yes, for updating recommendations.
- If Network Slow/Unavailable: Stale recommendations from last sync; new listens aren't factored in until reconnected, potentially reducing personalization accuracy.

Feature 6: Creation and management of playlists
- Likely software components involved:  
  - User Interface (UI): Playlist creation screen, “Add songs” search, drag-and-drop reordering, collaborative indicators and share button
  - Business logic: Adds/removes tracks, handles reordering, manages collaborative editing conflicts, updates metadata.
  - Network / APIs: Syncs changes to Spotify servers, uses real-time collaboration APIs (WebSockets/polling) for shared playlists.
  - Data storage: Local temporary storage for unsynced changes; master data on Spotify cloud servers.

- Does it require Internet? Partial (local edits possible); full sync and collaboration require internet.
- If Network Slow/Unavailable: Changes saved locally but not synced; collaborative edits by others won’t appear; potential merge conflicts on reconnect.

Feature 7: Streaming Playback & Controls
- Likely software components involved:  
  - User Interface (UI): Now Playing screen with large album art, progress bar, play/pause, skip, shuffle, repeat, queue button, and lyrics toggle.
  - Business logic: Manages audio buffering, adaptive bitrate switching (based on network speed), handles playback interruptions (calls, notifications), queue logic.
  - Network / APIs: Streams audio chunks from Spotify’s CDN using adaptive streaming protocols (HLS/DASH), fetches metadata updates.
  - Data storage: Temporary in-memory buffer and small local cache for preloading.

- Does it require Internet? Yes for streaming (unless content is downloaded).
- If Network Slow/Unavailable: Buffering occurs frequently, audio quality drops automatically, playback pauses or stops. Downloaded songs continue playing.



## Part C: Change and Maintainability

**Chosen change scenario:** [Pick ONE, e.g., Optimize the app for low-end smartphone            ]  
(Other options: Add offline support, Support 10× more users, Introduce dark mode across the app, Add mobile payments in Uganda)

**Which parts of the app would need changes?**  
1.

**What existing features could break?**  
1.Lyrics sync might fail on slower processors due to timing demands.
2.Playback might stutter if buffering isn't optimized for low RAM.

**Why would this change be difficult to implement?**  
1. Because the system is already deployed.
2. 

## Part D: Software Construction Challenges

Identify **at least 5** engineering challenges in maintaining/improving Spotify. Explain each briefly.

1. **Performance and scalability**  
   [Brief explanation... e.g., Handling millions of concurrent streams and personalized recommendations requires massive backend scaling without latency.]

2. **Security and data privacy**  
   1. one time login that kepps you logged in and this maybe insecure.
   2. 

4. **Testing across devices and OS versions**  
   [Brief... e.g., Ensuring the app works consistently on thousands of Android/iOS devices, old/new versions, and varying hardware.]

5. **Reliability under poor network conditions**  
   [Brief... e.g., In areas with unstable internet (common in Uganda), buffering, offline fallbacks, and reconnection logic must be robust.]

6. **Backward compatibility**  
   [Brief... e.g., New features can't break older app versions or devices still in use by millions.]

(Add more if you want, e.g., Tight coupling between features, handling large-scale data for recommendations.)

## Part E: Group Reflection

1. **What surprised your group most about the complexity behind this app?**  
   1. collaborative playlist. this involves creation of music playlist with friends and playing
   2. 

3. **Why is writing “working code” not enough for software systems at this scale?**  
   1. 
   2. 

5. **What did you learn about teamwork from this exercise?**  
   1. Easier to tackle about a number ideas
   2. finishing work in time in that every member will deliver work in time since the aspect given to them is a must do for them.
   3. 

## Group Contributions (Required)
- **Member 5 Name**: [e.g., Handled reflections in Part E and ensured clear formatting]

All members contributed meaningfully through brainstorming sessions and reviews.
