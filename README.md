# Sherprefrenc-


Bilkul! Flutter ke andar **SharedPreferences** aur **Local Storage** ka use kaafi important hai agar aapko user data ko locally (device ke andar) store karna ho. Main aapko step-by-step **Hinglish** mein full detail course jaisa samjhaata hoon.

---

## 📦 **1. SharedPreferences kya hota hai?**

**SharedPreferences** ek simple key-value storage hai jisme aap primitive data types (like `int`, `double`, `String`, `bool`, `List<String>`) ko store kar sakte ho. Ye data app close hone ke baad bhi save rehta hai.

Use case:

* Login status store karna (user logged in hai ya nahi)
* Theme (dark/light) ka preference store karna
* First-time launch flag store karna

---

## ⚙️ **2. SharedPreferences ka setup Flutter mein**

### 📌 Step 1: Dependency add karo

Apne `pubspec.yaml` file mein:

```yaml
dependencies:
  shared_preferences: ^2.2.2 # latest version check kar lena
```

### 📌 Step 2: Import karo

```dart
import 'package:shared_preferences/shared_preferences.dart';
```

---

## ✅ **3. Basic Usage - CRUD operations**

### ✅ **Save Data**

```dart
void saveData() async {
  SharedPreferences prefs = await SharedPreferences.getInstance();
  await prefs.setString('username', 'JohnDoe');
  await prefs.setBool('isLoggedIn', true);
}
```

### 🔍 **Read Data**

```dart
void readData() async {
  SharedPreferences prefs = await SharedPreferences.getInstance();
  String? username = prefs.getString('username');
  bool? isLoggedIn = prefs.getBool('isLoggedIn');

  print('Username: $username');
  print('Logged In: $isLoggedIn');
}
```

### ❌ **Remove Data**

```dart
void removeData() async {
  SharedPreferences prefs = await SharedPreferences.getInstance();
  await prefs.remove('username');
}
```

### 🚫 **Clear All Data**

```dart
void clearAll() async {
  SharedPreferences prefs = await SharedPreferences.getInstance();
  await prefs.clear();
}
```

---

## 🧠 Tip: SharedPreferences is asynchronous

Hamesha `await` ka use karo ya `.then()` to avoid issues.

---

## 🏗️ **4. Local Storage - Advanced (file-based ya database)**

Agar aapko zyada complex data store karna hai, tab SharedPreferences se kaam nahi chalega. Tab aap use karte ho:

### 📌 a. **Hive** – Lightweight NoSQL DB

### 📌 b. **SQFLite** – SQLite database

Agar tum chaho to main next part mein **Hive ya SQFLite** ka full tutorial bhi Hinglish mein de sakta hoon.

---

## 🧪 Example App Idea:

**Login Page:**

* User login karta hai
* `isLoggedIn = true` save hota hai SharedPreferences me
* Next time app open karne pe directly dashboard dikhe

---

## 📹 Video ya Project Banwana Hai?

Agar aap chahein to main aapko:

* Ek chhota Flutter project bana ke de sakta hoon
* Ya step-by-step video-like lesson de sakta hoon

---

### 🔔 Agla step kya hoga?

1. Kya aapko **Hive/SQFLite** bhi sikhna hai?
2. Kya aapko ek **practice project** banana hai (e.g., login with remember me)?
3. Kya aapko is topic ka **PDF ya code template** chahiye?

Batayein, main agla part shuru karta hoon.

Bahut badhiya sawaal hai! ✅

Aapko agar **complex ya structured data** store karna hai (jaise user ka pura profile, cart items list, offline data caching, etc.) to **Hive** ya **SQFLite** dono bahut kaam ke tools hain.

Main aapko dono ka comparison deta hoon pehle, fir aap decide kar paayenge ki kaunsa sikhna hai – ya dono.

---

## 🔄 **Hive vs SQFLite** – Simple Comparison in Hinglish

| Feature           | Hive 🐝                               | SQFLite 🗃️                    |
| ----------------- | ------------------------------------- | ------------------------------ |
| Type              | NoSQL DB (key-value based)            | SQL-based (tables & rows)      |
| Performance       | Fast (in-memory)                      | Reliable (but slightly slower) |
| Data Type Support | Primitive + Custom Models             | Structured Tabular Data        |
| Learning Curve    | Easy (JSON-like)                      | Medium (SQL knowledge chahiye) |
| Use Case          | Quick data, small apps, offline cache | Complex apps, structured data  |
| Offline Support   | ✅ Fully offline                       | ✅ Fully offline                |

---

## 🎯 Use Case Based Advice

| App Type                     | Recommended Storage |
| ---------------------------- | ------------------- |
| Simple ToDo App              | **Hive**            |
| Chat Messages                | **Hive**            |
| E-commerce Cart              | **Hive**            |
| Student Records App          | **SQFLite**         |
| Expense Tracker with Filters | **SQFLite**         |
| Relational Data              | **SQFLite**         |

---

## 💡 Aap kya seekhna chahte hain?

1. Agar aap beginner hain aur **simple aur fast local DB** sikhna chahte hain – 🐝 **Hive sikhna best rahega**
2. Agar aapko **SQL aata hai** ya aapko tabular data ka experience chahiye – to 🗃️ **SQFLite sikhna better hoga**
3. Agar aap serious Flutter dev banna chahte hain to – **dono aane chahiye**

---

### 🔥 To agla step ye ho sakta hai:

🔘 **Option A**: Hive sikhayein first? (fast, simple, beginner-friendly)
🔘 **Option B**: SQFLite sikhayein first? (thoda structured & advanced)
🔘 **Option C**: Ek chhoti app banayein jisme dono ka use ho?

Aap kaunsa option chahenge? Bataiye, main wahi path shuru karta hoon Hinglish mein step-by-step.
