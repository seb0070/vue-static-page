<template>
  <div class="app-shell" :class="{ 'is-day': !isNight }">
    <!-- 장식 배경 -->
    <div class="sky-layer" aria-hidden="true">
      <div class="moon"></div>
      <div class="stars">
        <span v-for="n in 25" :key="n" class="star"></span>
      </div>
      <div class="cloud cloud-1"></div>
      <div class="cloud cloud-2"></div>
      <div class="cloud cloud-3"></div>
      <div class="lantern-wrap">
        <div class="lantern" v-for="n in 3" :key="n"></div>
      </div>
    </div>

    <!-- 메인 -->
    <header class="topbar">
      <div class="brand">
        <span class="logo-dot"></span>
        <span class="logo-text">Chuseok 2025</span>
      </div>
      <div class="top-actions">
        <button class="top-btn" @click="toggleNight">
          <span v-if="isNight">🌕 달빛모드</span>
          <span v-else>🌅 새벽노을</span>
        </button>
      </div>
    </header>

    <main class="page">
      <!-- 히어로 -->
      <section class="hero">
        <div class="hero-left">
          <p class="hero-tag">🍂 한가위 특별 페이지</p>
          <h1 class="hero-title">
            넉넉한 보름달 아래
            <span>당신께 마음을 보냅니다.</span>
          </h1>
          <p class="hero-sub">
            2025년 9월의 추석을 위한 작은 웹 카드입니다.
            가족, 친구, 팀원에게 링크만 보내도 기분 좋게 열어볼 수 있어요.
          </p>
          <div class="hero-actions">
            <button class="cta" @click="scrollToWishes">인사 보기</button>
            <button class="ghost" @click="toggleNight">
              {{ isNight ? '아침으로 보기' : '달빛으로 보기' }}
            </button>
          </div>
          <div class="meta-row">
            <div class="meta">
              <p class="meta-label">올해 한가위</p>
              <p class="meta-value">2025 · 음력 8월 15일</p>
            </div>
            <div class="meta">
              <p class="meta-label">전하는 마음</p>
              <p class="meta-value">행복 · 건강 · 풍요</p>
            </div>
          </div>
        </div>

        <div class="hero-card">
          <div class="hero-card-inner">
            <p class="card-caption">오늘의 덕담</p>
            <p class="card-text">
              올 한가위는
              <strong>보름달만큼</strong> 환하고
              <strong>송편만큼</strong> 꽉 찬 날이 되길 바랄게요.
            </p>
            <p class="card-small">멀리서도 마음은 가까이 💌</p>
            <div class="divider"></div>
            <ul class="bless-list">
              <li>집에는 웃음이</li>
              <li>몸에는 건강이</li>
              <li>마음에는 평안이</li>
            </ul>
            <p class="card-footer">— 추석을 기다리는 사람 드림</p>
          </div>
        </div>
      </section>

      <!-- 덕담 카드 -->
      <section ref="wishesRef" class="wish-section">
        <h2 class="section-title">보내기 좋은 한가위 인사</h2>
        <p class="section-sub">
          아래 문구는 살짝만 고쳐서 카톡/메일로 보내도 어색하지 않게 맞춰놨어요.
        </p>
        <div class="wish-grid">
          <article class="wish" v-for="wish in wishes" :key="wish.title">
            <h3>{{ wish.title }}</h3>
            <p>{{ wish.body }}</p>
            <button class="copy-btn" @click="copyText(wish.body)">복사</button>
          </article>
        </div>
      </section>
    </main>

    <!-- 푸터/장식 -->
    <footer class="footer">
      <div class="ground"></div>
      <div class="rabbit" aria-label="달을 바라보는 토끼"></div>
      <p class="foot-text">2025 Chuseok • Vue + TS + Vite</p>
    </footer>
  </div>
</template>

<script setup lang="ts">
import { onMounted, ref } from 'vue'

const isNight = ref(true)
const wishesRef = ref<HTMLElement | null>(null)

