<template>
  <div>
    <h1>Posts</h1>

    <!-- Create or Post -->
    <input type="text"
           v-model="title"
           placeholder="Title"
           class="title-input" />
    <input type="text"
           v-model="body"
           placeholder="Body"
           class="body-input" />

    <!-- only render if editing post -->
    <button v-if="isEditing" @click="updatePost">Update</button>
    <button v-if="isEditing" @click="cancelEdit">Cancel</button>

    <!-- only render if not editing post -->
    <button v-else @click="createPost">Create</button>

    <!-- List of Posts -->
    <div v-for="post in posts" :key="post.id">
      <h5>[{{post.id}}] {{ post.title }}</h5>
      <p>{{ post.body }}</p>

      <button @click="editPost(post.id)">Edit</button>
      <button @click="deletePost(post.id)">Delete</button>
    </div>
  </div>
</template>

<script setup>

</script>

<style scoped>
.title-input {
  width: 100%;
  padding: 12px 20px;
  margin: 8px 0;
  box-sizing: border-box;
  border: 2px solid #ccc;
  background-color: #f8f8f8;
  color: #111;
  border-radius: 4px;
  resize: vertical;
}

.body-input {
  width: 100%;
  padding: 12px 20px;
  margin: 8px 0;
  box-sizing: border-box;
  border: 2px solid #ccc;
  background-color: #f8f8f8;
  color: #111;
  border-radius: 4px;
  resize: vertical;
}
</style>
