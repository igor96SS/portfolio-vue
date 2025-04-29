<template>
    <form name="contact" method="POST" netlify>
      <input type="hidden" name="form-name" value="contact" />
      <div>
        <label for="name">Name:</label>
        <input type="text" id="name" name="name">
      </div>
      <button type="submit">Send</button>
    </form>
  </template>
  
  <script setup>
  // No JavaScript here
  </script>