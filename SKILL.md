---
name: srao-agent-graph
description: 鏅鸿兘浣撳浘璋辨瀯寤猴紙SRAO闃舵2-3锛夈€傚皢缁撴瀯鍖栭渶姹?SRM)鎷嗚В涓哄師瀛愪换鍔AG锛屾槧灏勪负鍏被鏅鸿兘浣撹兘鍔涘浘璋憋紝杈撳嚭鍙疄渚嬪寲鐨凙gent闆嗙兢钃濆浘锛屾敮鎸佽法琛屼笟澶嶇敤妫€娴嬨€傝Е鍙戣瘝锛氭櫤鑳戒綋鍥捐氨銆丄gent鍥捐氨銆佷换鍔℃媶瑙ｃ€佸師瀛愪换鍔°€丏AG銆佹櫤鑳戒綋璁捐銆丄gent璁捐銆佽兘鍔涙槧灏勩€佹櫤鑳戒綋娉ㄥ唽銆丄gent闆嗙兢璁捐銆佽兘鍔涘浘璋便€佽法琛屼笟澶嶇敤銆丄gent鑳藉姏鍗°€佹櫤鑳戒綋鍒嗙被銆傚綋鐢ㄦ埛宸叉槑纭渶姹傚拰棰嗗煙妯″瀷锛岄渶瑕佽璁″叿浣揂gent闆嗙兢鏂规鏃朵娇鐢ㄣ€?
---

# SRAO 鏅鸿兘浣撳浘璋辨瀯寤哄櫒 v2.0

> **鏍稿績浠诲姟**锛氬皢SRM闇€姹傛媶瑙ｄ负鍘熷瓙浠诲姟DAG锛屾槧灏勪负鏍囧噯鍖栫殑鍏被鏅鸿兘浣擄紝鏋勫缓瀹屾暣鐨凙gent鑳藉姏鍥捐氨銆?

鎵挎帴 `srao-domain-modeler` 鐨勯鍩熷缓妯″拰闇€姹傜粨鏋勫寲锛屽皢涓氬姟钃濆浘杞寲涓哄彲瀹炰緥鍖栫殑鏅鸿兘浣撻泦缇ゆ柟妗堛€?

---

## 涓€銆佸墠缃潯浠?

闇€鍏堝畬鎴?`srao-domain-modeler` 鐨勯鍩熷缓妯″拰闇€姹傜粨鏋勫寲锛岃幏寰?SRM 鏂囨。銆?
鑻ョ敤鎴风洿鎺ヤ娇鐢ㄦ湰 skill锛屽厛蹇€熻ˉ寤?SRM 鐨勫叧閿儴鍒嗭紙domain銆乬oals銆亀orkflow_ref銆乧onstraints锛夈€?

---

## 浜屻€佹牳蹇冩祦绋?

```
SRM鏂囨。 鈫?闃舵2: 浠诲姟鎷嗚В(DAG) 鈫?闃舵3: 鏅鸿兘浣撴槧灏?鈫?杈撳嚭Agent闆嗙兢钃濆浘
```

---

## 涓夈€侀樁娈?锛氫换鍔℃媶瑙?鈥?浠嶴RM鍒板師瀛怐AG

### 3.1 鎷嗚В浜斿師鍒?

| 鍘熷垯 | 瀹氫箟 | 楠岃瘉鏂规硶 |
|------|------|----------|
| **鍘熷瓙鎬?* | 姣忎釜浠诲姟鏈夋槑纭緭鍏?杈撳嚭锛屾棤娉曞啀缁嗗垎 | "杩欎釜浠诲姟杩樿兘鎷嗘垚涓や釜鍚楋紵" 鑻ヤ笉鑳解啋鍘熷瓙 |
| **鐙珛鎬?* | 浠诲姟闂翠粎閫氳繃鏁版嵁浼犻€掕€﹀悎锛屼笉渚濊禆鍐呴儴鐘舵€?| "涓や釜浠诲姟鑳界嫭绔嬪紑鍙戞祴璇曞悧锛? |
| **鍙苟琛?* | 鏍囨槑鍝簺浠诲姟鍙悓鏃舵墽琛岋紝鍝簺蹇呴』涓茶 | "A绛塀鐨勭粨鏋滆繕鏄彲浠ュ悓鏃跺仛锛? |
| **鍙害閲?* | 姣忎釜浠诲姟鏈夋垚鍔熸爣鍑嗭紙鍑嗙‘鐜囥€佸欢杩熴€佸悶鍚愶級 | "鎬庝箞鍒ゆ柇杩欎釜浠诲姟鍋氬緱濂戒笉濂斤紵" |
| **鍙檷绾?* | 姣忎釜浠诲姟鏈夐檷绾ф柟妗?| "濡傛灉杩欎釜Agent鎸備簡锛屾湁浠€涔堝閫夛紵" |

