React로 todo-list 만들기

1. 컴포넌트 구성하기
- TodoTemplate : 템플릿의 역할
- Form : 인풋과 버튼이 담겨있는 컴포넌트 
  - 4가지의 props를 받아온다.
  - value : 인풋의 내용
  - onCreate : 버튼이 클릭 될 때 실행 될 함수
  - onChange : 인풋 내용이 변경 될 때 실행되는 함수
  - onKeyPress : 인풋에서 키를 입력 할 때 실행되는 함수, 이 함수는 나중에 Enter가 눌렸을 때 onCreate 를 한 것과 동일한 작업을 하기 위해서 사용
- TodoItemList : TodoItem 컴포넌트 여러개를 렌덩링해주는 역할
  - todos : todo 객체들이 들어있는 배열
  - onToggle : 체크박스를 키고 끄는 함수
  - onRemove : 아이템을 삭제시키는 함수
- TodoItem
  - text : todo 내용
  - cheched : 체크박스 상태
  - id : todo의 고유 아이디
  - onToggle : 체크박스를 키고 끄는 함수
  - onRemove : 아이템을 삭제시키는 함수 
2. 상태관리 하기
다른 컴포넌트끼리 직접 데이터를 전달하는 것은 ref를 사용하여 할 수 있지만, 비효율적인 방법 <br>
컴포넌트가 많아지면 유지보수하기 어려워짐 <br>
따라서 컴포넌트들은 부모를 통하여 대화 해야한다.
- Form 기능 구현하기
 - 텍스트 내용 바뀌면 state 업데이트
 - 버튼이 클릭되면 새로운 todo 생성 후 todos 업데이트
 - 인풋에서 Enter누르면 버튼을 클릭한것과 동일한 작업진행하기
- TodoItemList에서 배열을 TodoIem 컴포넌트 배열로 변환하기
- 체크 하기 / 체크 풀기
- 아이템 제거하기
3. 최적화 하기
- 컴포넌트 라이프 사이클 메소드중 shouldComponentUpdate는 컴포넌트가 리렌더링을 할 지 말지 정해준다. <br>
이게 따로 구현되지 않으면 언제나 true를 반환하는데, 이를 구현하는 경우에는 업데이트에 영향을 끼치는 조건을 return 해주면 된다. <br>
