# MUMET-website
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>SOYA HIGH SCHOOL</title>

<style>
body{
    margin:0;
    font-family: Arial, Helvetica, sans-serif;
    background: linear-gradient(to right, #ff9966, #3399ff);
}

/* HEADER */
header{
    background-color:#2c003e;
    color:white;
    text-align:center;
    padding:45px 20px;
}

header h1{
    margin:0;
    font-size:34px;
}

/* MOTTO */
.motto{
    margin-top:15px;
    background-color:#ffd700;
    color:#2c003e;
    display:inline-block;
    padding:10px 18px;
    border-radius:8px;
    font-weight:bold;
    font-size:18px;
}

/* MAIN SECTIONS */
.section{
    background-color:#fff8dc;
    margin:20px;
    padding:25px;
    border-radius:15px;
    box-shadow:0 6px 15px rgba(0,0,0,0.4);
}

h2{
    color:#8b0000;
    border-bottom:2px solid #8b0000;
    padding-bottom:6px;
}

p, li{
    font-size:16px;
    color:#003300;
    line-height:1.7;
}

ul{
    padding-left:20px;
}

button{
    padding:10px 15px;
    margin:5px;
    border:none;
    border-radius:6px;
    background:#2c003e;
    color:white;
    cursor:pointer;
}

button:hover{
    background:#8b0000;
}

/* FOOTER */
footer{
    background-color:#000;
    color:white;
    text-align:center;
    padding:15px;
    font-size:14px;
}
</style>

</head>
<body>

<header>
    <h1>SOYA HIGH SCHOOL</h1>
    <img src="logo.png" alt="School Logo" width="120" height="120">
    <div class="motto">EDUCATION IS LIVING – LET US AIM HIGHER</div>
</header>

<div class="section">
    <h2>About the School</h2>
    <p>
        Soya High School is a secondary school located in Chemba District, Dodoma Region,
        Tanzania. The school was established in <strong>1992</strong> during the presidency
        of <strong>Ali Hassan Mwinyi</strong>, the then President of the United Republic of Tanzania.
    </p>
    <p>
        Since its establishment, the school has focused on providing high-quality education
        and producing disciplined, confident, and academically strong students.
    </p>
    <p>
        The school offers O-Level education for both boys and girls, while A-Level education
        (Form Five and Form Six) is offered to boys only. The school is supported by dedicated
        and experienced teachers who are committed to students’ success.
    </p>
</div>

<div class="section">
    <h2>Academic Combinations (Subjects)</h2>
    <ul>
        <li>
            <strong>PCM (Physics, Chemistry, Mathematics):</strong>
            Prepares students for engineering, technology, and science-related careers.
        </li>
        <li>
            <strong>PCB (Physics, Chemistry, Biology):</strong>
            Equips students with a strong foundation for medical and biological science fields.
        </li>
    </ul>
</div>

<div class="section">
    <h2>Challenges and Areas That Need Improvement</h2>
    <ul>
        <li><strong>Modern Science Laboratories:</strong> The school needs upgraded laboratories.</li>
        <li><strong>Library Facilities:</strong> A shortage of books limits research.</li>
        <li><strong>Computers for Learning:</strong> Limited ICT access.</li>
        <li><strong>Sports Facilities:</strong> Lack of basketball court and modern infrastructure.</li>
    </ul>
</div>

<div class="section">
    <h2>What We Are Proud Of</h2>
    <ul>
        <li><strong>Strong Moral Discipline</strong></li>
        <li><strong>Freedom of Worship</strong></li>
        <li><strong>Dedicated Teachers</strong></li>
        <li><strong>Regular Examinations</strong></li>
    </ul>
</div>

<div class="section">
    <h2>Current Student Statistics</h2>
    <ul>
        <li><strong>O-Level Students:</strong> 650+</li>
        <li><strong>Form Five Students:</strong> 125</li>
        <li><strong>Form Six Students:</strong> 98</li>
    </ul>
</div>

<!-- RESULTS SECTION -->
<div class="section">
    <h2>Examination Results</h2>

    <button onclick="showForm4()">Form Four Results</button>
    <button onclick="showForm6()">Form Six Results</button>

    <div id="resultsArea" style="margin-top:20px;"></div>
</div>

<div class="section">
    <h2>Contact Information</h2>
    <p><strong>Phone:</strong> +255 626 576 956</p>
    <p><strong>Email:</strong> detectiveg997@gmail.com</p>
    <p><strong>Location:</strong> Chemba District, Dodoma Region, Tanzania</p>
</div>

<footer>
    <p>&copy; 2026 SOYA HIGH SCHOOL | All Rights Reserved</p>
</footer>

<script>
const years = [2023, 2024, 2025];
const combinations = ["PCM", "PCB"];

function generateStudents(year, level, combination="") {
    let output = `<h3>${level} Results - ${year} ${combination}</h3>`;
    output += "<ol>";

    for (let i = 1; i <= 50; i++) {

        let firstNames = ["John","David","Michael","Grace","Anna","James","Peter","Neema","Asha","Daniel"];
        let lastNames = ["Mashauri","John","Peter","Mussa","Juma","Kassim","Mwakalinga","Lucas","Joseph","Mwita"];

        let randomFirst = firstNames[Math.floor(Math.random()*firstNames.length)];
        let randomLast = lastNames[Math.floor(Math.random()*lastNames.length)];

        let grade;
        
        if(level === "Form Four"){
            const divisions = ["Division I","Division II","Division III","Division IV"];
            grade = divisions[Math.floor(Math.random()*divisions.length)];
        } else {
            const points = ["3 Points","4 Points","5 Points","6 Points","7 Points"];
            grade = points[Math.floor(Math.random()*points.length)];
        }

        output += `<li>${randomFirst} ${randomLast} - ${grade}</li>`;
    }

    output += "</ol>";
    return output;
}

function showForm4(){
    let content = "";
    years.forEach(year => {
        content += generateStudents(year,"Form Four");
    });
    document.getElementById("resultsArea").innerHTML = content;
}

function showForm6(){
    let content = "";
    years.forEach(year => {
        combinations.forEach(combo => {
            content += generateStudents(year,"Form Six",combo);
        });
    });
    document.getElementById("resultsArea").innerHTML = content;
}
</script>

</body>
</html>