### 3.2 鎷嗚В姝ラ

```
1. 浠嶴RM鐨剋orkflow_ref鍑哄彂
   鈫?灏嗘爣鍑嗗伐浣滄祦妯℃澘鐨勬瘡涓楠ゅ睍寮€涓?-N涓師瀛愪换鍔?

2. 璇嗗埆浠诲姟闂翠緷璧栧叧绯?
   鈫?鏁版嵁渚濊禆锛圱2闇€瑕乀1鐨勮緭鍑烘暟鎹級
   鈫?鏉′欢渚濊禆锛堜粎褰揟1缁撴灉>闃堝€兼椂鎵嶆墽琛孴2锛?
   鈫?鏃堕棿渚濊禆锛圱2蹇呴』鍦═1涔嬪悗锛屼絾涓嶉渶瑕佹暟鎹級

3. 鏍囨敞骞惰缁?
   鈫?灏嗘墍鏈夋棤鐩镐簰渚濊禆鐨勪换鍔℃爣璁颁负鍚岀粍鍙苟琛?

4. 瀹氫箟I/O Schema
   鈫?姣忎釜鍘熷瓙浠诲姟鏄庣‘锛氳緭鍏ュ瓧娈靛悕+绫诲瀷+蹇呭～銆佽緭鍑哄瓧娈靛悕+绫诲瀷

5. 鏍囨敞SLA
   鈫?寤惰繜涓婇檺銆佸噯纭巼涓嬮檺銆佸悶鍚愰渶姹?
```

### 3.3 DAG 璇︾粏鏍煎紡

```yaml
task_dag:
  name: "{琛屼笟}-{鍦烘櫙}-DAG"
  description: "浠嶴RM REQ-{id}鎷嗚В鐨勪换鍔″浘"
  source_srm: "REQ-{id}"
  estimated_total_duration: "棰勪及鎬昏€楁椂锛堜覆琛岀疮鍔狅紝骞惰鍙杕ax锛?
  
  # ===== 鍘熷瓙浠诲姟瀹氫箟 =====
  tasks:
    - id: T1
      name: "鍘熷瓙浠诲姟鍚嶏紙涓枃锛?
      description: "鐢ㄤ竴鍙ヨ瘽璇存竻妤氳繖涓换鍔″仛浠€涔?
      category: "鎰熺煡/鍒嗘瀽/鍐崇瓥/鎵ц/浜や簰/缂栨帓"
      
      input_schema:
        field_1: 
          type: "string"
          required: true
          description: "瀛楁鍚箟鍜屾潵婧?
          example: "绀轰緥鍊?
        field_2:
          type: "number"
          required: false
          default: 0.85
          description: "闃堝€煎弬鏁?
      
      output_schema:
        result:
          type: "object"
          description: "杈撳嚭缁撴瀯璇存槑"
          fields:
            score: { type: "number", range: [0, 1], description: "缃俊搴﹀垎鏁? }
            label: { type: "string", description: "鍒嗙被鏍囩" }
            detail: { type: "object", description: "璇︾粏淇℃伅" }
      
      deps: []            # 鏃犱緷璧栵紝鍙珛鍗虫墽琛?
      parallel_group: "A"  # 鍚屼竴缁勭殑浠诲姟鍙苟琛屾墽琛?
      
      sla:
        p95_latency_ms: 5000
        accuracy_target: ">95%"
        expected_throughput: "100 req/min"
      
      downgrade_strategy: "鑻ュけ璐モ啋浣跨敤瑙勫垯寮曟搸闄嶇骇"
      
    - id: T2
      name: "鍚庣画浠诲姟"
      description: "杩欎釜浠诲姟渚濊禆T1鐨勭粨鏋?
      deps: [T1]
      parallel_group: null
      input_schema:
        upstream_result: { type: "object", required: true, description: "鏉ヨ嚜T1鐨勮緭鍑? }
      output_schema:
        analysis: { type: "object", description: "鍒嗘瀽缁撴灉" }
      
    - id: T3
      name: "骞惰浠诲姟"
      description: "涓嶵2鍚屾椂鎵ц"
      deps: [T1]           # 涓嶵2骞惰锛岄兘渚濊禆T1
      parallel_group: "A"  # 鍚岀粍锛?
      
  # ===== 鏉′欢鍒嗘敮 =====
  branches:
    - id: BR-1
      condition: "T2.output.analysis.severity == 'critical'"
      then: [T4]            # 涓ラ噸鈫掕繘鍏ョ揣鎬ュ缃?
      else: [T5]            # 涓€鑸啋杩涘叆甯歌娴佺▼
      description: "鏍规嵁鍒嗘瀽缁撴灉鐨勪弗閲嶇▼搴﹂€夋嫨涓嶅悓鍚庣画璺緞"
  
  # ===== 骞惰缁勫畾涔?=====
  parallel_groups:
    A:
      description: "鍙苟琛岀殑鍒嗘瀽浠诲姟缁?
      max_concurrency: 5    # 鏈€澶у苟琛屾暟
      timeout_ms: 30000     # 缁勮秴鏃?
```

