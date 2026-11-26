Type Narrowing in TypeSctipt 

ভূমিকা =>
TypeScript- এ Type Narrowing একটি গুরুত্বপূর্ণ বৈশিষ্ট,যার মাধ্যমে কোনো variable এর একাধিক সম্ভাব্য type থেকে নির্দিষ্ট type শনাক্ত করা যায়। অনেক সময় একটি variable একাধিক ধরনের value গ্রহন করতে পারে। যেমনঃ একটি Variable এর Type যদি String অথবা Number হয়, তাহলে সেটির ওপর কোন Methode ব্যবহার করা যাবে তা নির্ধারণ করা প্রয়োজন। আর Type Narrowing এই কাজটি সহজ করে। এটি কোডের Runtime Error কমাতে এবং Type Safety বজায় রাখতে সাহায্য করে। ফলে Developer আরও নির্ভরযোগ্য ও পরিষ্কার কোড লিখতে পারে। তাই Type Narrowing খুবই গুরুত্বপূর্ণ ! 

 বিস্তারিত আলোচনা -->
 TypeScript এ Type Narrowing করার জন্য বিভিন্ন ধরনের Opreto ব্যবহার করা হয়। এর মধ্যে typeof, instanceof এবং in Opretor উল্লেখযোগ্য।

 1) Typeof Operator: 
 
  Typeof Operator ব্যবহার করে কোনো variable এর primitive type শনাক্ত করা যায়। যেমনঃ string, Number, এবং Boolean ইত্যাদি। 
 এটি Conditional Statement এর সঙ্গে ব্যবহার করে নির্দিষ্ট Type অনুযায়ী আলাদা কাজ করা যায়। 

     exmple --> 

      function showValue (value:string|number){
        if ( typeof vale === "string){
            consol.log (value.toUpperCase());
        }else{
            console.log (value.toFixed(2));
        }
      }
      
     -> এখানে valu String হলে বড় হাতের অক্ষরে রুপান্তর হবে। অন্যদিকে Number হলে দশমিকের পর দুই ঘর দেখাবে।

  2) Intanceof Operator:
  
   Intanceof Operator ব্যবহার করে কোনো Object নির্দিষ্ট class এর intance কি না, তা পরিক্ষা করা হয়। এটি মূলত class এবং Object নিয়ে কাজ করার সময় Type Narrowing করতে সাহায্য করে।

      exmple --> 

      class Dog {
        brak (){
            consol.log ("Dog is braking");
        }
      }
      const animal = new Dog ();
      if (animal instaceof Dog){
        animal.brak();
      }

      এখানে animal Dog class এর intance  হওয়ায় brak() Methode ব্যবহার করা হয়েছে।

   3) in Opretor :
   
      in Opretor ব্যবহার করে কোনো Object এর মধ্যে নির্দিষ্ট Property আছে কি না,তা যাচাই করে। বিশেষ করে একাধিক Object Type এর মধ্যে পার্থক্য নির্ধারণ করতে এটি কার্যকর।    

    exmple -->

     type Admin = {role:string};
     type User = {email:string};

     function checkUser (person: Admin|User){
        if("role in opertor){
            consol.log (person.role);
        
        }else{
            consol.log (person.email);
        }
     }

     এখানে Role Property থাকলে Admin এবং না থাকলে User হিসেবে Type Narrowinig করা হয়।

     উপসংহার -->
     
      সবশেষে বলা যায় -> Type Narrowing TypeScript এর একটি কার্যকর বৈশিষ্ট। এটি সঠিক type শনাক্ত করে নিরাপদে কোড লিখতে সাহায্য করে। typeof,instanceof এবং in operator এর সঠিক ব্যবহার জানলে কোড আরও পরিষ্কার, নির্ভরযোগ্য এবং পরিচালনাযোগ্য হয়।
