# 📈 StockWave - 주식 배당금 정보 플랫폼 💰

> 🎯 **한국 주식시장의 배당금 정보와 시세를 한눈에!** 📊

[![Java](https://img.shields.io/badge/Java-8+-orange?style=for-the-badge&logo=java)](https://www.java.com)
[![Servlet](https://img.shields.io/badge/Servlet-4.0-blue?style=for-the-badge)](https://javaee.github.io/servlet-spec/)
[![JSON](https://img.shields.io/badge/JSON-Server-green?style=for-the-badge&logo=json)](https://github.com/typicode/json-server)

---

## 🌟 프로젝트 소개

**StockWave**는 🇰🇷 한국 주식시장의 배당금 정보와 시세 정보를 실시간으로 조회할 수 있는 웹 애플리케이션입니다! 

### ✨ 프로젝트 기획 배경
- 📱 **실시간 정보**: 공공데이터 포털 API로 최신 정보 제공
- 💎 **배당금 계산**: 보유 주식의 예상 수익을 자동으로 계산
- 📅 **캘린더 기능**: 배당 일정을 한눈에 확인
- ⭐ **즐겨찾기**: 관심 종목을 쉽게 관리

---

## 📸 스크린샷

<table>
  <tr>
    <td align="center">
      <img src="screenshots/dividend-calculator.png" alt="예상 배당금 계산" width="100%"/>
      <br/>
      <b>💰 예상 배당금 계산</b><br/>
      <sub>보유 주식 수를 입력하면 예상 배당 수익을 자동으로 계산</sub>
    </td>
  </tr>
  <tr>
    <td align="center">
      <img src="screenshots/dividend-calendar.png" alt="배당락일 캘린더" width="100%"/>
      <br/>
      <b>📅 배당락일 캘린더</b><br/>
      <sub>월별 배당락일을 한눈에 확인할 수 있는 캘린더</sub>
    </td>
  </tr>
  <tr>
    <td align="center">
      <img src="screenshots/stock-info.png" alt="주식 시세 조회" width="100%"/>
      <br/>
      <b>📊 주식 시세 조회</b><br/>
      <sub>실시간 주식 정보 - 시가총액, 시가, 종가, 고가, 저가, 현재 시간</sub>
    </td>
  </tr>
</table>


## 🎨 주요 기능

### 📊 1. 주식 정보 조회
```
💹 시세 정보 - 시가, 종가, 고가, 저가, 시가총액
💵 배당 정보 - 배당 기준일, 지급일, 주당 배당금
```

### 💸 2. 배당금 계산기
```
🧮 보유 주식 수 입력 → 예상 배당 수익 자동 계산!
📈 최근 3개월 평균 기반 스마트 예측
```

### 📆 3. 배당 캘린더
```
🗓️ 올해 배당 지급 일정 확인
📍 월별 배당 현황 시각화
```

### ⭐ 4. 즐겨찾기 기능
```
❤️ 관심 종목 즐겨찾기 등록/해제
💾 JSON Server로 데이터 영속성 보장
```

---

## 🛠️ 기술 스택

### 🔧 Backend
| 기술 | 버전 | 설명 |
|------|------|------|
| ☕ **Java** | JDK 17 | 핵심 개발 언어 |
| 🌐 **Servlet/JSP** | 4.0 | 웹 애플리케이션 프레임워크 |


### 📚 Libraries
| 라이브러리 | 용도 |
|------------|------|
| 🚀 **OkHttp3** | HTTP 클라이언트 |
| 🔄 **Gson** | JSON 파싱 |
| 📄 **OpenCSV** | CSV 파일 처리 |
| 🔮 **Guava** | 유틸리티 기능 |

### 🌐 External APIs
- 🏢 **공공데이터포털 API**
  - 📈 주식 시세 정보 API
  - 💰 주식 배당금 정보 API
- 💾 **JSON Server** (로컬 데이터 저장)

---

## 📂 프로젝트 구조

```
🏗️ src/main/java/
┃
┣━━ 🎮 command/              ⟵ Command 패턴 구현
┃   ┣━━ 📋 AbstractStockDivi.java
┃   ┣━━ 📊 AbstractStockInfo.java
┃   ┣━━ 💾 AbstractStockJson.java
┃   ┣━━ 📅 StockCalendarCommand.java
┃   ┣━━ 📈 StockInfoCommand.java
┃   ┣━━ ⭐ StockLikePatchCommand.java
┃   ┣━━ 📜 StockListCommand.java
┃   ┗━━ 💰 StockRetainedCommand.java
┃
┣━━ 🎛️ controller/           ⟵ MVC 컨트롤러
┃   ┗━━ 🚦 StockWaveController.java
┃
┣━━ 🗃️ model/                ⟵ 데이터 모델
┃   ┣━━ 🔌 apiUtil/         
┃   ┃   ┣━━ 🔐 constant/ApiConstant.java
┃   ┃   ┣━━ 💵 StockDividendInfoAPI.java
┃   ┃   ┣━━ 📊 StockInfoAPI.java
┃   ┃   ┗━━ 💾 StockJsonAPI.java
┃   ┃
┃   ┣━━ 🗄️ dao/             
┃   ┃   ┣━━ 📁 impl/
┃   ┃   ┗━━ 📑 interfaces
┃   ┃
┃   ┣━━ ⚙️ service/         
┃   ┃   ┣━━ 🔧 impl/
┃   ┃   ┗━━ 📋 interfaces
┃   ┃
┃   ┗━━ 📦 vo/              
┃       ┣━━ 💰 StockDividendInfoVO.java
┃       ┣━━ 📈 StockInfoVO.java
┃       ┗━━ 💾 StockJsonVO.java
┃
┗━━ 🌐 servlet/             ⟵ 서블릿 (Legacy)
```

---

## ⚙️ 설정 방법

### 🔑 1. API 키 설정
`src/main/resources/api.properties` 파일 생성:
```properties
# 🔐 공공데이터포털 API 키
STOCK_KEY=your_api_key_here
```

### 💾 2. JSON Server 설치 및 실행
```bash
# 📦 JSON Server 설치
npm install -g json-server

# 🚀 JSON Server 실행
json-server --watch stock.json --port 3000
```


## 📡 API 엔드포인트

### 📊 주식 정보 조회
```http
GET /stockInfo.stockwave?name={종목명}
```
🔍 **예시**: `/stockInfo.stockwave?name=삼성전자`

### 📜 주식 리스트 조회
```http
GET /stockList.stockwave
```

### 💰 배당금 계산
```http
GET /stockRetained.stockwave?stockName={종목명}&stockCount={보유수량}
```
🔍 **예시**: `/stockRetained.stockwave?stockName=삼성전자&stockCount=100`

### 📅 배당 캘린더
```http
GET /stockCalendar.stockwave?itmsName={종목명}
```

### ⭐ 즐겨찾기 수정
```http
PATCH /stockLikePatch.stockwave
```
```json
{
  "stockId": "1",
  "isLike": true
}
```

---

## 🎯 주요 클래스 설명

### 🚦 StockWaveController
- ✅ 프론트 컨트롤러 패턴 구현
- ✅ URL 매핑을 통한 Command 객체 동적 생성
- ✅ `.stockwave` 확장자로 요청 처리

### 🔐 ApiConstant
- ✅ API 키 관리 및 HTTP 클라이언트 싱글톤
- ✅ API URL 상수 정의
- ✅ Properties 파일 자동 로딩

### 💸 StockRetainedCommand
- ✅ 배당금 계산 로직 구현
- ✅ 올해 배당 지급 현황 분석
- ✅ 예상 수익금 계산 (최근 3개월 평균)

---

## 📊 데이터 모델

### 💰 StockDividendInfoVO
| 필드명 | 타입 | 설명 |
|--------|------|------|
| 🏢 `isinCdNm` | String | 회사명 |
| 📅 `dvdnBasDt` | String | 배당기준일 |
| 💵 `cashDvdnPayDt` | String | 현금지급일 |
| 🎯 `stckDvdnRcdNm` | String | 배당 타입 |
| 💸 `stckGenrDvdnAmt` | String | 주당 배당금 |
| 📈 `stckGenrCashDvdnRt` | String | 현금배당률 |

### 📈 StockInfoVO
| 필드명 | 타입 | 설명 |
|--------|------|------|
| 💎 `mrktTotAmt` | String | 시가총액 |
| 🔑 `isinCd` | String | ISIN 코드 |
| 🌅 `mkp` | String | 시가 |
| 🌆 `clpr` | String | 종가 |
| ⬆️ `hipr` | String | 고가 |
| ⬇️ `lopr` | String | 저가 |


## 📝 API 응답 예시

### 📊 주식 정보 조회 응답
```json
{
  "mrktTotAmt": "28조 4728억원",
  "isinCd": "KR7035720002",
  "mkp": "63,000",
  "clpr": "64,400",
  "hipr": "65,200",
  "lopr": "63,000",
  "currentTime": "20:20:45"
}
```

### 💸 배당금 계산 응답
```json
{
  "company": "삼성전자",
  "stockCount": "97",
  "expectedDividend": "35,405원",
  "dividendHistory": {
    "2025": ["4월", "5월", "8월"]
  }
}
```