### 3.4 鎷嗚В瀹炴垬锛氬埗閫犱笟璁㈠崟鎺掍骇

```
SRM 鈫?"灏嗗鎴疯鍗曡嚜鍔ㄦ帓浜у埌浜х嚎"

鎷嗚В缁撴灉锛?
  T1: 璁㈠崟瑙ｆ瀽Agent
      杈撳叆: 璁㈠崟PDF/缁撴瀯鍖栨暟鎹?
      杈撳嚭: { 浜у搧鍨嬪彿, 鏁伴噺, 浜ゆ湡, 鐗规畩瑕佹眰 }
      
  T2: 搴撳瓨妫€鏌gent (骞惰缁凙)
      杈撳叆: { 浜у搧鍨嬪彿 鈫?鐗╂枡鍒楄〃 }
      杈撳嚭: { 鐗╂枡鍙敤閲? 缂烘枡鍒楄〃 }
      
  T3: 浜ц兘璁＄畻Agent (骞惰缁凙锛屼笌T2骞惰)
      杈撳叆: { 浜у搧鍨嬪彿 }
      杈撳嚭: { 鍚勪骇绾垮彲鐢ㄤ骇鑳? 棰勮宸ユ椂 }
      
  T4: 鎺掍骇浼樺寲Agent (绛塗2+T3)
      杈撳叆: { 鍙敤鐗╂枡, 鍙敤浜ц兘, 浜ゆ湡 }
      杈撳嚭: { 鎺ㄨ崘浜х嚎, 璁″垝寮€宸ユ椂闂? 棰勮瀹屽伐鏃堕棿 }
      
  T5: 宸ュ崟鐢熸垚Agent (绛塗4)
      杈撳叆: { 鎺掍骇缁撴灉 }
      杈撳嚭: { 宸ュ崟鍙? 涓嬪彂鐘舵€?}
      
  鍒嗘敮: 濡傛灉T2鍙戠幇缂烘枡 鈫?瑙﹀彂閲囪喘Agent (T6)
  鍒嗘敮: 濡傛灉T4鍙戠幇浜ц兘涓嶈冻 鈫?瑙﹀彂鍔犳€ヨ瘎浼癆gent (T7)
```

---

## 鍥涖€侀樁娈?锛氭櫤鑳戒綋鏄犲皠 鈥?鍏被鍒嗙被浣撶郴

### 4.1 鍏被鏅鸿兘浣撳畬鏁村畾涔?

