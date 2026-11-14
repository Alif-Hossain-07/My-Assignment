Type Narrowing in TypeSctipt 

ভূমিকা =>
TypeScript- এ Type Narrowing একটি গুরুত্বপূর্ণ বৈশিষ্ট,যার মাধ্যমে কোনো variable এর একাধিক সম্ভাব্য type থেকে নির্দিষ্ট type শনাক্ত করা যায়। অনেক সময় একটি variable একাধিক ধরনের value গ্রহন করতে পারে। তখন সঠিক type না জেনে কোনো Method বা property ব্যবহার করলে সমস্যা হতে পারে। Type narrowing এই সমস্যা কমিয়ে কোডকে আরও নিরাপদ করে।
 
 বিস্তারিত আলোচনা -->
 TupeScript এ typeof, instanceof এবং in Opretor ব্যবহার করে Type Narrowing করা যায়। 

 1) Typeof Operator: এটি string, Number, এবং Boolean এর মতো primitive type শনাক্ত করতে ব্যবহৃত হয়।

     exmple --> 
      function showValue (value:string|number){
        if ( typeof vale === "string){
            consol.log (value.toUpperCase());
        }else{
            console.log (value.toFixed(2));
        }
      }
      
  2) Intanceof Operator:এটি কোনো Object নির্দিষ্ট class এর intance কি না, তা পরিক্ষা করে।

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
   3) in Opretor :এটি Object এর মধ্যে নির্দিষ্ট Property আছে কি না, তা যাচাই করে।    

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

     উপসংহার --> Type Narrowing TypeScript এর একটি কার্যকর বৈশিষ্ট। এটি সঠিক type শনাক্ত করে নিরাপদে কোড লিখতে সাহায্য করে। typeof,instanceof এবং in operator এর সঠিক ব্যবহার জানলে কোড আরও পরিষ্কার, নির্ভরযোগ্য এবং পরিচালনাযোগ্য হয়।
