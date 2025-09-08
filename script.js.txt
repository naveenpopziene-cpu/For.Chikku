// --- Quiz ---
const quizData = [
    { question: "What is 2 + 2?", options: [2,3,4,5], answer: 4 },
    { question: "Capital of India?", options: ["Delhi","Mumbai","Kolkata","Chennai"], answer: "Delhi" },
    { question: "5 x 3 = ?", options: [8,15,10,20], answer: 15 }
];

let currentQuestion = 0;
let score = 0;

const quizContainer = document.getElementById("quiz-container");
const nextBtn = document.getElementById("next-btn");
const quizScore = document.getElementById("quiz-score");

function loadQuestion() {
    quizContainer.innerHTML = "";
    const q = quizData[currentQuestion];
    const questionEl = document.createElement("p");
    questionEl.textContent = q.question;
    quizContainer.appendChild(questionEl);

    q.options.forEach(opt => {
        const btn = document.createElement("button");
        btn.textContent = opt;
        btn.onclick = () => checkAnswer(opt);
        quizContainer.appendChild(btn);
    });
}

function checkAnswer(selected) {
    if(selected == quizData[currentQuestion].answer) score++;
    currentQuestion++;
    if(currentQuestion < quizData.length) loadQuestion();
    else quizScore.textContent = "Quiz finished! Score: " + score + "/" + quizData.length;
}

nextBtn.onclick = loadQuestion;
loadQuestion();

// --- Simple Math Game ---
function randomNum() { return Math.floor(Math.random()*10) + 1; }
let a = randomNum(), b = randomNum();
const gameQuestion = document.getElementById("game-question");
const gameAnswer = document.getElementById("game-answer");
const gameFeedback = document.getElementById("game-feedback");
const submitAnswer = document.getElementById("submit-answer");

function setQuestion() {
    a = randomNum(); b = randomNum();
    gameQuestion.textContent = `${a} + ${b} = ?`;
    gameAnswer.value = "";
    gameFeedback.textContent = "";
}
submitAnswer.onclick = () => {
    if(Number(gameAnswer.value) === a + b) gameFeedback.textContent = "Correct! 🎉";
    else gameFeedback.textContent = `Wrong! Answer is ${a + b}`;
    setQuestion();
}

setQuestion();
// --- Quiz Data ---
const quizData = [

    // --- Geography Questions ---
    { question: "Capital of France?", options: ["Paris","London","Rome","Berlin"], answer: "Paris" },
    { question: "Which continent is Egypt in?", options: ["Africa","Asia","Europe","Australia"], answer: "Africa" },
    { question: "Longest river in the world?", options: ["Nile","Amazon","Yangtze","Mississippi"], answer: "Nile" },
    { question: "Highest mountain in the world?", options: ["Everest","K2","Kangchenjunga","Lhotse"], answer: "Everest" },
    { question: "Which country has the largest population?", options: ["China","India","USA","Russia"], answer: "China" },
    { question: "Capital of Japan?", options: ["Tokyo","Kyoto","Osaka","Hiroshima"], answer: "Tokyo" },
    { question: "Which ocean is the largest?", options: ["Pacific","Atlantic","Indian","Arctic"], answer: "Pacific" },
    { question: "The Great Barrier Reef is in?", options: ["Australia","USA","India","South Africa"], answer: "Australia" },
    { question: "Sahara Desert is located in?", options: ["Africa","Asia","North America","Europe"], answer: "Africa" },
    { question: "Which country is famous for the fjords?", options: ["Norway","Canada","Chile","Finland"], answer: "Norway" },

    // --- Politics Questions ---
    { question: "Who is the current President of the USA?", options: ["Joe Biden","Donald Trump","Barack Obama","George Bush"], answer: "Joe Biden" },
    { question: "UN stands for?", options: ["United Nations","Universal Network","Union Nations","United Neighbors"], answer: "United Nations" },
    { question: "Capital of India?", options: ["New Delhi","Mumbai","Kolkata","Chennai"], answer: "New Delhi" },
    { question: "Which party is ruling India currently?", options: ["BJP","Congress","AAP","TMC"], answer: "BJP" },
    { question: "Who was the first Prime Minister of India?", options: ["Jawaharlal Nehru","Mahatma Gandhi","Indira Gandhi","Rajendra Prasad"], answer: "Jawaharlal Nehru" },
    { question: "The US Congress consists of?", options: ["Senate & House of Representatives","Parliament","Senate only","House only"], answer: "Senate & House of Representatives" },
    { question: "Which country has a monarchy?", options: ["United Kingdom","USA","India","Brazil"], answer: "United Kingdom" },
    { question: "The Indian President is elected for?", options: ["5 years","4 years","6 years","3 years"], answer: "5 years" },
    { question: "Which organization is for global peace?", options: ["UN","NATO","WHO","IMF"], answer: "UN" },
    { question: "Voting age in India?", options: ["18","16","21","25"], answer: "18" },

    // --- History Questions ---
    { question: "Who discovered America?", options: ["Christopher Columbus","Vasco da Gama","Ferdinand Magellan","Marco Polo"], answer: "Christopher Columbus" },
    { question: "Who was the first emperor of Rome?", options: ["Augustus","Julius Caesar","Nero","Caligula"], answer: "Augustus" },
    { question: "Independence Day of India?", options: ["15 August 1947","26 January 1950","2 October 1947","30 January 1948"], answer: "15 August 1947" },
    { question: "Who wrote the 'Iliad'?", options: ["Homer","Plato","Aristotle","Socrates"], answer: "Homer" },
    { question: "Industrial Revolution started in?", options: ["England","France","USA","Germany"], answer: "England" },
    { question: "The Berlin Wall fell in?", options: ["1989","1991","1985","1995"], answer: "1989" },
    { question: "Who was known as 'Father of Nation' in India?", options: ["Mahatma Gandhi","Subhash Chandra Bose","Jawaharlal Nehru","Bhagat Singh"], answer: "Mahatma Gandhi" },
    { question: "French Revolution started in?", options: ["1789","1776","1804","1799"], answer: "1789" },
    { question: "Who discovered penicillin?", options: ["Alexander Fleming","Marie Curie","Louis Pasteur","Thomas Edison"], answer: "Alexander Fleming" },
    { question: "Who was the first President of the USA?", options: ["George Washington","Abraham Lincoln","John Adams","Thomas Jefferson"], answer: "George Washington" },

    // --- Grammar Questions ---
    { question: "Choose the correct form: He ___ to school daily.", options: ["goes","go","going","gone"], answer: "goes" },
    { question: "Fill in the blank: I have ___ apple.", options: ["an","a","the","none"], answer: "an" },
    { question: "Select the correct past tense: She ___ a book yesterday.", options: ["read","reads","reading","red"], answer: "read" },
    { question: "Choose the correct sentence:", options: ["I am going home","I going home","I go home is","I go home are"], answer: "I am going home" },
    { question: "Identify the adjective: She is very tall.", options: ["tall","She","very","is"], answer: "tall" },
    { question: "Choose the correct article: ___ Eiffel Tower is in Paris.", options: ["The","A","An","No article"], answer: "The" },
    { question: "Select the correct plural form: child", options: ["children","childs","childes","child"], answer: "children" },
    { question: "Pick the correct preposition: He is good ___ math.", options: ["at","in","on","for"], answer: "at" },
    { question: "Choose the correct pronoun: This is ___ book.", options: ["my","me","mine","I"], answer: "my" },
    { question: "Fill in the blank: I ___ been to France.", options: ["have","has","had","having"], answer: "have" }
];

