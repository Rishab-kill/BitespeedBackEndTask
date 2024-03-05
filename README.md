url : https://bitespeedbackendtask-f959.onrender.com/identify

Code has been deployed on render.com with all database configuration.

json body format is:
{
    "email":"wxyz@gmail.com",
    "phonenumber":"123456789"
}

case 1 : there are no existing contacts against an incoming request
 ![Screenshot (6)](https://github.com/Rishab-kill/BitespeedBackendTask/assets/53389674/a4f76154-c393-4f51-981d-22af1fe86677)

 case 2 : when an incoming request has either of phoneNumber or email common to an existing contact

 ![Screenshot (7)](https://github.com/Rishab-kill/BitespeedBackendTask/assets/53389674/aedd03fb-23d4-4301-b0de-43f2cde848cb)

 here db entry with email id=abcd@gmail.com and phone no= 123456789 is already present and we are hitting url with below json data 
 {
    "email":"dcba@gmail.com",(this is new email id)
    "phonenumber":"123456789"
}

case 3: when primary contacts turn into secondary
 emailId_1 = abcd@gmail.com
 phoneNo_1 = 123456789
 linkprecedence_1 = primary 

 emailId_2 = wxyz@gmail.com
 phoneNo_1 = 987654321
 linkprecedence_2 = primary 

 json body :{
    "email":"wxyz@gmail.com",
    "phonenumber":"123456789"
}

response: ![Screenshot (8)](https://github.com/Rishab-kill/BitespeedBackendTask/assets/53389674/3b8ffde1-c2d9-4ed9-b503-7401cd98af06)
here older entry linkprecedence is primary and other one i.e wxyz@gmail.com linkprecedence has been updated to secondary.

Mostly corner cases has been handled and few of then has been shown above.



