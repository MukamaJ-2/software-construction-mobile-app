# Software Construction - Behind the App: Thinking Like Software Engineers

**Course:** Software Construction   

**Assignment Type:** Mobile application analysis 

**Group Members:** Rebecca Alinda., Anna Akumu., Namaganda Wakabi Precious., Odongkara Oscar., Joseph Mukama

**Selected App:** Spotify  

This README contains our group's complete submission for Assignment 1. We analyzed Spotify, a music streaming app we all use frequently for discovering and listening to music, podcasts, and more.

## 1. App Overview

**What problem does this app solve?**  
1. Relation to Copyright, spotify provides legal, licensed access to music, reducing illegal copying. Artists and record labels are paid for streams, which protects copyright ownership. By making music easy and affordable to access, Spotify helps prevent copyright infringement.
2. Access & Convenience Problem as before streaming services, people had to buy individual albums/songs or rely on radio. Music was spread across platforms like HowweBiz for local Ugandan music, Tubidy for international pop and hip-hop, and Boomplay for African genres. Spotify provides instant access to millions of songs of all genres in one place on-demand from any device without needing to purchase, download, or store music files locally. You can listen anywhere, anytime.
3. Artist Distribution & Monetisation: For artists, getting music to listeners traditionally required record labels and physical distribution. Spotify provides a direct distribution channel where independent artists can reach global audiences and earn royalties based on streams.

Basically, Spotify democratised music access while solving the friction between discovery, cost, and convenience.

**Who are its primary users?
1. Music enthusiasts, casual listeners, podcast listeners, and fitness users that are young adults (18-34 years). This is Spotify's largest demographic segment. Millenials and Gen Z are the most active users, comfortable with streaming technology and digital music consumption.
2. Content creators, Artists and Podcasters. Musicians, bands, podcaster, and audiobook creators who upload and distribute content through Spotify. They use Spotify for Artists/Podcasters dashboards to track analytics and earnings.


## 2. Core Features

List 5–7 key features of Spotify (based on current app experience):

1. **User authentication and Profile System/The login or signup page:** There are multiple options like Email, Google, Facebook and Apple. There is also profile managemet, and account settings where users can manage their subscription tier (Free, Premium, Family, Student plans).
2. **The search functionality: **A powerful search bar that lets you find songs, artists, albums, playlists, podcasts, and audiobooks. It includes filters and a search history to quickly access previous queries.
3. **Offline Downloads:** Permits saving content for offline use, emphasizing data storage strategies for reliability.
4. **Lyrics Display(Real-Time Synced): **Shows timed lyrics during playback, a feature that ties UI with timing algorithms.
5. **Personalized Recommendations: **Made for You sections like Daily Mixes, Discover Weekly, and Release Radar based on listening history.
6. **Streaming Playback & Controls:** Full player interface with play/pause, skip, shuffle, repeat, volume, queue management, lyrics toggle, casting (Spotify Connect), and share options.
7. **Personalized Home Feed:** Dynamic homepage that displays recommended playlists like Daily Mixes, Discover Weekly, and Release Radar based on listening history, new releases, and curated sections and the time of day as well.
8. **Playlist Creation & Management:** Provides the ability to create, edit, and organise custom playlists, add songs to library, collaborate on playlists with friends, reorder tracks with drag-and-drop, and download for offline listening Premium).
9. **Payment & Subscription Management:** In -app payment gateway for upgrading to Premium, managing billing information, changing subscription plans, and accessing payment history. Multiple payment methods supported (Credit card, mobile carrier billing)
10. **Library & Collection Organisation:** "Your Library" section where you can organise saved songs, albums, artists, podcasts, and audiobooks into folders and custom categories for easy access and management 


## Part B: Thinking Behind the Scenes

**Feature 1: User authentication/The login and registration.**
 - Likely software components involved:
  - User Interface (UI): Login screen with options (Continue with email, phone, Google); step-by-step flows for credentials or account selection.
  - Business Logic: Validates input, handles selected login method, creates secure session.
  - Network / APIs: Communicates with Spotify auth servers and external providers (e.g., Google OAuth).
  - Data Storage: Stores auth tokens locally; user data on Spotify servers.

Requires Internet Connectivity?: Yes (for verification).
If Network Slow or Unavailable: Login fails, pages may not load, user cannot access account (cached session may allow limited continued use if previously logged in).

