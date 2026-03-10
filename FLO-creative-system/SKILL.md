---
name: flo-creative-system
description: Apply the Dreamus design system when writing UI code. Use this skill whenever the user asks to build UI, create components, style pages, or implement vibe coding — especially when they mention cards, themes, color, playlist, or Korean app UI. This skill ensures all generated code matches the Figma design spec (colors, typography, spacing, border radius, component structure) without needing to re-check Figma every time. Also use when the user mentions icons, loading animation, or assets for this project.
---

# Dreamus Design System

Figma source: https://www.figma.com/design/C6PIvbjgPxGvbVI8Lbj2fB/Untitled?node-id=9-70

이 스킬은 Dreamus 디자인 시스템의 규칙을 담고 있습니다. UI 코드를 작성할 때 아래의 컬러, 타이포그래피, 컴포넌트 규칙을 항상 따르세요.

---

## ⚠️ 라이트모드 강제 적용 (최우선 규칙)

**이 프로젝트는 항상 라이트모드를 유지합니다.** 사용자 시스템의 다크모드 설정을 무시하고 라이트모드를 강제 적용하세요.

모든 HTML/CSS에 아래 코드를 반드시 포함하세요:

```html
<!-- HTML <meta> 또는 <head> 안 -->
<meta name="color-scheme" content="light only">
```

```css
/* 전역 CSS */
:root {
  color-scheme: light only;
}

* {
  color-scheme: light;
}
```

```jsx
// React의 경우 최상위 컨테이너에 style 속성 추가
<div style={{ colorScheme: 'light' }}>
```

Tailwind를 쓴다면 `dark:` prefix가 붙은 클래스를 **절대 사용하지 마세요.** 다크모드 관련 CSS 미디어 쿼리(`prefers-color-scheme: dark`)도 작성하지 마세요.

---

## 컬러 시스템

4가지 테마 중 하나를 선택해 사용합니다. 각 테마는 **배경색 → 서브타이틀 색 → 태그 배경/테두리/텍스트 → 보내기 버튼** 색이 세트로 구성됩니다.

### 1. Blue (기본 테마)
| 역할 | 토큰 | 값 |
|------|------|-----|
| 카드 배경 | `brand/main/blue/tint` | `#e1eaff` |
| 서브타이틀 텍스트 | `brand/main/blue/primary` | `#3f3fff` |
| 태그 배경 | `illustration/blue/6` | `#baceff` |
| 태그 테두리 | `illustration/blue/4` | `#7da0fe` |
| 태그 텍스트 | `brand/blue/1` | `#281e5f` |
| 보내기 버튼 배경 | `brand/main/blue/tint` | `#e1eaff` |
| 보내기 버튼 텍스트 | `brand/main/blue/primary` | `#3f3fff` |

### 2. Teal
| 역할 | 값 |
|------|-----|
| 카드 배경 | `#d1f4f1` |
| 서브타이틀 텍스트 | `brand/teal/1` = `#0b3c4b` |
| 태그 배경 | `#9deee6` |
| 태그 테두리 | `brand/teal/3` = `#59b1a7` |
| 태그 텍스트 | `brand/teal/2` = `#23667b` |
| 보내기 버튼 배경 | `#9deee6` |
| 보내기 버튼 텍스트 | `brand/teal/1` = `#0b3c4b` |

### 3. Pink
| 역할 | 값 |
|------|-----|
| 카드 배경 | `#efd9f9` |
| 서브타이틀 텍스트 | `#6b0147` |
| 태그 배경 | `#edc3ff` |
| 태그 테두리 | `#df93ff` |
| 태그 텍스트 | `#6b0147` |
| 보내기 버튼 배경 | `#edc3ff` |
| 보내기 버튼 텍스트 | `#6b0147` |

### 4. Yellow
| 역할 | 값 |
|------|-----|
| 카드 배경 | `#fff1bf` |
| 서브타이틀 텍스트 | `#b33700` |
| 태그 배경 | `#ffdd99` |
| 태그 테두리 | `illustration/brown/4` = `#d3a956` |
| 태그 텍스트 | `#b33700` |
| 보내기 버튼 배경 | `illustration/brown/5` = `#f0db93` |
| 보내기 버튼 텍스트 | `#b33700` |

### 공통 색상
| 역할 | 토큰 | 값 |
|------|------|-----|
| 기본 텍스트 (타이틀, 본문) | `brand/basic/black` | `#000000` |
| 흰 배경 (입력창, 버튼) | `brand/basic/white` | `#ffffff` |
| CTA 버튼 배경 | `brand/basic/black` | `#000000` |
| CTA 버튼 텍스트 | `brand/basic/white` | `#ffffff` |
| 콘텐츠 영역 배경 | — | `rgba(255,255,255,0.5)` |

