<div align="center">

# Maya Workflow Kit for Blender

### Blender를 사용하는 Maya 사용자를 위해

**한 번의 설치로 Blender에서 Maya 방식의 작업 환경을 사용하세요.**

[![Blender 5.2 LTS](https://img.shields.io/badge/Blender-5.2%20LTS-5285a6)](#requirements)
[![라이선스: GPL-3.0-or-later](https://img.shields.io/badge/license-GPL--3.0--or--later-blue)](LICENSE)

![Maya Workflow Kit — Blender에서 Maya에 익숙한 방식으로 작업하세요.](docs/distribution/marketing/kit/readme_hero.png)

</div>

> 이 README는 원본 프로젝트 설명의 한국어 번역입니다. 기능명과 메뉴 경로는 프로그램에서 쉽게 찾을 수 있도록 영문을 병기하거나 유지했습니다. 연결된 상세 문서와 이미지·영상 속 문구는 원문 그대로입니다.

**Blender 튜토리얼을 따라간 뒤에도, 익숙한 채널 박스로 돌아올 수 있습니다.**

Maya Workflow Kit는 Maya로 3D를 배운 사람을 위한 무료 오픈소스 Blender 확장입니다. 핫박스와 마킹 메뉴, 채널 박스(Channel Box)와 속성 편집기(Attribute Editor), 메뉴 세트, 셸프와 옵션 창, Maya 방식의 화면 조작과 선택을 Blender의 도구 위에 구현했습니다. Freeze Transformations, Delete History, 그룹, 센티미터 단위와 `pCube1` 같은 Maya의 장면 구성 방식도 제공합니다. **설치만으로는 아무것도 바뀌지 않으며, Maya 모드를 선택해야 적용됩니다.** Blender 고유 단축키를 사용하는 튜토리얼을 볼 때는 Maya | Blender 스위치를 한 번 눌러 기본 Blender로 돌아갈 수 있습니다.

▶ **[30초 소개 영상 보기(MP4)](docs/distribution/marketing/clips/00_trailer.mp4)** · [웹사이트](https://5hyuns.github.io/maya-workflow-kit-for-blender/)
· [설치](#installation) · [빠른 시작](#quick-start-for-maya-users) · [자주 묻는 질문](#faq)

📥 **무료 다운로드:** [Blender Extensions](https://extensions.blender.org/add-ons/allset/), 또는 Blender의 *Edit → Preferences → Get Extensions*에서 "Maya Workflow Kit"를 검색하세요.

---

## 👋 개발자의 인사

저는 오랫동안 Maya를 사용했습니다. Blender로 옮겨 보려 했을 때, 진짜 문제는 프로그램보다 손에 밴 습관이었습니다. Space를 길게 눌러도 아무것도 나타나지 않았고, 없는 채널 박스를 찾았으며, 몇 분마다 셸프를 찾는 제 모습을 발견했습니다. 저처럼 Maya에 익숙한 사람들이 Blender에 조금 더 편하게 적응하기를 바라며 이 도구를 만들었습니다.

솔직히 아직 부족한 부분이 있습니다. 구현되지 않은 Maya 도구도 있고, 사용감이 어색한 기능도 있습니다. 저도 직접 사용하며 계속 개선하겠지만, 문제를 알아야 고칠 수 있습니다. 작동하지 않거나 어색한 부분, 매일 쓰는데 빠져 있는 Maya 기능이 있다면 [이슈를 남겨 주세요](https://github.com/5hyuns/maya-workflow-kit-for-blender/issues/new). 한 줄의 제보도 큰 도움이 됩니다. 다른 방식의 참여도 환영합니다. [CONTRIBUTING.md](CONTRIBUTING.md)를 참고하세요.

사용해 주셔서 감사합니다 🙂

---

<a id="why-this-exists"></a>
## 프로젝트를 만든 이유

많은 아티스트가 Maya로 3D를 배우고 수년 동안 조작 습관을 익혔습니다. 팀이나 고객, 수업 또는 개인 프로젝트 때문에 Blender를 사용해야 할 때, 그 습관이 오히려 방해가 되기도 합니다. 이 프로젝트는 그런 어려움을 조금 줄이기 위해 만들어졌습니다.

Maya를 대체하거나 사용자가 Maya를 떠나게 하려는 목적은 아닙니다. 두 프로그램을 함께 사용하는 사람도 많습니다. 이 키트는 Blender에서도 손에 익은 방식으로 작업하고 싶은 순간을 위한 도구입니다.

Maya Workflow Kit는 개인이 만드는 무료 오픈소스 프로젝트입니다. 유료 버전도, 후원 요청도, 상업적인 목적도 없습니다. Autodesk와 제휴 관계가 없으며 Autodesk의 보증을 받지 않습니다.

---

## 목차

- [프로젝트를 만든 이유](#why-this-exists)
- [주요 기능](#features)
- [알려진 제약](#known-limits)
- [설치](#installation)
- [첫 실행: Maya 모드 켜고 끄기](#first-run-turning-maya-mode-on-and-off)
- [권장 설정](#recommended-setup)
- [Maya 사용자를 위한 빠른 시작](#quick-start-for-maya-users)
- [자주 묻는 질문](#faq)
- [개발](#development)
- [기여자](#contributors) · [크레딧](#credits) · [라이선스](#license) · [상표 안내](#trademarks)

---

<a id="features"></a>
## 주요 기능

[Smart Extrude](docs/smart_extrude.md)는 면을 돌출하거나 파내고 교차하는 면을 연결합니다. 이동·회전·크기 조절을 결합한 매니퓰레이터와 관통 절단을 지원합니다.

[Make Live](docs/make_live.md)는 Status Line의 자석과 히스토리 메뉴로 참조 메시를 관리합니다. 짙은 녹색 이름·와이어 표시, 뷰포트 선택 제한, 활성 참조 목록을 대상으로 하는 Move / Quad Draw 투영을 제공합니다.

아래 기능은 현재 버전에 포함되어 있습니다. Blender에서 구현할 수 없는 Maya 메뉴 항목도 표시되지만, 비활성화된 상태로 이유와 대안을 한 줄로 안내합니다.

### 외형과 레이아웃

- **Maya 레이아웃:** Maya 모드를 선택하면 열린 파일에 워크스페이스로 추가됩니다. 메뉴 바, Status Line, Shelf, Tool Box, Outliner, Channel Box / Layer Editor 탭 묶음, Time Slider, Range Slider, Help Line과 Command Line을 제공합니다.
- **Maya 방식 도킹:** Channel Box, Attribute Editor, Modeling Toolkit이 뷰포트 옆의 탭 묶음을 공유합니다. `:::::` 핸들로 분리해 떠 있는 창으로 만들 수 있습니다. Outliner와 Tool Settings는 왼쪽에 배치됩니다.
- Maya 스타일 **Move / Scale 매니퓰레이터**를 제공합니다.
- **Alt+B**로 모든 3D 뷰의 배경을 Maya의 단색 배경들로 순환합니다.
- 사용자가 선택한 Blender 테마를 사용합니다. Maya와 비슷한 외형은 [권장 설정](#recommended-setup)을 참고하세요.

### 화면 조작과 선택

- **Alt + 마우스 왼쪽 / 가운데 / 오른쪽 버튼(LMB / MMB / RMB)**으로 회전(tumble), 평행 이동(track), 전후 이동(dolly)을 합니다. **F / A**는 현재 뷰의 보이는 영역에서 선택 항목 / 전체를 화면에 맞춥니다. **Shift+F / Shift+A**는 모든 뷰에 적용됩니다. **`[` `]`**는 뷰 변경 실행 취소 / 다시 실행이며, **Space**를 짧게 누르면 단일 뷰 / 4분할 뷰를 전환합니다.
- **Q W E R T Y** 도구를 지원합니다. Y는 QWERT 이외의 마지막 도구입니다. Maya 방식 선택 보조키(Shift: 선택 전환, Ctrl: 선택 해제, Ctrl+Shift: 추가), **F8** 오브젝트 / 컴포넌트 전환, **F9–F12** 버텍스 / 에지 / 면 / UV 전환을 제공합니다.
- 선택 전 하이라이트, 편집 모드에서 가려진 요소까지 박스 선택, 선택 우선순위, 방향키 **pick-walk**(에지 루프 / 링, 조인트), 소프트 선택과 대칭을 지원합니다.
- **누르고 있는 동안 적용되는 키:** **X / C / V**는 그리드 / 에지 / 버텍스 스냅, **J**는 단계 스냅입니다. **D / Insert**로 피벗 편집을 전환하며, **D**를 누르는 동안만 임시 편집할 수도 있습니다. **B**는 소프트 선택입니다.

![피벗 편집과 V 키 스냅](docs/distribution/marketing/gif/05_pivot_snap.gif)

*Insert로 피벗을 편집합니다. 드래그하면서 V를 누르면 버텍스에 스냅됩니다. Insert를 다시 누르면 새 피벗을 중심으로 오브젝트를 회전할 수 있습니다.*

피벗 편집 중 버텍스, 에지, 면을 클릭하면 피벗을 해당 위치에 스냅하고 정렬합니다. Shift+클릭은 위치를, Ctrl+클릭은 방향을 변경합니다. 전체 조작법은 [사용자 피벗 편집](docs/pivot_component_picking.md)을 참고하세요.

### 핫박스, 마킹 메뉴와 메뉴 세트

- **Space를 길게 눌러 핫박스**를 엽니다. 현재 메뉴 세트의 모든 메뉴, 최근 명령(Recent Commands), 마킹 메뉴 영역을 제공합니다.
- 오브젝트와 컴포넌트 위에서 **우클릭, Shift+우클릭, Ctrl+우클릭**으로 Maya와 같은 방사형 배치의 마킹 메뉴를 엽니다. 제스처, 클릭 모드, 하위 메뉴와 옵션 박스를 지원합니다. **Q / W / E / R + LMB**는 도구 옵션 메뉴, **Shift+Q / Alt+Q / Shift+S**는 길게 누르는 메뉴입니다.
- **Marking Menu Editor**(Windows > Settings/Preferences)에서 키트의 마킹 메뉴를 바꾸거나 직접 만들 수 있습니다. Restore Default로 기본값을 복원할 수 있으며, 사용자 메뉴도 Maya처럼 단축키를 누른 채 LMB로 엽니다.
- **F2–F6**으로 Modeling / Rigging / Animation / FX / Rendering **메뉴 세트**를 선택합니다. Maya의 메뉴 순서와 명칭, 메뉴에 표시되는 Maya 단축키, 점선 분리선을 제공합니다.
- **옵션 박스(❒)**는 Maya 2022 기본값을 사용하는 옵션 창을 엽니다. Save Settings, Reset Settings, Apply와 명령 버튼을 제공하며, 일반 클릭으로 명령을 실행하면 저장한 설정을 사용합니다.
- **셸프:** Polygons, Rigging, Animation, Rendering, FX 등의 기본 셸프 버튼을 Maya와 같은 위치에 배치하고, 사용자 Python 셸프도 지원합니다.

![Space를 길게 눌러 핫박스 열기](docs/distribution/marketing/gif/01_hotbox.gif)

*Space를 짧게 누르면 단일 / 4분할 뷰를 전환하고, 길게 누르면 핫박스를 엽니다. 영상에서는 핫박스의 Select > All을 실행합니다.*

![우클릭 마킹 메뉴](docs/distribution/marketing/gif/02_marking_menu.gif)

*오브젝트 위에서 우클릭하면 Maya와 같은 위치에 마킹 메뉴가 나타납니다. Vertex로 드래그하면 컴포넌트 모드가 되고, 다시 우클릭해 Object Mode로 돌아갑니다.*

### 채널 박스와 편집기

- **Channel Box / Layer Editor:** 선택한 모든 오브젝트의 Translate / Rotate / Scale / Visibility, SHAPES와 INPUTS(히스토리), 키 설정 / 잠금 / 드리븐 상태별 색상, `+=5`와 `*=2` 입력, 선택 채널을 뷰포트 가운데 버튼 드래그로 조절하는 가상 슬라이더, Channels 메뉴, 우클릭 메뉴와 디스플레이 레이어를 제공합니다.
- **Attribute Editor:** Maya 스타일 노드 탭과 섹션(transform, shape, history, material, shading group), Notes를 제공합니다. **Ctrl+A**로 Channel Box ↔ Attribute Editor를 전환합니다.
- **Outliner:** Maya의 Display / Show 메뉴(DAG 계층, Shapes 표시 전환), 세트와 기본 행을 제공합니다.
- **Graph Editor, Dope Sheet, UV Editor, Hypershade, Render Settings, Script Editor**에 Maya 스타일 메뉴 바를 제공합니다. **Tool Settings** 도킹 패널과 **Modeling Toolkit**도 포함됩니다.
- **Command Line**과 **Script Editor**에서는 Python과 간단한 `maya.cmds` 유사 명령을 실행합니다. 예: `cmds.polyCube()`, `cmds.move(5, 0, 0)`.

![채널 박스에서 키 설정](docs/distribution/marketing/gif/03_channel_box_keys.gif)

*S를 누르면 모든 채널에 키가 설정되고 채널 박스가 빨간색으로 바뀝니다. Rotate Z에 `+=90`을 입력하고 우클릭 › Key Selected를 선택한 뒤 Time Slider를 움직여 보세요.*

### 모델링과 UV

- **Maya 생성 기본값:** `pCube1`, `pCubeShape1`, `group1`, `polySmooth1` 등의 이름, 센티미터 기준 크기와 기본 `lambert1` 재질을 사용합니다. 선택 사항인 **Maya Units** 설정은 Blender 1단위를 1cm로 취급합니다.
- **Maya 방식 작업:** Freeze Transformations(채널을 0 / 0 / 1로 되돌리면서 피벗 유지), Reset Transformations, Center Pivot, Delete History, Delete by Type, Maya 방식 부모 연결(**P / Shift+P**, 채널 박스 값 유지), **Ctrl+G** 그룹과 Duplicate Special을 제공합니다.
- **1 / 2 / 3**은 Smooth Mesh Preview, **4 / 5 / 6 / 7**은 표시 모드입니다.
- Combine / Separate / Mirror / Boolean, 편집 가능한 히스토리를 남기는 Extrude, **Ctrl+B** Bevel, Circularize, Connect, Make Hole과 Maya 방식 선택 변환 규칙을 제공합니다.
- **UV:** Cut / Sew UV Edges, 3D Cut and Sew, Unfold, Layout, UV 셸 선택, Maya 스타일 UV Editor 메뉴와 UV Toolkit을 제공합니다.

### 애니메이션

- **S**는 키를 설정할 수 있는 모든 채널에 키를 설정합니다. **Shift+W / E / R**은 이동 / 회전 / 크기 채널에 키를 설정합니다.
- 키 표시가 있는 **Time Slider**와 **Range Slider**, **K+드래그** 시간 탐색, **, / .** 이전 / 다음 키 이동, **Alt+V** 재생과 Time Slider 북마크를 제공합니다.
- **Graph Editor:** Maya 메뉴와 탄젠트 도구 모음(Spline, Linear, Clamped, Stepped, Flat 등), **Shift+S** 탄젠트 마킹 메뉴와 **I** 키 삽입 도구를 제공합니다.
- **Auto Key**와 **Playblast**를 지원합니다.

![Maya 방식 화면 조작](docs/distribution/marketing/gif/04_navigation.gif)

*Alt+왼쪽 드래그는 회전, Alt+가운데 드래그는 평행 이동, Alt+오른쪽 드래그는 전후 이동입니다. 오브젝트를 클릭하고 F로 선택 항목을, A로 전체를 화면에 맞춥니다.*

### 리깅

- **Joint Tool**, **IK Handle**, IK Spline, 조인트 pick-walk, Reroot와 Preferred Angle을 제공합니다.
- **Bind Skin**, **Paint Skin Weights**(영향 목록, Replace / Add / Scale / Smooth)와 Hammer weights를 제공합니다.
- **Set Driven Key**, 컨스트레인트, Cluster와 Soft Modification을 지원합니다.

![조인트, IK와 스킨 웨이트](docs/distribution/marketing/gif/06_rigging.gif)

*Rigging 셸프에서 클릭해 조인트를 만들고, 어깨에서 손목까지 IK Handle을 생성합니다. Bind Skin 후 핸들을 움직이고 Paint Skin Weights로 웨이트를 조절합니다.*

### 렌더링과 FX

- **Hypershade** 메뉴와 Browser 탭, Maya 셰이더 유형과 해당 Attribute Editor 섹션, 셰이딩 그룹을 제공합니다.
- Maya의 Common 탭이 있는 **Render Settings** 창과 Rendering 메뉴 세트(Render Current Frame, 렌더 뷰의 Keep Image)를 제공합니다.
- **FX** 메뉴 세트에서 Maya의 시뮬레이션 스케일에 맞춘 nucleus 중력, nParticles 이미터와 nCloth를 제공합니다.

### 장면과 파일

- **Maya 프로젝트:** Set Project / Project Window를 제공합니다. 파일 대화상자는 현재 프로젝트 폴더에서 시작합니다. 기본 프로젝트는 `Documents/Maya Workflow Kit/projects/default`입니다.
- **Ctrl+S / Ctrl+Shift+S**로 프로젝트의 scenes 폴더에 저장합니다. **Ctrl+Alt+S**는 Maya 방식으로 번호를 증가시켜 저장합니다(`shot_v001` → `shot_v001.0001`).
- **Ctrl+R** Create Reference는 라이브러리 오버라이드와 `namespace:name` 이름을 사용해 `.blend` 파일을 링크합니다.
- **File > Import / Export**에서 파일 유형(FBX, OBJ, Alembic, USD 등)과 Maya 프리셋(cm, Y-up)을 제공합니다.

### 모드 전환과 되돌리기

- 상단 바 오른쪽의 **Maya | Blender** 스위치, Edit 메뉴 항목 또는 **Ctrl+Alt+Shift+M**을 사용합니다.
- Blender로 전환하면 Maya 단축키와 UI 등록이 해제되어 기본 Blender로 돌아갑니다. 같은 장면이 열린 상태로 유지되며, 언제든 다시 전환할 수 있습니다.
- Maya 모드는 사용자 환경설정, 테마와 활성 키맵을 변경하지 않으므로 별도로 복원할 설정이 없습니다.

![한 번의 클릭으로 Maya 또는 Blender 전환](docs/distribution/marketing/gif/07_switch.gif)

*상단 스위치의 Blender를 누르면 같은 장면에서 기본 Blender로 돌아갑니다. Maya를 누르면 Maya 레이아웃과 단축키가 다시 적용됩니다.*

모든 영상의 MP4 버전(1920 × 1080): [docs/distribution/marketing/clips/](docs/distribution/marketing/clips/).

<a id="known-limits"></a>
### 알려진 제약

일부 Maya 동작을 구현하려면 Blender의 C++ 코드를 바꿔야 합니다. 이 키트는 Blender 자체를 포크하지 않으므로 다음 기능은 우회하거나 제외했습니다.

- **Z-up 좌표계:** Blender는 Z-up입니다. Y-up은 가져오기 / 내보내기 프리셋에만 적용됩니다.
- **오브젝트당 피벗 하나:** Maya처럼 회전 피벗과 크기 조절 피벗을 따로 둘 수 없습니다.
- **입력 필드에서 가운데 버튼 드래그 불가:** 대신 Channel Box에서 채널을 선택하고 뷰포트에서 가운데 버튼으로 드래그하세요.
- **MEL 미지원:** Python과 간단한 `maya.cmds` 유사 명령을 사용합니다.
- **Maya 장면 파일 미지원:** `.ma` / `.mb`를 읽을 수 없습니다. Maya에서 FBX, OBJ, Alembic 또는 USD로 내보내세요.
- **테마 미포함:** Maya의 회색 UI와 주 선택 항목의 녹색 표시는 직접 설치한 테마로 설정합니다([권장 설정](#recommended-setup)). extensions.blender.org 애드온은 테마를 변경할 수 없습니다.
- **도킹은 Blender 영역 안으로 제한:** Maya의 측면 탭과 운영체제 수준 패널 도킹을 그대로 구현하지 않습니다.
- Blender에 대응 기능이 없는 Maya 메뉴는 비활성화하고 설명을 표시합니다.
- Blender 5.2 이후 버전은 테스트하기 전까지 확장 호환 대상으로 제공하지 않습니다.

---

<a id="installation"></a>
## 설치

> **번역 참고:** 원문 설치 절에는 “Extensions 플랫폼 미등록” 및 “현재 버전 0.2.1”이라는 이전 안내가 남아 있어 상단 다운로드 안내와 일치하지 않습니다. 아래에는 원문의 표기를 남겼습니다. 실제 등록 상태와 설치 파일은 [Blender Extensions](https://extensions.blender.org/add-ons/allset/) 및 [원본 GitHub 최신 릴리스](https://github.com/5hyuns/maya-workflow-kit-for-blender/releases/latest)에서 확인하세요.

<a id="requirements"></a>
### 요구 사항

- **Blender 5.2 LTS:** 현재 지원·테스트 대상은 Blender 5.2입니다. 5.0과 5.1에도 설치할 수 있지만(`blender_version_min = "5.0.0"`, `blender_version_max = "5.3.0"`, 상한 제외), 더 이상 해당 버전을 테스트하지 않아 **문제가 생길 수 있습니다.** 가능하면 5.2를 사용하세요. Blender 4.5 LTS는 더 이상 지원하지 않습니다. **Blender 4.5용 마지막 버전은 0.6.2**이므로 해당 환경에서는 0.6.2를 사용하세요.
- 순수 Python으로 작성되었으며 컴파일된 코드나 네트워크 접근이 없습니다. Windows에서는 읽기 전용 시스템 호출 하나로 키 상태를 확인하며, 다른 운영체제에서는 Blender의 키 해제 이벤트를 사용합니다. 지금까지의 개발과 테스트는 Windows에서만 이루어졌습니다.

### 방법 1 — Blender Extensions 플랫폼 *(원문: 아직 미등록)*

원문에서는 아직 extensions.blender.org에 등록되지 않았다고 안내합니다. 등록 후에는 Blender의 *Edit > Preferences > Get Extensions*에서 **Maya Workflow Kit**를 검색하고 **Install**을 누르면 됩니다.

### 방법 2 — ZIP 파일로 설치

1. [GitHub Releases](https://github.com/5hyuns/maya-workflow-kit-for-blender/releases)에서 `maya-workflow-kit-<version>.zip`을 받습니다(원문 표기 버전: 0.2.1). 또는 방법 3으로 직접 빌드합니다.
2. Blender의 *Edit > Preferences > Get Extensions > ▾(오른쪽 위 메뉴) > Install from Disk…*에서 ZIP을 선택하거나, ZIP을 Blender 창으로 드래그합니다.

명령줄에서 설치하고 활성화하려면 다음을 실행합니다. 사용자 저장소에 설치됩니다.

```sh
blender --command extension install-file -r user_default --enable maya-workflow-kit-<version>.zip
```

### 방법 3 — 소스에서 빌드

```sh
git clone https://github.com/5hyuns/maya-workflow-kit-for-blender.git
cd maya-workflow-kit-for-blender
python tools/build.py            # -> dist/maya-workflow-kit-<version>.zip (+ dist/maya-workflow-kit-<version>-legacy.zip)
python tools/build.py --blender "/path/to/blender"   # 사용할 Blender 5.x 경로 지정
```

빌드는 임시 사용자 설정에서 `blender --command extension build`를 실행하고 매니페스트도 검증합니다. 생성된 `dist/maya-workflow-kit-<version>.zip`은 방법 2로 설치하세요.

---

<a id="first-run-turning-maya-mode-on-and-off"></a>
## 첫 실행: Maya 모드 켜고 끄기

**확장을 활성화하는 것만으로는 키맵, 환경설정, 테마나 레이아웃이 변경되지 않습니다.** 상단 바 오른쪽의 Maya | Blender 스위치, Edit 메뉴 항목, **Ctrl+Alt+Shift+M** 단축키와 한 번 표시되는 환영 창만 추가됩니다.

**Maya 모드 켜기:** 환영 창 또는 *Preferences > Add-ons > Maya Workflow Kit*의 **Make Blender feel like Maya**를 누르거나, 상단 스위치의 **Maya**를 누르세요. Maya 단축키가 애드온 키맵 항목으로 추가되지만 활성 키맵 선택은 유지됩니다. Maya 메뉴와 패널, 열린 파일의 워크스페이스로 Maya 레이아웃이 추가됩니다. 테마나 Blender 환경설정은 변경하지 않습니다.

**되돌리는 방법**

| 원하는 작업 | 방법 |
|---|---|
| 잠시 기본 Blender 사용 | 스위치의 **Blender** 또는 Ctrl+Alt+Shift+M을 누릅니다. Maya 단축키와 UI가 해제되며 언제든 다시 전환할 수 있습니다. |
| 확장 제거 | *Preferences > Add-ons*에서 비활성화하거나 **Remove**를 누릅니다. 확장이 등록한 항목이 해제되며 추가 복원 작업은 필요하지 않습니다. |
| 파일에서 Maya 레이아웃 제거 | 해당 워크스페이스 탭을 삭제하거나 파일을 저장하지 않습니다. 워크스페이스는 일반적인 파일 데이터입니다. |

키트는 사용자 환경설정을 저장하지 않습니다.

**확장 폴더 밖에 기록하는 파일**

- 확장의 사용자 폴더: 사용자가 만든 셸프.
- Maya 프로젝트 폴더: 프로젝트를 사용하는 대화상자를 처음 열 때 생성되는 기본 프로젝트 `Documents/Maya Workflow Kit/projects/default` 및 Set Project로 선택한 폴더.
- Playblast 영상: Blender 임시 폴더. 내보내기와 저장은 사용자가 선택한 위치를 사용합니다.

---

<a id="recommended-setup"></a>
## 권장 설정

선택 사항입니다. 테마와 환경설정은 사용자가 직접 관리합니다. Maya 사용자에게는 다음 설정이 권장됩니다.

- **짙은 회색 테마:** *Edit > Preferences > Get Extensions*에서 *Themes*로 필터링해 원하는 테마를 설치하거나 *Preferences > Themes > Presets*에서 선택하세요.
- **화면 조작**(*Preferences > Navigation*): Orbit Method는 *Turntable*, Orbit Around Selection은 *끔*, Zoom to Mouse Position은 *끔*, Auto Perspective는 *켬*, Zoom Method는 *Dolly*, Zoom Axis는 *Horizontal*로 설정합니다.
- **Undo Steps 256**(*Edit > Preferences > System > Memory & Limits > Undo Steps*): Maya의 실행 취소 기록은 무제한이지만 Blender는 기본 32단계여서 긴 모델링 작업 중 더 빨리 기록 한도에 도달합니다. Blender의 최대값은 256입니다. 확장은 Blender 환경설정을 바꿀 수 없어 직접 설정할 수 없으며, 값이 낮으면 확장 설정에 안내를 표시합니다.
- **Emulate 3 Button Mouse 끄기**(*Preferences > Input*): 켜져 있으면 키맵에 전달되기 전에 Alt+왼쪽 드래그가 가운데 버튼 드래그로 바뀌어 Maya의 Alt+LMB 회전이 작동하지 않습니다. 켜져 있는 동안 키트에서 안내합니다.
- **Linux:** GNOME, KDE, Xfce 등은 Blender가 입력을 받기 전에 Alt+드래그로 창을 이동할 수 있습니다. 창 관리자의 이동 보조키를 Super로 변경하면 Maya에서처럼 Alt로 회전 / 평행 이동 / 전후 이동을 할 수 있습니다.
- **Region Overlap 끄기**(*Preferences > Interface > Editors*): Maya처럼 측면 패널이 뷰포트 옆에 배치됩니다.
- **Only Insert Available**(*Preferences > Animation > Keyframes*): Maya와 비슷한 Auto Key 동작을 위한 설정입니다.

---

<a id="quick-start-for-maya-users"></a>
## Maya 사용자를 위한 빠른 시작

Maya 모드가 켜진 상태를 기준으로 합니다. 모든 Maya 단축키와 Blender 대응 항목은 Maya 스타일 Hotkey Editor(*Windows > Settings/Preferences > Hotkey Editor*)에서 확인할 수 있습니다.

| 작업 | 키 / 마우스 |
|---|---|
| 회전 / 평행 이동 / 전후 이동 | Alt + LMB / MMB / RMB 드래그 |
| 선택 항목 / 전체 화면 맞춤 | F / A (Shift+F / Shift+A: 모든 뷰) |
| 단일 뷰 ↔ 4분할 뷰 | Space 짧게 누르기 |
| 핫박스 | Space 길게 누르기 |
| 마킹 메뉴 | 오브젝트나 컴포넌트 위에서 RMB, Shift+RMB, Ctrl+RMB |
| 선택 / 이동 / 회전 / 크기 조절 | Q / W / E / R (키를 누른 채 LMB: 도구 마킹 메뉴) |
| 마지막 도구 | Y |
| 선택 추가 / 전환 / 해제 | Ctrl+Shift+클릭 / Shift+클릭 / Ctrl+클릭 |
| 오브젝트 ↔ 컴포넌트 모드 | F8; F9 버텍스, F10 에지, F11 면, F12 UV |
| Pick-walk | 방향키 |
| 피벗 편집 | D 길게 누르기 또는 Insert로 전환 |
| 그리드 / 에지 / 버텍스 스냅 | 드래그하면서 X / C / V 누르기 |
| 소프트 선택 | B |
| 스무스 미리보기 / 표시 모드 | 1 / 2 / 3 · 4 / 5 / 6 / 7 |
| Channel Box ↔ Attribute Editor | Ctrl+A |
| 메뉴 세트 | F2 Modeling · F3 Rigging · F4 Animation · F5 FX · F6 Rendering |
| 실행 취소 / 다시 실행 | Z 또는 Ctrl+Z / Shift+Z |
| 복제 / 변환 반복 복제 / 특수 복제 | Ctrl+D / Shift+D / Ctrl+Shift+D |
| 그룹 / 부모 연결 / 연결 해제 | Ctrl+G / P / Shift+P |
| 히스토리 삭제 | Alt+Shift+D |
| 숨기기 / 표시 | Ctrl+H / Shift+H |
| 키 설정 / 이동·회전·크기 키 설정 | S / Shift+W, Shift+E, Shift+R |
| 이전 / 다음 키 · 재생 | , / . · Alt+V |
| 시간 탐색 | K + LMB 드래그 |
| 탄젠트 마킹 메뉴 | Shift+S를 누른 채 LMB |
| 배경색 변경 | Alt+B |
| 저장 / 번호를 증가시켜 저장 | Ctrl+S / Ctrl+Alt+S |
| 참조 생성(Create Reference) | Ctrl+R |
| Maya ↔ Blender 전환 | Ctrl+Alt+Shift+M |

---

<a id="faq"></a>
## 자주 묻는 질문

**Blender 설정이 바뀌나요?**  
아니요. Maya 모드는 열린 파일에 애드온 키맵 항목, 메뉴, 패널과 레이아웃 워크스페이스를 추가합니다. 사용자 환경설정, 테마나 활성 키맵을 기록하지 않습니다. 일반적으로 Maya 사용자가 바꾸는 설정은 [권장 설정](#recommended-setup)을 참고해 직접 조절하세요.

**원래대로 돌아갈 수 있나요?**  
네. 상단 스위치의 **Blender**를 누르거나 확장을 비활성화 / 제거하면 등록한 항목이 해제됩니다. 다른 설정은 변경하지 않습니다. [첫 실행](#first-run-turning-maya-mode-on-and-off)을 참고하세요.

**설치한 상태로 Blender 튜토리얼을 따라갈 수 있나요?**  
네. Blender 모드로 전환해 기본 단축키로 따라 한 뒤 Maya 모드로 돌아오면 됩니다.

**지원하는 Blender 버전은 무엇인가요?**  
현재는 Blender 5.2 LTS입니다. 5.0과 5.1에도 설치되지만 테스트되지 않아 문제가 생길 수 있습니다. Blender 4.5 LTS용 마지막 버전은 0.6.2이며, 5.2 이후 버전은 테스트를 거친 뒤 추가됩니다.

**Maya의 `.ma` / `.mb` 파일을 열 수 있나요?**  
아니요. Maya에서 FBX, OBJ, Alembic 또는 USD로 내보내세요. 키트의 Import는 Maya 프리셋(cm, Y-up)을 사용합니다.

**Maya 코드나 파일이 포함되어 있나요?**  
아니요. Autodesk의 코드, 아이콘, MEL 스크립트나 기타 자산을 포함하지 않습니다. Blender 도구를 기반으로 동작을 다시 구현했으며 Maya를 설치할 필요도 없습니다.

**Autodesk와 관련된 공식 프로젝트인가요?**  
아니요. Maya Workflow Kit는 독립적인 무료 오픈소스 프로젝트입니다. Autodesk 또는 Blender Foundation과 제휴하거나 보증받지 않습니다. [상표 안내](#trademarks)를 참고하세요.

**네트워크를 사용하나요?**  
네트워크에 접근하지 않으며 자동 업데이터도 없습니다. Help 메뉴를 직접 클릭할 때만 브라우저에서 Blender 매뉴얼을 엽니다.

---

<a id="development"></a>
## 개발

확장의 내부 ID는 `allset`입니다. 패키지는 `src/allset/`, 오퍼레이터는 `allset.*`, 클래스는 `ALLSET_*`, 환경변수는 `ALLSET_*`를 사용합니다. 표시 이름과 관계없이 내부 ID는 유지됩니다.

### 저장소 구조

| 경로 | 내용 |
|---|---|
| `src/allset/` | 확장 본체: `blender_manifest.toml`, `preferences.py`, `switch.py`, `keymap/`, `marking/`, `operators/`, `ui/`, `compat.py`(Blender 버전 차이 처리) |
| `tests/` | 헤드리스 테스트 실행기 `run.py`, GUI 테스트 `gui/`, 보조 도구 `kit.py`, `test_*.py` 테스트 |
| `tools/` | 패키징 `build.py`, `release_check.py`, 정적 확장 저장소 생성 `build_repo.py`, 레이아웃 템플릿 `make_startup.py` |
| `docs/` | `distribution/`(릴리스 노트, 스토어·홍보 자료), 사용자 가이드 |

### 빌드와 테스트

모든 Blender 실행은 `tmp/` 아래의 격리된 사용자 설정을 사용합니다. 실제 Blender 설정은 읽거나 쓰지 않습니다.

```sh
python tools/build.py              # dist/maya-workflow-kit-<version>.zip 및 legacy ZIP 빌드
python tests/run.py                # 빌드 + tmp/test_env에 설치 + 전체 헤드리스 테스트
python tests/run.py -k enable      # 이름이 일치하는 테스트 파일만 실행
python tests/run.py --no-build     # dist/의 기존 ZIP 재사용
python tests/gui/run.py            # 키·마우스 입력을 모의하는 GUI 테스트(Blender 창이 잠깐 열림)
python tools/release_check.py      # 빌드, 확장 검증, 새 설정으로 설치·활성화, 스크린샷
python tools/build_repo.py         # dist/repo/에 정적 확장 저장소 생성(zip + index.json + index.html)
```

---

<a id="contributors"></a>
## 기여자

키트에 코드를 보내 주신 모든 분께 감사드립니다! 🙏

| 기여자 | 기여 내용 |
|---|---|
| [@cnzim](https://github.com/cnzim) | 실시간 변환, 조인트 선택, Paint Skin Weights 워크스페이스 ([#125](https://github.com/5hyuns/maya-workflow-kit-for-blender/pull/125)) |
| [@LSKianhao](https://github.com/LSKianhao) | 고해상도 화면의 Time Slider 크기 조절, 눈금자 글자 크기 테스트 ([#188](https://github.com/5hyuns/maya-workflow-kit-for-blender/pull/188)) |
| [@youngmin2k](https://github.com/youngmin2k) | 컴포넌트 모드 진입 전 숨겨진 메시 경고 ([#196](https://github.com/5hyuns/maya-workflow-kit-for-blender/pull/196)); 피벗 편집, Prevent Negative Scale, Smart Extrude, Make Live ([#207](https://github.com/5hyuns/maya-workflow-kit-for-blender/pull/207)) |
| [@Kevorama](https://github.com/Kevorama) | Outliner 숨기기 단축키와 숨겨진 부모 처리 ([#223](https://github.com/5hyuns/maya-workflow-kit-for-blender/issues/223)) |
| Tom Pilott | Channel Box 값 드래그, Alt+B 그라데이션, ViewCube 조작, 선택 와이어 깊이 ([#224](https://github.com/5hyuns/maya-workflow-kit-for-blender/issues/224)) |

이슈 제보와 테스트로 도와주신 더 많은 분께는 각 [릴리스 노트](https://github.com/5hyuns/maya-workflow-kit-for-blender/releases)에서 감사 인사를 전합니다. Pull Request도 환영합니다.

<a id="credits"></a>
## 크레딧

스크린샷과 영상 속 장면에는 각자의 라이선스에 따라 사용한 외부 모델과 이미지가 포함됩니다. 각 자산의 제작자, 출처와 라이선스는 [docs/distribution/marketing/CREDITS.md](docs/distribution/marketing/CREDITS.md)에 기록되어 있습니다. 캡션에는 Inter 글꼴(SIL OFL)을 사용합니다. 이 자산들은 홍보 자료에만 쓰이며 확장에 포함되어 배포되지 않습니다.

<a id="license"></a>
## 라이선스

코드: **GPL-3.0-or-later**([LICENSE](LICENSE)). 확장에 포함된 자체 제작 이미지와 데이터 파일(환영 PNG, Maya 레이아웃 `startup.blend`)은 **CC0-1.0**입니다([src/allset/ASSETS_LICENSE.txt](src/allset/ASSETS_LICENSE.txt)). Copyright 2026 5hyuns.

<a id="trademarks"></a>
## 상표 안내

Autodesk와 Maya는 미국 및 기타 국가에서 Autodesk, Inc.와 그 자회사 또는 계열사의 등록 상표 또는 상표입니다. 이 프로젝트는 Blender용 독립 무료 오픈소스(GPL) 확장입니다. Autodesk, Inc. 또는 Blender Foundation과 제휴하거나, 보증·후원·기타 승인을 받지 않았습니다. Autodesk의 코드, 아이콘, MEL 스크립트나 기타 자산을 포함하지 않으며, Maya에 대한 언급은 호환성과 사용 대상을 설명하기 위한 것입니다.
