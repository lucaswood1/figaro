# figaro
This was an idea that instead of visualizing data, what if we could hear it. It normalizes values to a single octave scale and then plays back.

## Requirements
* audiosynth.js (Github repo)[https://github.com/keithwhor/audiosynth]
* Google Voice API
* Example datasets were JSON files- in this case oil prices over a couple years. Data was normalized between the min and max of the given period. 

## Components
There are two features:
* The user would be able to query for single values over Google Voice.
* The user would be able to playback datasets as a musical group.

## Commands
Some example built in commands and the library of functions used.
```
case "OPEN QUERY RANDOM": 				
  a = generateRandomArray(); output2Console("Data set generated"); break;
case "OPEN QUERY EXAMPLE":				
  a = [1,2,3,2,1,4,5,6,7,8,9]; output2Console("Data set generated"); break;
case "OPEN QUERY SPOT PRICE NEW YORK":
case "OPEN QUERY SPOT PRICE CUSHING": 			
case "OPEN QUERY SPOT PRICE BRENT": 	
  openconnection(utilCommand(qryUpper)); break;
case "SUMMATION OF VALUES": 			
  output2Console("The sum of the values is "+math('sum',a)); break;
case "AVERAGE OF VALUES": 				
  output2Console("The average of the values is "+math('avg',a)); break;
case "COUNT OF VALUES": 				
  output2Console("The count of the values is "+math('count',a)); break;
case "STANDARD DEVIATION OF VALUES":	
  output2Console("The standard deviation of the values is "+standardDeviation(a)); break;
case "READ VALUES": 					
  read2Console(a); break;
case "READ NORMALIZED VALUES":			
  read2Console(normalize(a)); break;
case "PLAY VALUES": 					
  playscale(normalize(a)); break;
case "PLAY VALUES WITH AVERAGE":		
  playscale(normalize(a),math('avg',a)); break;
case "TEST": 							
  output2Console("Test Message"); break;
```
