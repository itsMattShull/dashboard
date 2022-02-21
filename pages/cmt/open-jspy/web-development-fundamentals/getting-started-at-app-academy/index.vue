<template>
  <div>
    <section class="nav">
      <h1>Units</h1>
      <div>
          <b-button variant="info">Add Unit</b-button>
      </div>
    </section>
    <section>
      <b-list-group>
        <b-list-group-item v-for="unit in courses[0].modules[0].units" :key="unit.index" class="flex">
          <a :href="`/dashboard/cmt/open-jspy/web-development-fundamentals/getting-started-at-app-academy/${unit.slug}`">{{unit.name}}</a>
          <div>
            <b-button-group>
              <b-button variant="info">Edit</b-button>
              <b-button variant="danger">Delete</b-button>
            </b-button-group>
          </div>
        </b-list-group-item>
      </b-list-group>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      lessonTypes: ["reading", "video", "quiz", "project", "coding"],
      courses: [
        {
          slug: 'web-development-fundamentals',
          name: "Web Development Fundamentals",
          locked: false,
          unitCount: 10,
          assessmentCount: 2,
          modules: [
            {
              slug: "getting-started-at-app-academy",
              name: "Getting Started at App Academy",
              complete: true,
              viewCompleted: false,
              units: [
                {
                  slug: "getting-started",
                  name: "Getting Started",
                  ttc: "49 mins",
                  complete: true,
                  lessonCount: 8,
                  completedLessonCount: 8,
                  lessons: [
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
              slug: "javascript-fundamentals123",
              name: "Javascript Fundamentals",
              complete: false,
              viewCompleted: false,
              lessonCount: 45,
              completedLessonCount: 17,
              units: [
                {
                  name: "Data Types",
                  complete: true,
                  ttc: "1 hr and 29 mins",
                  lessonCount: 18,
                  completedLessonCount: 18,
                  lessons: [
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
                  lessonCount: 17,
                  completedLessonCount: 4,
                  lessons: [
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
                  name: "Control Flow",
                  complete: false,
                  ttc: "39 mins",
                  lessonCount: 7,
                  completedLessonCount: 0,
                  lessons: [
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
                  name: "Javascript Fundamentals Formative Quiz",
                  complete: false,
                  ttc: "3 hrs",
                  lessonCount: 3,
                  completedLessonCount: 0,
                  lessons: [
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
              slug: "html-and-css-fundamentals",
              name: "HTML and CSS Fundamentals",
              complete: false,
              viewCompleted: false,
              lessonCount: 34,
              completedLessonCount: 0,
              units: [
                {
                  name: "HTML Basics",
                  complete: false,
                  ttc: "1 hr and 58 mins",
                  lessonCount: 11,
                  completedLessonCount: 0,
                  lessons: [
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
                  lessonCount: 5,
                  completedLessonCount: 0,
                  lessons: [
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
                  lessonCount: 6,
                  completedLessonCount: 0,
                  lessons: [
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
                  lessonCount: 9,
                  completedLessonCount: 0,
                  lessons: [
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
                  lessonCount: 3,
                  completedLessonCount: 0,
                  lessons: [
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
            }, {
              slug: "local-javascript",
              name: "Local Javascript",
              complete: true,
              viewCompleted: false,
              units: [
                {
                  name: "Getting Started with Node",
                  ttc: "49 mins",
                  complete: true,
                  lessonCount: 8,
                  completedLessonCount: 8,
                  lessons: [
                    {
                      name: "Basic Setup",
                      isLesson: true,
                      practices: [
                        {
                          name: "Node.js",
                          complete: true,
                          ttc: "5 mins",
                          type: "reading"
                        }, {
                          name: "Running Your Code",
                          complete: true,
                          ttc: "2 mins",
                          type: "coding"
                        }, {
                          name: "Hello World Terminal",
                          complete: true,
                          ttc: "2 mins",
                          type: "coding"
                        }
                      ]
                    }, {
                      name: "Javascript Unit Tests",
                      isLesson: true,
                      practices: [
                        {
                          name: "A Brief Intro to Unit Tests",
                          complete: true,
                          ttc: "5 mins",
                          type: "reading"
                        }
                      ]
                    }
                  ]
                }, {
                  name: "Local Javascript Practice",
                  ttc: "49 mins",
                  complete: true,
                  lessonCount: 8,
                  completedLessonCount: 8,
                  lessons: [
                    {
                      name: "",
                      isLesson: true,
                      practices: [
                        {
                          name: "Local Javascript Practice",
                          complete: true,
                          ttc: "10 mins",
                          type: "video"
                        }, {
                          name: "Refactoring Javascript Practice",
                          complete: true,
                          ttc: "5 mins",
                          type: "reading"
                        }, {
                          name: "Non-standard For Loops",
                          complete: true,
                          ttc: "10 mins",
                          type: "quiz"
                        }, {
                          name: "Non-Standard For Loops Quiz",
                          complete: true,
                          ttc: "5 mins",
                          type: "reading"
                        }, {
                          name: "Non-Standard For Loops Practice",
                          complete: true,
                          ttc: "5 mins",
                          type: "reading"
                        }
                      ]
                    }, {
                      name: "HTML / CSS Unit Tests",
                      isLesson: true,
                      practices: [
                        {
                          name: "Intro to Cypress Testing",
                          complete: true,
                          ttc: "5 mins",
                          type: "reading"
                        }, {
                          name: "Cypress Practice - HTML Forms Debugging",
                          complete: true,
                          ttc: "2 mins",
                          type: "coding"
                        }
                      ]
                    }
                  ]
                }
              ]
            }
          ]
        }, {
          slug: 'javascript-fundamentals',
          name: "JavaScript Fundamentals",
          locked: false,
          unitCount: 10,
          assessmentCount: 2,
          modules: [
            {
              name: "Getting Started at App Academy",
              complete: false,
              viewCompleted: false,
              units: [
                {
                  name: "Getting Started",
                  ttc: "49 mins",
                  complete: false,
                  lessonCount: 8,
                  completedLessonCount: 0,
                  lessons: [
                    {
                      name: "How to Learn at App Academy",
                      complete: false,
                      ttc: "10 mins",
                      type: "video"
                    }, {
                      name: "How to Manage Difficulty",
                      complete: false,
                      ttc: "5 mins",
                      type: "reading"
                    }, {
                      name: "How to Succeed at App Academy",
                      complete: false,
                      ttc: "10 mins",
                      type: "quiz"
                    }, {
                      name: "Documenting My Expectations",
                      complete: false,
                      ttc: "5 mins",
                      type: "reading"
                    }, {
                      name: "How to Ask Great Questions",
                      complete: false,
                      ttc: "5 mins",
                      type: "reading"
                    }, {
                      name: "The Secret to Solving Any Problem",
                      complete: false,
                      ttc: "7 mins",
                      type: "reading"
                    }, {
                      name: "Polya's Problem Solving Framework",
                      complete: false,
                      ttc: "5 mins",
                      type: "quiz"
                    }, {
                      name: "Using Online Resources and Documentation",
                      complete: false,
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
              lessonCount: 45,
              completedLessonCount: 0,
              units: [
                {
                  name: "Data Types",
                  complete: false,
                  ttc: "1 hr and 29 mins",
                  lessonCount: 18,
                  completedLessonCount: 0,
                  lessons: [
                    {
                      name: `A Particularly Long and Detailed "Hello World!"`,
                      complete: false,
                      ttc: "10 mins",
                      type: "reading"
                    }, {
                      name: `"Hello World!" REPL`,
                      complete: false,
                      ttc: "10 mins",
                      type: "coding"
                    }, {
                      name: `Intro to Javascript`,
                      complete: false,
                      ttc: "3 mins",
                      type: "reading"
                    }, {
                      name: `The Number Data Type`,
                      complete: false,
                      ttc: "2 mins",
                      type: "reading"
                    }, {
                      name: `The Number Data Type Demo`,
                      complete: false,
                      ttc: "9 mins",
                      type: "video"
                    }, {
                      name: `Numbers Exercise`,
                      complete: false,
                      ttc: "4 mins",
                      type: "coding"
                    }, {
                      name: `Artithmetic Operators`,
                      complete: false,
                      ttc: "7 mins",
                      type: "quiz"
                    }, {
                      name: `The Boolean Data Type`,
                      complete: false,
                      ttc: "2 mins",
                      type: "reading"
                    }, {
                      name: `The Boolean Data Type Lecture`,
                      complete: false,
                      ttc: "5 mins",
                      type: "video"
                    }, {
                      name: `The Boolean Data Type Demo`,
                      complete: false,
                      ttc: "4 mins",
                      type: "video"
                    }, {
                      name: `Boolean Exercise`,
                      complete: false,
                      ttc: "7 mins",
                      type: "coding"
                    }, {
                      name: `Variables`,
                      complete: false,
                      ttc: "3 mins",
                      type: "reading"
                    }, {
                      name: `Variables Demo`,
                      complete: false,
                      ttc: "11 mins",
                      type: "video"
                    }, {
                      name: `Variables Practice`,
                      complete: false,
                      ttc: "4 mins",
                      type: "coding"
                    }, {
                      name: `Variables Quiz`,
                      complete: false,
                      ttc: "5 mins",
                      type: "quiz"
                    }, {
                      name: `The String Data Type`,
                      complete: false,
                      ttc: "3 mins",
                      type: "reading"
                    }, {
                      name: `String Type Lecture`,
                      complete: false,
                      ttc: "6 mins",
                      type: "video"
                    }, {
                      name: `String Type Demo`,
                      complete: false,
                      ttc: "8 mins",
                      type: "video"
                    }
                  ]
                }, {
                  name: "Intro to Functions",
                  complete: false,
                  ttc: "1 hr and 46 mins",
                  lessonCount: 17,
                  completedLessonCount: 0,
                  lessons: [
                    {
                      name: `Functions`,
                      complete: false,
                      ttc: "9 mins",
                      type: "reading"
                    }, {
                      name: `Parameters and Arguments`,
                      complete: false,
                      ttc: "2 mins",
                      type: "reading"
                    }, {
                      name: `Functions Lecture`,
                      complete: false,
                      ttc: "9 mins",
                      type: "video"
                    }, {
                      name: `Intro to Functions Quiz`,
                      complete: false,
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
                  name: "Control Flow",
                  complete: false,
                  ttc: "39 mins",
                  lessonCount: 7,
                  completedLessonCount: 0,
                  lessons: [
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
                  name: "Javascript Fundamentals Formative Quiz",
                  complete: false,
                  ttc: "3 hrs",
                  lessonCount: 3,
                  completedLessonCount: 0,
                  lessons: [
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
              lessonCount: 34,
              completedLessonCount: 0,
              units: [
                {
                  name: "HTML Basics",
                  complete: false,
                  ttc: "1 hr and 58 mins",
                  lessonCount: 11,
                  completedLessonCount: 0,
                  lessons: [
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
                  lessonCount: 5,
                  completedLessonCount: 0,
                  lessons: [
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
                  lessonCount: 6,
                  completedLessonCount: 0,
                  lessons: [
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
                  lessonCount: 9,
                  completedLessonCount: 0,
                  lessons: [
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
                  lessonCount: 3,
                  completedLessonCount: 0,
                  lessons: [
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
        }
      ]
    }
  },
};
</script>

<style>
.nav, .flex {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>