# Получение подView (частей View)
## 1. fun findViewById
```java
TextView nameView = view.findViewById(R.id.nameView);
nameView.setText("123");
```
```kotlin
val nameView = view.findViewById<TextView>(R.id.nameView)
nameView.text = "123"
```

- если View отсутствует: null
- если не совпадает тип View: ошибка
- узнает о существовании View, только на этапе исполнения
- не требует подключения доп. библиотек: вшит в Android SDK
- и в kotlin и в java

## 2. Synthetics
````kotlin
view.nameView.text = "123"
````
- только в kotlin
- сам генерирует новую переменную для каждого id(части View). Эта переменная является 
расширением класса View
- узнает о существовании View, только на этапе исполнения
- если View отсутствует: null
- тип View проверяется на этапе компиляции
- требует подключения плагина kotlin-android-extensions (библиотеки для gradle)

## 3. Binding
````kotlin
binding.nameView.text = "123"
````
````java
binding.nameView.setText("123"); 
````

- и в kotlin и в java
- генерирует по классу на каждую верстку и в этом классе содержится по переменной
для каждой вложенной View