const wishes = [
  {
    title: '가족에게',
    body: '풍성한 한가위 보내시고 올 한해도 건강하고 행복하게 지내요. 맛있는 거 많이 드시고 곧 뵙겠습니다!'
  },
  {
    title: '친구에게',
    body: '이번 추석에도 우리 우정 꽉 채워두자 😊 멀리 있어도 마음은 옆자리! 맛난 거 먹고 인증 보내~'
  },
  {
    title: '직장/팀원에게',
    body: '항상 함께해 주셔서 감사합니다. 명절 동안은 푹 쉬시고, 연휴 끝나면 또 힘차게 달려봐요!'
  },
  {
    title: '나에게',
    body: '올해도 잘 해냈어. 지금은 잠깐 쉬는 시간. 천천히 숨 고르고 다시 시작하자 ✨'
  }
]

const toggleNight = () => {
  isNight.value = !isNight.value
  const root = document.documentElement
  if (isNight.value) {
    root.style.setProperty('--bg-top', '#0f172a')
    root.style.setProperty('--bg-bottom', '#1f2937')
    root.style.setProperty('--accent', '#f97316')
  } else {
    root.style.setProperty('--bg-top', '#f97316')
    root.style.setProperty('--bg-bottom', '#fde68a')
    root.style.setProperty('--accent', '#0f172a')
  }
}

const scrollToWishes = () => {
  wishesRef.value?.scrollIntoView({ behavior: 'smooth', block: 'start' })
}

const copyText = async (text: string) => {
  try {
    await navigator.clipboard.writeText(text)
    // 간단한 피드백
    alert('인사말이 복사됐어요! 붙여넣기만 하세요 🎉')
  } catch (e) {
    alert('복사를 지원하지 않는 환경이에요. 직접 복사해주세요 🙏')
  }
}

onMounted(() => {
  // 초기 컬러 세팅
  const root = document.documentElement
  root.style.setProperty('--bg-top', '#0f172a')
  root.style.setProperty('--bg-bottom', '#1f2937')
  root.style.setProperty('--accent', '#f97316')
})
</script>

<style scoped>
:global(:root) {
  --bg-top: #0f172a;
  --bg-bottom: #1f2937;
  --accent: #f97316;
  --surface: rgba(15, 23, 42, 0.55);
  --border: rgba(255, 255, 255, 0.08);
  --radius-lg: 1.6rem;
  --gap: 1.5rem;
}

.app-shell {
  min-height: 100vh;
  background:
      radial-gradient(circle at 12% 20%, rgba(226, 232, 255, 0.12), transparent 50%),
      linear-gradient(180deg, var(--bg-top) 0%, var(--bg-bottom) 100%);
  color: #fff;
  position: relative;
  display: flex;
  flex-direction: column;
  overflow-x: hidden;
}

.is-day .moon {
  filter: saturate(0.4) brightness(1.05);
}
.is-day .cloud {
  background: rgba(255, 255, 255, 0.45);
}

.sky-layer {
  position: fixed;
  inset: -3rem 0 auto 0;
  height: 390px;
  pointer-events: none;
  z-index: 0;
  overflow: visible;
}

.moon {
  position: absolute;
  top: 4.1rem;
  right: clamp(1.8rem, 6vw, 4.5rem);
  width: clamp(6.5rem, 11vw, 8.5rem);
  aspect-ratio: 1;
  background: radial-gradient(circle, #ffffff 0%, #fde68a 40%, rgba(255, 255, 255, 0) 70%);
  border-radius: 9999px;
  box-shadow: 0 0 90px rgba(252, 211, 77, 0.7);
  animation: moon-float 4.5s ease-in-out infinite;
}
@keyframes moon-float {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(5px); }
}

