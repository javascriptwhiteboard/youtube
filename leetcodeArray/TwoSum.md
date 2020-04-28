 JavaScript Whiteboard#1

Two Sum
Given an array of integers, return indices of the two numbers such that they add up to a specific target.
You may assume that each input would have exactly one solution, and you may not use the same element twice.


Example:

[5,6,2,4], target = 9 

The number inside index 0 = 5;
The number inside index 3 = 4;
5+4 = 9

return [0,3];


Brute Force Solution.


const sumTwo = (nums, target) => {
 
if(nums.length < 1 ) { return -1; }

for(let i=0;i<nums.length;i++){
   for(let j=i+1;j<nums.length;j++){
         if(nums[i] + nums[j] === target){

           return [i,j]
        }
     }
 }
return [-1,-1]
}



Time Complexity


O(N^2) //slow

----------------------------------------------------


2. Two pointers Solution.

//the array should be sorted, or we need to sort it if not sorted
//left: firstIndex
//right: LastIndex


Const sumTwo = ( nums, target ) =>{

  if(nums.length < 1 ) { return -1; }


  nums.sort( (a,b)=> a-b );// Nlogn
  Let left = 0;
  Let right = nums.length -1;
  
  while( left <= right ){

  if( nums[left] + nums[right] == target ){
        return [left,right]

      }

   if( nums[left] + nums[right] < target ){
        
            left++;
      }


   if( nums[left] + nums[right] > target ){
        
            right--;
      }

}

return [-1,-1]

}

   Time Complexity NLogN// better time.


----------------------------------------------------

3. Hash Map.

Map {

             4: 0,
3: 1,
7: 2,

}

[5,6,2,4], target = 9 

const sumTwo = (nums,target){
 if(nums.length < 1 ) { return -1; }
  
  let map = new Map();
  for( let i=0;i< nums.length;i++){
       Let num = nums[i];
  if(map.has(num){
        return [map.get(num), i]
   }
else{
    map.set(target - nums[i], i);
  }

 }

}


Time Complexity O(N) linear :)
Space Complexity O(N) // add extra space “map”






















Build a habit to solve a problem everyday


Thank You :)
Stay Safe
Stay Healthy
