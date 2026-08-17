# Lab 17 Golden Set Report

- Implementation: `student`
- Kind: `golden`
- Cases: **20**
- Passed: **20/20**
- Evidence hit rate: **100.0%**
- Average retrieval latency: **1533.8 ms**
- Average token reduction vs full source context: **6.3%**
- Golden bonus: **10/10** (100% required)

| Case | Layer | Pass | Latency ms | Retrieved tokens | Token reduction | Missing / Error |
| --- | --- | --- | ---: | ---: | ---: | --- |
| G01 | short_term | PASS | 0.2 | 227 | 0.0% |  |
| G02 | short_term | PASS | 0.0 | 133 | 0.0% |  |
| G08 | long_term | PASS | 10987.3 | 608 | 0.0% |  |
| G09 | long_term | PASS | 1114.1 | 785 | 0.0% |  |
| G12 | semantic | PASS | 257.7 | 418 | 8.9% |  |
| G14 | semantic | PASS | 258.6 | 270 | 30.2% |  |
| G15 | semantic | PASS | 274.1 | 270 | 41.2% |  |
| G19 | mixed | PASS | 1941.8 | 581 | 0.0% |  |
| G03 | long_term | PASS | 3273.5 | 776 | 0.0% |  |
| G04 | long_term | PASS | 1326.5 | 785 | 0.0% |  |
| G05 | long_term | PASS | 1393.6 | 775 | 0.0% |  |
| G10 | episodic | PASS | 347.3 | 223 | 0.0% |  |
| G11 | episodic | PASS | 276.8 | 250 | 0.0% |  |
| G13 | semantic | PASS | 394.2 | 416 | 26.4% |  |
| G16 | mixed | PASS | 1735.8 | 581 | 0.0% |  |
| G18 | mixed | PASS | 613.3 | 500 | 11.5% |  |
| G20 | mixed | PASS | 1698.0 | 820 | 0.0% |  |
| G06 | long_term | PASS | 1251.7 | 787 | 0.0% |  |
| G07 | long_term | PASS | 1295.1 | 773 | 0.0% |  |
| G17 | mixed | PASS | 2237.1 | 581 | 8.1% |  |

## Evidence excerpts

### G01 - short_term

`<SESSION_SUMMARY> user: Constraint HOLD-ALPHA-0900: standup is 09:00 sharp and must not be forgotten. | assistant: Noted standup constraint. | user: Constraint HOLD-BETA-STAGING: writes go to staging DB only. | assistant: Noted staging constraint. | user: Filler A about button padding. | assistant: Filler A. | user: Filler B about color tokens. | assistant: Filler B. | user: Filler C about copy tone. | assistant: Filler C. </SESSION_SUMMARY> <DURABLE_NOTES> - user: Constraint HOLD-ALPHA-0900: standup is 09:00 sharp and must not be forgotten. - assistant: Noted standup constraint. - user: Constraint HOLD-BETA-STAGING: writes go to staging DB only. - assistant: Noted staging constraint. </DURA`

### G02 - short_term

`<RECENT_TURNS> user: Ten du an ca nhan cua toi la ORCHID-27. Toi thich Python va khong thich Java. Khi giai thich code, hay dung vi du ngan. assistant: Da hieu: demo ca nhan ORCHID-27, uu tien Python, tranh Java, vi du ngan. user: Toi dang hoc async/await va hay nham coroutine voi Task. Neu sau nay gap chu de nay, hay giai thich bang timeline. assistant: Toi se uu tien timeline khi giai thich coroutine va Task. user: TODO: hoan thanh benchmark report truoc thu Sau luc 16:00. Day la open loop LAB-REPORT-1600. </RECENT_TURNS>`

### G08 - long_term

