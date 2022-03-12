<template>
  <div>
    <b-nav>
      <b-nav-item active>Home</b-nav-item>
      <b-nav-item>Log In</b-nav-item>
    </b-nav>

    <div class="flex">
      <aside>
        <div class="lesson-title">
          Lesson 1
        </div>
        <div class="practice-title">
          Practice 1
        </div>
        <div class="practice-title">
          Practice 2
        </div>
        <div class="practice-title">
          Practice 3
        </div>
        <div class="practice-title">
          Practice 4
        </div>
        <div class="lesson-title">
          Lesson 2
        </div>
        <div class="practice-title">
          Practice 1
        </div>
        <div class="practice-title">
          Practice 2
        </div>
        <div class="practice-title">
          Practice 3
        </div>
        <div class="lesson-title">
          Lesson 3
        </div>
        <div class="practice-title">
          Practice 1
        </div>
        <div class="practice-title">
          Practice 2
        </div>
        <div class="practice-title">
          Practice 3
        </div>
        <div class="practice-title">
          Practice 4
        </div>
        <div class="practice-title">
          Practice 5
        </div>
      </aside>

      <b-container id="main">
        <b-row>
          <b-col>
            <h1>Some Content</h1>
          </b-col>
        </b-row>
      </b-container>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      lessonTypes: ["reading", "video", "quiz", "project", "coding"]
    }
  },
};
</script>

<style>
html,
body {
  background: #F1F1F0;
}

#main {
  margin-top: 15px;
}

.nav {
  display: flex;
  justify-content: space-between;
  background: white;
  padding: 10px 15px;
}

.flex {
  display: flex;
}

aside {
  margin-top: 15px;
  border-right: 1px solid black;
  padding: 0px 15px;
  width: 15%;
  height:100vh;
}

.lesson-title {
  font-weight: 700;
  font-size: 16px;
}

aside .lesson-title:not(:first-of-type) {
  margin-top: 15px;
}

.practice-title {
  cursor: pointer;
  padding-left: 15px;
  margin-bottom: 5px;
}

.path {
  margin-bottom: 20px;
}

.content .path:not(:first-child):not(:last-child) {
  margin: 20px 0px;
}

.path .course:not(:first-child):not(:last-child) {
  margin: 10px 0px;
}

.subheader {
  font-size: 12px;
  margin: -10px 0px 20px;
}

.courseTitle {
  display: flex;
  flex-direction: row;
  align-items: center;
}

.courseTitle h3 {
  margin: 0px;
}

.course {
  border: 0px;
}

.course .complete svg {
  width: 27px;
  height: 27px;
  margin-right: 5px;
}

.lockedContent {
  display: flex;
  width: 100%;
  flex-direction: row;
  align-items: center;
}

.unit:first-child {
  margin-top: 15px;
}

.unit {

}

.unitProgress {

}

.unitTitle {
  display: flex;
  flex-direction: row;
  align-items: center;
  margin-bottom: 5px;
  cursor: pointer;
}

.unitTitle h5 {
  margin: 0px;
}

.unit svg {
  width: 18px;
  height: 18px;
  margin-right: 5px;
}

.courseSubheader span {
  cursor: pointer;
}

.assignmentTitle {
  cursor: pointer;
  display: flex;
  flex-direction: row;
  align-items: center;
}

.assignmentTitle svg {
  width: 16px;
  height: 16px;
}

.assignment.complete {
  background: gray;
  color: lightgray;
}

.list-group-item + .list-group-item {
 border-top-width: thin;
}
</style>