---

## 타이포그래피

폰트 패밀리: **Pretendard** (모든 텍스트에 사용)

| 요소 | 폰트 웨이트 | 사이즈 | Line Height | 기타 |
|------|------------|--------|-------------|------|
| 서브타이틀 | Medium (500) | 24px | 34px | — |
| 타이틀 | Bold (700) | 50px | 60px | — |
| 태그 텍스트 | SemiBold (600) | 20px | 28px | — |
| 입력창 placeholder | Regular (400) | 22px | 32px | — |
| 보내기 버튼 텍스트 | SemiBold (600) | 20px | 28px | — |
| 본문 텍스트 | Regular (400) | 22px | 32px | — |
| CTA 버튼 텍스트 | Bold (700) | 30px | 35px | letter-spacing: -0.5px |
| 플레이리스트 제목 | Bold (700) | 22px | 30px | letter-spacing: -0.66px |
| 플레이리스트 출처 | Medium (500) | 18px | normal | opacity: 0.5 |

---

## 레이아웃 & 스페이싱

### 카드 컨테이너
- 너비: `530px`
- 높이: `1038px`
- 패딩: `100px` (상하) / `50px` (좌우)
- 자식 간격 (gap): `30px`
- 정렬: 세로 방향, 가운데 정렬

### 헤더 영역 (서브타이틀 + 타이틀)
- 너비: `271px`
- gap: `10px`
- 텍스트 정렬: 가운데

---

## 컴포넌트 스펙

### 태그 (분류 버튼)
- 높이: `42px`
- 좌우 패딩: `15px`, 상하 패딩: `1px`
- border-radius: `6px`
- 테두리: `1px solid`
- gap (태그들 사이): `10px`

### 콘텐츠 영역 (빈 카드)
- 높이: `368px`
- border-radius: `30px`
- 배경: `rgba(255,255,255,0.5)`
- 너비: 카드 너비에서 좌우 패딩 제외한 전체 (`100%`)

### 입력창 (텍스트 입력 + 보내기)
- 전체 높이: `52px`
- 배경: `white`
- border-radius: `30px`
- 좌 패딩: `22px`, 우 패딩: `5px`, 상하 패딩: `5px`
- 내부 버튼 (보내기): 높이 `42px`, border-radius `30px`, 좌우 패딩 `15px`

### CTA 버튼 (선물 자세히 보기)
- 너비: `382px`
- 높이: `90px`
- border-radius: `68px`
- 좌우 패딩: `75px`, 상하 패딩: `32px`
- 배경: `#000000`
- 텍스트: `#ffffff`

---

## 플레이리스트 컴포넌트

Figma source: https://www.figma.com/design/C6PIvbjgPxGvbVI8Lbj2fB/Untitled?node-id=16-720

"플레이리스트를 만들어줘", "음악 목록", "playlist" 등을 요청받으면 **추가 질문 없이 바로 아래 Figma 스펙 레이아웃으로 구현**하세요. 사용자가 별도의 레이아웃을 요청하지 않는 한 이 구조가 기본값입니다.

### 전체 래퍼
- 배경: `white`
- border-radius: `12px`
- 패딩: `20px` (상하) / `32px` (좌우)
- 내부 리스트 너비: `406px`
- 리스트 아이템 gap: `30px`

### 플레이리스트 아이템 (line)
각 아이템은 썸네일 + 텍스트 + 재생버튼으로 구성됩니다:

```
[썸네일 100×100] [제목 / 출처]              [▶ 재생버튼]
────────────────────────────────────────── (구분선)
```

**썸네일**
- 크기: `100px × 100px`
- border-radius: `6px`
- 테두리: `1px solid rgba(0,0,0,0.2)`
- object-fit: cover

**텍스트 영역**
- 제목: Pretendard Bold, 22px, line-height 30px, letter-spacing -0.66px, 색상 `#000000`
- 출처(FLO): Pretendard Medium, 18px, 색상 `#000000`, opacity `0.5`
- 제목과 출처 사이 gap: `5px`

**재생 버튼 (btn_play)**
- 전체 크기: `48px × 48px` (원형)
- 아이콘: GitHub 에셋의 `btn_play.svg` 또는 `icon_play.svg` 사용
- 아이콘 내부 크기: `18px × 18px`, 버튼 내 위치: left `14px`, top `15px`