`<USER_SUMMARY> Lan Tran prioritizes Java and Spring Boot for backend development and does not use Python. The user's project is LOTUS-88. </USER_SUMMARY>  <EPISODES> Episodes are source message or document excerpts shown in selection order.   - Created At: 2026-08-01 11:00:00     Source: message     Content: [user] {   "user_id": "lan-lab17",   "first_name": "Lan",   "last_name": "Tran",   "user_alias": "Lan Tran" }: Toi la Lan. Du an cua toi la LOTUS-88. Toi uu tien Java va Spring Boot, va khong dung Python trong vi du backend.   - Created At: 2026-08-01 11:00:20     Source: message     Content: Lab Assistant (assistant): Da hieu: LOTUS-88, Java + Spring Boot cho backend examples. </EPISODE`

### G09 - long_term

`<USER_SUMMARY> The user's personal project is named ORCHID-27 and they prefer Python for it. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used.  The user prefers Python and dislikes Java. They want code explanations to include brief examples. The user prefers Python for personal projects like ORCHID-27, but for the company project BLUEBIRD-42, the backend must use TypeScript with NestJS.  When explaining async/await and the difference between coroutines and Tasks, use a timeline format. The assistant will prioritize the timeline when explaining coroutines and Tasks. </USER_SUMMARY>  <EPISODES> Episodes are source message or documen`

### G12 - semantic

`EPISODE: {"id":"kb-payment-retry","entity":"Payment API Retry Policy","summary":"For POST /payments, every retryable request MUST send the same Idempotency-Key. Retry only HTTP 429 or transient 5xx errors, use exponential-backoff, and stop after max-3-retries. Marker: PAYMENT-RULE-3.","source":"internal-api-guideline-v3","updated_at":"2026-08-10T00:00:00Z"} metadata= EPISODE: For POST /payments, every retryable request MUST send the same Idempotency-Key. Retry only HTTP 429 or transient 5xx errors, use exponential-backoff, and stop after max-3-retries. Marker: PAYMENT-RULE-3. metadata= EPISODE: {"id":"kb-memory-privacy","entity":"Agent Memory Privacy Rule","summary":"Do not persist personal `

### G14 - semantic

`EPISODE: {"id":"kb-memory-privacy","entity":"Agent Memory Privacy Rule","summary":"Do not persist personal data without explicit opt-in. A deletion request must remove user-scoped memory and be verified across every store. Marker: DELETE-VERIFY-ALL.","source":"memory-governance-policy","updated_at":"2026-08-12T00:00:00Z"} metadata= EPISODE: Do not persist personal data without explicit opt-in. A deletion request must remove user-scoped memory and be verified across every store. Marker: DELETE-VERIFY-ALL. metadata= EPISODE: {"id":"kb-context-budget","entity":"Memory Context Budget","summary":"Reserve bounded context for memory. This lab uses short-term 10 percent, long-term 4 percent, episodi`

### G15 - semantic

`EPISODE: {"id":"kb-memory-privacy","entity":"Agent Memory Privacy Rule","summary":"Do not persist personal data without explicit opt-in. A deletion request must remove user-scoped memory and be verified across every store. Marker: DELETE-VERIFY-ALL.","source":"memory-governance-policy","updated_at":"2026-08-12T00:00:00Z"} metadata= EPISODE: Do not persist personal data without explicit opt-in. A deletion request must remove user-scoped memory and be verified across every store. Marker: DELETE-VERIFY-ALL. metadata= EPISODE: {"id":"kb-context-budget","entity":"Memory Context Budget","summary":"Reserve bounded context for memory. This lab uses short-term 10 percent, long-term 4 percent, episodi`

### G19 - mixed

`<LONG_TERM> <USER_SUMMARY> Lan Tran prioritizes Java and Spring Boot for backend development and does not use Python. The user's project is LOTUS-88. </USER_SUMMARY>  <EPISODES> Episodes are source message or document excerpts shown in selection order.   - Created At: 2026-08-01 11:00:00     Source: message     Content: [user] {   "user_id": "lan-lab17",   "first_name": "Lan",   "last_name": "Tran",   "user_alias": "Lan Tran" }: Toi la Lan. Du an cua toi la LOTUS-88. Toi uu tien Java va Spring Boot, va khong dung Python trong vi du backend.   - Created At: 2026-08-01 11:00:20     Source: message     Content: Lab Assistant (assistant): Da hieu: LOTUS-88, Java + Spring Boot cho backend example`

