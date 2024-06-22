<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Student Report</title>
    <link rel="stylesheet" href="Student Report.css">
    <script>
        var totalMarks;
        var per;
        function total() {
            var phy = document.getElementById("physics").value;
            var chem = document.getElementById("chemistry").value;
            var bio = document.getElementById("biology").value;
            totalMarks = parseInt(phy) + parseInt(chem) + parseInt(bio);
            document.getElementById("Total").innerHTML = "Total Marks: " + totalMarks;
        }

        function percentage() {
            per = parseFloat(totalMarks)/3;
            document.getElementById("percentage").innerHTML = "Percentage: " + per + "%";
        }

        function grading() {
            if(per>=75) {
                document.getElementById("grade").innerHTML = "Grade: A";
            }
            else if(per<75 && per>=50)
            {
                document.getElementById("grade").innerHTML = "Grade: B";
            }
            else if(per<50 && per>=35)
            {
                document.getElementById("grade").innerHTML = "Grade: C";
            }
            else {
                document.getElementById("grade").innerHTML = "Grade: Fail";
            }
        }

        function calculateGrade() {
            total();
            percentage();
            grading();
        }
    </script>
</head>
<body>
<style>
@media (max-width: 800px) {

.header_title {

font-size: 1rem;

}
  body{
    background-color: green;
  }
  }

.header_sun {

width: 1.3rem;

height: 1.3rem;

}
@media (min-width: 1200px) {

.header_title {

font-size: 1rem;

}
  body{
    background-color: red;
  }
  }
.header_sun {

width: 1.3rem;

height: 1.3rem;

}@media (max-width: 600px) {

.header_title {

font-size: 1rem;

}

.header_sun {

width: 1.3rem;

height: 1.3rem;

}
h1{

text-align: center;

}

form{

text-align: center;

background-color: #FFB6C1;

}

select {

width: 70px;

}
h1 {
    color: #006400; /* Dark green color for h1 */
}
</style>
    <div class="heading">
        <h1>Student Report</h1>
    </div>
    <div class="form">
        <form>
            <table>
                <tr>
                    <td><label for="Physics">Enter marks for Physics : </label></td>
                    <td><input type="number" id="physics" required></td>
                </tr>
                <tr>
                    <td></td>
                    <td></td>
                </tr>
                <tr>
                    <td><label for="Chemistry">Enter marks for Chemistry : </label></td>
                    <td><input type="number" id="chemistry" required></td>
                </tr>
                <tr>
                    <td></td>
                    <td></td>
                </tr>
                <tr>
                    <td><label for="Biology">Enter marks for Biology : </label></td>
                    <td><input type="number" id="biology" required></td>
                </tr>
            </table>
        </form>
        <br><br>
    </div>
    <div class="button">
        <button onclick="calculateGrade()">Calculate</button>
    </div>
    <div class="Result">
        <p id="Total"></p> 
        <p id="percentage"></p> 
        <h1 id="grade"></h1>
    </div>
</body>
</html>