| 绫诲埆 | 鍥炬爣 | 鏍稿績鑱岃矗 | 鍏稿瀷鑳藉姏 | 瀹炵幇鍊惧悜 | SLA瑕佹眰 |
|------|------|----------|----------|----------|---------|
| **鎰熺煡绫?* | 馃摗 | 鑾峰彇澶栭儴鏁版嵁 | 鍥惧儚/璇煶璇嗗埆銆両oT閲囬泦銆佸婧愯瀺鍚?| API+妯″瀷鎺ㄧ悊/杈圭紭璁＄畻 | 浣庡欢杩熴€侀珮鍚炲悙 |
| **鍒嗘瀽绫?* | 馃М | 璁＄畻銆佹帹鐞嗐€侀娴?| 浠跨湡妯℃嫙銆佹椂搴忛娴嬨€佺煡璇嗘帹鐞嗐€佺粺璁?| Python+ML/绉戝璁＄畻 | 璁＄畻瀵嗛泦銆佸彲鎺掗槦 |
| **鍐崇瓥绫?* | 馃幆 | 缁欏嚭寤鸿鎴栬嚜鍔ㄨ鍔?| 闃堝€煎垽鏂€佽矾寰勮鍒掋€佽祫婧愯皟閰嶃€佷紭鍏堢骇鎺掑簭 | 瑙勫垯寮曟搸+LLM+杩愮 | 鍙В閲娿€佸彲瀹¤ |
| **鎵ц绫?* | 鈿?| 鎿嶆帶纭欢鎴栬蒋浠?| 璁惧鎺у埗銆侀偖浠跺彂閫併€佹暟鎹簱鍐欏叆銆丄PI璋冪敤 | SDK+CLI+鍗忚閫傞厤 | 楂樺彲闈犮€佷簨鍔℃€?|
| **浜や簰绫?* | 馃挰 | 鐢ㄦ埛/绯荤粺閫氫俊 | 瀵硅瘽銆佹姤琛ㄣ€佸彲瑙嗗寲銆侀€氱煡鎺ㄩ€併€丄PI缃戝叧 | LLM+妯℃澘+WebSocket | 浣庡欢杩熴€佸娓犻亾 |
| **缂栨帓绫?* | 馃幖 | 绠＄悊鍏朵粬鏅鸿兘浣?| 宸ヤ綔娴佽皟搴︺€佺洃鎺с€佸閿欏垏鎹€佺増鏈鐞?| 鐘舵€佹満+閲嶈瘯+DAG寮曟搸 | 楂樺彲鐢ㄣ€佹寔涔呭寲 |

### 4.2 璺ㄨ涓氭櫤鑳戒綋澶嶇敤鐭╅樀

**杩欐槸鏈琒kill鐨勬牳蹇冧环鍊?*鈥斺€旇瘑鍒凡鍦ㄥ叾浠栬涓氶獙璇佽繃鐨勯€氱敤Agent锛岀洿鎺ュ鐢ㄨ€岄潪閲嶆柊寮€鍙戯細

| 閫氱敤Agent | 鍒堕€犱笟搴旂敤 | 鑳芥簮搴旂敤 | 鍖荤枟搴旂敤 | 鍐滀笟搴旂敤 | 浜ら€氬簲鐢?|
|-----------|-----------|----------|----------|----------|----------|
| 馃柤锔?**鍥惧儚缂洪櫡妫€娴?* | 浜х嚎璐ㄦ | 鍙剁墖瑁傜汗 | 鑲虹粨鑺?| 鐥呮枒璇嗗埆 | 闅ч亾瑁傜紳 |
| 馃搳 **鏃跺簭寮傚父妫€娴?* | 璁惧鎸姩 | 椋庢満鐘舵€?| 蹇冪數寮傚父 | 鐜绐佸彉 | 鍥村博褰㈠彉 |
| 馃椇锔?**璺緞瑙勫垝** | AGV璋冨害 | 鏃犱汉鏈鸿埅绾?| 鎵嬫湳瀵艰埅 | 鍐滄満璺緞 | 搴旀€ヨ矾绾?|
| 馃搱 **瓒嬪娍棰勬祴** | 璁惧瀵垮懡 | 鍙戠數鍔熺巼 | 鐥呮儏杩涘睍 | 浜ч噺棰勬祴 | 褰㈠彉閫熺巼 |
| 馃敂 **閫氱煡鎺ㄩ€?* | 浜х嚎鍛婅 | 棰勮鍙戝竷 | 鍗辨€ュ€?| 鏂借嵂鎻愰啋 | 绱ф€ュ箍鎾?|
| 馃摑 **鎶ュ憡鐢熸垚** | 璐ㄦ鎶ュ憡 | 杩愯鏈堟姤 | 璇婃柇鎶ュ憡 | 浜ч噺鎶ヨ〃 | 瀹夊叏璇勪及 |
| 馃攳 **鐭ヨ瘑妫€绱?* | 缁翠慨鎵嬪唽 | 杩愮淮瑙勭▼ | 涓村簥鎸囧崡 | 妞嶄繚鐭ヨ瘑 | 搴旀€ラ妗?|

