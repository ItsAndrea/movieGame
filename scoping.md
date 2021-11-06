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
![homePage](https://user-images.githubusercontent.com/85640313/139603468-37425001-4a4f-4997-b2ef-5e6e5696297d.jpg)
#### Pagina de inicio 
Contiene un elemento h1 y un botón con la función play. 
![questions](https://user-images.githubusercontent.com/85640313/139603476-3c63dfcc-04e1-4e49-871a-1cfc076f3472.jpg)
#### Pagina del juego
Contiene un h1, los cuadrados respresentan las imagenes y 3 elementos de opciones de respuesta. Cuando un jugador escoja una respuesta debe mostrarse si es correcta u incorrecta.
![endPage](https://user-images.githubusercontent.com/85640313/139603480-5107f293-3ccc-4cc5-8fb1-a887ca65e70d.jpg)
#### Pagina del final
Contiene un h1 y un botón con la función re-start.
### 🚩 Implementation <br>
The file 'questions.json' contains the game content
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
Phase where the system was executed and a verification of the above requirements was performed.
### 🚩 Maintenance <br>
This project will be maintenance free. 
