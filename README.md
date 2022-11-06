# TinyDB--Android-Shared-Preferences-Turbo-Turkce


This class simplifies calls to SharedPreferences in a line of code. It can also do more like: saving a list of strings, integers and saving images. All in 1 line of code!

**Örnek kullanım:**
```Java
TinyDB tinydb = new TinyDB(context);

//Veri tabanına veri göndermek
tinydb.putInt("clickCount", 2);
tinydb.putFloat("xPoint", 3.6f);
tinydb.putLong("userCount", 39832L);

tinydb.putString("userName", "John");
tinydb.putBoolean("isUserMale", true); 

tinydb.putList("MyUsers", mUsersArray);
tinydb.putImagePNG("DropBox/WorkImages", "MeAtlunch.png", lunchBitmap);

//Veri tabanından veri çekmek
int dataint = tinyDB.getInt("clickCount");
String datastring = tinyDB.getString("userName");
//Bunlara ek olarak ilgili 'get' yöntemlerinin tümü aynı mantıktadır

```


Bu ne kadar kolay kullanabileceğinize ait birkaç örnekti. Bu sınıfın içinde daha nice metot var.:)



Ayrıca nesne (Object) kaydı için de bu metodu kullanabilirsiniz: 
```Java
tinydb.putObject(key, object);
tinydb.putListObject(key, objectsArray);
```
**Nesne kayıt örneği:**
```Java
Person person = new Person("john", 24);
tinydb.putObject("user1", person); //nesneyi kaydetme
tinydb.getObject("user1", Person.class); // nesneyi hafızadan geri çekme

ArrayList<Person> usersWhoWon = new ArrayList<Person>();
ArrayList<Object> winnersObjects = new ArrayList<Object>();

for(Person p : usersWhoWon){
    winnersObjects.add((Object)p); // casting to raw objects
}

tinydb.putListObject("allWinners", winnersObjects);
```
**Kotlin kullanım örneği:**
```Kotlin
// TinyDB nesnesi oluşturma
var tinyDB : TinyDB = TinyDB(applicationContext)


// veriyi kaydetme
tinyDB.putString("nameKey", "John")

var winnerPerson : Person = Person()
tinyDB.putObject("winnerKey", winnerPerson);

// veriyi çekme
var personName : String  = tinyDB.getString("nameKey")
var winnerPerson : Person = tinyDB.getObject("winnerKey", Person::class.java)
```


Nesne kaydetme metodunu kullanmadan önce: 

1. Gson'u projenize aktarmalısınız
Gradle:
```gradle
dependencies {
  implementation 'com.google.code.gson:gson:2.8.8'
}
```

2. TinyDB.java adlı sınıfınızdaki nesneleri kaydetme metotlarının yorumunu kaldırmalısınız, yorumlar şu satırlardadır : [**Line31**][5], [**Line330**][2], [**Line345**][3], [**Line486**][4]

[1]:  http://search.maven.org/#artifactdetails%7Ccom.google.code.gson%7Cgson%7C2.4%7Cjar
[2]:  https://github.com/kcochibili/TinyDB--Android-Shared-Preferences-Turbo/blob/master/TinyDB.java#L330 
[3]:  https://github.com/kcochibili/TinyDB--Android-Shared-Preferences-Turbo/blob/master/TinyDB.java#L345
[4]:  https://github.com/kcochibili/TinyDB--Android-Shared-Preferences-Turbo/blob/master/TinyDB.java#L486
[5]:  https://github.com/kcochibili/TinyDB--Android-Shared-Preferences-Turbo/blob/master/TinyDB.java#L31  
[6]:  https://bit.ly/learn_app_dev_videos



### Kurulum
TinyDB.java dosyasını projenize Java Sınıfı olarak eklemeniz yeterlidir.



### Uygulama geliştirmeyi öğrenmek mi istiyorsunuz?
[**Youtube kanalından**][6] kolayca öğrenebilirsiniz.
