<script setup lang="ts">
</script>

<template>
  <main>
    <div class="progress" data-value="75">
      <progress id="file" max="100" value="70">70 %</progress>
    </div>
  </main>
</template>

<style scoped>
progress {
  opacity: 0;
  position: absolute;
  top: 0;
  width: 100%;
  height: 1rem;
}

.progress {
  position: relative;
  border-radius: 0.5rem; 
  height: 1rem;
  width: 100%;
  --fg-color-rgb: 240,250,255;
  --bg-color-rgb: 34,51,68;
  background-color: rgb(var(--bg-color-rgb));
  color: rgb(var(--fg-color-rgb));
}
.progress:before {
  content: " ";
  display: block;
  height: 1rem;
  border-radius: 0.5rem; 
  color: var(--fg-color-rgb);
  background: rgb(var(--bg-color-rgb));
  background: linear-gradient(90deg, rgba(var(--bg-color-rgb),0.5) 0%, rgba(var(--fg-color-rgb),1) 100%);
  width: 70%;
  width: attr(data-value %); /* experimental */
}
.progress:after {
  position: absolute;
  display: flex;
  justify-content: center;
  align-items: center;
  content: attr(data-value) "%";
  color: rgb(var(--bg-color-rgb));
  top: 50%;
  left: 70%;
  left: attr(data-value %); /* experimental */
  transform: translate(-50%, -50%);
  background-color: rgb(var(--fg-color-rgb));
  height: 2rem;
  width: 2rem;
  border-radius: 50%;
  font-size: 0.75em;
  box-shadow: 0px 0px 0.5rem 0.25rem rgb(var(--fg-color-rgb));
}
</style>
