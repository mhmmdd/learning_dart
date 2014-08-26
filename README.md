# Dart Rehberi
Kütüphane ekleme
```dart
import 'dart:math';

void main() {
  print(pow(2, 3));
}
```

True-False değerler
```dart
String a = '';
var b = 0;
print(a==b);
print(identical(a, b));
var b3 = (7 is num);
print(b3);
```


For in
```dart
var s = '';
var numbers = [0, 1, 2, 3, 4, 5, 6, 7];
for (var n in numbers) {
  s = '$s$n ';
}
```

## String
String birleştirme
```dart
var s1 = 'String' 'concatenation';
```

String içine değişken koyma
```dart
var name="Bob";
void main() {
  print("kemal ve $name");
}
```

String içinde toplama yapma
```dart
print("The answer is ${5 + 10}");
```

Multiline String
```dart
var multiline = """
<div id='greeting'>
"Hello World"
</div>
""";
var multiline2 = """
aeimaeimk'''eamiyieamusaeingğı '' eaeiu
""";
```

String fonksiyonları
```dart
var string = 'Dart';
print(string[0]); // D
```


## Function
Fonksiyon tanımlama
```dart
topla(a, b) {
  return a+b;
}

main() {
  print(topla(2, 300));
}
```

Kısayoldan fonksiyon tanımlama
```dart
main() => print("Hello, World!");
```

## Class
```dart
main() {
  var ba = new BankAccount("John Gates","075-0623456-72", 1000.0);
  print("Initial balance:\t\t ${ba.balance} \$");
  ba.deposit(250.0);
  print("Balance after deposit:\t\t ${ba.balance} \$");
}
class BankAccount {
  String owner, number;
  double balance;
  // constructor:
  BankAccount(this.owner, this.number, this.balance);
  // methods:
  deposit(double amount) => balance += amount;
}
```

**Method Cascades** (Ardarda method çağırma)
```dart
main() {
  var ba = new BankAccount("John Gates","075-0623456-72", 1000.0);
  ba
    ..balance = 5000.0
    ..withdraw(100.0)
    ..deposit(250.0);
}
class BankAccount {
  String owner, number;
  double balance;
  // constructor:
  BankAccount(this.owner, this.number, this.balance);
  // methods:
  deposit(double amount) => balance += amount;
}
```
[Örnek](chapter_2/banking_v2/banking_v2.dart)

## List
```dart
var empty = [];
var empty2 = new List();
List l = [];
l.add('kemal');
```

**.add**
```dart
var langs = new List();
langs.add('Kemal');
langs.add('Yasin');
print(langs);
var readOnlyList = const ["Java","Python","Ruby", "Dart"];
```

**.split** (String'i liste şeklinde ayırır)
```dart
var number = "075-0623456-72";
var parts = number.split('-');
print('$parts'); // produces [075, 0623456, 72]
```

**.join** (listeyi birleştirir String yapar)
```dart
var number = "075-0623456-72";
var parts = number.split('-');
print('$parts'); // produces [075, 0623456, 72]
var str = parts.join('-');
print('$str'); 
```

## Map
```dart
Map map = {};
Map map2 = new Map();
```
```dart
Map map = {
    'hello': 'merhaba'
};

map['world'] = 'dünya';

print(map); // {hello: merhaba, world: dünya}

print(map.containsKey('world')); // true
```

**.putIfAbsent** yoksa ekler
```dart
Map map = {
    'hello': 'merhaba',
    'world': 'dünya'
};
map.putIfAbsent('F#', () => 'www.fsharp.net');
print(map);
```

optional parameter(s) **[parameter]**
```dart
webLanguage([name]) => 'The best web language is: $name';
print( webLanguage('kemal'));
```

```dart
webLanguage([name = 'Dart']) => 'The best web language is: $name';
print( webLanguage());
```

```dart
// Strign dönen opsiyon parametre alan fonksiyon
String hi(String msg, [String from='en', String to='tr']) 
    => '$msg from $from to $to';
print(hi('hello'));
```

```dart
String hi3(String msg, {String from, String to}) =>
'$msg from $from to $to';

// Sırası değişik parametre gönderiliyor
print(hi3('hi', to:'you', from:'me')); 
```

## Exceptions
```dart
var input = "47B9"; // value read from input,
try{
    int inp = int.parse(input);
} on FormatException{
    print ('ERROR: Integer bir değer girmelisin!');
}
```

```dart
// diger hataları yakalar
var input = "47B9";
try{
  int inp = int.parse(input);
} on Exception catch(e) {
  print('Unknown exception: $e');
}
```
```dart
// Tüm hataları yakalar
var input = "47B9";
try{
  int inp = int.parse(input);
} catch(e) {
  print('Unknown exception: $e');
}
```
```dart
// Bir hata fırlatır
var area = PI * pow(radius, 2);
if (area > 200) {
  throw 'This area is too big for me.';
}
print(area);
```
Debug için
```dart
var lst = [1, 2, 3, 4, 5];

for (var i=0; i<=lst.length; i++) {
  print(lst[i] * lst[i]);
}
```




**Sayfa 61**

[Github Markdown](http://daringfireball.net/projects/markdown/basics)
