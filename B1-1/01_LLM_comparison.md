<!-- Copy and paste the converted output. -->

<!-----



Conversion time: 2.676 seconds.


Using this Markdown file:

1. Paste this output into your source file.
2. See the notes and action items below regarding this conversion run.
3. Check the rendered output (headings, lists, code blocks, tables) for proper
   formatting and use a linkchecker before you publish this page.

Conversion notes:

* Docs™ to Markdown version 2.0β2
* Sun Jun 21 2026 04:45:49 GMT-0700 (미 태평양 하계 표준시)
* Source doc: [AI 수학 튜터] 1. LLM 모델 비교·선정 보고서
* Tables are currently converted to HTML tables.
----->



# LLM 모델 비교·선정 보고서

**프로젝트명:** 고등학생 맞춤형 AI 수학 튜터 도입


## 1. 비교 테스트 개요



* **비교 목적:** 고등학생 대상 수학 문제 출제 및 단계별 튜터링에 가장 적합한 LLM 모델 선정
* **테스트 과업:** 고등학교 2학년 '수학 II - 미분가능성과 연속성' 단원의 심화 난이도 응용 문제 출제 및 힌트 제공 (총 2턴)
* **테스트 환경:** Web
* **비교 대상 모델:** GPT-5, Claude Sonnet 4.6, Gemini 3.1 Pro
* **공통 지시사항 (프롬프트):**
    * **Turn 1:** "나는 수학 II를 공부하고 있는 고등학교 2학년 학생이야. '미분가능성과 연속성의 관계'를 확실하게 이해했는지 점검할 수 있는 심화 난이도의 응용 문제를 딱 1개만 출제해 줘. 수식을 출력할 때 절대 LaTeX 기호($, ^, \cdot, \frac 등)를 쓰지 말고, 교과과정에서 소개하는 기호만 사용하도록 해."
    * **Turn 2:** "모르겠어. 어떻게 풀어야 해?"


## 2. 모델별 평가표 (1~5점)


<table>
  <tr>
   <td>평가 축
   </td>
   <td>GPT-5
   </td>
   <td>Claude Sonnet 4.6
   </td>
   <td>Gemini 3.1 Pro
   </td>
  </tr>
  <tr>
   <td>1) 수학적 정확성 (오류 유무)
   </td>
   <td>3
   </td>
   <td>1
   </td>
   <td><strong>5</strong>
   </td>
  </tr>
  <tr>
   <td>2) 튜터링 유도 능력 (스포일러 금지)
   </td>
   <td>3
   </td>
   <td>1
   </td>
   <td><strong>2</strong>
   </td>
  </tr>
  <tr>
   <td>3) 학생 눈높이 맞춤 (설명 질/톤앤매너)
   </td>
   <td>2
   </td>
   <td>3
   </td>
   <td><strong>4</strong>
   </td>
  </tr>
  <tr>
   <td>4) 문제의 질 (난이도/교과과정/포맷팅)
   </td>
   <td>1
   </td>
   <td>2
   </td>
   <td><strong>4</strong>
   </td>
  </tr>
  <tr>
   <td><strong>총점</strong>
   </td>
   <td><strong>9</strong>
   </td>
   <td><strong>7</strong>
   </td>
   <td><strong>15</strong>
   </td>
  </tr>
</table>



## 3. 모델별 상세 평가 근거


### GPT-5



* **장점:** 힌트를 바로 제공하지 않고 문제 안에서 순서에 따라 해결할 수 있도록 단계별로 가이드를 해주는 튜터링 구조가 훌륭함. 수식 자체의 연산 오류는 없었음.
* **단점 (감점 근거):** 교과과정 이탈 및 지시사항 위반이 심각함. $x^2 \sin(1/|x|)$와 같은 대학교 수준의 함수를 출제하여 고등학교 교과과정을 완전히 벗어남. 또한, 수식을 텍스트로 쓰라는 지시에도 불구하고 `$` 기호나 `\ne` 같은 LaTeX 문법을 그대로 노출하여 가독성을 떨어뜨림.


### Claude Sonnet 4.6



* **장점:** 교과과정의 기호를 정확하게 보여주어 문제가 한눈에 잘 들어오며, 가독성이 높음.
* **단점 (감점 근거):** 가장 심각한 수학적 환각을 일으킴. 본인이 오류가 있는 문제를 출제해놓고, 풀이 단계에서는 사실 함정 문제였다고 말하는 치명적인 논리 오류를 범해 튜터로서 신뢰할 수 없음.


### Gemini 3.1 Pro



* **장점:** 교과과정에 완벽하게 들어맞는, 오류 없는 훌륭한 심화 문제를 출제함. x=2에서 절댓값 때문에 꺾일 위험이 있는데 미분가능하려면 인수를 하나 더 가져야 한다는, 모의고사 단골 출제 원리를 정확히 꿰뚫고 있어 수학적 역량이 가장 뛰어남.
* **단점 (감점 근거):** 기호 사용 금지 지시에 과민 반응하여 'x제곱'처럼 불필요하게 말로 길게 풀어서 설명함. 또한, 첫 턴부터 묻지도 않은 힌트를 제공하고, 힌트를 요구했을 때 핵심 계산 과정(g(2)=0)을 모두 스포일러하는 등 튜터로서의 '유도 능력'이 다소 부족함.


## 4. 최종 선정 결론

**최종 선정 모델:** **Gemini 3.1 Pro**

**선정 근거:**

1. 다른 모델들과 달리 교과과정을 정확히 이해하고 모의고사 수준의 수학적 오류가 없는 완벽한 심화 문제를 출제함.

2. 타 모델에서 발생한 치명적인 수학적 환각이 전혀 발생하지 않아 튜터의 가장 중요한 자질인 정확성을 충족함.

3. 튜터링 과정에서 힌트를 너무 많이 주었으나, 이는 시스템 프롬프트 제어를 통해 충분히 교정 가능한 부분이라고 판단함.
