<template>
  <div>
    <a href="https://discord.com/invite/jMtqPjH" target="_blank">
      <b-img src="~/assets/img/discord-icon.png" class="discord-btn shadow-lg rounded" />
    </a>
  </div>
</template>

<style scoped>
.discord-btn {
  height: 3.5rem;
  background-color:rgb(139, 157, 254);
  position: fixed;
  right: 25px;
  bottom: 25px;
  margin-bottom: 0;
  z-index: 997;
  display: table-cell;
  display: flex;
}

.discord-btn:hover {
  text-decoration: none;
  animation-name: discord-btn-animation;
  animation-duration: 0.75s;
}

@keyframes discord-btn-animation {
  0% {transform: rotate(5deg);}
  20%  {transform: rotate(-7.5deg);}
  40%  {transform: rotate(10deg);}
  60% {transform: rotate(-7.5deg);}
  80% {transform: rotate(5deg);}
  100% {transform: rotate(0deg);}
}
</style>
