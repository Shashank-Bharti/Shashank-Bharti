<div style="width: 200px; height: 200px; background-color: green; border-radius: 15px; display: flex; align-items: center; justify-content: center; color: white; font-weight: bold; margin: 10px;">
  box1
</div>

<div style="width: 200px; height: 200px; background-color: green; border-radius: 15px; display: flex; align-items: center; justify-content: center; color: white; font-weight: bold; margin: 10px;">
  box2
</div>

<button id="soundButton" onclick="toggleSound()" style="background:none; border: none; color: white; text-align: center; text-decoration: none; display: inline-block; font-size: 16px; margin: 4px 2px; cursor: pointer; border-radius: 12px; transition: transform 0.3s ease;">
  🔊 
</button>

<audio id="audioPlayer" preload="auto" loop>
  <source src="sounds/World War Outerspace - Audio Hertz.mp3" type="audio/mpeg">
  Your browser does not support the audio element.
</audio>

<style>
button:hover {
  transform: scale(1.2);
}
</style>

<script>
let isPlaying = false;

function toggleSound() {
  var audio = document.getElementById("audioPlayer");
  var button = document.getElementById("soundButton");
  
  if (!isPlaying) {
    audio.play().then(function() {
      isPlaying = true;
      button.innerHTML = "🔊";
    }).catch(function(error) {
      console.log("Error playing audio:", error);
      alert("Could not play audio. Please check if the file exists.");
    });
  } else {
    audio.pause();
    isPlaying = false;
    button.innerHTML = "🔇";
  }
}
</script>