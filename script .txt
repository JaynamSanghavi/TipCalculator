function calculateTip(){
    var billAmount = document.getElementById("billAmount").value;
    var serviceQuality = document.getElementById("serviceQuality").value;
    var numPeople = document.getElementById("totalPeople").value;
    
    //quick validation
    
    if(billAmount === "" || serviceQuality == "0"){
        window.alert("Something is Missing!!");  
        return;
    }
    
    //check the number of people and manage properly
    if(numPeople === "" || numPeople <=1 ){
        numPeople = 1;
        document.getElementById("each").style.display = "none";
    }
    else{
        document.getElementById("each").style.display = "block";
    }
    
    //do some math
    var total = (billAmount * serviceQuality)/numPeople;
    total = total.toFixed(2);
    
    //display the total
    document.getElementById("totalTip").style.display = "block";
    document.getElementById("tip").innerHTML = total;
}

//hide the tip amount
document.getElementById("totalTip").style.display = "none";
document.getElementById("each").style.display = "none";

document.getElementById("calculateButton").onclick = function (){
 calculateTip();  
};