### 4.3 鑳藉姏缁勫悎妯″紡

閫氳繃缂栨帓灏嗙畝鍗旳gent缁勫悎鎴愬鏉傛妧鑳斤細

```
"娑堥槻宸℃" = 鐑垚鍍忓紓甯告娴?+ 璁炬柦缂烘崯璇嗗埆 + 浜哄憳瀹氫綅 + 杞借嵎鎺у埗

"鏅鸿兘鎺掍骇" = 璁㈠崟瑙ｆ瀽 + 搴撳瓨妫€鏌?+ 浜ц兘璁＄畻 + 鎺掍骇浼樺寲 + 宸ュ崟鐢熸垚

"绮惧噯鏂借嵂" = 鐥呰櫕璇嗗埆 + 鎵╂暎棰勬祴 + 鍓傞噺璁＄畻 + 鑸嚎瑙勫垝 + 鎵ц鍠锋磼
```

### 4.4 Agent 鑳藉姏鍗★紙鏍囧噯鏍煎紡锛?

```yaml
agent_card:
  id: "AGT-{琛屼笟缂╁啓}-{搴忓彿}"
  name: "Agent涓枃鍚嶇О"
  category: "鎰熺煡/鍒嗘瀽/鍐崇瓥/鎵ц/浜や簰/缂栨帓"
  
  # ===== 鏍稿績鑳藉姏 =====
  capability: |
    鐢ㄤ竴鍙ヨ瘽鎻忚堪璇gent鐨勬牳蹇冭兘鍔?
  detail: |
    璇︾粏璇存槑杩欎釜Agent鑳藉仛浠€涔堛€佷笉鑳藉仛浠€涔堛€佽竟鐣屽湪鍝?
  
  # ===== 鎺ュ彛瀹氫箟 =====
  input:
    format: "json"
    schema:
      field_1: { type: "string", required: true, desc: "瀛楁璇存槑", example: "example_value" }
      field_2: { type: "number", required: false, desc: "瀛楁璇存槑", default: 0.5 }
  
  output:
    format: "json"
    schema:
      result: { type: "object", desc: "杩斿洖缁撴灉" }
      status: { type: "enum", values: ["success", "failure", "pending"], desc: "鎵ц鐘舵€? }
      metrics: { type: "object", desc: "鎵ц鎸囨爣" }
  
  # ===== 瀹炵幇鏂规 =====
  implementation:
    type: "api_call | python_script | llm_chain | rule_engine | human_in_loop | containerized_service"
    language: "Python/Go/TypeScript"
    framework: "FastAPI/Flask/gRPC"
    dependencies: ["渚濊禆搴?==1.0.0", "渚濊禆搴?"]
    model_requirements: "濡傞渶瑕侊細妯″瀷鍚嶇О銆佹樉瀛樸€佹帹鐞嗗欢杩?
    hardware_requirements: "濡傞渶瑕侊細GPU鍨嬪彿銆丆PU鏍稿績鏁?
  
  # ===== SLA =====
  sla:
    p95_latency_ms: 5000
    p99_latency_ms: 10000
    availability_target: "99.9%"
    accuracy_target: ">95%"
    max_retry_count: 3
  
  # ===== 瀹归敊 =====
  fallback:
    strategy: "degrade | alternate_agent | human_escalation | skip"
    alternate_agent_id: "AGT-xxx"   # 澶囩敤Agent
    human_escalation:
      webhook_url: "https://..."
      expected_response_time: "5min"
  
  # ===== 澶嶇敤鎬?=====
  reusability:
    cross_industry: true/false
    applicable_industries: ["鍒堕€犱笟", "鑳芥簮", "浜ら€?]
    adaptation_effort: "low|medium|high"
    adaptation_notes: "閫傞厤鍏朵粬琛屼笟闇€瑕佽皟鏁村摢浜涘弬鏁?閰嶇疆"
  
  # ===== 鏇夸唬鏂规 =====
  alternatives:
    - name: "鍟嗕笟浜у搧鏇夸唬"
      vendor: "鍘傚晢鍚?
      tradeoff: "浼樺娍/鍔ｅ娍瀵规瘮"
    - name: "寮€婧愭浛浠?
      repo: "github.com/xxx"
      tradeoff: "鎴愮啛搴?绀惧尯娲昏穬搴﹀姣?
```