.stars {
  position: absolute;
  inset: 0;
}
.star {
  position: absolute;
  width: 3px;
  height: 3px;
  background: rgba(255, 255, 255, 0.6);
  border-radius: 9999px;
  animation: twinkle 4s ease-in-out infinite;
}
.star:nth-child(odd) { width: 2px; height: 2px; opacity: 0.7; }
.star:nth-child(1) { top: 18%; left: 6%; }
.star:nth-child(2) { top: 12%; left: 28%; animation-delay: 1s; }
.star:nth-child(3) { top: 7%; left: 48%; animation-delay: 2.1s; }
.star:nth-child(4) { top: 16%; left: 66%; animation-delay: 0.4s; }
.star:nth-child(5) { top: 3%; left: 82%; animation-delay: 2.8s; }
/* 나머지는 랜덤해보이는 위치로 */
@keyframes twinkle {
  0%, 100% { opacity: 0.2; transform: scale(1); }
  50% { opacity: 1; transform: scale(1.25); }
}

.cloud {
  position: absolute;
  top: 6.2rem;
  width: 11rem;
  height: 3.1rem;
  background: rgba(226, 232, 255, 0.22);
  border-radius: 9999px;
  filter: blur(1px);
  animation: cloud-move 26s linear infinite;
}
.cloud-1 { left: -10%; top: 7rem; animation-delay: 0s; }
.cloud-2 { left: -25%; top: 9rem; animation-delay: 5s; opacity: 0.5; }
.cloud-3 { left: -35%; top: 5rem; animation-delay: 10s; opacity: 0.8; }

@keyframes cloud-move {
  0% { transform: translateX(0); }
  100% { transform: translateX(150vw); }
}

.lantern-wrap {
  position: absolute;
  left: clamp(1rem, 4vw, 3.5rem);
  top: 1rem;
  display: flex;
  gap: 1rem;
}
.lantern {
  width: 1.5rem;
  height: 3.6rem;
  background: radial-gradient(circle, rgba(251, 146, 60, 1) 0%, rgba(180, 83, 9, 1) 90%);
  border: 2px solid rgba(254, 249, 195, 0.75);
  border-radius: 9999px;
  box-shadow: 0 6px 25px rgba(251, 146, 60, 0.5);
  animation: swing 2.7s ease-in-out infinite;
  transform-origin: top;
}
.lantern:nth-child(2) { animation-delay: 0.2s; }
.lantern:nth-child(3) { animation-delay: 0.4s; }

@keyframes swing {
  0%, 100% { transform: rotate(0deg); }
  50% { transform: rotate(4deg); }
}

/* 상단바 */
.topbar {
  position: sticky;
  top: 0;
  z-index: 10;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: .9rem clamp(1.1rem, 4vw, 2.6rem);
  background: linear-gradient(180deg, rgba(15, 23, 42, 0.7) 0%, rgba(15, 23, 42, 0) 100%);
  backdrop-filter: blur(16px);
}
.brand {
  display: flex;
  align-items: center;
  gap: .5rem;
}
.logo-dot {
  width: .55rem;
  aspect-ratio: 1;
  background: #fde68a;
  border-radius: 9999px;
  box-shadow: 0 0 14px rgba(254, 243, 199, 0.6);
}
.logo-text {
  font-weight: 600;
  letter-spacing: .02em;
}
.top-actions {
  display: flex;
}
.top-btn {
  background: rgba(15, 23, 42, 0.4);
  border: 1px solid rgba(255, 255, 255, 0.04);
  border-radius: 9999px;
  padding: .35rem .9rem;
  color: #e2e8f0;
  font-weight: 500;
  cursor: pointer;
}

/* 페이지 본문 */
.page {
  position: relative;
  z-index: 1;
  max-width: 1180px;
  width: min(100%, 1180px);
  margin: 0 auto;
  padding: clamp(1.5rem, 3vw, 2.4rem);
  padding-bottom: 4.5rem;
  display: flex;
  flex-direction: column;
  gap: clamp(2rem, 4vw, 3rem);
}

