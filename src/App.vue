<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'


</script>

<script>
export default {
  data() {
    return {
      message1: 'RACECAR...',
      message2: 'Dogma I am God', 
      demo: '---'
    }
  },
  methods: {
    reverseMessage() {
      var tmp = document.getElementById("flexRadioDefault1").checked; 
      if (tmp == 1)
      { 
        this.message1 = this.message1.split('').reverse().join(''); 
      } 
      else 
      {
         this.message2 = this.message2.split('').reverse().join(''); 
      }
    },
    notify() {
      alert('navigation was prevented.')
    },
    myFunction1() {
      // textIn1_id = id of input box. this is setting x to the value of the string in the input box  
      var x = document.getElementById("textIn1_id").value;

      // docid_1 is new, made up id for this element it's assinged the value of x 
      // docid_1 is then displayed with the <p> 
      document.getElementById("docid_1").innerHTML = x;
      // we could make up more if we wanted 
      document.getElementById("docid_2").innerHTML = x;
      
    },
    myFunction2() {
      // flexRadioDefault1 = id of checkbox? 
      var x = document.getElementById("flexRadioDefault1").checked;
      document.getElementById("radio_1").innerHTML = x;  
      var y = document.getElementById("flexRadioDefault2").checked;
      document.getElementById("radio_2").innerHTML = y; 
    },
  },

}
</script>




<template>
<!--   
--  add an external CSS file 

<head>
<link rel="stylesheet" href="mystyle.css">
</head>
-->

<h1> Vue 3 & Bootstrap 5.2 demo</h1> 
<br>

<!-- 
--  container for video 
-->
<div class="container" >
    <h3>Bootstrap image carousel</h3>
    <div id="carouselExampleControls" class="carousel slide" data-bs-ride="carousel">
      <div class="carousel-inner">
          <div class="carousel-item active">
            <img src="../src/assets/images/eraserhead.png"  height=300 width=600 alt="...">
          </div>
          <div class="carousel-item">
            <img src="https://picsum.photos/id/211/600/300" class="d-block w-200" alt="...">
          </div>
          <div class="carousel-item">
            <img src="https://picsum.photos/id/212/600/300" class="d-block w-200" alt="...">
          </div>
          <div class="carousel-item">
            <img src="https://picsum.photos/id/213/600/300" class="d-block w-200" alt="...">
          </div>
          <div class="carousel-item">
            <img src="https://picsum.photos/id/214/600/300" class="d-block w-200" alt="...">
          </div>
          <div class="carousel-item">
            <img src="https://picsum.photos/id/215/600/300" class="d-block w-200" alt="...">
          </div>
      </div>
      <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleControls" data-bs-slide="prev">
        <span class="carousel-control-prev-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Previous</span>
      </button>
      <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleControls" data-bs-slide="next">
        <span class="carousel-control-next-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Next</span>
      </button>
    </div>
    <br>
<!-- end of video container -->
</div>

<!-- 
-- container for checkbox, radio buttons, palindrome feature
-- bootstrap checkbox example 
-->
<div class="container">
  <br><br>
    <div class="form-check">
        <input class="form-check-input" type="checkbox" value="" id="flexCheckDefault">
        <label class="form-check-label" for="flexCheckDefault">
        check box default/unchecked
        </label>
    </div>
    <div class="form-check">
      <input class="form-check-input" type="checkbox" value="" id="flexCheckChecked" checked>
      <label class="form-check-label" for="flexCheckChecked">
        check box checked
      </label>
    </div> 

<!-- 
  -- Radio button example 
-->
    <div class="form-check">
        <input class="form-check-input" type="radio" name="flexRadioDefault" id="flexRadioDefault1" checked>
        <label class="form-check-label" for="flexRadioDefault1">
          Use message1 for pallindrome
        </label>
    </div>
    <div class="form-check">
      <input class="form-check-input" type="radio" name="flexRadioDefault" id="flexRadioDefault2">
      <label class="form-check-label" for="flexRadioDefault2">
        Use message2 for palindrome
      </label>
    </div>
    <!-- <button @click="myFunction2">Submit</button> -->
    <p id="radio_1"></p>
    <p id="radio_2"></p>
    <!-- This just displays the message strings created in the script section    -->
    <h6>message1: {{ message1 }}</h6>
    <h6>message2: {{ message2 }}</h6>
     <!-- Can also be an inline expression statement   --> 
    <button @click="message2 += 'ABC'">Append "ABC"</button>
    <button @click="reverseMessage">Reverse Message</button>



<!-- Example single danger button (red)
  -- Pulldown menu 
-->
<br><br>
  <div class="btn-group">
    <button type="button" class="btn btn-danger dropdown-toggle" data-bs-toggle="dropdown" aria-expanded="false">
      Other Stuff
    </button>
    <ul class="dropdown-menu">
      <li><a class="dropdown-item" href="../src/Page1/index.html">page1-html</a></li>
      <li><a class="dropdown-item" href="../src/Page1/page1.md">page1-md</a></li>
      <li><a class="dropdown-item" href="./foo.html">foo</a></li>
      <li><a class="dropdown-item" href="#">Something else here</a></li>
      <li><hr class="dropdown-divider"></li>
      <li><a class="dropdown-item" href="https://www.w3schools.com" target="_blank">Visit W3Schools</a></li>
      <li><a class="dropdown-item" href="http://localhost:5170/" target="_blank">Visit WorkNotes</a></li>
    </ul>
  </div>
    <!-- end of checkbox/radio button/danger pulldown container -->
</div>

<!--  
  --  container for text manipulation buttons  
--->

<span class="border border-dark">
  <div class="container" >
    <br><br><br>
    
    <h6>in the junk....Accessing & manipulating a Text Field</h6>
    <p>Click the button below to get & display the text in the text field.</p>
    
    <!-- input tag will create a small text box - id is textIn1_id-->
    <input type="text" id="textIn1_id" value="FUBAR...">
   
    <!--button calls myfunction1, which sets var x to text in testIn1_id 
      -- then it sets the doc innerHTML to value of the id lklk to x -->
    <button @click="myFunction1">Option API Try me...</button>

    <p id="docid_1"></p>
    
<!-- 
  -- Slider/switch thing example 
-->
  <div class="form-check form-switch">
    <span class="border border-dark">
          <input class="form-check-input" type="checkbox" role="switch" id="flexSwitchCheckDefault">
          <label class="form-check-label" for="flexSwitchCheckDefault">Default switch checkbox input</label>
    </span>  
  </div>
</div>

</span>
<!--
  end of template ------------------------------------------------------------- 
-->
</template>


<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}

h1 {
  color: maroon;
}
h2 {
  color: red;
}
h3 {
  color: navy;
}

#container {
border: 12px solid #B22222;
border-radius: 10px;
margin-top: 15px;
margin-bottom: 15px;
}
</style>

