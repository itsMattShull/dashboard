<template>
  <div>
    <b-nav>
      <b-nav-item active>Home</b-nav-item>
      <b-nav-item>Log In</b-nav-item>
    </b-nav>

    <b-container id="main">
      <b-row>
        <b-col>
          <b-alert show
            ><a href="#">Complete your onboarding</a> to get the most out of
            your experience.</b-alert
          >
        </b-col>
      </b-row>

      <b-row class="content">
        <b-col>
          <div v-for="path in paths" v-bind:key="path.index" class="path">
            <b-overlay :show="path.locked" rounded="sm" opacity="0.90">
              <b-card :aria-hidden="!path.locked ? 'true' : null">
                <h1>
                  {{ path.name }}
                </h1>
                <div class="subheader">
                  {{ path.unitCount }} Units &bull; {{ path.assessmentCount }} Assessments
                </div>

                <b-card v-for="course in path.courses" v-bind:key="course.index" class="course" v-show="path.locked == false">
                  <div class="courseTitle">
                    <div v-if="course.complete" class="complete">
                      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 64 64" enable-background="new 0 0 64 64"><circle cx="32" cy="32" r="30" fill="#fff"/><path d="M32,2C15.431,2,2,15.432,2,32c0,16.568,13.432,30,30,30c16.568,0,30-13.432,30-30C62,15.432,48.568,2,32,2z M25.025,50  l-0.02-0.02L24.988,50L11,35.6l7.029-7.164l6.977,7.184l21-21.619L53,21.199L25.025,50z" fill="#43a047"/></svg>
                    </div>
                    <h3>
                      {{ course.name }}
                    </h3>
                    <div class="courseSubheader">
                      <div v-if="!course.viewCompleted">
                        <span @click="course.viewCompleted=!course.viewCompleted">
                          &bull; show completed
                        </span>
                      </div>
                      <div v-else>
                        <span @click="course.viewCompleted=!course.viewCompleted">
                          &bull; hide completed
                        </span>
                      </div>
                    </div>
                  </div>

                  <b-list-group v-show="course.complete == false || course.viewCompleted == true">
                    <b-list-group-item v-for="unit in course.units" v-bind:key="unit.index" class="unit">
                      <b-container id="main">
                        <b-row>
                          <b-col>
                            <div class="unitTitle">
                              <svg v-if="unit.complete" class="complete" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 64 64" enable-background="new 0 0 64 64"><circle cx="32" cy="32" r="30" fill="#fff"/><path d="M32,2C15.431,2,2,15.432,2,32c0,16.568,13.432,30,30,30c16.568,0,30-13.432,30-30C62,15.432,48.568,2,32,2z M25.025,50  l-0.02-0.02L24.988,50L11,35.6l7.029-7.164l6.977,7.184l21-21.619L53,21.199L25.025,50z" fill="#43a047"/></svg>
                              <h5>{{ unit.name }}</h5>
                            </div>
                          </b-col>
                          <b-col>
                            <div class="unitProgress">
                              <div>{{ unit.ttc }}</div>
                              <div>
                                <b-progress :max="unit.assignmentCount" height="22px" class="w-100">
                                  <b-progress-bar style="overflow: visible" :value="unit.completedAssignmentCount" :variant="unit.completedAssignmentCount==unit.assignmentCount ? 'success' : ''">
                                    <span>Progress: <strong>{{ unit.completedAssignmentCount }} / {{ unit.assignmentCount }} assignments</strong></span>
                                  </b-progress-bar>
                                </b-progress>
                              </div>
                            </div>
                          </b-col>
                        </b-row>
                      </b-container>
                    </b-list-group-item>
                  </b-list-group>
                </b-card>
              </b-card>
              <template #overlay>
                <div class="lockedContent">
                  <b-icon icon="lock" font-scale="3" style="width:27px;"></b-icon>
                  <div>
                    Complete "Web Development Fundamentals" to unlock this content
                  </div>
                </div>
              </template>
            </b-overlay>
          </div>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
