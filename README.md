# JavaScript-Quiz
This is the project to build a quiz using JavaScript.  


# index.html 

<code>
<pre>

<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title> JavaScript Quiz</title>
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
</head>

<body>

    <!-- top section -->
    <div class="intro py-3 bg-white text-center">
        <div class="container">
            <h2 class="text-primary display-3 my-4"> Quiz using Javascript</h2>
        </div>
    </div>


    <!-- result section -->
    <div class="result py-4 d-none bg-light text-center">
        <div class="container lead">
            <p>You are <span class="text-primary display-4 p-3">0%</span> ninja</p>
        </div>
    </div>

    <!-- quiz section -->
    <div class="quiz py-4 bg-primary">
        <div class="container">
            <h2 class="my-5 text-white">On with the questions...</h2>

            <form class="quiz-form text-light">
                <div class="my-5">
                    <p class="lead font-weight-normal">1. How do you give a ninja directions?</p>
                    <div class="form-check my-2 text-white-50">
                        <input type="radio" name="q1" value="A" checked>
                        <label class="form-check-label">Show them a map</label>
                    </div>
                    <div class="form-check my-2 text-white-50">
                        <input type="radio" name="q1" value="B">
                        <label class="form-check-label">Don't worry, the ninja will find you</label>
                    </div>
                </div>
                <div class="my-5">
                    <p class="lead font-weight-normal">2. If a ninja has 3 apples, then gives one to Mario & one to Yoshi, how many apples does the ninja have left?</p>
                    <div class="form-check my-2 text-white-50">
                        <input type="radio" name="q2" value="A" checked>
                        <label class="form-check-label">1 apple</label>
                    </div>
                    <div class="form-check my-2 text-white-50">
                        <input type="radio" name="q2" value="B">
                        <label class="form-check-label">3 apples, and two corpses</label>
                    </div>
                </div>
                <div class="my-5">
                    <p class="lead font-weight-normal">3. How do you know when you've met a ninja?</p>
                    <div class="form-check my-2 text-white-50">
                        <input type="radio" name="q3" value="A" checked>
                        <label class="form-check-label">You'll recognize the outfit</label>
                    </div>
                    <div class="form-check my-2 text-white-50">
                        <input type="radio" name="q3" value="B">
                        <label class="form-check-label">The grim reaper will tell you</label>
                    </div>
                </div>
                <div class="my-5">
                    <p class="lead font-weight-normal">4. What's a ninja's favourite array method?</p>
                    <div class="form-check my-2 text-white-50">
                        <input type="radio" name="q4" value="A" checked>
                        <label class="form-check-label">forEach()</label>
                    </div>
                    <div class="form-check my-2 text-white-50">
                        <input type="radio" name="q4" value="B">
                        <label class="form-check-label">slice()</label>
                    </div>
                </div>
                <div class="text-center">
                    <input type="submit" class="btn btn-light">
                </div>
            </form>

        </div>
    </div>

    <script src="app.js"></script>
</body>

</html>

</pre>

</code>


# app.js file

<code>
<pre>
const correctAnswers = ['B', 'B', 'B', 'B'];
const form = document.querySelector('.quiz-form');

const result = document.querySelector('.result');


form.addEventListener('submit', e =>{

    e.preventDefault();

    let score = 0;
    const userAnswer = [form.q1.value, form.q2.value,    form.q3.value, form.q4.value]
    //check answers

    userAnswer.forEach((answer, index) =>{

        if(answer === correctAnswers[index]){
            score +=25;
        }
      //  console.log(score);
      //show result on page

    });

    scrollTo(0, 0);
    result.classList.remove('d-none');
    let output = 0;
    const timer = setInterval(()=>{
        result.querySelector('span').textContent = `${output}%`;
        if(output === score){
            clearInterval(timer);
        }else{
            output++;
        }
    }, 10)

})
 
// let i = 0; 
// const timer = setInterval(()=>{
//     console.log("hello")
//     i++;
//     if(i == 5){
//         clearInterval(timer);
//     }
// }, 1000)
</pre>
</code>