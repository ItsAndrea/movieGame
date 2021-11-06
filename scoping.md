# Guess the movie game 👾
## Software development plan(Waterfall Methodology or a try)
Construction time 📍 30/10/2021 - 06/11/2021<br>
Created by Andrea <br>

### 🚩 Requirements <br>
📌 A user must be able to navigate the system without getting lost <br>
📌 When a player clicks on an answer it should be shown whether it is correct or incorrect <br>
📌 Responsive design <br>
📌 There should be 10 questions in total <br>
### 🚩 Design <br>
## Index Page
![index](https://user-images.githubusercontent.com/85640313/140626838-e9000bc4-2140-40c1-9741-734b66088766.png)
## Game Page
![game](https://user-images.githubusercontent.com/85640313/140626848-902dd81f-6016-48b8-95d9-352374cccd18.png)


### 🚩 Implementation <br>
The file 'questions.json' contains the game content <br>
Check 'index.html' and 'game.html' for more <br>

    function chooseRandomQuestion(){
            chooseQuestion(Math.floor(Math.random() * interpreter_bq.length))
        }
<br>

    function chooseQuestion(n){
            quest = interpreter_bq[n]
            select_id("question").innerHTML = quest.question
            select_id("img").setAttribute("src", quest.img)
            style("img").objectFit = quest.objectFit;
            messAnswers(quest)
<br>

    function messAnswers(quest){
            possible_answers = [
                quest.incorrect1, 
                quest.answer, 
                quest.incorrect2
            ]
            possible_answers.sort(()=>Math.random()-0.5)
            select_id("btn1").innerHTML = possible_answers[0]
            select_id("btn2").innerHTML = possible_answers[1]
            select_id("btn3").innerHTML = possible_answers[2]
        }
<br>        
        
        function press_btn(i){
            if(possible_answers[i]==quest.answer){
                btn_correspondent[i].style.background = "#2FBF71"
            } else{
                btn_correspondent[i].style.background = "#EF2D56"
            }
            setTimeout(() => {
                restart_btn()
            }, 300);
        }
    
### 🚩 Verification <br>
Phase where the system was executed and a verification of the above requirements was performed <br> 
📌 A user must be able to navigate the system without getting lost ✔️<br>
📌 When a player clicks on an answer it should be shown whether it is correct or incorrect ✔️<br>
📌 Responsive design ✔️<br>
📌 There should be 10 questions in total ✔️
### 🚩 Maintenance <br>
This project will be maintenance free. 
