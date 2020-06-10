<template>

<div class="app-container">
  <div class="quiz-container">
    <div class="quiz-header">
<h1>Quiz App</h1>
    </div>
    <div class="quiz-main" v-for="(element, index) in questions.slice(a,b)" :key="index">
<div class="question-box">
<h4>Question</h4>
<p>{{element.question}}</p>
</div>

<div class="suggestion-box">
<ul>

  <li v-for="(item, index) in element.suggestions" :key="index">{{item.suggestion}}</li>
</ul>
</div>
    </div>
<div class="score-box"></div>
    <div class="quiz-footer"></div>
  </div>
</div>


</template>

<script>
export default {
  name: 'quiz-app',
  data () {
    return {
      questions:[
        { question: 'whats the full meaning of HTML',

          suggestions : [
            {suggestion:"Hypertext Markup Language"},
            {suggestion:"Hyphenated Markup Language"},
            {suggestion:"Hypertext Markdown Language"},
            {suggestion:"Hyphenated Markdown Language"},

          ],
        },

       { question:"whats the full meaning of XML",

          suggestions:[
            {suggestion:"Extended Markup Language"},
            {suggestion:"Extensible  Markup Language"},
            {suggestion:"Extended Markdown Language"},
            {suggestion:"Extensible Markdown Language"},

          ]
          },

           {
             question:"whats the full meaning of WWW",


          suggestions:[
            {suggestion:"World Wide Web"},
            {suggestion:"World Web Wide"},
            {suggestion:"Word Wide Web"},
            {suggestion:"Word Web Wide"},

          ]
          },


           {
             question:"whats the full meaning of PHP",

          suggestions:[
            {suggestion:"Processor Hyperactive Program"},
            {suggestion:"Hypertext Preprocessor"},
            {suggestion:"Preprocessor Hyperactive Programming"},
            {suggestion:"Programmable Hypertext Program"},

          ]
          },


           {
             question:"whats the full meaning of PHP",
        
          suggestions:[
            {suggestion:"Processor Hyperactive Program"},
            {suggestion:"Hypertext Preprocessor"},
            {suggestion:"Preprocessor Hyperactive Programming"},
            {suggestion:"Programmable Hypertext Program"},

          ]
          }
      ],
      a:0,
      b:1,

    }
  }
}
</script>

<style scoped src = "./assets/css/quiz-app.css">

</style>
