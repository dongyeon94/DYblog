---
layout: post
title:  "Springboot Email Sender"
date:   2020-06-16
author: DY
comments: true
categories: Daily
---

# springboot email send

Springboot에서 email을 전송하는 방법입니다. 먼저 lib을 다운받아야합니다. 

  - pom.xml 파일에 아래 코드를 입력합니다.
  
```xml

<!-- Java Mail API -->
<dependency>
    <groupId>javax.mail</groupId>
    <artifactId>mail</artifactId>
    <version>1.4.3</version>
</dependency>

```



그리고 나서 java code를 작성하게 됩니다.

저는 Naver에 pop 서버를 사용했습니다. 설정 방법은 아래 링크에서 확인할 수 있습니다.  
- https://help.naver.com/support/contents/contents.help?serviceNo=2342&categoryNo=2281

pop 설정을 마치고 아래 코드를 작성해서 보내면 메일의 테스트는 완료됩니다.

```java

import javax.mail.internet.MimeMessage;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.mail.javamail.JavaMailSender;
import org.springframework.mail.javamail.MimeMessageHelper;
import org.springframework.stereotype.Service;

@Service
public class javaxEmailService {
	@Autowired
	private JavaMailSender  mailSender;
	
	private String  from ="user email address";
	private String subject = "subject";
	
	public String emailTeat() {
		try {
			MimeMessage mes = mailSender.createMimeMessage();
			MimeMessageHelper hel = new MimeMessageHelper(mes ,true,"UTF-8");
			hel.setTo("email address");
			hel.setText("main text");
			hel.setFrom(from);
			hel.setSubject(subject);
			
			mailSender.send(mes);
			
			return "suc";
		}catch (Exception e) {
			// TODO: handle exception
			return "fail";
		}
		
	}
}


```

이제 작성한 코드를 테스트 해야합니다. Test code를 작성하지 않고 그냥 실행해서 테스트 
할 수 있지만 Test code를 작성할 것을 추천드립니다. 



```java

import javax.mail.MessagingException;

import org.junit.Test;
import org.junit.runner.RunWith;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.boot.test.context.SpringBootTest;
import org.springframework.test.context.junit4.SpringRunner;

import com.toy.root.email.javaxEmailService;
import com.toy.root.email.springbootEmail;


@RunWith(SpringRunner.class)
@SpringBootTest
public class mailsendTest  {

	@Autowired
	private springbootEmail email;
	
	@Autowired
	private javaxEmailService ser;
	
	@Test
	public void test() throws MessagingException {
//		System.out.println(email.sendSimpleMessage());
		System.out.println(ser.emailTeat());
	}
	
}

```




보내는 사람의 이메일 주소를 config를 테스트 하고있습니다. 제 이메일로 보내는데는 
성공했지만 실제로는 제가 보냈는데 보낸 사람의 주소를 바꿀수 있는 방법을 찾고있습니다. 

Email send를 하는 라이브러리가  몇개 더 있었습니다. 아래와 같이 Springboot-starter에도 
email lib이 있습니다.

```xml

<!-- https://mvnrepository.com/artifact/org.springframework.boot/spring-boot-starter-mail -->
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-mail</artifactId>		      
</dependency>

```


같이 공부해보는 것도 좋을것 같습니다. 

---

<div style="height: 50px;"></div>
<div style="float: right;">
  <button onclick="location.href='https://docs.spring.io/spring-boot/docs/current/reference/htmlsingle/' ">Spring Boot Reference</button> 
</div>
