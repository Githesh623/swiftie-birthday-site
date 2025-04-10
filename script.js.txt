// script.js

// Landing page animation
document.getElementById('startButton').addEventListener('click', function() {
    document.getElementById('landing-page').classList.add('hidden');
    document.getElementById('timeline').classList.remove('hidden');
    document.getElementById('countdown').classList.remove('hidden');
});

// Countdown Timer
const birthday = new Date('2025-04-20T00:00:00'); // Set your girlfriend's birthday
function updateCountdown() {
    const now = new Date();
    const timeLeft = birthday - now;

    if (timeLeft <= 0) {
        document.getElementById('countdown-timer').innerHTML = "It's your birthday today! 🎉";
    } else {
        const days = Math.floor(timeLeft / (1000 * 60 * 60 * 24));
        const hours = Math.floor((timeLeft % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
        const minutes = Math.floor((timeLeft % (1000 * 60 * 60)) / (1000 * 60));
        const seconds = Math.floor((timeLeft % (1000 * 60)) / 1000);
        document.getElementById('countdown-timer').innerHTML = `${days}d ${hours}h ${minutes}m ${seconds}s`;
    }
}
setInterval(updateCountdown, 1000);

// Song Dedication Form
document.getElementById('song-form').addEventListener('submit', function(e) {
    e.preventDefault();
    const selectedSong = document.querySelector('input[name="song"]:checked');
    if (selectedSong) {
        document.getElementById('song-result').innerText = `You dedicated "${selectedSong.value}" to yourself! 🎶`;
    } else {
        document.getElementById('song-result').innerText = "You didn't pick a song!";
    }
});

// Hidden Message
document.getElementById('show-message').addEventListener('click', function() {
    document.getElementById('message-content').classList.remove('hidden');
});
