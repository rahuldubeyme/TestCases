# TestCases


in js

try{
  //let a =  [65, 44, 12, 4] //   
//let a = "4"
// let a ;
 // let a = null ;
let a =  ['65', '44', '12', '4']
console.log("check==>>", typeof a, "====", Array.isArray(a))

let b =  Array.isArray(a) == false && typeof a != undefined ? [parseInt(a)] :  a.map(function(x){ return parseInt(x) } )// c = a //? a.map(x => return parseInt(x) : [] )     // || (typeof a == 'array' ? a : [] ) // || typeof a != null || typeof a != undefined ? [parseInt(a)] : 0;
console.log("==>>",b )
}catch{
  
  console.log("==>>err throw" )
  
}
