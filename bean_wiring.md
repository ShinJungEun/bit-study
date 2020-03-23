1. Spring Container
2. Bean Wiring (Spring in Action 2, 3, 5장 참고~!) : 설정 파일의 설정, Bean Class 설정


##wiring  
xml config ----  auto  :  annotation scan   	=> 암시적(implicity) 설정
       	   |---- explicity	(xml)  <bean,,,,,/>	=> 명시적(explicity) 설정

java config  ---- auto annotation scan, @ComponentScan
	     |---- explicity  @Bean


* xml 설정 : bean 설정

@ComponentScan("위치지정")		=> 1) auto config
public class config {
	@Bean			=> 2) Explicity java config
	public DataSource dateSource() {
		return new BasicDataSource();
	}
}

new ClassPathXmlApplicationContext("config.xml");
new ClassPathAnnotationlApplicationContext(Config.class);



### 1. Spring Container test 예제 package
src/main/java
 com.douzone.container.user   
    |---- User1.java   
    |---- User.java   
    |---- Friend.java   
 config.user   
     |---- AppConfig01.java   
src/main/resources   
 config.user   
     |---- applicationContext01.xml	(Auto Configuration, Annotation Scanning)   
     |---- applicationContext02.xml	(Bean Configuration, Explicit Configuration)   
src/test/java   
 com.douzone.container.test   
    |---- JavaConfigTest.java		=> junit을 활용한 test   
    |---- XmlConfigTest.java		=> spring 환경에서의 test   
   
### 2-1. Bean Wiring 예제 : 암시적 설정(auto scanning) package
src/main/java   
 com.douzone.container.soundsystem   
    |---- CDPlayerJavaConfigTest.java   
    |---- CDPlayerXmlConfigTest.java   
 com.douzone.container.soundsystem   
    |---- CompactDisc.java   
    |---- HighSchoolRapper3.java   
    |---- CDPlayer.java   
 config.soundsystem   
     |---- CDPlayerConfig.java   (Java Config)   
src/main/resources   
 config.soundsystem   
     |---- CDPlayerConfig.xml	(XML Config)   

### 2-2. Bean Wiring 예제 : 명시적 설정 package