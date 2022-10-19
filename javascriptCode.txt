
users = {};


var apa = 2;
    function pasee() {
      apa = Number(apa) + 1;
      if(apa % 2 != 0) {
      pass.type = "text";
      anki.style.color = "dodgerblue";
    }
    else {
      pass.type = "password";
      anki.style.color = "lightgrey";
    }
    }
  
  
  
  
  var usersDataLS = localStorage.getItem("users_data_LS");
  users = JSON.parse(usersDataLS);
  var userId = localStorage.getItem("us_id_num");
    
    var nam = document.getElementById("name");
    var phoneNo = document.getElementById("phoneNo");
    var pass = document.getElementById("password");
   
    /*$.getJSON("/users_data.json", function(data){
            data = JSON.parse(users);
        });*/
   
   
   
   
    function submit() {
      
      userId = Number(userId) + Number(1);
      localStorage.setItem("us_id_num", userId);
      
      var n = nam.value;
      var pn = phoneNo.value;
      var p = pass.value;
      
      if(n === "" || pn === "" || p === "") {
        thnx.innerHTML = "Please Enter Valid input!";   
      }
      else {
       
      
      /*Object.defineProperty(users, n, {
        value: {
          "username": n,
          "phoneNumber": pn,
          "password": p
        },
        writable: true
      });*/
     users[userId] = {
        "userId": userId,
        "username": n,
        "phoneNumber": pn,
        "password": p
     }
     
     
     //try 
     
    /* $.getJSON("/users_data.json", function(data){
            data = JSON.parse(users);
        });*/
     
     
 
    localStorage.setItem("users_data_LS", JSON.stringify(users));
 
      thnx.innerHTML = "Thanks for Submitting!";
      setTimeout(function() {
        thnx.innerHTML = "";
        nam.value = "";
        phoneNo.value = "";
        pass.value = "";
      }, 2000);
}
    }
    
