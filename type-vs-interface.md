Type vs interface in typeScript

ভূমিকা =>

TypeScript- এ type এবং interface দুটি গুরুত্বপূর্ণ বৈশিষ্ট্য। এগুলো ব্যবহার করে ডেটার ধরন ও গঠন নির্ধারণ করা যায়। ফলে কোড আরও পরিষ্কার, নিরাপদ এবং সহজে পরিচালনাযোগ্য হয়। তবে এদের মধ্যে কিছু গুরুত্বপূর্ণ পার্থক্য রয়েছে। তা নিচে বিস্তারিত আলোচনা করা হয়েছে। 
 
বিস্তারিত আলোচনা => 
 
Type Alias :

 type ব্যবহার করে বিভিন্ন ধরনের ডেটার জন্য নতুন নাম তৈরি করা যায়। যেমনঃ Object,primitive, Union,   Intersection & tuple type তৈরিতে ব্যবহার করা যায়। 

 Interface : interface মূলত Object এর Structure নির্ধারণ করতে ব্যবহৃত হয় । interface এ extends,Declaration Margine সুবিধা রয়েছে।
  
  Type এবং Interface এর পার্থক্য ঃ

  1) Type দিয়ে Primitive,Union,intersection তৈরি করা যায়, কিন্তু interface সরাসরি primitive বা Union alias তৈরি করতে পারে না।
  2) interface-এ extends ব্যবহার করে অন্য interface সম্প্রসারণ করা যায়। অন্যদিকে,type- এ & ব্যবহার করে intersection তৈরি করা হয়।
  3) interface-এর Declearation Merging সুবিধা রয়েছে ,কিন্তু type এ একই নামে পুনরায় Declaration করা যায় না ।
  4) type বিভিন্ন ধরনের জটিল type তৈরি করতে পারে, কিন্তু interface প্রধানত Object Structure নির্ধারণে ব্যবহৃত হয়। 
  5) উভয়কেই class-এর সঙ্গে implement ব্যবহার করে প্রয়োগ করা যায়।

Type Alias :

উদহারনঃ 

 Object type ->

 type Student = {
    namr:string;
    age: number;
  };
   const student : Student ={
    name: "AlIF",
    age: 25
   };

    primitive type ->
    type Age = number;
    let stuAge=  Age = 25;

    Union type ->
     type ID = string | number;
     let stuId: ID = 101;
     stuId = "ST101";

     Intersection type -> 
     type person = {
        name: string;
     };
       type Employee = {
        salary: number;
       };
      type Staff = Person & Employee;
       const staff: Staff = {
        name: "ALIF";
        salary: 50000;
         }; 
    
    Tuple type -> 
    type UserInfo = [string,number,boolean];
    const user : UserInfo = ["ALIF",25,true];
                    
Interface :

    উদহারনঃ 
    Extends -->
     interface person {
        name:string;
     }
     interface Student extands person  {
       studentId: number;
     }
      const student:Student = {
        name:"ALIF",
        studentId:101
      };

     Declearation Merging -->
      interface person {
        name:string;
     }
     interface  person  {
       studentId: number;
     }
      const student:person = {
        name:"ALIF",
        studentId:101
      };

 উপসংহার ঃ
 
 সবশেষে বলা যায়, উভয়ই typeScript এর গুরুত্বপূর্ণ অংশ। Object এর Structure এবং Extends এর জন্য interface ভালো পছন্দ । অন্যদিকে Union , intersection এবং জটিল type তৈরির জন্য type বেশি উপযোগী। 
  কাজের প্রয়োজন অনুযায়ী সঠিকটি নির্বাচন করাই একজন ভালো ডেভেলপারের দক্ষতা ।
