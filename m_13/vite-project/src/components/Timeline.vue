<template>
  <ul class="timeline" type="both">
    <li class="timeline-title">
      <div class="icon" />
      <div class="title">2021.06.13</div>
      <div class="comment">comment</div>
    </li>
    <li class="timeline-item" side="left">
      <img class="icon" src="../assets/logo.png" style="--circleColor: #f5cdcd">
      <div class="title">Study Vue</div>
      <div class="comment">comment</div>
    </li>
    <li class="timeline-item" side="right">
      <img class="icon" src="../assets/logo.png" style="--circleColor: #f5cdcd">
      <div class="title">Write simple program</div>
      <div class="comment">comment</div>
    </li>
    <li class="timeline-title">
      <div class="icon" />
      <div class="title">2021.06.14</div>
      <div class="comment">comment</div>
    </li>
    <li class="timeline-item" side="right">
      <img class="icon" src="../assets/logo.png" style="--circleColor: #f5cdcd">
      <div class="title">Read news</div>
      <div class="comment">comment</div>
    </li>
    <li class="timeline-item" side="right">
      <img class="icon" src="../assets/logo.png" style="--circleColor: #f5cdcd">
      <div class="title">Do homework</div>
      <div class="comment">comment</div>
    </li>
  </ul>
</template>

<script>
export default {
  name: "Timeline",
  props: {
    msg: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.timeline {
  position: relative;
  list-style-type: none;
  padding: 0;
  word-break: break-word;
  text-align: left;
}

.timeline::after {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 0.1rem;
  height: 100%;
  background: #000;
  z-index: 0;
}

.timeline li:not(:first-child) {
  margin-top: 2rem;
}

.timeline .timeline-title + .timeline-item {
  margin-top: 0.5rem;
}

.timeline-title {
  font-size: 0.75rem;
}

.timeline[type="single"] {
  left: 1rem;
}

.timeline[type="both"] {
  left: 50%;
  width: 50%;
}

.timeline[type="both"] .timeline-title {
  width: 200%;
  margin-left: -100%;
  display: flex;
  flex-direction: row;
  justify-content: center;
}

.timeline[type="both"] .timeline-title > .icon {
  margin-left: 0.1rem;
}

.timeline[type="both"] .timeline-title > .title {
  width: 50%;
  transform: translateY(-0.375rem);
  margin-right: 1rem;
  text-align: right;
  align-self: center;
  order: 0;
  flex: 1;
}

.timeline[type="both"] .timeline-title > .comment {
  width: 50%;
  transform: translateY(-0.375rem);
  margin-left: 1rem;
  align-self: center;
  order: 2;
  flex: 1;
}

.timeline[type="both"] .timeline-item[side="left"] > .title,
.timeline[type="both"] .timeline-item[side="left"] > .comment {
  width: 100%;
  margin-left: calc(-100% - 1rem);
  text-align: right;
}

.timeline[type="single"] .title,
.timeline[type="single"] .comment,
.timeline[type="both"] .timeline-item[side="right"] > .title,
.timeline[type="both"] .timeline-item[side="right"] > .comment {
  margin-left: 1rem;
}

.timeline-title .icon {
  position: absolute;
  width: 0.5rem;
  height: 0.5rem;
  border-radius: 100%;
  background: rgb(180, 180, 180);
  margin-left: -0.2rem;
  z-index: 1;
}

.timeline-item .icon {
  position: absolute;
  width: 1rem;
  height: 1rem;
  border-radius: 100%;
  background: var(--circleColor);
  margin-left: -0.45rem;
  display: block;
  z-index: 1;
}
</style>