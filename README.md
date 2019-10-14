# Assessment
1 : Callback :)
Ans)

function good(a)
{
    console.log('Im good and got 90 marks out of ' + a);
}
function boy(a,callback)
{
    callback(a);
}
boy(100,good);


2 : Promises :)
Ans)

function promise(){
    return new Promise(function(resolve, reject){
        setTimeout(() => {
            const error = true;
            if(error){
                console.log('Promise has been resolved');
                resolve();
            }
            else{
                console.log('Promise is rejected');
                reject();
            }
        },5000);
    })
}

promise().then((a)=> console.log('All Set!!')).catch((b)=> console.log('All gone!'));


3 : Async_await :)
Ans)

function square(x) {
    return new Promise(resolve => {
      setTimeout(() => {
        resolve(Math.pow(x, 2));
      }, 5000);
    });
  }
  
  async function Dog(x)
  {
    const value = await square(x);
    console.log(' value is '+ value);
  }
  
  Dog(3);
  
  
  4 : Async_Waterfall :)
  Ans)
  
  
var async =  require('async');

async.waterfall([

  function task1(callback) {
    console.log('start!');
    setTimeout(function(){
    	console.log("T1 Complete"); 
      callback(null, 'Value from task1',); 
     },5000);
     
  },
  function task2(t1Result, callback) {
    console.log(t1Result);
    setTimeout(function(){
    	console.log("T2 Complete");
    	callback(null,'Hello');
      },1000);
    
  },
  function task3 (task2Result, callback) {
    console.log(task2Result);
    setTimeout(function(){
    	console.log("T3 Complete");
        callback(null,'Async waterfall'); 
    },1000);
   
  }
],
function (err,result) {
  if (err) {
    throw new Error(err);
  } else {
    console.log(result);  
  }
});

5 : Async_Auto :)
Ans)
var async =  require('async')
async.auto({
    a : function(callback) {
        console.log('Hello');
        callback(null, 'data', 'converted to array');
    },
    b : function(callback) {
        console.log('Hi');
        callback(null, 'folder');
    },
},
 function(err, results) {
    console.log('err = ', err);
    console.log('results = ', results);
});


6 : Async_Series :)
Ans)
var async = require("async");

async.series([
  function(callback) {
    setTimeout(function() {
      console.log("Task 1");
      callback(null, 1);
    }, 300);
  },
  function(callback) {
    setTimeout(function() {
       console.log("Task 2");
      callback(null, 2);
    }, 200);
  },
  function(callback) {
    setTimeout(function() {
      console.log("Task 3");
      callback(null, 3);
    }, 100);
  }
], function(error, results) {
  console.log(results);
});


7 : Generators :)
Ans)
function *process(){
    yield 'Hi there!';
    yield 20;
}
let a = process()
console.log(a.next().value);
console.log(a.next());
console.log(a.next());
