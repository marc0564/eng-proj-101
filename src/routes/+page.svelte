<!DOCTYPE html>
<head>
  <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap" rel="stylesheet">
</head>
 <style>
  @import './styles.css';
  
</style>

<body>

<div class="parallax" alt="yes" title="image from images.radio.com">
    <img class="arrow" src="https://cdn3.iconfinder.com/data/icons/google-material-design-icons/48/ic_keyboard_arrow_down_48px-128.png" style = "left: 1px;
    right: unset;"alt ="scroll down" <input type="button" onClick="smoothScroll(getElementById('middle'));"title="SCROLL!"/>
  <div class="image-credit">Image from images.radio.com</div>
</div>

<div id="middle"class="content">
  <div class="blog-header">
    <div class="blog-title">Common Misconceptions in Learning Programming</div>
    <div class="blog-author"> Marc Hosana</div>
     <div class="separator"></div>
   <div class="blog-date"> April 23, 2023</div>
  </div>

  <p>Have you ever wondered about the common goof-ups kids have when learning to code? Well, let’s dive into that. My study focuses on fifth-grade students learning Python, a popular programming language, and I wanted to see what misconceptions were persistent amongst students, and ultimately dissect these problems to find ways to address and avoid them.</p>

  <p>Here's what I found in my studies: implementing <a href='https://www.youtube.com/watch?v=cQT33yu9pY8' target='_blank'> variables</a>, using the right <a href='https://www.youtube.com/watch?v=ppsCxnNm-JI' target='_blank'>data type</a>, and, using the right <a href='https://www.youtube.com/watch?v=ppsCxnNm-JI' target='_blank'> order of execution</a> were the most common mistakes among students. These were the 3 that seemed to haunt and hinder the students.</p>

  <p>It is shocking however that a problem that persisted and was tough to shake off for a majority of the students was variables, arguably the most fundamental concept in programming. It turns out that kids thought variables— things that hold a single value— could hold a bunch of different values. Kids also got confused about how to change the value of a variable. They thought replacing the variable with a new value would make it add up all the previously held values. (For ex. If the variable x held 4 and reassigned the value 6, students would think x would be 10 instead of 6)</p>

  <p>While mistakes are to be expected, especially since they are only kids, the biggest difference in production output was when teachers began to teach differently. Teachers often just pushed for a syntactic understanding of the programming language, instead of the actual concepts behind it. But this is flawed because teaching programming isn't just about the code itself; it's about understanding where students might get tripped up and helping them navigate those hurdles, especially through reinforcing concepts. A crucial part of students' learning was the introduction to visualizing these concepts as they were able to make mental connections in their minds.</p>

  <p>So, what does this mean for your teachers? Knowing where their students, like yourself,  might stumble is key to helping them learn better. By giving extra attention to tricky concepts like variables and using supplemental teaching tools such as visualizations, teachers can help students avoid these common concepts and possibly even beyond these simple ones.</p>

  <p>You might not think every kid needs to become a computer whiz (which is true), but learning how to think like one is super useful.  If we can fix these problems, we are in return facilitating their computational and problem-solving skills.</p>

    <button class="btn-style"id="showQuizButton">click this to take a quiz about the same programming misconceptions kids made!</button> 

  <div id="quizContainer" style="display: none;">
    <div class="quiz-container">
        <h1> Answer the questions and run the code! </h1>
        <h3>Question 1:</h3>
        <p>What is the output of the following Python code?</p>
        <p></p>
        <form id="quiz-form">
            <input type="radio" id="option1" name="answer" value="20">
            <label for="option1">20</label><br>
            <input type="radio" id="option2" name="answer" value="10">
            <label for="option2">10</label><br>
            <input type="radio" id="option3" name="answer" value="30">
            <label for="option3">30</label><br><br>
            <button type="submit">Submit</button>
        </form>
        <div id="result"></div>
    </div> 

    <div class="ide-container">
        <iframe src="https://trinket.io/embed/python3/7fdbfaf879?toggleCode=true&runOption=true" title="EMBEDDED-IDE" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
    </div>

    <!-- Quiz 2 -->
    <div class="quiz-container">
        <h3>Question 2:</h3>
        <p>Is this valid code, is it able to run?</p>
        <p></p>
        <form id="quiz-form-2">
            <input type="radio" id="option1-2" name="answer-2" value="True">
            <label for="option1-2">It cannot run</label><br>
            <input type="radio" id="option2-2" name="answer-2" value="False">
            <label for="option2-2">It is able to run</label><br><br>
            <button type="submit">Submit</button>
        </form>
        <div id="result-2"></div>
    </div>

    <div class="ide-container">
        <iframe src="https://trinket.io/embed/python3/f7195d2c85?toggleCode=true&runOption=true" title="EMBEDDED-IDE" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
    </div>
  </div>
</div>

<script>
   document.getElementById('showQuizButton').addEventListener('click', function() {
    var quizContainer = document.getElementById('quizContainer');
    if (quizContainer.style.display === 'none' || quizContainer.style.display === '') {
        quizContainer.style.display = 'block';
    } else {
        quizContainer.style.display = 'none';
    }
});

    // Smooth scroll function
    window.smoothScroll = function(target) {
        var scrollContainer = target;
        do {
            scrollContainer = scrollContainer.parentNode;
            if (!scrollContainer) return;
            scrollContainer.scrollTop += 1;
        } while (scrollContainer.scrollTop == 0);
        
        var targetY = 0;
        do {
            if (target == scrollContainer) break;
            targetY += target.offsetTop;
        } while (target = target.offsetParent);
        
        scroll = function(c, a, b, i) {
            i++; if (i > 30) return;
            c.scrollTop = a + (b - a) / 30 * i;
            setTimeout(function(){ scroll(c, a, b, i); }, 2);
        }
        scroll(scrollContainer, scrollContainer.scrollTop, targetY, 0);
    }
</script>


<script>
    // Quiz 1
    document.getElementById('quiz-form').addEventListener('submit', function(event) {
        event.preventDefault(); // Prevent form submission
        const selectedAnswer = document.querySelector('input[name="answer"]:checked');
        if (selectedAnswer) {
            if (selectedAnswer.value === '20') {
                selectedAnswer.parentNode.style.backgroundColor = 'lightgreen';
                document.getElementById('result').textContent = 'Correct!';
            } else {
                selectedAnswer.parentNode.style.backgroundColor = 'red';
                document.getElementById('result').textContent = 'Incorrect!';
            }
        } else {
            document.getElementById('result').textContent = 'Please select an answer.';
        }
    });
    
    // Quiz 2
    document.getElementById('quiz-form-2').addEventListener('submit', function(event) {
        event.preventDefault(); // Prevent form submission
        const selectedAnswer = document.querySelector('input[name="answer-2"]:checked');
        if (selectedAnswer) {
            if (selectedAnswer.value === 'True') {
                selectedAnswer.parentNode.style.backgroundColor = 'lightgreen';
                document.getElementById('result-2').textContent = 'Correct!';
            } else {
                selectedAnswer.parentNode.style.backgroundColor = 'red';
                document.getElementById('result-2').textContent = 'Incorrect!';
            }
        } else {
            document.getElementById('result-2').textContent = 'Please select an answer.';
        }
    });
</script>

</body>