.hero {
  display: grid;
  grid-template-columns: 1.1fr .85fr;
  gap: clamp(1.6rem, 3vw, 2.4rem);
  align-items: center;
  margin-top: 1rem;
}
.hero-left {
  max-width: 34rem;
}
.hero-tag {
  display: inline-flex;
  gap: .4rem;
  align-items: center;
  background: rgba(15, 23, 42, 0.45);
  border: 1px solid rgba(252, 211, 77, 0.38);
  padding: .3rem .85rem;
  border-radius: 9999px;
  font-size: .72rem;
  margin-bottom: 1.25rem;
  backdrop-filter: blur(12px);
}
.hero-title {
  font-size: clamp(2.6rem, 4.2vw, 3.4rem);
  line-height: 1.03;
  letter-spacing: -.01em;
  margin-bottom: 1.1rem;
  text-wrap: balance;
}
.hero-title span {
  display: block;
  font-size: clamp(1.5rem, 2.6vw, 2.2rem);
  background: linear-gradient(90deg, #fde68a 0%, #f97316 50%, #f472b6 100%);
  -webkit-background-clip: text;
  color: transparent;
  margin-top: .6rem;
}
.hero-sub {
  color: rgba(241, 245, 249, 0.75);
  max-width: 30rem;
  line-height: 1.5;
  margin-bottom: 1.25rem;
}
.hero-actions {
  display: flex;
  gap: .8rem;
  flex-wrap: wrap;
  margin-bottom: 1.4rem;
}
.cta, .ghost {
  border: none;
  border-radius: 9999px;
  padding: .6rem 1.3rem;
  font-weight: 600;
  cursor: pointer;
}
.cta {
  background: radial-gradient(circle, #fdba74 0%, #f97316 65%);
  color: #0f172a;
  box-shadow: 0 12px 25px rgba(249, 115, 22, 0.35);
}
.ghost {
  background: rgba(15, 23, 42, 0.25);
  border: 1px solid rgba(148, 163, 184, 0.22);
  color: #e2e8f0;
}
.meta-row {
  display: flex;
  gap: 1rem;
  flex-wrap: wrap;
}
.meta {
  background: rgba(15, 23, 42, 0.25);
  border: 1px solid rgba(255, 255, 255, 0.03);
  border-radius: 1rem;
  padding: .5rem .9rem .6rem;
}
.meta-label {
  font-size: .65rem;
  text-transform: uppercase;
  opacity: .7;
  margin-bottom: .25rem;
  letter-spacing: .08em;
}
.meta-value {
  font-weight: 500;
}

.hero-card {
  background: rgba(15, 23, 42, 0.55);
  border: 1px solid rgba(255, 255, 255, 0.06);
  border-radius: 1.5rem;
  backdrop-filter: blur(15px);
  overflow: hidden;
  position: relative;
  box-shadow: 0 24px 60px rgba(15, 23, 42, 0.4);
  min-height: 16.5rem;
}
.hero-card::before {
  content: '';
  position: absolute;
  inset: -40% 10% auto -40%;
  height: 55%;
  background: radial-gradient(circle, rgba(249, 115, 22, 0.45) 0%, rgba(15, 23, 42, 0) 60%);
  pointer-events: none;
}
.hero-card-inner {
  position: relative;
  padding: 1.5rem 1.6rem 1.5rem;
}
.card-caption {
  font-size: .72rem;
  opacity: .75;
  letter-spacing: .08em;
  text-transform: uppercase;
  margin-bottom: .6rem;
}
.card-text {
  font-size: 1.05rem;
  line-height: 1.5;
  margin-bottom: 1rem;
}
.card-text strong {
  color: #fde68a;
  font-weight: 700;
}
.card-small {
  font-size: .8rem;
  opacity: .7;
}
.divider {
  height: 1px;
  background: linear-gradient(90deg, rgba(248, 250, 252, 0.08) 0%, rgba(248, 250, 252, 0) 100%);
  margin: 1.15rem 0 .9rem;
}
.bless-list {
  display: grid;
  gap: .35rem;
  margin-bottom: .9rem;
}
.bless-list li {
  display: flex;
  gap: .45rem;
  align-items: center;
  font-size: .85rem;
}
.bless-list li::before {
  content: '•';
  color: #fde68a;
}
.card-footer {
  font-size: .7rem;
  opacity: .6;
}

/* 덕담 섹션 */
.wish-section {
  margin-top: .5rem;
}
.section-title {
  font-size: 1.4rem;
  font-weight: 600;
}
.section-sub {
  color: rgba(241, 245, 249, 0.5);
  margin-top: .3rem;
  margin-bottom: 1.25rem;
}
.wish-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(13.5rem, 1fr));
  gap: 1rem;
}
.wish {
  background: rgba(15, 23, 42, 0.4);
  border: 1px solid rgba(255, 255, 255, 0.02);
  border-radius: 1.2rem;
  padding: 1.1rem 1rem 1.05rem;
  min-height: 8.8rem;
  display: flex;
  flex-direction: column;
  gap: .6rem;
  position: relative;
  overflow: hidden;
  transition: transform .15s ease-out, background .15s ease-out;
}
.wish::after {
  content: '';
  position: absolute;
  inset: -30% 40% auto -30%;
  height: 50%;
  background: radial-gradient(circle, rgba(249, 115, 22, 0.23) 0%, rgba(15, 23, 42, 0) 65%);
  pointer-events: none;
}
.wish:hover {
  transform: translateY(-3px);
  background: rgba(15, 23, 42, 0.65);
}
.wish h3 {
  font-weight: 600;
}
.wish p {
  color: rgba(241, 245, 249, 0.65);
  line-height: 1.35;
  flex: 1 1 auto;
}
.copy-btn {
  align-self: flex-start;
  background: rgba(252, 211, 77, 0.05);
  border: 1px solid rgba(252, 211, 77, 0.3);
  border-radius: 9999px;
  padding: .32rem .7rem;
  font-size: .68rem;
  color: #fff;
  cursor: pointer;
}

