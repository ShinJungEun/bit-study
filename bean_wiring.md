1. Spring Container     
2. Bean Wiring (Spring in Action 2, 3, 5�� ����~!) : ���� ������ ����, Bean Class ����     


##wiring     
xml config ----  auto  :  annotation scan  => �Ͻ���(implicity) ����     
       	   |---- explicity	(xml)  <bean,,,,,/>  => �����(explicity) ����     

java config  ---- auto annotation scan, @ComponentScan     
	     |---- explicity  @Bean      
 

* xml ���� : bean ����     

@ComponentScan("��ġ����")  => 1) auto config    
public class config {    
	@Bean  => 2) Explicity java config    
	public DataSource dateSource() {    
		return new BasicDataSource();    
	}    
}    

new ClassPathXmlApplicationContext("config.xml");     
new ClassPathAnnotationlApplicationContext(Config.class);      



### 1. Spring Container test ���� package     
src/main/java      
	com.douzone.container.user      
		|---- User1.java      
		|---- User.java      
		|---- Friend.java   
	config.user     
		|---- AppConfig01.java     
src/main/resources      
	config.user       
		|---- applicationContext01.xml  (Auto Configuration, Annotation Scanning)   
		|---- applicationContext02.xml  (Bean Configuration, Explicit Configuration)   
src/test/java      
	com.douzone.container.test   
		|---- JavaConfigTest.java  => junit�� Ȱ���� test   
		|---- XmlConfigTest.java  => spring ȯ�濡���� test   
   
### 2-1. Bean Wiring ���� : �Ͻ��� ����(auto scanning) package     
src/main/java      
	com.douzone.container.soundsystem      
		|---- CompactDisc.java    
		|---- HighSchoolRapper3.java     
		|---- CDPlayer.java     
	config.soundsystem     
		|---- CDPlayerConfig.java   (Java Config)    
src/test/java     
	com.douzone.container.soundsystem    
		|---- CDPlayerJavaConfigTest.java   
		|---- CDPlayerXmlConfigTest.java   
src/main/resources     
	config.soundsystem   
		|---- CDPlayerConfig.xml  (XML Config)   

### 2-2. Bean Wiring ���� : ����� ���� package
src/main/java   
	com.douzone.container.videosystem      
		|---- DigitalViedoDisc.java     
		|---- DVDPlayer.java     
		|---- Avengers.java     
		|---- IronMan.java     
		|---- BlankDisc.java     
		|---- DVDPack.java    
	config.videosystem   
		|---- DVDPlayerConfig.java  (Java Config)   
	config.videosystem.mixing    
		|---- DVDPlayerConfig.java  (Java Config)    
		|---- DVDConfig.java  (Java Config)    
		|---- VideoSystemConfig.java  (Java Config)    
     
src/test/java     
	com.douzone.container.videosystem      
		|---- DVDPlayerJavaConfigTest.java     
		|---- DVDPlayerXmlConfigTest.java      
		|---- DVDPlayerMixingConfigTest01.java     
		|---- DVDPlayerMixingConfigTest02.java    
src/main/resources      
	config.videosystem     
		|---- DVDPlayerConfig.xml  (XML Config)     