### 4.5 鏄犲皠姝ラ锛堟寜椤哄簭鎵ц锛?

```
姝ラ1: 閫愪换鍔″垎绫?
  灏嗘瘡涓師瀛愪换鍔℃槧灏勫埌鍏被涔嬩竴
  鈫?闂細杩欎釜浠诲姟涓昏鍋氫粈涔堬紵
  鈫?鑾峰彇鏁版嵁鈫掓劅鐭?| 璁＄畻鎺ㄧ悊鈫掑垎鏋?| 鍒ゆ柇鍐崇瓥鈫掑喅绛?
    | 鎿嶆帶鎵ц鈫掓墽琛?| 杩斿洖鐢ㄦ埛鈫掍氦浜?| 绠＄悊Agent鈫掔紪鎺?

姝ラ2: 鑱氬悎妫€鏌?
  鍚屼竴绫诲埆鐨勪换鍔℃槸鍚﹀彲浠ュ悎骞朵负涓€涓狝gent锛?
  鈫?鍚堝苟鍘熷垯锛氬鏋淚/O鐩镐技銆佸疄鐜版柟寮忕浉鍚屸啋鍚堝苟
  鈫?鎷嗗垎鍘熷垯锛氬鏋淪LA瑕佹眰涓嶅悓銆侀渶瑕佺嫭绔嬫墿缂╁鈫掑垎寮€

姝ラ3: 澶嶇敤浼樺厛
  鍦ㄨ法琛屼笟澶嶇敤鐭╅樀涓煡鎵炬槸鍚︽湁鍙鐢ㄧ殑Agent
  鈫?瀹屽叏鍖归厤鈫掔洿鎺ュ紩鐢?
  鈫?閮ㄥ垎鍖归厤鈫掓爣璁?adaptation_effort
  鈫?鏃犲尮閰嶁啋鏂板缓

姝ラ4: 鑳藉姏鍗″～鍐?
  涓烘瘡涓狝gent锛堟柊寤?澶嶇敤锛夌敓鎴愬畬鏁磋兘鍔涘崱

姝ラ5: 鍥捐氨杩炵嚎
  寤虹珛Agent闂寸殑鏁版嵁娴佸拰鎺у埗娴?
  鈫?鏁版嵁娴侊細A鐨勮緭鍑?鈫?B鐨勮緭鍏?
  鈫?鎺у埗娴侊細A瑙﹀彂B鎵ц锛圔涓嶄緷璧朅鐨勬暟鎹級
  鈫?浜嬩欢娴侊細A鐩戝惉B鐨勪簨浠?

姝ラ6: 璺ㄨ涓氭爣娉?
  鏍囪鍝簺Agent鍙法琛屼笟澶嶇敤锛屽～鍐?reusability 瀛楁
```

---

## 浜斻€佹櫤鑳戒綋鍥捐氨鍙鍖?

### 5.1 閭绘帴鍏崇郴锛堝彲鐢ㄤ簬Neo4j锛?

```yaml
agent_graph:
  name: "{琛屼笟}-{鍦烘櫙}-Agent鍥捐氨"
  nodes:
    - id: "AGT-MFG-001"
      name: "璁㈠崟瑙ｆ瀽Agent"
      category: "鎰熺煡"
      mapped_tasks: [T1]
      reusability: { cross_industry: true, industries: ["鎵€鏈夎涓?] }
      
    - id: "AGT-MFG-002"
      name: "搴撳瓨妫€鏌gent"
      category: "鎵ц"
      mapped_tasks: [T2]
      implementation: "璋冪敤ERP搴撳瓨API"
      
    - id: "AGT-MFG-003"
      name: "浜ц兘璁＄畻Agent"
      category: "鍒嗘瀽"
      mapped_tasks: [T3]
      
    - id: "AGT-MFG-004"
      name: "鎺掍骇浼樺寲Agent"
      category: "鍐崇瓥"
      mapped_tasks: [T4]
      
    - id: "AGT-MFG-005"
      name: "宸ュ崟鐢熸垚Agent"
      category: "鎵ц"
      mapped_tasks: [T5]
  
  edges:
    - from: "AGT-MFG-001"
      to: ["AGT-MFG-002", "AGT-MFG-003"]
      type: "data_flow"
      payload: "瑙ｆ瀽鍚庣殑璁㈠崟鏁版嵁"
      
    - from: "AGT-MFG-002"
      to: "AGT-MFG-004"
      type: "data_flow"
      payload: "搴撳瓨鍙敤閲?
      
    - from: "AGT-MFG-003"
      to: "AGT-MFG-004"
      type: "data_flow"
      payload: "浜ц兘鏁版嵁"
      
    - from: "AGT-MFG-004"
      to: "AGT-MFG-005"
      type: "control_flow"
      condition: "鎺掍骇鎴愬姛鈫掔敓鎴愬伐鍗?
```

