# LomBok annotation 정리

### @NotNull<br>
필드의 값이 null이 될 수 없음을 명시

### @Getter<br>
필드의 get 메서드를 생성<br>

### @Getter(lazy=true) <br> 
getter 최초 호출 시 값을 한번 계산한 후 그 값을 캐시해서 사용가능 매번호출(X)

### @Setter<br>
필드의 set 메서드를 생성 <br>
AccessLevel 지정 가능

### @NoArgsConstructor<br>
기본 생성자 생성

### @RequiredArgsConstructor<br>
<초기화되지 않은> final 필드 , @NotNull인 필드에 대한 생성자 생성

### @AllArgsConstructor<br>
모든 필드를 가진 생성자

### ToString<br>
toString() 메서드 생성
exclude 속성을 사용하여 필요없는 속성 제거 @ToString(exclude ="value")

### @EqualsAndHashCode<br>
equeals() , hashCode() 메서드 생성
exclude 속성을 사용 가능

### @Data<br>
@Getter + @Setter + @RequiredArgsConstructor + @ToString + @EqualsAndHashCode

### @Value<br>
불변을 의미하는 어노테이션
@Value가 붙은 멤버 필드는 private 접근 제어자와 final이 붙은 상수가 된다

### @Log<br>
Logger 자동 생성 가능
자동으로 log 필드를 만들고 해당 class 명으로 로거 객체를 생성하여 할당해준다.

### @Builder<br>
Buillder 자동 생성<br> <br>
@Singular 어노테이션 사용시 원소를 하나씩 추가할 수 있다.

<br>

### @Builder + @Singular 예제

```java
@Builder
public class Movie {
	private String title;
    @Singular
    private List<String> actress;
}

// movie(title="삼진그룹 영어토익반", actress= ["고아성", "이솜", "박혜수"])
Movie movie = Movie.builder()
				.title("삼진그룹 영어토익반")
                .actress("고아성")
                .actress("이솜")
                .actress("박혜수")
                .build();
```

<br>

`toString()` : 객체의 값들을 문자열로 변환후 반환 <br>
`equals()` : 동등성 비교 연산자  <br>
`hashCode()` : 동일성 비교 연산자 