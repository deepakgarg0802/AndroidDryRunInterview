# AndroidDryRunInterview
 This repository contains the answer of Interview practice part under Udacity Android Nanodegree Program


## Question 1 - What’s your favorite tool or library for Android? Why is it so useful?
> Android has lot of good libraries, like retrofit, volley, butterknife and many more. My favourite is Retrofit library. Retrofit is a REST Client for Android and Java by Square. It makes it relatively easy to retrieve and upload JSON (or other structured data) via a REST based webservice.

## Question 2 - You want to open a map app from an app that you’re building. The address, city, state, and ZIP code are provided by the user. What steps are involved in sending that data to a map app?

> Creating intent:
* Create a Map URI, 
* USe intent service to open the URI in maps app (if installed) or browser.
* Start the intent.
Code:


```java
    String myuri = "http://maps.google.co.in/maps?q=" + Address;
    Intent intent = new Intent(Intent.ACTION_VIEW, Uri.parse(myuri));
    context.startActivity(intent);
  ```

### Question 3 - Implement a method to perform basic string compression using the counts of repeated characters. For example, the string aabcccccaaa would become a2b1c5a3. If the "compressed" string would not become smaller than the original string, your method should return the original string. The method signature is: “public static String compress(String input)” You must write all code in proper Java, and please include import statements for any libraries you use.
> Here is the solution:
```java
  String input = "AAABBBBCC";
  int count = 1;
  char last = input.charAt(0);
  StringBuilder output = new StringBuilder();
  for(int i = 1; i < input.length(); i++){
      if(input.charAt(i) == last){
      count++;
      }
      else{
          if(count > 1){
              output.append(""+count+last);
          }else{
              output.append(last);
          }
      count = 1;
      last = input.charAt(i);
      }
  }
  if(count > 1){
      output.append(""+count+last);
  }else{
      output.append(last);
  }
  System.out.println(output.toString());
```

### Question 4 - List and explain the differences between four different options you have for saving data while making an Android app. Pick one, and explain (without code) how you would implement it.
> Options to store data: 

* Shared Preferences - Store private primitive data in key-value pairs.
* Internal Storage - Store private data on the device memory.
* External Storage - Store public data on the shared external storage.
* SQLite Databases - Store structured data in a private database.
* Network Connection - Store data on the web with your own network server.

Shared preferences are useful for storing the primitive data types like `integer`, `boolean` and also `String`. 
In onCreate() method, we can create the shared preference, and add it to the Shared Preference database. We can add values with methods such as putInt(), putBoolean() and putString(). 
If at any point, we have to change the preference, we just open the Preference Editor using SharedPreferences.Editor, and just start editing it. Also, we can get the instance at any point of time.

For complex data types, we should use remaining methods.
  

### Question 5 - What are your thoughts about Fragments? Do you like or hate them? Why?
> Fragments are a way of implementing "sub-forms" or "sub-pages" within a single Activity. They can of course be reused and so provide the same UI component to more than one Activity. They can also be displayed in their own right and provide the framework needed to implement dialog boxes that take over the UI for periods of time. The advantages of this are that you can compartmentalize the logic and almost as a spin off you can arrange for the screen real estate to be used in different ways according to how much is available.

### Q6: If you were to start your Android position today, what would be your goals a year from now? 
> I would like to learn the internals of android libraries and design patterns, and build very robust and cool apps. By next year, I want to see myself leading a team or android developers, building something cool.
I also have plans to contibute more towards open source software and help the Android community make great products.