**아이템 간 구분선**
- 높이: `1px`
- 색상: `rgba(0,0,0,0.1)` (얇은 수평선)
- 너비: `100%`

### 플레이리스트 React + Tailwind 예시

```jsx
const items = [
  { title: '외힙 붐은 왔다', source: 'FLO', thumb: '...' },
  { title: '오? 좀 느낌 있는데?\n하는 외힙 🔥', source: 'FLO', thumb: '...' },
];

// btn_play 아이콘: GitHub의 asset/icon/btn_play.svg 사용
const btnPlayIcon = 'https://raw.githubusercontent.com/flo-olive/creative_guide/main/asset/icon/btn_play.svg';

<div className="bg-white rounded-[12px] px-[32px] py-[20px]" style={{ colorScheme: 'light' }}>
  <div className="flex flex-col gap-[30px] w-[406px]">
    {items.map((item, i) => (
      <div key={i}>
        {/* 아이템 행 */}
        <div className="flex gap-[20px] items-center">
          <img
            src={item.thumb}
            className="w-[100px] h-[100px] rounded-[6px] border border-black/20 object-cover shrink-0"
          />
          <div className="flex flex-1 items-center">
            <div className="flex flex-col gap-[5px] flex-1">
              <p className="font-bold text-[22px] leading-[30px] tracking-[-0.66px] text-black whitespace-pre-line">
                {item.title}
              </p>
              <p className="font-medium text-[18px] text-black/50">
                {item.source}
              </p>
            </div>
            {/* 재생 버튼 */}
            <div className="relative w-[48px] h-[48px] shrink-0">
              <img src={btnPlayIcon} className="w-full h-full" />
            </div>
          </div>
        </div>
        {/* 구분선 (마지막 아이템 제외) */}
        {i < items.length - 1 && (
          <div className="w-full h-px bg-black/10 mt-[30px]" />
        )}
      </div>
    ))}
  </div>
</div>
```

---

## 에셋 (아이콘 & 로딩)

GitHub 저장소: `https://github.com/flo-olive/creative_guide`
Raw 파일 base URL: `https://raw.githubusercontent.com/flo-olive/creative_guide/main/`

아이콘이나 로딩 이미지가 필요할 때는 **반드시 이 저장소의 파일을 사용**하세요. 임의의 외부 아이콘 라이브러리(Heroicons, FontAwesome 등)를 사용하지 마세요.

### 아이콘 목록 (`asset/icon/`)

| 파일명 | 용도 |
|--------|------|
| `btn_play.svg` | 재생 버튼 (플레이리스트, 미니플레이어) |
| `icon_alarm.svg` | 알림 |
| `icon_check.svg` | 체크 / 완료 |
| `icon_gift.svg` | 선물 |
| `icon_like.svg` | 좋아요 / 하트 |
| `icon_link.svg` | 링크 복사 |
| `icon_music.svg` | 음악 |
| `icon_play.svg` | 재생 (일반) |
| `icon_refresh.svg` | 새로고침 |
| `icon_search.svg` | 검색 |
| `icon_write.svg` | 쓰기 / 편집 |

**사용 예시:**
```jsx
// SVG를 raw URL로 직접 img 태그에 사용
<img src="https://raw.githubusercontent.com/flo-olive/creative_guide/main/asset/icon/icon_gift.svg" alt="선물" />

// CSS background-image로도 사용 가능
background-image: url('https://raw.githubusercontent.com/flo-olive/creative_guide/main/asset/icon/icon_search.svg');
```

### 로딩 애니메이션 (`asset/loading.json`)

로딩 스피너/애니메이션이 필요할 때는 Lottie 파일(`loading.json`)을 사용하세요.

```
URL: https://raw.githubusercontent.com/flo-olive/creative_guide/main/asset/loading.json
```

**Lottie 사용 예시 (React):**
```jsx
import Lottie from 'lottie-react';

// fetch로 불러오거나 직접 URL 참조
<Lottie
  path="https://raw.githubusercontent.com/flo-olive/creative_guide/main/asset/loading.json"
  loop
  autoplay
/>
```

**순수 HTML/JS 환경:**
```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/lottie-web/5.12.2/lottie.min.js"></script>
<div id="loading-container"></div>
<script>
  lottie.loadAnimation({
    container: document.getElementById('loading-container'),
    path: 'https://raw.githubusercontent.com/flo-olive/creative_guide/main/asset/loading.json',
    renderer: 'svg',
    loop: true,
    autoplay: true,
  });
</script>
```

