## set 과 map

### set

set객체는 중복되지 않는유일한 값들의 집합이다.
요소 순서에 의미가 없다.
인덱스로 요소에 접근할 수 없다.
set객체의 요소 개수를 확인할 때는 Set.prototype.size프로퍼티를 사용한다.
요소를 추가할 때는 Set.prototype.add메서드를 사용한다.
요소가 존재하는지 확인할 때는 Set.prototype.has 메서드를 사용한다.
요소를 삭제할때는 Set.prototype.delete 일괄 삭제는 Set.prototype.clear

### map

map객체는 키와 값의 쌍으로 이루어진 컬렉션이다.
이터러블이며 요소개수확인을 map.size를 사용한다.
요소를 추가할 때는 map.prototype.set메서드를 사용한다.