/* footer */
.footer {
  position: relative;
  height: 7.3rem;
  margin-top: auto;
  z-index: 1;
}
.ground {
  position: absolute;
  inset: auto -4rem 0 -4rem;
  height: 5.7rem;
  background: radial-gradient(circle at 50% 100%, #020617 50%, #0f172a 85%);
  border-top-left-radius: 50%;
  border-top-right-radius: 50%;
}
.rabbit {
  position: absolute;
  bottom: 1rem;
  right: 14%;
  width: 2.5rem;
  height: 2.95rem;
  background: radial-gradient(circle, #f8fafc 0%, #cbd5f5 80%);
  border-radius: 9999px 9999px 40% 40%;
  transform: rotate(-6deg);
  box-shadow: 0 10px 35px rgba(248, 250, 252, 0.55);
}
.rabbit::after {
  content: '';
  position: absolute;
  top: -1.8rem;
  left: .9rem;
  width: .55rem;
  height: 1.85rem;
  background: radial-gradient(circle, #f8fafc 0%, #cbd5f5 50%);
  border-radius: 9999px;
  transform: rotate(9deg);
}
.foot-text {
  position: absolute;
  bottom: .5rem;
  width: 100%;
  text-align: center;
  font-size: .68rem;
  color: rgba(241, 245, 249, 0.28);
}

/* 반응형 */
@media (max-width: 960px) {
  .hero {
    grid-template-columns: 1fr;
  }
  .hero-card {
    max-width: 28rem;
  }
  .sky-layer {
    height: 340px;
  }
}
@media (max-width: 650px) {
  .topbar {
    gap: 1rem;
  }
  .hero-title {
    font-size: clamp(2.3rem, 11vw, 2.9rem);
  }
  .hero-sub {
    max-width: none;
  }
  .hero-actions {
    flex-direction: row;
  }
  .wish-grid {
    grid-template-columns: 1fr;
  }
  .footer {
    height: 6.5rem;
  }
  .ground {
    height: 5.2rem;
  }
  .rabbit {
    right: 8%;
  }
}
@media (max-width: 460px) {
  .topbar {
    padding-inline: 1rem;
  }
  .hero-left {
    text-align: left;
  }
  .hero-actions {
    flex-wrap: wrap;
  }
  .cta, .ghost {
    width: fit-content;
  }
  .sky-layer {
    height: 300px;
  }
  .hero-card {
    border-radius: 1.2rem;
  }
}
</style>