---

## 코드 작성 규칙

1. **라이트모드 강제**: `color-scheme: light only` 항상 적용. `dark:` Tailwind 클래스 사용 금지.

1-a. **인터랙션 효과 금지 (명시적 요청 없을 시)**: hover, focus, active, pressed 등의 상태 스타일을 임의로 추가하지 마세요. CSS `transition`, `animation`, `transform` 효과도 사용자가 요청할 때만 작성합니다. Tailwind의 `hover:`, `focus:`, `active:` prefix를 사용하지 마세요.

1-b. **Shadow 효과 금지 (명시적 요청 없을 시)**: `box-shadow`, `drop-shadow`, `filter: drop-shadow()` 등 모든 그림자 효과를 임의로 추가하지 마세요. Tailwind의 `shadow-*` 클래스도 사용하지 마세요. Figma 원본 스펙에 명시된 경우에만 적용합니다.

2. **항상 Pretendard 폰트를 사용**하세요. 없는 환경이면 Noto Sans KR을 fallback으로 사용하세요.

3. **테마는 4가지 중 하나**를 선택합니다. 여러 테마를 함께 보여줄 때는 구조는 동일하게 유지하고 색만 교체하세요.

4. **border-radius 값을 정확히 지키세요**:
   - 태그: `6px` / 썸네일: `6px`
   - 플레이리스트 래퍼: `12px`
   - 콘텐츠 영역, 입력창: `30px`
   - 보내기 버튼: `30px`
   - CTA 버튼: `68px`

5. **아이콘은 GitHub 에셋만 사용** — `flo-olive/creative_guide` 저장소의 SVG 파일을 raw URL로 사용하세요.

6. **로딩 애니메이션은 Lottie** — `loading.json`을 lottie-web 또는 lottie-react로 재생하세요.

7. **CTA 버튼은 항상 검정 배경 + 흰 텍스트**로 유지합니다 (테마에 관계없이 동일).

8. Tailwind를 쓰는 프로젝트라면 Tailwind 클래스로, CSS-in-JS라면 그에 맞게, 순수 CSS라면 CSS 변수로 변환하세요.

---

## 빠른 참고 - React + Tailwind 예시 (Blue 테마 카드)

```jsx
// 최상위에 color-scheme 라이트 강제
<div style={{ colorScheme: 'light' }} className="flex flex-col items-center gap-[30px] px-[50px] py-[100px] bg-[#e1eaff] w-[530px] h-[1038px]">

  {/* 헤더 */}
  <div className="flex flex-col items-center gap-[10px] text-center w-[271px]">
    <p className="font-medium text-[24px] leading-[34px] text-[#3f3fff]">서브타이틀 텍스트</p>
    <p className="font-bold text-[50px] leading-[60px] text-black">타이틀 텍스트</p>
  </div>

  {/* 태그 */}
  <div className="flex gap-[10px] justify-center">
    {['분류1','분류2','분류3','분류4'].map(tag => (
      <div key={tag} className="h-[42px] px-[15px] py-px rounded-[6px] bg-[#baceff] border border-[#7da0fe] flex items-center justify-center">
        <span className="font-semibold text-[20px] leading-[28px] text-[#281e5f] whitespace-nowrap">{tag}</span>
      </div>
    ))}
  </div>

  {/* 콘텐츠 영역 */}
  <div className="w-full h-[368px] rounded-[30px] bg-white/50" />

  {/* 입력창 */}
  <div className="w-full h-[52px] rounded-[30px] bg-white flex items-center pl-[22px] pr-[5px] py-[5px] gap-[10px]">
    <span className="flex-1 text-[22px] leading-[32px] text-black truncate">텍스트 입력하기</span>
    <div className="h-[42px] px-[15px] py-px rounded-[30px] bg-[#e1eaff] flex items-center">
      <span className="font-semibold text-[20px] leading-[28px] text-[#3f3fff] whitespace-nowrap">보내기</span>
    </div>
  </div>

  {/* 본문 */}
  <p className="text-[22px] leading-[32px] text-black text-center w-full">본문 텍스트는 이렇게 표시됩니다</p>

  {/* CTA 버튼 */}
  <div className="w-[382px] h-[90px] rounded-[68px] bg-black flex items-center justify-center px-[75px] py-[32px]">
    <span className="font-bold text-[30px] leading-[35px] text-white tracking-[-0.5px] whitespace-nowrap">선물 자세히 보기</span>
  </div>

</div>
```