export default {
  data() {
    return {
      assignmentTypes: ["reading", "video", "quiz", "project", "coding"],
      paths: [
        {
          name: "Web Development Fundamentals",
          locked: false,
          unitCount: 10,
          assessmentCount: 2,
          courses: [
            {
              name: "Getting Started at App Academy",
              complete: true,
              viewCompleted: false,
              units: [
                {
                  name: "Getting Started",
                  ttc: "49 mins",
                  complete: true,
                  assignmentCount: 8,
                  completedAssignmentCount: 8,
                  assignments: [
                    {
                      name: "How to Learn at App Academy",
                      complete: true,
                      ttc: "10 mins",
                      type: "video"
                    }, {
                      name: "How to Manage Difficulty",
                      complete: true,
                      ttc: "5 mins",
                      type: "reading"
                    }, {
                      name: "How to Succeed at App Academy",
                      complete: true,
                      ttc: "10 mins",
                      type: "quiz"
                    }, {
                      name: "Documenting My Expectations",
                      complete: true,
                      ttc: "5 mins",
                      type: "reading"
                    }, {
                      name: "How to Ask Great Questions",
                      complete: true,
                      ttc: "5 mins",
                      type: "reading"
                    }, {
                      name: "The Secret to Solving Any Problem",
                      complete: true,
                      ttc: "7 mins",
                      type: "reading"
                    }, {
                      name: "Polya's Problem Solving Framework",
                      complete: true,
                      ttc: "5 mins",
                      type: "quiz"
                    }, {
                      name: "Using Online Resources and Documentation",
                      complete: true,
                      ttc: "2 mins",
                      type: "reading"
                    }
                  ]
                }
              ]
            }, {
              name: "Javascript Fundamentals",
              complete: false,
              viewCompleted: false,
              assignmentCount: 45,
              completedAssignmentCount: 17,
              units: [
                {
                  name: "Intro to Javascript",
                  complete: true,
                  ttc: "1 hr and 29 mins",
                  assignmentCount: 18,
                  completedAssignmentCount: 18,
                  assignments: [
                    {
                      name: `A Particularly Long and Detailed "Hello World!"`,
                      complete: true,
                      ttc: "10 mins",
                      type: "reading"
                    }, {
                      name: `"Hello World!" REPL`,
                      complete: true,
                      ttc: "10 mins",
                      type: "coding"
                    }, {
                      name: `Intro to Javascript`,
                      complete: true,
                      ttc: "3 mins",
                      type: "reading"
                    }, {
                      name: `The Number Data Type`,
                      complete: true,
                      ttc: "2 mins",
                      type: "reading"
                    }, {
                      name: `The Number Data Type Demo`,
                      complete: true,
                      ttc: "9 mins",
                      type: "video"
                    }, {
                      name: `Numbers Exercise`,
                      complete: true,
                      ttc: "4 mins",
                      type: "coding"
                    }, {
                      name: `Artithmetic Operators`,
                      complete: true,
                      ttc: "7 mins",
                      type: "quiz"
                    }, {
                      name: `The Boolean Data Type`,
                      complete: true,
                      ttc: "2 mins",
                      type: "reading"
                    }, {
                      name: `The Boolean Data Type Lecture`,
                      complete: true,
                      ttc: "5 mins",
                      type: "video"
                    }, {
                      name: `The Boolean Data Type Demo`,
                      complete: true,
                      ttc: "4 mins",
                      type: "video"
                    }, {
                      name: `Boolean Exercise`,
                      complete: true,
                      ttc: "7 mins",
                      type: "coding"
                    }, {
                      name: `Variables`,
                      complete: true,
                      ttc: "3 mins",
                      type: "reading"
                    }, {
                      name: `Variables Demo`,
                      complete: true,
                      ttc: "11 mins",
                      type: "video"
                    }, {
                      name: `Variables Practice`,
                      complete: true,
                      ttc: "4 mins",
                      type: "coding"
                    }, {
                      name: `Variables Quiz`,
                      complete: true,
                      ttc: "5 mins",
                      type: "quiz"
                    }, {
                      name: `The String Data Type`,
                      complete: true,
                      ttc: "3 mins",
                      type: "reading"
                    }, {
                      name: `String Type Lecture`,
                      complete: true,
                      ttc: "6 mins",
                      type: "video"
                    }, {
                      name: `String Type Demo`,
                      complete: true,
                      ttc: "8 mins",
                      type: "video"
                    }
                  ]
                }, {
                  name: "Intro to Functions",
                  complete: false,
                  ttc: "1 hr and 46 mins",
                  assignmentCount: 17,
                  completedAssignmentCount: 4,
                  assignments: [
                    {
                      name: `Functions`,
                      complete: true,
                      ttc: "9 mins",
                      type: "reading"
                    }, {
                      name: `Parameters and Arguments`,
                      complete: true,
                      ttc: "2 mins",
                      type: "reading"
                    }, {
                      name: `Functions Lecture`,
                      complete: true,
                      ttc: "9 mins",
                      type: "video"
                    }, {
                      name: `Intro to Functions Quiz`,
                      complete: true,
                      ttc: "6 mins",
                      type: "quiz"
                    }, {
                      name: `Goodbye (*)`,
                      complete: false,
                      ttc: "6 mins",
                      type: "coding"
                    }, {
                      name: `Goodbye Walkthrough`,
                      complete: false,
                      ttc: "8 mins",
                      type: "video"
                    }, {
                      name: `Muscle Memory`,
                      complete: false,
                      ttc: "12 mins",
                      type: "coding"
                    }, {
                      name: `Plus 5`,
                      complete: false,
                      ttc: "5 mins",
                      type: "coding"
                    }, {
                      name: `Call This Function`,
                      complete: false,
                      ttc: "5 mins",
                      type: "coding"
                    }, {
                      name: `Average of Two`,
                      complete: false,
                      ttc: "6 mins",
                      type: "coding"
                    }, {
                      name: `Hello`,
                      complete: false,
                      ttc: "5 mins",
                      type: "coding"
                    }, {
                      name: `Divide by Three`,
                      complete: false,
                      ttc: "4 mins",
                      type: "coding"
                    }, {
                      name: `Whisper`,
                      complete: false,
                      ttc: "6 mins",
                      type: "coding"
                    }, {
                      name: `Average of Four`,
                      complete: false,
                      ttc: "6 mins",
                      type: "coding"
                    }, {
                      name: `Average Walkthrough`,
                      complete: false,
                      ttc: "6 mins",
                      type: "video"
                    }, {
                      name: `Yell (*)`,
                      complete: false,
                      ttc: "5 mins",
                      type: "coding"
                    }, {
                      name: `Echo (*)`,
                      complete: false,
                      ttc: "6 mins",
                      type: "coding"
                    }
                  ]
                }, {
                  name: "Intro to Control Flow",
                  complete: false,
                  ttc: "39 mins",
                  assignmentCount: 7,
                  completedAssignmentCount: 0,
                  assignments: [
                    {
                      name: `Conditionals`,
                      complete: false,
                      ttc: "4 mins",
                      type: "reading"
                    }, {
                      name: `Conditionals Demo`,
                      complete: false,
                      ttc: "8 mins",
                      type: "video"
                    }, {
                      name: `Mutually Exclusive Conditions`,
                      complete: false,
                      ttc: "2 mins",
                      type: "reading"
                    }, {
                      name: `Basic Loops`,
                      complete: false,
                      ttc: "5 mins",
                      type: "reading"
                    }, {
                      name: `Loops Demo`,
                      complete: false,
                      ttc: "8 mins",
                      type: "video"
                    }, {
                      name: `Arrays`,
                      complete: false,
                      ttc: "5 mins",
                      type: "reading"
                    }, {
                      name: `Array Lecture`,
                      complete: false,
                      ttc: "7 mins",
                      type: "video"
                    }
                  ]
                }, {
                  name: "Javascript Fundamentals Assessment",
                  complete: false,
                  ttc: "3 hrs",
                  assignmentCount: 3,
                  completedAssignmentCount: 0,
                  assignments: [
                    {
                      name: `Assessment Expectations`,
                      complete: false,
                      ttc: "2 mins",
                      type: "reading"
                    }, {
                      name: `Assessment Quiz`,
                      complete: false,
                      ttc: "1 hr",
                      type: "quiz"
                    }, {
                      name: `JavaScript Unit Test Problems`,
                      complete: false,
                      ttc: "2 hrs",
                      type: "project"
                    }
                  ]
                }
              ]
            }, {
              name: "HTML and CSS Fundamentals",
              complete: false,
              viewCompleted: false,
              assignmentCount: 34,
              completedAssignmentCount: 0,
              units: [
                {
                  name: "HTML Basics",
                  complete: false,
                  ttc: "1 hr and 58 mins",
                  assignmentCount: 11,
                  completedAssignmentCount: 0,
                  assignments: [
                    {
                      name: `Hello HTML`,
                      complete: false,
                      ttc: "10 mins",
                      type: "coding"
                    }, {
                      name: `Intro to HTML`,
                      complete: false,
                      ttc: "5 mins",
                      type: "reading"
                    }, {
                      name: `Intro to HTML Summary`,
                      complete: false,
                      ttc: "3 mins",
                      type: "video"
                    }, {
                      name: `HTML Tags Summary`,
                      complete: false,
                      ttc: "2 mins",
                      type: "video"
                    }, {
                      name: `HTML Elements Reference I`,
                      complete: false,
                      ttc: "16 mins",
                      type: "reading"
                    }, {
                      name: `HTML Elements Quiz I Directions`,
                      complete: false,
                      ttc: "1 min",
                      type: "reading"
                    }, {
                      name: `HTML Elements Quiz I`,
                      complete: false,
                      ttc: "15 mins",
                      type: "quiz"
                    }, {
                      name: `HTML Tags Practice`,
                      complete: false,
                      ttc: "30 mins",
                      type: "coding"
                    }, {
                      name: `Debugging HTML Demo`,
                      complete: false,
                      ttc: "5 mins",
                      type: "video"
                    }, {
                      name: `Debugging HTML`,
                      complete: false,
                      ttc: "15 mins",
                      type: "coding"
                    }, {
                      name: `HTML Basics Quiz`,
                      complete: false,
                      ttc: "15 mins",
                      type: "quiz"
                    }
                  ]
                }, {
                  name: "HTML Forms",
                  complete: false,
                  ttc: "2 hrs and 3 mins",
                  assignmentCount: 5,
                  completedAssignmentCount: 0,
                  assignments: [
                    {
                      name: `HTML Forms Overview`,
                      complete: false,
                      ttc: "7 mins",
                      type: "reading"
                    }, {
                      name: `HTML Elements Reference II`,
                      complete: false,
                      ttc: "10 mins",
                      type: "reading"
                    }, {
                      name: `HTML Elements Quiz II Directions`,
                      complete: false,
                      ttc: "1 min",
                      type: "reading"
                    }, {
                      name: `HTML Elements Quiz II`,
                      complete: false,
                      ttc: "15 mins",
                      type: "reading"
                    }, {
                      name: `Building HTML Forms`,
                      complete: false,
                      ttc: "1 hr and 30 mins",
                      type: "coding"
                    }
                  ]
                }, {
                  name: "CSS Basics",
                  complete: false,
                  ttc: "1 hr and 22 mins",
                  assignmentCount: 6,
                  completedAssignmentCount: 0,
                  assignments: [
                    {
                      name: `Intro to CSS`,
                      complete: false,
                      ttc: "2 mins",
                      type: "reading"
                    }, {
                      name: `CSS Selectors`,
                      complete: false,
                      ttc: "17 mins",
                      type: "reading"
                    }, {
                      name: `Styling a Webpage with CSS`,
                      complete: false,
                      ttc: "30 mins",
                      type: "coding"
                    }, {
                      name: `Debugging CSS`,
                      complete: false,
                      ttc: "3 mins",
                      type: "reading"
                    }, {
                      name: `Refactoring CSS`,
                      complete: false,
                      ttc: "15 mins",
                      type: "coding"
                    }, {
                      name: `CSS Basics Quiz`,
                      complete: false,
                      ttc: "15 mins",
                      type: "quiz"
                    }
                  ]
                }, {
                  name: "CSS Layout & Transitions",
                  complete: false,
                  ttc: "3 hrs",
                  assignmentCount: 9,
                  completedAssignmentCount: 0,
                  assignments: [
                    {
                      name: `The Box Model`,
                      complete: false,
                      ttc: "9 mins",
                      type: "reading"
                    }, {
                      name: `CSS Positioning`,
                      complete: false,
                      ttc: "7 mins",
                      type: "reading"
                    }, {
                      name: `Flexbox Froggy`,
                      complete: false,
                      ttc: "30 mins",
                      type: "coding"
                    }, {
                      name: `Flexbox Defense`,
                      complete: false,
                      ttc: "30 mins",
                      type: "coding"
                    }, {
                      name: `Grid Garden`,
                      complete: false,
                      ttc: "30 mins",
                      type: "coding"
                    }, {
                      name: `CSS Transitions`,
                      complete: false,
                      ttc: "5 mins",
                      type: "reading"
                    }, {
                      name: `CSS Whack-A-Mole`,
                      complete: false,
                      ttc: "1 hr",
                      type: "coding"
                    }, {
                      name: `CSS Quiz 2`,
                      complete: false,
                      ttc: "15 mins",
                      type: "quiz"
                    }, {
                      name: `CSS Layout Practice`,
                      complete: false,
                      ttc: "30 mins",
                      type: "coding"
                    }
                  ]
                }, {
                  name: "HTML & CSS Assessment",
                  complete: false,
                  ttc: "3 hrs",
                  assignmentCount: 3,
                  completedAssignmentCount: 0,
                  assignments: [
                    {
                      name: `Assessment Expectations`,
                      complete: false,
                      ttc: "2 mins",
                      type: "reading"
                    }, {
                      name: `HTML & CSS Quiz`,
                      complete: false,
                      ttc: "1 hr",
                      type: "quiz"
                    }, {
                      name: `HTML & CSS Assessment`,
                      complete: false,
                      ttc: "2 hrs",
                      type: "project"
                    }
                  ]
                }
              ]
            }
          ]
        }, {
          name: "Front-End Engineering",
          locked: true,
          unitCount: 15,
          assessmentCount: 2,
          courses: [
            {
              name: "Dummy text",
              complete: false,
              units: [
                {
                  name: "Dummy text",
                  complete: false,
                  ttc: "1 hr and 58 mins",
                  assignments: [
                    {
                      name: `Dummy text`,
                      complete: false,
                      ttc: "10 mins",
                      type: "coding"
                    }, {
                      name: `Dummy text`,
                      complete: false,
                      ttc: "10 mins",
                      type: "coding"
                    }, {
                      name: `Dummy text`,
                      complete: false,
                      ttc: "10 mins",
                      type: "coding"
                    }
                  ]
                }, {
                  name: "Dummy text",
                  complete: false,
                  ttc: "1 hr and 58 mins",
                  assignments: [
                    {
                      name: `Dummy text`,
                      complete: false,
                      ttc: "10 mins",
                      type: "coding"
                    }, {
                      name: `Dummy text`,
                      complete: false,
                      ttc: "10 mins",
                      type: "coding"
                    }, {
                      name: `Dummy text`,
                      complete: false,
                      ttc: "10 mins",
                      type: "coding"
                    }
                  ]
                }, {
                  name: "Dummy text",
                  complete: false,
                  ttc: "1 hr and 58 mins",
                  assignments: [
                    {
                      name: `Dummy text`,
                      complete: false,
                      ttc: "10 mins",
                      type: "coding"
                    }, {
                      name: `Dummy text`,
                      complete: false,
                      ttc: "10 mins",
                      type: "coding"
                    }, {
                      name: `Dummy text`,
                      complete: false,
                      ttc: "10 mins",
                      type: "coding"
                    }
                  ]
                }
              ]
            }
          ]
        }, {
          name: "Back-End Engineering",
          locked: true,
          unitCount: 17,
          assessmentCount: 3,
          courses: [
            {
              name: "Dummy text",
              complete: false,
              units: [
                {
                  name: "Dummy text",
                  complete: false,
                  ttc: "1 hr and 58 mins",
                  assignments: [
                    {
                      name: `Dummy text`,
                      complete: false,
                      ttc: "10 mins",
                      type: "coding"
                    }, {
                      name: `Dummy text`,
                      complete: false,
                      ttc: "10 mins",
                      type: "coding"
                    }, {
                      name: `Dummy text`,
                      complete: false,
                      ttc: "10 mins",
                      type: "coding"
                    }
                  ]
                }, {
                  name: "Dummy text",
                  complete: false,
                  ttc: "1 hr and 58 mins",
                  assignments: [
                    {
                      name: `Dummy text`,
                      complete: false,
                      ttc: "10 mins",
                      type: "coding"
                    }, {
                      name: `Dummy text`,
                      complete: false,
                      ttc: "10 mins",
                      type: "coding"
                    }, {
                      name: `Dummy text`,
                      complete: false,
                      ttc: "10 mins",
                      type: "coding"
                    }
                  ]
                }, {
                  name: "Dummy text",
                  complete: false,
                  ttc: "1 hr and 58 mins",
                  assignments: [
                    {
                      name: `Dummy text`,
                      complete: false,
                      ttc: "10 mins",
                      type: "coding"
                    }, {
                      name: `Dummy text`,
                      complete: false,
                      ttc: "10 mins",
                      type: "coding"
                    }, {
                      name: `Dummy text`,
                      complete: false,
                      ttc: "10 mins",
                      type: "coding"
                    }
                  ]
                }
              ]
            }
          ]
        }
      ]
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
</style>