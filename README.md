# 🚗 자율주행 AI 윤리적 딜레마 분석 (Moral Machine Analysis)

### "자율주행차의 브레이크가 고장 났을 때, AI는 누구를 살려야 할까?"
MIT Moral Machine 대규모 데이터를 활용하여 문화권별(동양 vs 서양) 윤리적 판단 기준의 차이를 분석하고, 자율주행 AI의 로컬라이제이션(Localization) 필요성을 제안한 데이터 분석 프로젝트입니다.

---

## 📊 1. 프로젝트 개요
- **프로젝트명:** 자율주행 AI 윤리 판단 기준의 문화적 차이 분석
- **수행 기간:** 2025.11 (인하공업전문대학 3학년 프로젝트)
- **데이터 출처:** [MIT Moral Machine Dataset (OSF)](https://osf.io/3hbt7/)
- **기술 스택:**
  - **Language:** Python
  - **Data Processing:** Pandas, NumPy (Data Cleaning, Mapping, Min-Max Scaling)
  - **Visualization:** Matplotlib, Plotly Express
- **개발 환경:** Google Colab, Jupyter Notebook
- ## 📄 프로젝트 결과물
* [📊 발표 자료 (PDF)](./presentation.pdf)
* [📄 최종 보고서 (PDF)](./final_report.pdf)

---

## 🛠 2. 데이터 구축 (Data Pipeline)
본 프로젝트는 MIT에서 제공하는 원본 데이터(`CountriesChangePr.csv.tar.gz`)를 직접 수집 및 가공하여 분석에 활용했습니다.

### **Step 1. 데이터 수집 (Collection)**
- OSF 저장소에서 국가별 통계 데이터 원본(`tar.gz`) 수집
- 전 세계 130여 개국 데이터 중 신뢰도가 확보된 **주요 52개국 선별**

### **Step 2. 데이터 전처리 (Preprocessing)**
- **매핑(Mapping):** 논문용 복잡한 변수명(`utilitarian`, `law` 등)을 직관적인 분석 용어(`save_many`, `compliance`)로 변경
- **파생 변수 생성:** 원본에 없는 '노인 선호(Save Elderly)' 지표를 역산하여 생성
- **정규화(Normalization):** 서로 다른 척도를 가진 데이터를 비교 가능하도록 **Min-Max Scaling** 기법을 적용하여 0~1 사이 값으로 통일

---

## 🔍 3. 분석 내용 및 시각화

### ① [거시 분석] 전 세계 윤리적 성향 분포
전 세계 50여 개국의 **'젊은이 선호(Save Young)'** 경향을 지도에 시각화하여 동서양의 차이를 확인했습니다.
![Map](https://github.com/user-attachments/assets/16bb5b04-e0a1-490e-8385-3a69fac27413)
> **인사이트:** > - **서구권(Blue Zone):** 미국, 유럽 등은 '남은 수명(Young)'과 '미래 가치'를 중시하는 경향이 뚜렷함.
> - **동양권(Red Zone):** 한국, 아시아 등은 상대적으로 이를 덜 중요시하며, 다른 가치(규범, 어른 공경)가 개입됨.

<br>

### ② [중간 분석] 핵심 분석 대상 선정 (Target Selection)
시장 규모와 데이터 특성을 고려하여 동/서양을 대표하는 핵심 국가를 선정했습니다.
![Champions](https://github.com/user-attachments/assets/7447e110-1afe-4ee2-825a-c91e4603f8b0)
> **선정 근거:** > - **미국(USA):** 세계 최대 자율주행 시장이자, 서구권의 보편적 윤리관(젊은이 선호 0.52)을 대변하는 표준 시장.
> - **대한민국(KOR):** 기술 도입의 타겟 시장이자, 동양권 중에서도 '법규 준수(Compliance)' 성향이 최상위권(0.46)인 규범 중심 국가.

<br>

### ③ [미시 분석] 대한민국 vs 미국 상세 비교
가장 대조적인 두 국가(한국 vs 미국)의 5대 핵심 윤리 지표를 상세 비교했습니다.
![Butterfly](https://github.com/user-attachments/assets/e3f80c52-b8cc-4982-b08f-a73ffe3b29c5)
> **결론:** > - **🇺🇸 미국 (효율과 균형):** 위급 상황에서 전체적인 희생을 줄이고 효율성을 추구하는 합리적 성향.
> - **🇰🇷 대한민국 (규범과 질서):** "법을 어긴 보행자는 보호받지 못한다"는 인식이 강하며, 사회적 합의와 규범을 최우선시함.

---

## 💡 4. 최종 결론 및 제언
**"윤리에 정답은 없다. 하지만 문화적 정답은 있다."**

데이터 분석 결과, 전 세계를 관통하는 단 하나의 'Global One-Model' 알고리즘은 존재하지 않음이 증명되었습니다. 서구권 데이터를 학습한 AI를 한국에 그대로 도입할 경우, 사회적 거부감과 법적 분쟁이 발생할 수 있습니다.

따라서 자율주행차 제조사는 **출시 국가의 문화적 특성(Culture-Fit)** 을 반영한 **'윤리적 알고리즘 옵션(Ethical Knob)'** 을 제공하여 기술의 사회적 수용성을 높여야 합니다.

---

## 📂 폴더 구조

```bash
Moral-Machine-Analysis
├── data         # 원본 및 전처리된 데이터셋 (CSV 파일)
├── notebooks    # 데이터 전처리 및 시각화 소스 코드 (.ipynb)
├── results      # 시각화 결과 이미지 (지도, 차트 PNG 파일)
└── README.md    # 프로젝트 포트폴리오 문서
```
