<ul>
<li>실습 위주   —&gt;  git 링크첨부하기 !</li>
</ul>
<hr />
<h2 id="name과-id의-차이"><strong><code>name</code>과 <code>id</code>의 차이</strong></h2>
<table>
<thead>
<tr>
<th><strong>속성</strong></th>
<th><strong>역할</strong></th>
<th><strong>고유성 필요 여부</strong></th>
<th><strong>주요 용도</strong></th>
</tr>
</thead>
<tbody><tr>
<td><strong><code>id</code></strong></td>
<td>HTML 문서 내에서 요소를 고유하게 식별</td>
<td>반드시 고유해야 함</td>
<td>CSS/JavaScript에서 특정 요소를 선택하거나 <strong><code>&lt;label&gt;</code></strong>과 연결하는 데 사용</td>
</tr>
<tr>
<td><strong><code>name</code></strong></td>
<td>폼 데이터를 서버로 전송할 때 해당 입력 필드의 이름(키) 역할</td>
<td>고유하지 않아도 됨</td>
<td>서버로 데이터를 전송할 때, 데이터의 이름(key)로 사용</td>
</tr>
<tr>
<td>1. <strong><code>name</code> 속성의 역할</strong></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td>- HTML에서 <strong><code>name</code></strong> 속성은 <strong>폼 데이터를 서버로 전송할 때 사용하는 이름(키)</strong>입니다.</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td>- 이 키를 통해 서버는 어떤 데이터가 어떤 입력 필드에서 왔는지 구분할 수 있습니다.</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td>2. <strong><code>name=&quot;name&quot;</code>의 의미</strong></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td>- 첫 번째 <strong><code>name</code></strong>은 HTML 속성 이름으로, 데이터를 구분하는 데 사용되는 키를 정의합니다.</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td>- 두 번째 <strong><code>&quot;name&quot;</code></strong>은 그 필드의 고유한 키(key)로 설정된 값입니다.</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td>- 즉, 이 입력 필드는 &quot;이름&quot; 데이터를 받는 필드이며, 서버로 전송될 때 <strong><code>&quot;name&quot;</code></strong>이라는 키로 데이터를 보냅니다.</td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody></table>
<ul>
<li>참고</li>
</ul>
<table>
<thead>
<tr>
<th><strong><code>type</code> 값</strong></th>
<th><strong>설명</strong></th>
<th><strong>특징/조건</strong></th>
</tr>
</thead>
<tbody><tr>
<td><strong>text</strong></td>
<td>일반 텍스트 입력 필드</td>
<td>제한 없이 텍스트 입력 가능</td>
</tr>
<tr>
<td><strong>password</strong></td>
<td>비밀번호 입력 필드</td>
<td>입력한 텍스트가 화면에 표시되지 않고 ●●●●처럼 숨겨짐</td>
</tr>
<tr>
<td><strong>email</strong></td>
<td>이메일 주소 입력 필드</td>
<td>이메일 형식(<strong><code>example@example.com</code></strong>) 검증</td>
</tr>
<tr>
<td><strong>number</strong></td>
<td>숫자만 입력받는 필드</td>
<td>숫자만 입력 가능 (최소값/최대값 설정 가능)</td>
</tr>
<tr>
<td><strong>tel</strong></td>
<td>전화번호 입력 필드</td>
<td>전화번호 형식으로 입력받음 (형식 검증은 없음)</td>
</tr>
<tr>
<td><strong>url</strong></td>
<td>URL(웹 주소) 입력 필드</td>
<td>URL 형식(<strong><code>https://example.com</code></strong>) 검증</td>
</tr>
<tr>
<td><strong>date</strong></td>
<td>날짜 선택 필드</td>
<td>날짜 선택 UI 제공 (브라우저마다 다를 수 있음)</td>
</tr>
<tr>
<td><strong>time</strong></td>
<td>시간 선택 필드</td>
<td>시간 선택 UI 제공</td>
</tr>
<tr>
<td><strong>datetime-local</strong></td>
<td>날짜와 시간을 함께 선택할 수 있는 필드</td>
<td>날짜와 시간 모두 선택 가능</td>
</tr>
<tr>
<td><strong>checkbox</strong></td>
<td>체크박스</td>
<td>여러 값을 선택할 수 있음</td>
</tr>
<tr>
<td><strong>radio</strong></td>
<td>라디오 버튼</td>
<td>동일한 그룹 내에서 하나의 값만 선택 가능</td>
</tr>
<tr>
<td><strong>range</strong></td>
<td>슬라이더로 값을 선택</td>
<td>최소값/최대값 설정 가능</td>
</tr>
<tr>
<td><strong>color</strong></td>
<td>색상 선택 필드</td>
<td>색상 선택 UI 제공</td>
</tr>
<tr>
<td><strong>file</strong></td>
<td>파일 업로드 필드</td>
<td>파일을 업로드할 수 있는 버튼 제공</td>
</tr>
<tr>
<td><strong>hidden</strong></td>
<td>화면에 표시되지 않는 숨겨진 필드</td>
<td>사용자에게 보이지 않지만 데이터를 전송할 때 사용</td>
</tr>
<tr>
<td><strong>submit</strong></td>
<td>폼 제출 버튼</td>
<td>버튼을 클릭하면 폼 데이터가 서버로 전송됨</td>
</tr>
<tr>
<td><strong>reset</strong></td>
<td>폼 초기화 버튼</td>
<td>클릭 시 모든 입력값 초기화</td>
</tr>
</tbody></table>
<h2 id="유효성-검사">유효성 검사</h2>
<p>프론트엔드에선는 입력값이 형태에 맞게 잘입력되었는지 확인 </p>
<p>(ex. 이메일형식에 맞게 입력되었는지 )</p>
<p>백엔드에서 유효성검사 </p>
<p>→ 18세이상 회원가입가능할때 통과시켜주는 로직 </p>
<h2 id="html-반응형-웹">HTML 반응형 웹</h2>
<ul>
<li>화면 크기에 맞에 적절하게 보여줌</li>
</ul>
<p>메타테그 : 문서에 대한 메타데이터 제공 ,  태그에 위치함 </p>
<pre><code> &lt;meta name = “description”</code></pre><p>—&gt; 웹페이지 내용 짧은설명 —&gt; SEO를 위해 </p>
<h2 id="html--시맨틱태그">HTML  시맨틱태그</h2>
<ul>
<li>의미적으로 , 사람이 읽기좋게 만든 태그</li>
</ul>
<pre><code>&lt;section&gt;</code></pre><p>--&gt; 하나의 묶음 내용 → 근데 넣어도 안넣어도 결과가 달라지지않는다.</p>
<p>근데 왜 사용하지 ? </p>
<p>—&gt; 시멘틱 태그 사용이유  :  영역만 봐도 어떤구조 인지 확인할 수 있다</p>