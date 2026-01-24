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
7.   


## Part B: Thinking Behind the Scenes

For each of the features listed above, discuss:

- Likely software components involved:  
  - User Interface (UI)  
  - Business logic  
  - Network / APIs  
  - Data storage  

- Whether the feature requires internet connectivity
- 1. It rquires for live streaming
- What might happen if the network is slow or unavailable
- 1. You will only be able to access the downloaded content
  2. some features like the colloborative creation of playlists and messaging services wo't be available

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
  - User Interface (UI):
       Search icon (magnifying glass), Search screen with a text input field, Categories and suggestions (songs, artists, albums, playlists), Results list that updates as the user types.
  - Business logic:
       Interprets what the user types
       Decides how to rank results (songs first, artists, playlists)
       Filters and matches search terms with Spotify’s catalog
  - Network / APIs:
        Sends the search query to Spotify servers
        Receives matching results (songs, artists, albums, playlists)
  - Data storage: 
        Temporary caching of recent searches
        Search history saved to improve recommendations
  - Does it require Internet?
         Yes.
  - If Network Slow/Unavailable:
         Search results load slowly or not at all
         Only previously cached results (if any) may appear
         User cannot discover new music

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
- Likely software components involved:  
  - User Interface (UI): 
  - Business logic: 
  - Network / APIs: 
  - Data storage: 

- Does it require Internet?
- If Network Slow/Unavailable: 



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
