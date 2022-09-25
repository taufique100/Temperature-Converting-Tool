# Temperature-Converting-Tool
Here we can change Temperature from Celsius to Fahrenheit and reverse.


### HTML Code ###
<body>
    
    <div class="container">
        <h3 id="header">Terperature Convert</h3>
        
        <select name="Parameters" id="select">
            <option value="1">- - Select Here - -</option>
            <option value="2" id="cel">Farenheit to celcius</option>
            <option value="3" id="fer">Celcius to Farenheit</option>
        </select>
        <input type="number" class="input" placeholder="Enter the temperature" id="value">
        <input type="text" class="input" placeholder="Result" id="Result">
       
        <button class="button" id="btn" onclick="farenheit()">Convert</button>
        <button class="button" id="reset" onclick="Reset()">Reset</button>
    </div>
</body>

#------------CSS CODE------#-------------------
<style>
    .container{
        border: 2px solid rgb(19, 18, 18);
        border-radius: 10%;
        margin:09px;
        padding-left: 30px;
        padding-right: 30px;
        padding-bottom: 30px;
        height: 200px;
        width: 200px;
        background-color: rgb(241, 203, 184);
    
    }
    #header{
        text-align: center;
    }
    #para{
        text-align: center;
        border-color: black;
        border-radius: 4px;
        
    }
    .input{
        margin-top: 10px;
        border: 2px solid black;
        border-radius: 6px;
    
    }
    .button{
        margin-top: 10px;
        border-radius: 6px;
        font-weight: bold;
       
    }
    .button:hover{
        background-color: rgb(249, 172, 78);
    }
</style>


#---------JavaScript Code----------------
function celcius(){
    var values = document.getElementById('value').value;
    let result1 = (parseFloat(values)-32) * 5/9;
    document.getElementById("Result").value =parseFloat(result1).toFixed(2);
}
function farenheit(){
    let value1 = document.getElementById('value').value;
    let result2 = parseFloat(value1) * (1.8) +32;
    document.getElementById("Result").value =parseFloat(result2).toFixed(2);
}
function Selectparameter(){
   let selectElement = document.queryCommandValue('#select');
   let output = selectElement.options[selectElement.selectIndex].text;
   console.log(output);
   
   if(output == '2') {
    celcius();
    console.log("clicus print");
   }
   else if(output == '3' )
   {
    farenheit();
    console.log("Farenheit print");
   }else{
    alert("Select parameter");
   }
  
}
function Reset(){
    document.getElementById('value').value ='';
    document.getElementById('Result').value ='';
    document.getElementById('select').value ='' ;
}
