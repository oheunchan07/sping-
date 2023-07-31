# 스프링빈

## 스르링빈을 등록하는 방법은 총 2가지가 있다
### 1.컴포넌트 스캔과 자동 의존관계 설정
#### @Component 를 포함하는 다음 애노테이션도 스프링 빈으로 자동 등록된다
* @Controller
* @Service
* @Repository

#### ex)
```
@Service
public class MemberService {

  private final MemberRepository memberRepository;

  @Autowired
  public MemberService(MemberRepository memberRepository) {
    this.memberRepository = memberRepository;

  }

}
```

#### ※ 생성자에 @Autowired 를 사용하면 객체 생성 시점에 스프링 컨테이너에서 해당 스프링 빈을 찾아서 주입한다. 생성자가 1개만 있으면 @Autowired 는 생략할 수 있다

### 2.컴포넌트 스캔과 자동 의존관계 설정

#### ex)
```
@Configuration
public class SpringConfig {

  @Bean
  public MemberService memberService() {
    return new MemberService(memberRepository());

  }

  @Bean
  public MemberRepository memberRepository() {
    return new MemoryMemberRepository();

  }
}
```

#### ※ XML로 설정하는 방식도 있지만 최근에는 잘 사용하지 않으므로 생략
#### ※ 의존관계가 실행중에 동적으로 변하는 경우는 거의 없으므로 생성자 주입을 권장
