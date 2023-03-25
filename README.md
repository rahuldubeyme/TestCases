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


---------------------------time zone ----------------------------

//utc
const timeZone = Intl.DateTimeFormat().resolvedOptions().timeZone;
console.log('timeZone==>',timeZone); //systemTimeZone
var gfg =  new Date().toISOString()
const date = new Date(gfg);
console.log('local utc==>',date); //local utc date
console.log('local date==>>',date.toLocaleString()); //local date

//Pacific/Midway //
const str = new Date(date).toLocaleString('en-US', { timeZone: 'Pacific/Midway' }); //static timezone with utc time
let dt = new Date(str);

console.log('Pacific/Midway===>>',str); 

console.log('time zone ==>>',dt.toISOString()); 


--------------------------------------------------------------------------

db.collection.aggregate([
  {
    $project: {
      timestamp: {
        $toDate: "$timestamp"
      }
    }
  },
  {
    "$project": {
      timestamp: 1,
      timestamps: {
        $gte: [
          {
            $dayOfMonth: "$timestamp"
          },
          15
        ]
      }
    }
  },
  {
    $match: {
      timestamps: true
    }
  }
])