### G03 - long_term

`<USER_SUMMARY> The user's personal project is named ORCHID-27 and they prefer Python for it. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used.  The user prefers Python and dislikes Java. They want code explanations to include brief examples. The user prefers Python for personal projects like ORCHID-27, but for the company project BLUEBIRD-42, the backend must use TypeScript with NestJS.  When explaining async/await and the difference between coroutines and Tasks, use a timeline format. The assistant will prioritize the timeline when explaining coroutines and Tasks. </USER_SUMMARY>  <EPISODES> Episodes are source message or documen`

### G04 - long_term

`<USER_SUMMARY> The user's personal project is named ORCHID-27 and they prefer Python for it. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used.  The user prefers Python and dislikes Java. They want code explanations to include brief examples. The user prefers Python for personal projects like ORCHID-27, but for the company project BLUEBIRD-42, the backend must use TypeScript with NestJS.  When explaining async/await and the difference between coroutines and Tasks, use a timeline format. The assistant will prioritize the timeline when explaining coroutines and Tasks. </USER_SUMMARY>  <EPISODES> Episodes are source message or documen`

### G05 - long_term

`<USER_SUMMARY> The user's personal project is named ORCHID-27 and they prefer Python for it. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used.  The user prefers Python and dislikes Java. They want code explanations to include brief examples. The user prefers Python for personal projects like ORCHID-27, but for the company project BLUEBIRD-42, the backend must use TypeScript with NestJS.  When explaining async/await and the difference between coroutines and Tasks, use a timeline format. The assistant will prioritize the timeline when explaining coroutines and Tasks. </USER_SUMMARY>  <EPISODES> Episodes are source message or documen`

### G10 - episodic

`EPISODE: Hom nay toi debug async HTTP. Toi da thu tang timeout len 60s nhung van fail. EPISODE: Cach hieu qua la reuse aiohttp ClientSession va dat concurrency=20. Reflection: loi chinh la connection churn, khong phai timeout threshold. Ma su co ASYNC-FIX-20. EPISODE: Minh dang lam kiem ke lai mo hinh cac du an backend de bao cao, ma minh rat so cai vu bi gan nham du an cua nguoi khac vao ho so cua minh, chuyen do tung xay ra roi nen lan nay minh can cham. Ban liet EPISODE: Minh dang setup lai moi truong dev cho mot buoi ngoi code mot minh cuoi tuan nay, kieu khong co ai chung nhom, chi lam project rieng cua minh cho vui thoi. Truoc khi minh chon template va cai dependen EPISODE: Sang mai mi`

### G11 - episodic

`EPISODE: Cach hieu qua la reuse aiohttp ClientSession va dat concurrency=20. Reflection: loi chinh la connection churn, khong phai timeout threshold. Ma su co ASYNC-FIX-20. EPISODE: Cap nhat moi: voi du an cong ty BLUEBIRD-42, backend bat buoc dung TypeScript voi NestJS; khong dung Python cho backend du an nay. Preference Python van dung cho demo ca nhan ORCHID-27. EPISODE: Minh dang lam kiem ke lai mo hinh cac du an backend de bao cao, ma minh rat so cai vu bi gan nham du an cua nguoi khac vao ho so cua minh, chuyen do tung xay ra roi nen lan nay minh can cham. Ban liet EPISODE: Minh dang setup lai moi truong dev cho mot buoi ngoi code mot minh cuoi tuan nay, kieu khong co ai chung nhom, ch`

### G13 - semantic

`EPISODE: {"id":"kb-async-http","entity":"Async HTTP Incident Playbook","summary":"When async HTTP calls time out, inspect connection pooling, downstream saturation and concurrency before increasing timeout. Reuse a long-lived client session where possible. Marker: CONN-POOL-FIRST.","source":"incident-playbook-2026","updated_at":"2026-08-11T00:00:00Z"} metadata= EPISODE: When async HTTP calls time out, inspect connection pooling, downstream saturation and concurrency before increasing timeout. Reuse a long-lived client session where possible. Marker: CONN-POOL-FIRST. metadata= EPISODE: {"id":"kb-memory-privacy","entity":"Agent Memory Privacy Rule","summary":"Do not persist personal data witho`

