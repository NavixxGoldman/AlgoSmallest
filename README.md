# AlgoSmallest
This an algorithm to know the smallest multiple of a range of number

```javascript
function smallestCommons(arr) {
  var checkArray=[];
  //Sort array
  checkArray=arr.sort((a,b)=> a-b);
  //Create all the range
  var end=checkArray[1];
  var start=checkArray[0];
  var newArray=[];
  for(var i=start;i<=end;i++){
  newArray.push(i);
  }
  //Sort array from greatest to smallest
  newArray=newArray.sort((a,b)=> a+b);
  //Variable needed
    var quot = 0;
  var loop = 1;
  var n;
  //Check for divisibility

  do{
     quot = newArray[0] * loop * newArray[1];
     for (n = 2; n < newArray.length; n++) {
      if (quot % newArray[n] !== 0) {
        break;
      }
    }

    loop++;
  } while(n!==newArray.length);
  return quot;
  
}


console.log(smallestCommons([1,5]));
console.log(smallestCommons([2, 10]));
```
