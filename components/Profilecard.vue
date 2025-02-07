<template>
    <div class="profile-card">
      <img :src="profilePicture" alt="Profile Picture" data-testid="profilePicture" class="profile-image" />
      <h2 data-testid="fullName">{{ fullName }}</h2>
      <p data-testid="jobTitle" class="job-title">{{ jobTitle }}</p>
      <p data-testid="shortBio" class="bio">{{ shortBio }}</p>
      <p data-testid="currentLocation" class="location">{{ currentLocation }}</p>
      <p data-testid="emailAddress" class="email">{{ emailAddress }}</p>
      <div class="social-links" data-testid="socialLinks">
        <a v-for="link in socialLinks" :key="link.name" :href="link.url" target="_blank">{{ link.name }}</a>
      </div>
      <p data-testid="currentTimeUTC" class="utc-time">UTC Time: {{ currentTime }}</p>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        profilePicture: "/Snapchat-1136970090.jpg",
        fullName: "Lawal Sodiq Olalekan",
        jobTitle: "Frontend Developer",
        shortBio: "Passionate about building user-friendly interfaces with Vue.js and modern web technologies.",
        currentLocation: "Osun, Nigeria",
        emailAddress: "Lawalholamilekan@gmail.com",
        socialLinks: [
          { name: "GitHub", url: "https://github.com/Lekside081/Frontendtaskstage0" },
          { name: "LinkedIn", url: "https://linkedin.com/in/lawal" },
          { name: "Twitter", url: "https://twitter.com/lawal" }
        ],
        currentTime: new Date().toISOString().slice(0, 19).replace("T", " ") + " UTC"
      };
    },
    mounted() {
      setInterval(() => {
        this.currentTime = new Date().toISOString().slice(0, 19).replace("T", " ") + " UTC";
      }, 1000);
    }
  };
  </script>
  
  <style scoped>
  .profile-card {
    max-width: 400px;
    margin: auto;
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    text-align: center;
    font-family: Arial, sans-serif;
  }
  .profile-image {
    width: 100px;
    height: 100px;
    border-radius: 50%;
    object-fit: cover;
    justify-self: center;
  }
  .job-title {
    font-weight: bold;
    color: #333;
  }
  .bio, .location, .email, .utc-time {
    font-size: 14px;
    color: #666;
  }
  .social-links a {
    margin: 0 5px;
    text-decoration: none;
    color: #007bff;
  }
  </style>