### G16 - mixed

`<LONG_TERM> <USER_SUMMARY> The user's personal project is named ORCHID-27 and they prefer Python for it. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used.  The user prefers Python and dislikes Java. They want code explanations to include brief examples. The user prefers Python for personal projects like ORCHID-27, but for the company project BLUEBIRD-42, the backend must use TypeScript with NestJS.  When explaining async/await and the difference between coroutines and Tasks, use a timeline format. The assistant will prioritize the timeline when explaining coroutines and Tasks. </USER_SUMMARY>  <EPISODES> Episodes are source messag`

### G18 - mixed

`<EPISODIC> EPISODE: Cach hieu qua la reuse aiohttp ClientSession va dat concurrency=20. Reflection: loi chinh la connection churn, khong phai timeout threshold. Ma su co ASYNC-FIX-20. EPISODE: Minh dang lam kiem ke lai mo hinh cac du an backend de bao cao, ma minh rat so cai vu bi gan nham du an cua nguoi khac vao ho so cua minh, chuyen do tung xay ra roi nen lan nay minh can cham. Ban liet EPISODE: Minh dang setup lai moi truong dev cho mot buoi ngoi code mot minh cuoi tuan nay, kieu khong co ai chung nhom, chi lam project rieng cua minh cho vui thoi. Truoc khi minh chon template va cai dependen EPISODE: Sang mai minh phai hop review tien do voi mentor nen toi nay minh muon don dep lai het `

### G20 - mixed

`<LONG_TERM> <USER_SUMMARY> The user's personal project is named ORCHID-27 and they prefer Python for it. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used.  The user prefers Python and dislikes Java. They want code explanations to include brief examples. The user prefers Python for personal projects like ORCHID-27, but for the company project BLUEBIRD-42, the backend must use TypeScript with NestJS.  When explaining async/await and the difference between coroutines and Tasks, use a timeline format. The assistant will prioritize the timeline when explaining coroutines and Tasks. </USER_SUMMARY>  <EPISODES> Episodes are source messag`

### G06 - long_term

`<USER_SUMMARY> The user's personal project is named ORCHID-27 and they prefer Python for it. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used.  The user prefers Python and dislikes Java. They want code explanations to include brief examples. The user prefers Python for personal projects like ORCHID-27, but for the company project BLUEBIRD-42, the backend must use TypeScript with NestJS.  When explaining async/await and the difference between coroutines and Tasks, use a timeline format. The assistant will prioritize the timeline when explaining coroutines and Tasks. </USER_SUMMARY>  <EPISODES> Episodes are source message or documen`

### G07 - long_term

`<USER_SUMMARY> The user's personal project is named ORCHID-27 and they prefer Python for it. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used.  The user prefers Python and dislikes Java. They want code explanations to include brief examples. The user prefers Python for personal projects like ORCHID-27, but for the company project BLUEBIRD-42, the backend must use TypeScript with NestJS.  When explaining async/await and the difference between coroutines and Tasks, use a timeline format. The assistant will prioritize the timeline when explaining coroutines and Tasks. </USER_SUMMARY>  <EPISODES> Episodes are source message or documen`

### G17 - mixed

`<LONG_TERM> <USER_SUMMARY> The user's personal project is named ORCHID-27 and they prefer Python for it. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS, and Python is not to be used.  The user prefers Python and dislikes Java. They want code explanations to include brief examples. The user prefers Python for personal projects like ORCHID-27, but for the company project BLUEBIRD-42, the backend must use TypeScript with NestJS.  When explaining async/await and the difference between coroutines and Tasks, use a timeline format. The assistant will prioritize the timeline when explaining coroutines and Tasks. </USER_SUMMARY>  <EPISODES> Episodes are source messag`
