<template>

<div class="app-container">
  <div class="quiz-container">
    <div class="quiz-header">
<h1 class="mt-5">Quiz App</h1>
    </div>
    <div class="quiz-main" v-for="(element, index) in questions.slice(a,b)" :key="index" v-show="quiz">
<div class="question-box">
<h2>Question {{b}} / {{questions.length}}</h2><br>
<p>{{element.question}}</p>
</div>

<div class="suggestion-box">
<ul>

  <li v-for="(item, index) in element.suggestions" :key="index" :class="select ? check(item):''" @click="selectResponse(item)">{{item.suggestion}}</li>
</ul>
</div>
    </div>
<div v-if="score_show" class="score-box">
<h2>Your score is </h2>
<h2>{{score}} / {{questions.length}}</h2>
  <div class="btn-restart"> 
  <button @click="restartQuiz"> Restart <i class="fas fa-sync-alt"></i></button>
  </div>
    </div>
    <div class="quiz-footer">
      <div class="box-button">
        <button @click="skipQuestion"> Skip</button>
        <button @click="nextQuestion">Next</button>
      </div>
    </div>
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
            {suggestion:"Hypertext Markup Language" ,correct :true},
            {suggestion:"Hyphenated Markup Language"},
            {suggestion:"Hypertext Markdown Language"},
            {suggestion:"Hyphenated Markdown Language"},

          ],
        },

       { question:"whats the full meaning of XML",

          suggestions:[
            {suggestion:"Extended Markup Language"},
            {suggestion:"Extensible  Markup Language", correct:true},
            {suggestion:"Extended Markdown Language"},
            {suggestion:"Extensible Markdown Language"},

          ]
          },

           {
             question:"whats the full meaning of WWW",


          suggestions:[
            {suggestion:"World Wide Web", correct:true},
            {suggestion:"World Web Wide"},
            {suggestion:"Word Wide Web"},
            {suggestion:"Word Web Wide"},

          ]
          },


           {
             question:"whats the full meaning of PHP",

          suggestions:[
            {suggestion:"Processor Hyperactive Program"},
            {suggestion:"Hypertext Preprocessor", correct:true},
            {suggestion:"Preprocessor Hyperactive Programming"},
            {suggestion:"Programmable Hypertext Program"},

          ]
          },


           {
             question:"whats the full meaning of PHP",

          suggestions:[
            {suggestion:"Processor Hyperactive Program"},
            {suggestion:"Hypertext Preprocessor", correct:true},
            {suggestion:"Preprocessor Hyperactive Programming"},
            {suggestion:"Programmable Hypertext Program"},

          ]
          }
      ],
      a:0,
      b:1,
      select : false,
      score : 0,
      quiz : true,
      score_show :false,

    }
  },
  methods: {
    selectResponse(e){
      this.select = true;

      if (e.correct) {
        this.score++;
        
      }
    },

    check(status){
      if (status.correct) {
        return 'correct'       
      }else{
        return 'incorrect'
      }
    },
    nextQuestion(){
      if (this.questions.length- 1 == this.a) {
       this.score_show = true;
       this.quiz = false; 
      } else {
      this.a++;
      this.b++;
      this.select = false;
      }
      
    },
     skipQuestion(){
      if (this.questions.length- 1 == this.a) {
       this.score_show = true;
       this.quiz = false; 
      } else {
      this.a++;
      this.b++;
      }  
    },
    restartQuiz(){
    Object.assign(this.$data,this.$options.data());
  }
  }
  
}
</script>

<style scoped src = "./assets/css/quiz-app.css">

</style>
