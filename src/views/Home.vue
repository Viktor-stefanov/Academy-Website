<template>
  <div class="landing">
    <!-- Background image -->
    <div class="bg-image"></div>

    <!-- Content container -->
    <div class="content-container">
      <!-- Headline -->
      <h1 class="headline">Unlock Your Full Potential in Tech</h1>

      <!-- Your photo -->
      <img src="@/assets/images/personal_photo.png" alt="Your Photo" class="your-photo" />

      <!-- Services paragraph -->
      <p class="services-paragraph">
        Dive deep into personalized, one-on-one mentorship tailored to your unique journey in
        software development. Whether aiming for your first tech internship or advancing to senior
        roles, discover a path that aligns with your goals and schedule, complete with job position
        recommendations.
      </p>
    </div>
  </div>
</template>

<script setup lang="ts">
// Your Vue 3 <script setup> code herpnge
</script>

<style scoped>
/* The main container for your landing page, occupying the full width and at least the full height of the viewport */
.landing {
  position: relative;
  width: 100%; /* Full width of the viewport */
  min-height: 100vh; /* Minimum height of 100% of the viewport height, can grow if content is larger */
  display: flex; /* Using Flexbox for centering content */
  flex-direction: column; /* Children (content-container) stacked vertically */
  justify-content: center; /* Centers content vertically within the viewport */
  align-items: center; /* Centers content horizontally within the viewport */
  padding: 5vh 0; /* Adds vertical padding on top and bottom for some space */
}

/* The background image styling, positioned absolutely to cover the whole .landing container */
.bg-image {
  position: absolute;
  z-index: -1; /* Ensures the background image is behind the content */
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-image: url("@/assets/images/main_background.png"); /* Replace with your actual image path */
  background-size: cover; /* Ensures the background covers the entire container */
  background-position: center; /* Centers the background image */
  filter: blur(1.5px); /* Applies a blur effect to create a soft-focus look */
}

/* The container for the text content and your photo, centered within the .landing container */
.content-container {
  z-index: 1; /* Positioned above the background image */
  text-align: center; /* Centers the text within the container */
  max-width: 80%; /* Limits the width of the container for better readability */
  padding: 20px; /* Adds padding inside the container */
  display: flex; /* Flex layout to align children elements */
  flex-direction: column; /* Aligns children elements (your photo, headline, paragraph) vertically */
  align-items: center; /* Centers children elements horizontally */
}

/* Styling for your photo, making it round and appropriately sized */
.your-photo {
  width: 450px; /* Set the width of your photo */
  height: auto; /* Ensures the height is adjusted automatically to maintain aspect ratio */
  border-radius: 50%; /* Rounds the corners of your photo to make it a circle */
  margin-bottom: 30px; /* Adds space below your photo */
}

/* Styling for the headline, making it prominent and visually impactful */
.headline {
  font-size: 2.5rem; /* Sets the size of the headline text */
  color: #fff; /* Sets the color of the headline text, white is used here for contrast */
  margin-bottom: 30px; /* Adds space below the headline */
}

/* Styling for the paragraph detailing your services */
.services-paragraph {
  font-size: 1.2rem; /* Sets the size of the paragraph text */
  color: #ddd; /* Sets the color of the paragraph text, a lighter grey for readability */
  max-width: 600px; /* Maximum width of the paragraph to maintain readability */
  margin: 0 auto; /* Centers the paragraph in the container if it's less than the max width */
}
</style>
