# spring-cloud-study

## 추가 설정 for 인텔리제이 
### Git Clone 후 Intellij로 프로젝트 Open 시 Maven을 인식하지 못합니다. 
   통합 빌드 설정이 필요할 것 같지만, 예제니까 생략하고, 인텔리제이 추가 설정해서 프로젝트 run 방법을 알려 드리겠습니다! 포트 설정이 들어가 있어서 이해를 돕기 위해 해당 예제 파일의 Eureka Zone 구성에 대한 책의 서버구성도를 첨부 합니다. 
   
![KakaoTalk_Image_2022-04-17-15-38-45](https://user-images.githubusercontent.com/39294100/163703715-4e9b0b9e-9498-4d66-a821-bdf2348936d3.jpeg)
 - 게이트웨이 port: 8765, 8766, 8767  
 - 애플리케이션 port: 8081, 8082, 8083
 - 유레카 port : 8761, 8762, 8763  

### 인텔리제이 > 모듈 추가  
 - 인텔리제이 File > Project Structure > Modules에 클라이언트, GW, Discovery 모듈을 import하여 추가합니다.  
<img width="908" alt="스크린샷 2022-04-17 오후 3 33 29" src="https://user-images.githubusercontent.com/39294100/163703852-7fb7d355-fc39-487f-8716-45c0d10e23b8.png">  

### 인텔리제이 > 어플리케이션 및 포트 설정  
 - Run/Debug Configurations에서 Springboot Application을 추가해줍니다. (앱 3, gw3, 유레카3) 모두 추가한 경우 아래와 같이 9개의 앱이 추가됩니다. 각 앱에 위에 설정한 포트로 환경변수를 설정해줍니다.  
<img width="1146" alt="스크린샷 2022-04-17 오후 3 34 45" src="https://user-images.githubusercontent.com/39294100/163703898-13b87c6c-3cb2-47dd-af17-bb6dd8ad3863.png">

<img width="1146" alt="스크린샷 2022-04-17 오후 3 34 45" src="https://user-images.githubusercontent.com/39294100/163703599-06387f9e-c319-422d-aa55-06e236ae9070.png">

### 확인  
  - 어플리케이션은 샘플코드로 스웨거2가 연동되어 있습니다.  
  - GW를 통해 어플리케이션 호출이 잘 된 경우 연결이 잘 된 것입니다.  
  - 유레카 대시보드도 확인합니다. 

<img width="944" alt="스크린샷 2022-04-17 오후 1 36 06" src="https://user-images.githubusercontent.com/39294100/163703982-17b75281-bae8-4264-ab58-4135d8413fc5.png">  
게이트웨이 포트인 8767로 앱의 스웨거 호출시 성공한 것을 볼 수 있습니다.  

<img width="1200" alt="스크린샷 2022-04-17 오후 1 18 13" src="https://user-images.githubusercontent.com/39294100/163705888-07bfecb8-d95d-4d81-b20c-09999da4d0ee.png">
 
유레카 대시보드 확인시 CLIENT-SERVICE, DISCOVERY-SERVICE, GATEWAY-SERVICE가 3개의 존에 레지스터드 되었음을 확인할 수 있습니다.  

<끝!! 즐거운 실습되세요!>
