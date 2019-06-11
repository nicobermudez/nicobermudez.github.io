---
layout: post
title:      "Waves Records - React with Ruby on Rails app"
date:       2019-06-11 19:29:45 +0000
permalink:  waves_records_-_react_with_ruby_on_rails_app
---

For my final project for Flatiron School, I was tasked with creating an application using React, Redux, and a Ruby on Rails back end. I had been wanting to make use of Spotify's API for a while, so I finally decided to make an app revolving around Spotify. 

Waves Records is a music-based platform aimed to facilitate the music searching process. Users simply take a selfie or use an old photo of them which captures their current state of mind, and we take care of the rest. Based on a users current mood, Waves Records will curate a set of perfect playlists through Spotify, allowing users to save or remove any playlists through the app.

Essentially, a user logs in using Spotify's authentication, and enters the app. A user can navigate between the home page, their playlists page, the Spotify app, and can logout. In the home screen, a user is shown a carefully selected group of featured playlists. Then, they can either search for different playlists, or upload a photo of themselves to have their mood evaluated. The uploaded photo is sent to the Rails back end, stored as a URL and sent to Face++ Facial Recognition API, which detects emotion. Based on the user's dominant emotion, mood is updated and the playlists from the home page update to reflect the user's current mood. 

Within the home page, users can favorite different playlists so that they can listen at any time. These saved playlists are located under the playlists tab, which, once in the page you can unfavorite to remove from your playlists. Playlists are fetched from the Rails back end API depending on the current user.

Waves Records uses Redux to store the global state of the current user, playlists, user_playlists, and current mood. 

I hope this app entertains and can be helpful for the creation of more music-based applications. If you have any questions, suggestions, or feedback, please do not hesitate to leave a comment or contact me through bermnicolas@gmail.com.


