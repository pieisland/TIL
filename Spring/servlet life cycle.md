# Servlet Life Cycle_210318
https://kangdaseul.tistory.com/13   
그냥 옮겨 적음.

클라이언트의 요청이 들어오면 WAS는 해당 요청에 맞는 servlet이 메모리에 있는지 확인한다.    
메모리에 없다면 해당 servlet Class 객체를 생성하고 init 메서드를 실행한다.    
이후 service 메서드를 실행한다.   
메모리에 없다면 바로 service 메서드를 실행한다.

## init()
servlet 객체를 초기화하는 역할을 한다.   
한 번만 수행되며, 클라이언트의 요청에 따라 적절한 servlet이 생성되고 이 servlet이 메모리에 로드될 때 init 메서드가 호출된다.   

## service(requet, response)
응답에 대한 모든 내용은 service() 메서드에 구현해야 한다.    
servlet이 수신한 모든 request에 대해 service 메서드가 호출된다.   
service 메서드는 request의 type(get, post, put delete)에 따라 적절한 메서드(doGet, doPost, doPut, doDelte)를 호출한다.    
메서드가 return하면 thread는 제거된다.   

## destroy()
servlet 객체를 메모리에서 제거한다.   
한 번만 수행되며 Web Application이 갱신되거나 WAS가 종료될 때 호출된다.   

## HttpServletRequest request 객체
사용자가 html form에 입력한 내용을 request 객체에서 받아온다.   
http 프로토콜의 request 정보를 servlet에게 전달한다.    
헤더 정보, 파라미터, 쿠키, uri, url, body stream 등을 읽어들이는 메서드가 있다.   
getHeader, getParameter ...

## HttpServletResponse response 객체
인자의 내용에 맞게 동적인 html 코드를 생성하여 response 객체에 담아 반환한다.    
form data를 처리한 결과를 web page에 생성해 반환한다.   
