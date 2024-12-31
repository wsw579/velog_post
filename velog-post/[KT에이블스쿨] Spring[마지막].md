<p>페이지네이션 pagination </p>
<p>→ 페이지네이션(Pagination)은 데이터나 콘텐츠를 여러 페이지로 나눠서 사용자에게 보여주는 방법. 
대규모 데이터를 한 번에 로드하지 않고 적절한 크기로 나눠서 전달하므로 성능과 사용자 경험을 개선한다.</p>
<p>findby </p>
<p>findAll</p>
<hr />
<h2 id="rest--rest-api">REST / REST API</h2>
<ol>
<li>행위를 포함하지 않는다. </li>
</ol>
<p><strong>HTTP 메서드 사용</strong></p>
<ul>
<li>CRUD 작업(Create, Read, Update, Delete)을 HTTP 메서드로 처리합니다.</li>
</ul>
<pre><code>| **HTTP 메서드** | **동작** | **설명** |
| --- | --- | --- |
| GET | 조회(Read) | 리소스를 가져옵니다. |
| POST | 생성(Create) | 새로운 리소스를 생성합니다. |
| PUT | 업데이트(Update) | 기존 리소스를 수정합니다. |
| DELETE | 삭제(Delete) | 리소스를 삭제합니다. |</code></pre><ul>
<li><strong>Validation</strong></li>
</ul>
<p><strong>Validation</strong>은 데이터가 특정 조건이나 규칙에 부합하는지 확인하고, 부적합한 데이터를 처리하기 전에 차단하는 과정입니다. 주로 사용자 입력을 서버나 데이터베이스로 보내기 전에 데이터의 유효성을 검증하는 데 사용됩니다.</p>
<h3 id="dto에서-validation의-의미"><strong>DTO에서 Validation의 의미</strong></h3>
<p>DTO(Data Transfer Object)는 주로 계층 간 데이터를 전달하는 객체입니다. 이 과정에서 <strong>Validation</strong>을 사용하면 DTO에 담긴 데이터가 정해진 조건에 부합하는지 확인할 수 있습니다.</p>
<p>예를 들어:</p>
<ul>
<li>이메일 형식이 올바른지 확인</li>
<li>문자열의 길이가 특정 범위 내에 있는지 확인</li>
<li>숫자가 음수가 아닌지 확인</li>
<li>필수 값이 누락되지 않았는지 확인</li>
</ul>
<p>entity에서 NUll   /  DTO에서 NUll</p>
<h3 id="entity와-dto에서-null의-주요-차이점"><strong>Entity와 DTO에서 <code>NULL</code>의 주요 차이점</strong></h3>
<table>
<thead>
<tr>
<th><strong>구분</strong></th>
<th><strong>Entity</strong></th>
<th><strong>DTO</strong></th>
</tr>
</thead>
<tbody><tr>
<td><strong>사용 목적</strong></td>
<td>데이터베이스 테이블 매핑</td>
<td>계층 간 데이터 전달</td>
</tr>
<tr>
<td><strong>NULL의 의미</strong></td>
<td>DB 필드가 비어 있는 상태를 반영</td>
<td>클라이언트 또는 응답에서 값이 없는 상태</td>
</tr>
<tr>
<td><strong>유효성 검증</strong></td>
<td>데이터베이스 제약 조건 (<code>@Column(nullable = false)</code>)</td>
<td>어노테이션 기반 검증 (<code>@NotNull</code>, <code>@NotBlank</code>)</td>
</tr>
<tr>
<td><strong>사용 위치</strong></td>
<td>데이터베이스와 직접 연관</td>
<td>컨트롤러, 서비스 계층</td>
</tr>
</tbody></table>
<p>정리 : Entity는 데이터베이스와의 저장 및 조회에서 NULL 처리를 주로 다루고, DTO는 데이터의 유효성을 검증하며 NULL 처리 여부를 비즈니스 로직에 활용</p>
<ul>
<li>Entity: 데이터베이스 중심, NULL은 그대로 데이터베이스 상태를 반영.</li>
<li>DTO: 클라이언트와의 데이터 통신 중심, NULL은 값이 없음을 나타내며 유효성 검증(Validation)으로 관리.</li>
</ul>
<p><strong><em>mywords : Entity 값으로 처리 , DTO 응답없음</em></strong></p>