### 5.2 Mermaid 鍙鍖?

```
graph TD
    A1[馃摗 璁㈠崟瑙ｆ瀽Agent<br/>鎰熺煡绫籡 --> A2[鈿?搴撳瓨妫€鏌gent<br/>鎵ц绫籡
    A1 --> A3[馃М 浜ц兘璁＄畻Agent<br/>鍒嗘瀽绫籡
    A2 --> A4[馃幆 鎺掍骇浼樺寲Agent<br/>鍐崇瓥绫籡
    A3 --> A4
    A4 -->|鎺掍骇鎴愬姛| A5[鈿?宸ュ崟鐢熸垚Agent<br/>鎵ц绫籡
    A4 -->|浜ц兘涓嶈冻| A6[馃幆 鍔犳€ヨ瘎浼癆gent<br/>鍐崇瓥绫籡
    A2 -->|缂烘枡| A7[鈿?閲囪喘瑙﹀彂Agent<br/>鎵ц绫籡
```

---

## 鍏€佽法琛屼笟Agent澶嶇敤瀹炴垬

### 6.1 澶嶇敤妫€娴嬫祦绋?

```
鏂板満鏅疉gent闇€姹?
    鈹?
    鈻?
鍦ㄥ鐢ㄧ煩闃典腑鎼滅储鐩稿悓绫诲瀷鐨凙gent
    鈹?
    鈹溾攢 鎵惧埌瀹屽叏鍖归厤 鈫?鐩存帴寮曠敤锛堣妭鐪?00%寮€鍙戦噺锛?
    鈹?
    鈹溾攢 鎵惧埌杩戜技鍖归厤 鈫?璇勪及閫傞厤宸ヤ綔閲?
    鈹?    鈹溾攢 effort=low 鈫?璋冩暣閰嶇疆/闃堝€煎嵆鍙?
    鈹?    鈹溾攢 effort=medium 鈫?闇€淇敼鎺ュ彛/鏂板閫昏緫
    鈹?    鈹斺攢 effort=high 鈫?寤鸿鏂板缓
    鈹?
    鈹斺攢 鏃犲尮閰?鈫?鏂板缓Agent锛屽姞鍏ュ鐢ㄧ煩闃?
```

### 6.2 瀹為檯澶嶇敤妗堜緥

**妗堜緥锛氬浘鍍忕己闄锋娴婣gent 璺ㄨ涓氬鐢?*

```
鍩虹鑳藉姏锛氭帴鏀跺浘鍍?鈫?妫€娴嬪紓甯稿尯鍩?鈫?杈撳嚭缂洪櫡浣嶇疆+绫诲瀷+缃俊搴?

鍒堕€犱笟锛堜骇绾胯川妫€锛夛細
  - 杈撳叆锛氫骇绾挎媿鎽勭殑浜у搧楂樻竻鍥?
  - 閫傞厤锛氳缁冧笉鍚屼骇鍝佸瀷鍙风殑妫€娴嬫ā鍨?
  - 杈撳嚭锛氱己闄锋爣绛撅紙鍒掔棔/鍑归櫡/鑹插樊锛? 浣嶇疆鍧愭爣

鑳芥簮锛堥鏈哄彾鐗囧贰妫€锛夛細
  - 杈撳叆锛氭棤浜烘満鎷嶆憚鐨勫彾鐗囩孩澶?鍙鍏夊浘
  - 閫傞厤锛氬鍔犵孩澶栭€氶亾澶勭悊 + 鍙剁墖瑁傜汗涓撶敤妯″瀷
  - 杈撳嚭锛氳绾?鑴辫兌/鑵愯殌 绫诲瀷+闈㈢Н+浣嶇疆

浜ら€氾紙闅ч亾瑁傜紳妫€娴嬶級锛?
  - 杈撳叆锛氶毀閬撳闈㈠睍寮€鍥撅紙鎷兼帴鍚庯級
  - 閫傞厤锛氳皟鏁磋緭鍏ヤ负楂樺垎杈ㄧ巼鎷兼帴鍥?+ 瑁傜紳瀹藉害璁＄畻
  - 杈撳嚭锛氳缂濆潗鏍?瀹藉害+璧板悜+鍙樺寲瓒嬪娍

鈫?鏍稿績AI鑳藉姏瀹屽叏澶嶇敤锛屼粎闇€閫傞厤锛氳緭鍏ラ澶勭悊 + 妯″瀷寰皟 + 杈撳嚭鏍煎紡鍖?
鈫?澶嶇敤绋嬪害锛?0%锛岄€傞厤宸ヤ綔閲忥細medium锛堢害2鍛級
```

