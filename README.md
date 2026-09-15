# 🖼️ SCOP (Screen Capture On Python)

**Python을 기반으로 하는 오픈 소스 스크린 캡쳐 도구**

![Python](https://img.shields.io/badge/Python-3.x-blue)
![License](https://img.shields.io/badge/License-Apache%202.0-green)
![Platform](https://img.shields.io/badge/Platform-Windows%2011-success)

---

## 📝 개요

SCOP는 Python으로 작성된 간단하고 효율적인 스크린 캡쳐 프로그램입니다. PyQt5를 기반으로 한 직관적인 GUI와 단축키 기능을 제공하며, Windows 11 환경에서 최적화되어 있습니다.

**주요 기능:**
- 🎯 빠르고 간편한 스크린 캡쳐
- ⌨️ 커스터마이징 가능한 핫키 설정
- 🛠️ 사용자 정의 저장 경로 설정
- 🎨 PyQt5 기반의 사용하기 쉬운 인터페이스
- ⚙️ 설정 자동 저장 기능

---

## 🚀 설치 및 실행

### 필수 요구사항

Python 3.7 이상이 설치되어 있어야 합니다.

### 1단계: 패키지 설치

다음 명령어로 필요한 패키지를 설치하세요:

```bash
pip install keyboard pyautogui PyQt5
```

**패키지 설명:**
- `keyboard`: 핫키 감지
- `pyautogui`: 스크린 캡쳐 기능
- `PyQt5`: GUI 인터페이스

### 2단계: 프로그램 실행

```bash
# Python 콘솔을 표시하며 실행 (디버깅 시)
python SCOP.py

# 콘솔 없이 백그라운드에서 실행 (정상 사용)
pythonw SCOP.pyw
```

---

## ⚙️ PyQt5 플러그인 경로 설정

일부 Windows 11 환경에서는 PyQt5 플러그인을 찾지 못할 수 있습니다. 이 경우 다음과 같이 설정하세요:

### 자신의 Python 설치 경로 확인

```python
import sys
print(sys.executable)
# 예: C:\Users\YourName\AppData\Local\Programs\Python\Python313\python.exe
```

### SCOP.py (또는 SCOP.pyw) 파일 상단에 추가

```python
import os
import sys

# PyQt5 플러그인 경로 설정 (자신의 경로에 맞게 수정)
qt_plugin_path = r"C:\Users\YourName\AppData\Local\Programs\Python\Python313\Lib\site-packages\PyQt5\Qt5\plugins"
os.environ["QT_PLUGIN_PATH"] = qt_plugin_path
```

**참고:**
- `YourName`을 자신의 Windows 사용자명으로 변경하세요
- `Python313`을 설치된 Python 버전으로 변경하세요
- 정상 작동하면 위 코드는 주석 처리하거나 제거해도 됩니다

### 오류 발생 시 확인 방법

```bash
# .pyw 파일로 실행할 때 오류를 볼 수 없는 경우:
python SCOP.py  # .py 파일로 실행하여 콘솔에서 오류 메시지 확인
```

---

## 📖 사용 방법

### 기본 사용법

1. **프로그램 실행**
   - `pythonw SCOP.pyw` 실행
   - 시스템 트레이에 아이콘이 표시됩니다

2. **설정 열기**
   - 트레이 아이콘을 우클릭
   - "Settings" 선택

3. **핫키 설정**
   - 설정 창에서 원하는 핫키 입력
   - 예: `ctrl+shift+s`

4. **저장 경로 설정**
   - 설정 창에서 캡쳐 이미지가 저장될 폴더 선택

5. **캡쳐 실행**
   - 설정한 핫키 누르기
   - 이미지가 자동으로 설정된 경로에 저장됩니다

### 프로그램 종료

트레이 아이콘 → "Exit" 선택

---

## 🔧 프로젝트 구조

```
Screen_Capture_On_Python/
├── SCOP.py              # 메인 프로그램 (콘솔 표시)
├── SCOP.pyw             # 메인 프로그램 (콘솔 숨김)
├── README.md            # 프로젝트 문서
└── settings.json        # 설정 파일 (자동 생성)
```

---

## 🎯 향후 계획

- [ ] 영역 캡쳐 기능 (드래그로 영역 선택)
- [ ] 다양한 이미지 포맷 지원 (.png, .jpg, .bmp 등)
- [ ] 캡쳐 이후 편집 기능
- [ ] 클라우드 자동 업로드 기능
- [ ] 다국어 지원

---

## 📋 시스템 요구사항

- **OS**: Windows 11 (다른 버전은 테스트되지 않음)
- **Python**: 3.7 이상
- **메모리**: 최소 100MB

---

## 🤝 기여하기

이 프로젝트는 오픈 소스이며 자유롭게 수정하고 배포할 수 있습니다. 개선 사항이나 버그 리포트는 Issues를 통해 등록해주세요.

---

## 📄 라이선스

이 프로젝트는 [Apache License 2.0](LICENSE)을 따릅니다.

---

## ❓ 자주 묻는 질문 (FAQ)

**Q: MacOS나 Linux에서 사용 가능한가요?**  
A: 현재 Windows 11에서만 테스트되었습니다. 다른 OS에서 사용하려면 코드 수정이 필요할 수 있습니다.

**Q: 캡쳐 이미지의 저장 형식을 변경할 수 있나요?**  
A: 현재는 기본 형식만 지원하지만, `pyautogui` 문서를 참고하여 코드를 수정하면 가능합니다.

**Q: 프로그램이 시작되지 않습니다.**  
A: 위의 "PyQt5 플러그인 경로 설정" 섹션을 참고하여 경로를 설정해주세요.

---


---

**마지막 업데이트**: 2025년 1월
