<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simple Interest Calculator</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
  <div class="container">
    <div class="main">
    <h2>Simple Interest Calculator</h2>
    <label for="principal">Principal Amount:</label>
    <input type="number" id="principal" placeholder="Enter principal" required>
    
    <label for="rate">Rate of Interest (%):</label>
    <input type="number" id="rate" placeholder="Enter rate" required>
    
    <label for="time">Time (years):</label>
    <input type="number" id="time" placeholder="Enter time" required>
    
    <button onclick="calculateInterest()">Calculate</button>
    <div id="result"></div>
  </div>
</div>

   <script src="script.js"> </script>
   
</body>
</html>
*{
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

.container{
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  background: #f0f0f0;
}
.main{
  background: white;
  max-width: 340px;
  box-shadow: 2px 2px 12px rgba(0, 0, 0, 0.1);
  padding: 30px 24px;
  border: 1px solid #ccc;
  border-radius: 10px;
  font-family: Arial, sans-serif;
  z-index:10;
}
h2{
  margin-bottom: 20px;
  font-size: 23px;
}
label{
  font-size: 18px;
}
input{
  padding: 10px;
  margin: 10px 0;
  border: 1px solid #ccc;
  border-radius: 5px;
  transition: border-color 0.2s;
}
input ,button {
  width: 100%;
  margin: 10px 0;
  padding: 10px;
  font-size: 16px;
}
input:focus{
  border-color: #007bff;
  outline :none;
}
button {
  background-color: #007bff;
  color: white;
  border-radius: 5px;
  border: none;
  cursor: pointer;
}
button:hover {
  background-color: #0056b3;
}
#result {
  margin-top: 20px;
  margin-left: 5px;
  line-height: 30px;
  font-size: 18px;
  color: green;
  font-size: 21px;
}

.yt{
  position: absolute;
  margin-top: -80px;
  margin-left:33px;
  width: 300px;
  text-align: center;
  padding: 8px;

  border-radius: 5px;
    color:white;
    background: rgb(0, 132, 255);
    cursor:pointer ;
    border:1px solid rgb(250,230,250);

}
.yt a{
  font-size: 20px;
  color: white;
  text-decoration: none;
  font-weight: bold;
  display:block ;
}


function calculateInterest() {
  const principal = parseFloat(document.getElementById('principal').value);
  const rate = parseFloat(document.getElementById('rate').value);
  const time = parseFloat(document.getElementById('time').value);
  
  if (isNaN(principal) || isNaN(rate) || isNaN(time)) {
      alert('Please enter values...');
      return;
  }
  
  const interest = (principal * rate * time) / 100;
  const totalAmount = principal + interest;
  
  document.getElementById('result').innerHTML = `Simple Interest: $${interest.toFixed(2)} <br> Total Amount: $${totalAmount.toFixed(2)}`;
  
  document.getElementById('principal').value = "";
  document.getElementById('rate').value = "";
  document.getElementById('time').value = ""
  
}
