# Random
var n = 1000001;
function flip() {
	  return Math.random() >= 0.5;	 
	}

	function randomNumber(n) {
		try {	  
	  if(n <= 0) throw n+" must be greater than 0";
	  if(n > 1000000) throw "n must be less than 1,000,000";
	  if(n === 1) return 0;
	  
	
	  function randomBinary(m){
		
	    binary = "";
	    for (var i=0; i<m; i++) {
	      binary+= flip()? "1" : "0";
	    }
	    return binary;
	  }

	  var maxPosibleValue = n-1;
	  var k = maxPosibleValue.toString(2).length;	  
	  var r;
	  do {	   
	    r = parseInt(randomBinary(k), 2);  
	   
	  } while (r > maxPosibleValue);
	
	  return r;
		}
		catch(err) {
			if (r==undefined){
				document.write("Error: "+err);
				r=0;
			}			
		}
	}
	
	document.write("Value of n= "+n +" Ouput: "+randomNumber(n));
