# webDev
var demo=[
    {
      "name": "鑺傜偣1",
      "son": [
        {
          "id": 11,
          "name": "鑺傜偣11",
          "parentName": "鑺傜偣1",
          "son": [
            {
              "id": 111,
              "name": "鑺傜偣111",
              "parentName": "鑺傜偣11"
            },
            {
              "id": 112,
              "name": "鑺傜偣112",
              "parentName": "鑺傜偣11"
            }
          ]
        },
        {
          "id": 12,
          "name": "鑺傜偣12",
          "parentName": "鑺傜偣1"
        }
      ]
    },
    {
      "name": "鑺傜偣2",
      "son": [
        {
          "id": 21,
          "name": "鑺傜偣21",
          "parentName": "鑺傜偣2"
        }
      ]
    },
    {
      "name": "鑺傜偣3",
      "son": [
        {
          "id": 31,
          "name": "鑺傜偣31",
          "parentName": "鑺傜偣3"
        }
      ]
    },
    {
      "name": "鑺傜偣4",
      "son": [
        {
          "id": 41,
          "name": "鑺傜偣41",
          "parentName": "鑺傜偣4"
        }
      ]
    },
    {
      "name": "鑺傜偣5",
      "son": [
        {
          "id": 51,
          "name": "鑺傜偣51",
          "parentName": "鑺傜偣5"
        },
        {
          "id": 52,
          "name": "鑺傜偣52",
          "parentName": "鑺傜偣5"
        },
        {
          "id": 53,
          "name": "鑺傜偣53",
          "parentName": "鑺傜偣5"
        },
        {
          "id": 54,
          "name": "鑺傜偣54",
          "parentName": "鑺傜偣5"
        }
      ]
    }
  ]
  


 
 function getArr (arr) {
    var  a=new Array();
      for(var i=0;i<arr.length;i++){
         var json=new Object();
         var blog=arr[i].hasOwnProperty('son');
         if(blog){
            json.sets= getArr(arr[i].son)
         }    
         json.id=arr[i].name 
         a.push(json)
      }
      return a
  }
  
  function getArr (arr) {
    var u="<ul>"
      for(var i=0;i<arr.length;i++){
       
        
         u += '<li>'+"<a>"+arr[i].name+"</a>";
         u +="</li>"
         var blog=arr[i].hasOwnProperty('son');
         if(blog){
            u +=getArr(arr[i].son) ;
         }
         
      }
      u+="</ul>"
      return u
  }