Feature 2: The search functionality   
- Likely software components involved:  
  - User Interface (UI):
       Search icon (magnifying glass), Search screen with a text input field, Categories and suggestions (songs, artists, albums, playlists), Results list that updates as the user types.
  - Business logic:
      - Interprets what the user types
      -  Decides how to rank results (songs first, artists, playlists)
      -  Filters and matches search terms with Spotify’s catalog
  - Network / APIs:
      - Sends the search query to Spotify servers
      - Receives matching results (songs, artists, albums, playlists)
  - Data storage: 
     - Temporary caching of recent searches
     - Search history saved to improve recommendations
 Does it require Internet?: Yes.
 If Network Slow/Unavailable: Results load slowly or fail; falls back to cached searches or shows "No internet" message; local library search may work partially.

Feature 3: Offline Downloads
- Likely software components involved:  
  - User Interface (UI):
      Download button on songs, albums, or playlists
      Download progress indicator
      Offline library screen to access downloaded content
  - Business logic:
       Checks if the user has permission (Premium subscription)
       Manages what gets downloaded and storage space
       Handles play requests from offline content
  - Network / APIs:
       Downloads music from Spotify servers when connected
       Updates download status and syncs playlists with the cloud
  - Data storage:
       Stores music files securely on the device
       Saves metadata (song info, playlists, progress) locally
  - Does it require Internet?
       Yes to download new songs
       No to play songs already downloaded
  - If Network Slow/Unavailable:
       New downloads may fail or pause
       Only already-downloaded songs are playable
       Features like streaming, search, or updating playlists are limited

Feature 4: Lyrics Display(Real-Time Synced) 
- UI: Lyrics appear line by line as the song plays, often highlighted in sync with music; scrollable lyric view for longer songs.
- Business Logic: Matches song playback position to the correct lyric line; handles timing, scrolling, and any user interactions like pause or seek.
- Network/APIs: Retrieves lyrics from Spotify’s servers or licensed lyric providers; may update lyrics in real time for new songs.
- Data Storage: Caches recently viewed lyrics locally for faster access; stores timing data and song-lyrics mapping for offline playback.
- Does it require internet?
    Yes, for new songs or lyrics not yet cached; no for already downloaded songs with cached lyrics.
- If network is slow/unavailable:
    Lyrics for new songs may not appear
    Existing cached lyrics will display, but real-time sync may lag
    1. Search Bar/Input field with a test input box with a placeholder tex, a clear/X button to reset input.
    2. Search suggestions dropdown with a list suggested search terms as you type, recent searches section.
    3. Search button/icon with a clickable search icon to trigger search and active/inactive states.
    4. Category Filter Tabs with tab buttons "All", "Songs", "Artists", "Albums", "Playlists", "Podcasts", "Profiles"
    5. Search Results Container with a grid or list ayout for results and a scrollable area.
    6. Results Cards/List items with thumbnail/album art image, title text, subtitle/artist name text, duration/ metadata text, play button overlay, three-dot menu (for options), and hover effects.
    7. Empty State Display with "No results found" message
    8. Search history panel with a list of recent searches, "clear all" button, and individual delete buttons per search term.
  - Business logic: 
  - Network / APIs: 
  - Data storage: 

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
    - User Interface (UI): Screens to create, name, edit, and delete playlists; drag-and-drop or add/remove tracks; share and collaborative playlist options.
    - Business Logic: Handles playlist creation, editing, and deletion; manages permissions for collaborative playlists; enforces limits (number of songs, playlist size).
    - Network / APIs: Syncs playlist changes to Spotify servers; fetches updates from shared/collaborative playlists; communicates with friends’ accounts for collaboration.
    - Data Storage: Stores playlist structure locally for offline access; syncs metadata (song order, collaborators, playlist info) with cloud storage.
    - Does it require Internet? Yes for creating, sharing, and collaborating on playlists.
         Partly for accessing already downloaded songs in a playlist offline.
    - If Network Slow/Unavailable:
         Cannot create or share new playlists
         Collaborative playlists won’t update in real time
         User can still play downloaded songs in existing playlists, but any changes won’t sync until reconnected
Feature 7: 
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
1.Lyrics sync might fail on slower processors due to timing demands                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        .
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
