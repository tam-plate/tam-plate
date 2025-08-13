import { GitHubNowPlaying } from 'github-now-playing';

const nowPlaying = new GitHubNowPlaying({
 token: process.env.GITHUB_ACCESS_TOKEN,
});

// Create a new source to retrieve the track that is currently playing
const spotifySource = new GitHubNowPlaying.Sources.Spotify({
 // wait time in milliseconds between checks for any track changes
 updateFrequency: 1000,
});

// Make sure a source is set before calling listen()
nowPlaying.setSource(spotifySource);

// Don't forget to handle the error event!
nowPlaying.on(GitHubNowPlaying.Events.Error, error => {
  console.log('something went wrong');
});

// Listen to any track changes and update the profile status accordingly.
nowPlaying.listen();

// Don't forget to stop reporting any track changes when the process exists.
process.on('SIGINT', () => {
  // Calling the stop() method will clear the profile status.
  nowPlaying.stop()

<!--
**tam-plate/tam-plate** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
