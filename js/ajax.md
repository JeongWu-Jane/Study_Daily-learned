# ajax
## ajax 메소드
- $.ajax() : 비동기식 ajax 이용하여 HTTP 요청 전송
- $.get() : 전달받은 주소로 get 방식의 HTTP 요청 전송
- $.post() : 전달받은 주소로 POST 방식의 HTTP 요청 전송
- $.getScript: 웹 페이지에 스크립트 추가
- $.getJSON(): 전달받은 주소로 GET 방식의 HTTP 요청 전송하여, 응답으로 JSON 파일 전송받음
- .load() 서버에서 데이터를 읽은 후 읽어드린 HTML 코드 선택한 요소에 배치

### .ajax() 메소드
- url: 요청 url
- settings: key/value 쌍으로 된 Ajax 요청 Set
  - url : 요청 url
  - data : 요청과 함께 서버에 보내는 string or json
  - success: 요청이 성공일떄 실행되는 callback 함수
  - dataType: 서버에서 내려온 data 형신(default: xml, json, script, text,html)
  <!-- - accepts -->
  <!-- - async -->
  - beforeSend: request 보내기전에 작동하는 함수
    ex) loading.show
  - complete: 성공/실패/에러 등 모든 상황이 종료된 이후의 함수
  - method(type): "GET","POST"
  - error: 전송 완료된 후 에러상황에 대한 함수
  - cache: IE브라우저에서 ajax 사용 -> 데이터 갱신x


### 메소드 체이닝
- done: HTTP 요청이 성공하면 요청한 데이터가 전달
- fail: HTTP 요청이 실패하면 어루와 상태에 관한 정보가 전달
- always: 성공/실패 상관없이 언제나 실행

`
$.ajax({ 
    url: "/rest/1/pages/245", // 클라이언트가 HTTP 요청을 보낼 서버의 URL 주소 data: { name: "홍길동" }, // HTTP 요청과 함께 서버로 보낼 데이터 
    method: "GET", // HTTP 요청 메소드(GET, POST 등) 
    dataType: "json" // 서버에서 보내줄 데이터의 타입 
    }) 
    // HTTP 요청이 성공하면 요청한 데이터가 done() 메소드로 전달됨. 
    .done(function(json) { 
        $("<h1>").text(json.title).appendTo("body"); 
        $("<div class=\"content\">").html(json.html).appendTo("body"); 
    }) 
    // HTTP 요청이 실패하면 오류와 상태에 관한 정보가 fail() 메소드로 전달됨. 
    .fail(function(xhr, status, errorThrown) { 
        $("#text").html("오류가 발생했다.<br>") 
        .append("오류명: " + errorThrown + "<br>") 
        .append("상태: " + status); 
        }) 
        // .always(function(xhr, status) { 
         $("#text").html("요청이 완료되었습니다!"); 
     });
     // .always(function(xhr, status) { $("#text").html("요청이 완료되었습니다!"); });
`