---

## 涓冦€佹櫤鑳戒綋娉ㄥ唽涓績璁捐

### 7.1 鍏冩暟鎹ā鍨?

```yaml
agent_registry_entry:
  agent_id: "AGT-MFG-001"
  name: "璁㈠崟瑙ｆ瀽Agent"
  category: "鎰熺煡"
  version: "1.2.0"
  status: "active | deprecated | testing"
  
  # 鏈嶅姟鍙戠幇
  endpoints:
    health: "GET /health"
    execute: "POST /agent/AGT-MFG-001/execute"
    metrics: "GET /agent/AGT-MFG-001/metrics"
  
  # 杩愯鏃?
  deployment:
    type: "container | serverless | edge"
    replicas: 3
    resources: { cpu: "2", memory: "4Gi", gpu: "T4" }
    
  # 渚濊禆
  dependencies:
    services: ["redis://cache:6379", "erp-api"]
    models: ["token-classifier-v2.pt"]
    
  # 娉ㄥ唽涓績
  registry:
    type: "consul | etcd | kubernetes_service"
    tags: ["order-processing", "nlp", "manufacturing"]
    health_check: "http://localhost:8000/health"
    health_check_interval_sec: 10
```

---

## 鍏€佷氦浠樼墿妫€鏌ユ竻鍗?

Agent鍥捐氨鏋勫缓瀹屾垚鍚庯紝纭浠ヤ笅杈撳嚭榻愬叏锛?

- [ ] 瀹屾暣鐨勫師瀛愪换鍔AG锛堝惈渚濊禆鍏崇郴銆佸苟琛岀粍銆佹潯浠跺垎鏀級
- [ ] 姣忎釜鍘熷瓙浠诲姟鐨処/O Schema锛堝惈瀛楁绫诲瀷銆佸繀濉€佺ず渚嬪€硷級
- [ ] 鍏ㄩ儴Agent鑳藉姏鍗★紙鍏被鏍囨敞銆佹帴鍙ｅ畾涔夈€丼LA銆佸閿欐柟妗堬級
- [ ] Agent鍥捐氨閭绘帴鍏崇郴锛堟暟鎹祦 + 鎺у埗娴侊級
- [ ] Mermaid鍙鍖栧浘锛堝彲鐩存帴宓屽叆README锛?
- [ ] 璺ㄨ涓氬鐢ㄥ垎鏋愭姤鍛婏紙鍝簺鍙鐢ㄣ€佸摢浜涢渶鏂板缓銆侀€傞厤宸ヤ綔閲忥級
- [ ] Agent娉ㄥ唽淇℃伅锛堟湇鍔″彂鐜般€侀儴缃查厤缃級

---

## 涔濄€佷笌鍏朵粬Skill鐨勫崗浣?

```
srao-domain-modeler 鈫?浜у嚭: SRM + 棰嗗煙妯″瀷 + 宸ヤ綔娴佹ā鏉?
                              鈹?
                              鈻?
     鏈琒kill (srao-agent-graph) 鈫?浜у嚭: task_dag + agent_cards + agent_graph
                              鈹?
                              鈻?
srao-workflow-orchestrator 鈫?浜у嚭: 鍙墽琛孌AG浠ｇ爜 + 鐩戞帶闈㈡澘 + 鍙嶉闂幆
```

鑻ョ敤鎴烽渶瑕佸皢鍥捐氨钀藉湴涓哄彲鎵ц鐨勫伐浣滄祦锛屽紩瀵间娇鐢?`srao-workflow-orchestrator` skill銆?
