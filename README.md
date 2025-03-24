/*
class Person {
  String _name = "";
  int _age = 0;

  Person(this._name, this._age);

  String get name => _name;
  int get age => _age;

  void addoneyear() {
    _age++;
  }
}

void main() {
  var p = Person('정세팔', 40);
  print([p.name, p.age]);
  print('');

  // p.name = 'ㄴㅇㄴ' 일케 하면 오류임 _인 접근지정자 땜에. 아래도 마찬가지
  // p.age = 100;

  print(' 나이 한살 추가');
  p.addoneyear();
  print([p.name, p.age]);
  print('');

  var p2 = Person('김지현', 40);
  print([p2.name, p2.age]);
  print('');
  print(p._name); // 접근이 되는 이유?
}
*/

/*

class Rectangle {
  num left, top, width, height;

  Rectangle(this.left, this.top, this.width, this.height);

  num get rigth => left + width;
  set rigth(num value) => left = value - width;
  num get bottom => top + height;
  set bottom(num value) => top = value - height;
}

class Rectangle2 {
  num left, top, right, bottom;

  Rectangle2(this.left, this.top, this.right, this.bottom);

  num get width => right - left;
  set width(num value) => right = value + left;
  num get height => bottom - top;
  set height(num value) => bottom = value + top;
}

void main() {
  var r = Rectangle(5, 10, 25, 30);
  print(
    '[r.left, r.top, r.width, r.height] = ${[r.left, r.top, r.width, r.height]}',
  );
  print('[width,height] = ${[r.height, r.bottom]}');

  var r2 = Rectangle2(5, 10, 30, 40);
  print(
    '[r2.left, r2.top, r2.width, r2.height] = ${[r.left, r.top, r.width, r.height]}',
  );
  print('[right,bottom] = ${[r2.right, r2.bottom]}');
}

*/

/*

class Hero {
  String name = '영웅';

  void run() {
    print('뛰어!');
  }
}

class SuperHero extends Hero {
  @override
  void run() {
    print('--------------');
    //super.run();
    this.fly();
    print('--------------');
  }

  void fly() {
    print('날아가!');
  }
}

void main() {
  var h1 = SuperHero();
  h1.run();
  // hero.fly();
  print(h1.name);

  var h2 = Hero();
  h2.run();
  print('');

  List<Hero> heroes = [h1, h2];
  heroes.forEach((h) => h.run());
}

*/

/*

abstract class Monster {
  void attack();
}

class Goblin implements Monster {
  @override
  void attack() {
    print('고블린 어택');
  }
}

class Bat implements Monster {
  @override
  void attack() {
    print('할퀴기 공격');
  }
}

void main() {
  Goblin g1 = Goblin();
  Bat b1 = Bat();

  // 아래의 코드에서 Goblin 또는 Bat이 드러나지 않기 때문에 단순한 코드 전개가 가능함
  List<Monster> monster = [g1, b1];
  monster.forEach((m) => m.attack());
  //
}

*/

/*

enum Status { login, logout } // enum = 열거타입이라고 함 특정한 값의 집합을 정의할 때 사용

void main() {
  var s1 = Status.login;
  var s2 = Status.logout;

  switch (s2) {
    case Status.login:
      print('로그인');
      break;
    case Status.logout:
      print('로그아웃');
      break;
  }
}

*/

/*

void main() {
  var lottonums = [5, 6, 11, 13, 17, 21];
  lottonums.forEach((num) {
    print(num);
  });
  lottonums.forEach((num) => print(num));
  lottonums.forEach(print);

  lottonums.remove(6);
  lottonums.add(9);
  print(lottonums);

  var map = {'한국': '서울', '일본': '도쿄'};
  print(map['한국']);
  map['중국'] = '북경';
  print(map);
}

*/

/*

Function getFunc(bool isChoice) {
  return isChoice == true ? () => '왼쪽' : () => '오른쪽';
}

void main() {
  var func = getFunc(true);
  var result = func();
  print(result);
}

*/

/*

void main() {
  var nums = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
  print(nums);
  print(nums.length);

  var evenums = nums.where((n) => n % 2 == 0).toList(); // 짝수
  print(evenums);

  var strnums = evenums.map((n) => '#$n').toList(); // 짝수
  print(strnums);

  var nums2 = [1, 2, 3, 3, 3, 4, 5, 6, 6];
  print(nums2);
  print(nums2.toSet().toList()); // 중복없애줌

  print(nums2.any((e) => e == 3)); // 뭐임이거?

  nums2
    ..add(-1)
    ..add(-2)
    ..add(-3);
  print(nums2);
}


*/

/*

void main(){
  bool promoactive = true;
  
  /* if (promoactive){
  print([1,2,3,4,5,6]);
} else {
  print([1,2,3,4,5]);
}
*/

print([1,2,3,4,5, if (promoactive) 6]);
  
  var listofints = [1,2,3];
  var listofstrings = [
    '#0',
    for
  ]
}
*/

void main() {
  String? name; // 변수 오른쪽에 ? 를 주면 null 뜸
  print(name?.length ?? 0);
}

/*
class Person {
  // 쿨래스 필드 이름 앞에 '_'를 붙이는 것은 다수의 언어에서 사용하는 스타일임
  // 예) Jave, C++, C#
  String _name = "";
  int _age = 0;
  String _desc;

  // 이런 방식의 생성자는 Dart언어의 고유한 형태임
  Person(this._name, this._age, this._desc);

  // 필드 값을 수정하는 것은 통제된 메서드에서만 하는 것이 좋음!
  void addOneYear() {
    _age++;
  }

  // 게터, 세터를 이용해 값을 전달하거나 수정하는 것을 통제할 수 있음!
  String get name => _name;
  int get age => _age;
  String get desc => '$_desc!!!';
  set desc(String v) => _desc = v;
}

void main() {
  var na = Person('홍준화', 24, '홍준화는 대의원이다');
  //na.name = '홍준화';
  //na.age = 24;
  print([na.name, na.age, na.desc]);
  na.addOneYear();
  na.desc = '아니다. 학회장이다';

  print([na.name, na.age, na.desc]);
}



class Rectangle {
  // 사각형을 왼쪽, 상단, 너비, 높이로 표현
  num left, top, width, height;

  Rectangle(this.left, this.top, this.width, this.height);

  // 오른쪽, 하단은 필드를 생성하지 않고 get/set으로 계산하여 표현
  num get right => left + width;
  set right(num value) => left = value - width;
  num get bottom => top + height;
  set bottom(num value) => top = value - height;
}

void main() {
  var r1 = Rectangle(5, 10, 20, 25);
  print([r1.left, r1.top, r1.width, r1.height]);
  print([r1.width, r1.height]);

  // left, top, width, height <-> left, top, right, bottom
}
*/
