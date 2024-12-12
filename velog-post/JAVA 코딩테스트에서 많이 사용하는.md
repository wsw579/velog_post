<h3 id="1-scannernext">1. scanner.next()</h3>
<p>기능: 공백(띄어쓰기, 탭, 개행 문자 등)을 기준으로 단어 하나를 읽습니다.
동작: 입력된 데이터에서 첫 번째 공백 전까지의 문자열을 반환합니다. 즉, 공백이 나타나면 입력을 중단합니다.
예시: 만약 사용자가 &quot;Hello World&quot;라고 입력하면, next()는 &quot;Hello&quot;를 반환합니다.</p>
<h3 id="2-scannernextline">2. scanner.nextLine()</h3>
<p>기능: 한 줄 전체를 읽습니다.
동작: 개행 문자(Enter)를 만날 때까지 입력된 전체 문자열을 반환합니다. 즉, 공백을 포함한 한 줄 전체를 읽습니다.
예시: 사용자가 &quot;Hello World&quot;라고 입력하면, nextLine()은 &quot;Hello World&quot;를 반환합니다.</p>
<h3 id="3-공백포함--공백제외--단어수">3. 공백포함 , 공백제외 , 단어수</h3>
<pre><code> a = scanner.nextLine(); // 공백포함 모든문자열
 -&gt; scanner.nextLine().trim() // 맨앞,맨뒤 공백제외 

int wordNumexp = a.replaceAll(&quot; &quot;,&quot;&quot;).length(); // 공백포함 문자수
int wordNum= a.length();  // 공백제외 문자수
String[] words = a.split(&quot; &quot;); // 공백기준으로 나누기기

</code></pre><ul>
<li>&quot;\s+&quot;: 이 부분은 정규 표현식입니다.</li>
<li>\s는 공백 문자(space, tab 등)를 의미합니다.</li>
<li>+는 하나 이상의 연속된 공백 문자를 나타냅니다. 즉, 공백이 여러 개 연속으로 있을 경우에도 이를 모두 매칭합니다.</li>
</ul>
<h3 id="4-직각삼각형-조건">4. 직각삼각형 조건</h3>
<p><img alt="" src="https://velog.velcdn.com/images/victoryone/post/56cf86f9-63a1-4f48-ad42-e97126c9b9e9/image.png" /></p>