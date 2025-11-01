<template>
  <main class="page">
    <!-- ================= HERO ================= -->
    <section class="hero">
      <div class="hero-aura" aria-hidden="true"></div>
      <div class="hero-moon" aria-hidden="true"></div>
      <div class="hero-pattern" aria-hidden="true"></div>

      <div class="hero-inner">
        <div class="hero-left">
          <p class="hero-pill">Chuseok · Harvest Moon</p>
          <h1 class="hero-title">
            달이 가장 예쁜 밤,<br />
            마음도 둥글어지는 한가위
          </h1>
          <p class="hero-subtitle">
            수확의 감사와 가족의 웃음, 그리고 달빛 아래의 추억.
            가을의 한가위를 담은 따뜻한 장면들을 모았습니다.
          </p>
          <div class="hero-actions">
            <a href="#story" class="btn primary">한가위 이야기 보기</a>
            <a href="#foods" class="btn ghost">맛있는 추석음식</a>
            <a href="#play" class="btn ghost">즐거운 전통놀이</a>
          </div>
        </div>

        <div class="hero-right">
          <p class="hero-tagline">“더도 말고<br />덜도 말고<br />이 날만 같아라.”</p>
          <p class="hero-small">가을이 기준이 되는 하루.</p>
        </div>
      </div>
    </section>

    <!-- ================= STORY ================= -->
    <section id="story" class="section story">
      <header class="section-head center">
        <p class="eyebrow">story of chuseok</p>
        <h2 class="section-title">풍요가 예절이 되던 날</h2>
        <p class="section-desc section-desc--spaced">
          익어가는 들판, 가득 찬 바구니, 반가운 얼굴들.
          가을의 한가위는 감사와 정성, 그리고 나눔으로 이어집니다.
        </p>
      </header>

      <div class="story-grid">
        <article class="story-card">
          <h3>달에게 올리는 마음</h3>
          <p>
            둥근 달을 보며 멀리 있는 가족의 안녕과 풍년을 빌었습니다.
            같은 달을 본다는 마음이 우리를 이어주었지요.
          </p>
        </article>
        <article class="story-card">
          <h3>나눔이 곧 복</h3>
          <p>
            햇곡식과 송편을 이웃과 나누며 “우리 함께 잘 지내자”는
            소박한 축복을 건넸습니다.
          </p>
        </article>
        <article class="story-card">
          <h3>뿌리를 기억하는 시간</h3>
          <p>
            조상께 감사드리고, 고향에서 오랜만에 모인 가족이
            웃음과 이야기로 가을 밤을 채웠습니다.
          </p>
        </article>
      </div>
    </section>

    <!-- ================= FOODS ================= -->
    <section id="foods" class="section foods">
      <header class="section-head">
        <p class="eyebrow">seasonal table</p>
        <h2 class="section-title">한가위의 맛과 마음</h2>
        <p class="section-desc section-desc--spaced">
          햇쌀로 빚은 떡, 정성 가득한 부침, 손님을 위한 달콤한 다과.
          보기만 해도 입에서 군침이 흐르는 한가위 음식입니다.
        </p>
      </header>

      <div class="card-grid">
        <article class="food-card">
          <img src="/images/songpyeon.png" alt="쑥송편" class="food-img" />
          <div class="food-body">
            <h3>🌿 쑥송편 – 푸른 향기로 빚은 소망의 떡</h3>
            <p>
              향긋한 쑥을 반죽에 고루 섞어 빚은 송편 한 알.
              은은한 향기 속에는 한가위의 정성과 소망이 깃들어 있습니다.
              쑥 향이 퍼지는 송편은 풍요로운 가을의 기운을 담은 선물,
              가족이 함께 웃으며 나누는 행복의 맛입니다.
            </p>
          </div>
        </article>

        <article class="food-card">
          <img src="/images/jeon.png" alt="전" class="food-img" />
          <div class="food-body">
            <h3>🥢 전 – 정성과 손맛이 어우러진 한가위의 향기</h3>
            <p>
              애호박전, 동태전, 산적, 육전까지—
              재료마다 고유의 맛과 향을 담아 부쳐낸 전은
              명절 밥상에 빠질 수 없는 풍요의 상징입니다.
              노릇노릇한 전 냄새가 부엌을 가득 채우면
              그곳엔 가족의 웃음과 따뜻한 정이 함께 피어납니다.
            </p>
          </div>
        </article>

        <article class="food-card">
          <img src="/images/hangwa.png" alt="한과" class="food-img" />
          <div class="food-body">
            <h3>🍯 한과 – 달콤함 속에 깃든 고운 마음</h3>
            <p>
              유과, 약과, 강정, 다식까지.
              한과는 고운 빛깔과 정갈한 모양으로 한가위의 품격을 더합니다.
              은은한 단맛 속에는 감사와 복을 비는 마음이 담겨 있고,
              한 입의 달콤함이 오래된 전통의 아름다움을 전합니다.
            </p>
          </div>
        </article>
      </div>
    </section>

    <!-- ================= PLAY ================= -->
    <section id="play" class="section play">
      <header class="section-head center">
        <p class="eyebrow">autumn play</p>
        <h2 class="section-title">달빛 아래서 이어가던 놀이</h2>
        <p class="section-desc section-desc--spaced">
          밥상 치우고 마당에 모이면, 거기서부터는 아이도 어른도 없었어요.
          손을 맞잡고, 윷을 던지고, 씨름판을 둘러싸고 환호했죠.
        </p>
      </header>

      <div class="card-grid">
        <article class="play-card">
          <div class="play-thumb">
            <img src="/images/play-kang.png" alt="강강술래" />
          </div>
          <div class="play-body">
            <h3>🌕 강강술래</h3>
            <p>
              달 밝은 가을밤, 모두가 손을 잡고 원을 그리며 노래하던 춤.
              느린 장단과 웃음이 마당을 한꺼번에 따뜻하게 만들었습니다.
            </p>
          </div>
        </article>

        <article class="play-card">
          <div class="play-thumb">
            <img src="/images/play-yut.png" alt="윷놀이" />
          </div>
          <div class="play-body">
            <h3>🥢 윷놀이</h3>
            <p>
              윷 네 개를 던져 도·개·걸·윷·모를 내며
              팀끼리 응원하고 놀던 한가위 대표 놀이.
              이겼다고 으스대고, 져도 다시 하자며 웃었어요.
            </p>
          </div>
        </article>

        <article class="play-card">
          <div class="play-thumb">
            <img src="/images/play-ssireum.png" alt="씨름" />
          </div>
          <div class="play-body">
            <h3>💪 씨름</h3>
            <p>
              모래 위에서 허리를 잡고 힘과 기술을 겨루던 시간.
              누가 이겨도 박수, 누가 져도 웃음.
              결국은 다 같이 즐기려고 벌이던 한판이었어요.
            </p>
          </div>
        </article>
      </div>
    </section>

    <!-- ================= FOOTER ================= -->
    <footer class="footer">
      <p>올가을에도 이렇게 단정하게, 이렇게 따뜻하게.</p>
      <small>© 2025 Chuseok · Autumn Page</small>
    </footer>
  </main>
</template>

<script setup lang="ts">
</script>

<style scoped>
/* ===== base ===== */
.page {
  min-height: 100vh;
  background: radial-gradient(circle at 15% 5%, #152032 0%, #0f172a 40%, #020617 85%);
  color: #e2e8f0;
  font-family: "Pretendard", "Noto Sans KR", system-ui, -apple-system, BlinkMacSystemFont,
  "Segoe UI", sans-serif;
  line-height: 1.6;
}

/* ===== hero ===== */
.hero {
  position: relative;
  min-height: 82vh;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 5.5rem 1.5rem 4.5rem;
  overflow: hidden;
}
.hero-aura {
  position: absolute;
  inset: 0;
  background: radial-gradient(circle at 30% 20%, rgba(249, 115, 22, 0.12), rgba(2, 6, 23, 0)),
  radial-gradient(circle at 95% 35%, rgba(248, 250, 252, 0.08), rgba(2, 6, 23, 0));
}
.hero-moon {
  position: absolute;
  top: -9rem;
  right: -6.5rem;
  width: min(440px, 48vw);
  aspect-ratio: 1/1;
  border-radius: 9999px;
  background: radial-gradient(circle, #ffe9bf 0%, #fbbf24 58%, rgba(17, 24, 39, 0) 78%);
  filter: drop-shadow(0 0 45px rgba(251, 191, 36, 0.5));
  opacity: 0.85;
}
.hero-pattern {
  position: absolute;
  right: 2.5rem;
  bottom: 2.5rem;
  width: 16rem;
  height: 16rem;
  background-image: radial-gradient(circle, rgba(251, 191, 36, 0.12) 1px, transparent 1px);
  background-size: 18px 18px;
  opacity: 0.22;
}
.hero-inner {
  position: relative;
  z-index: 5;
  width: min(1150px, 100%);
  display: grid;
  grid-template-columns: 1.05fr 0.6fr;
  gap: 2.3rem;
  align-items: center;
}
.hero-left {
  display: flex;
  flex-direction: column;
  gap: 1.1rem;
}
.hero-pill {
  display: inline-flex;
  gap: 0.35rem;
  align-items: center;
  background: rgba(15, 23, 42, 0.45);
  border: 1px solid rgba(251, 191, 36, 0.5);
  border-radius: 999px;
  padding: 0.35rem 1.05rem;
  font-size: 0.68rem;
  letter-spacing: 0.16em;
  text-transform: uppercase;
  width: fit-content;
}
.hero-title {
  font-size: clamp(2.5rem, 4.5vw, 3.5rem);
  line-height: 1.05;
}
.hero-subtitle {
  color: rgba(203, 213, 225, 0.9);
  line-height: 1.65;
  max-width: 34rem;
}
.hero-actions {
  display: flex;
  gap: 1rem;
  flex-wrap: wrap;
}
.btn {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  border-radius: 999px;
  padding: 0.7rem 1.4rem;
  font-weight: 500;
  border: 1px solid transparent;
  text-decoration: none;
  transition: 0.2s ease;
}
.btn.primary {
  background: linear-gradient(110deg, #f97316 0%, #fdae3e 45%, #f97316 100%);
  color: #0f172a;
  box-shadow: 0 16px 30px rgba(249, 115, 22, 0.25);
}
.btn.ghost {
  background: rgba(15, 23, 42, 0.35);
  border: 1px solid rgba(148, 163, 184, 0.35);
  color: #e2e8f0;
}
.hero-right {
  text-align: right;
  display: flex;
  flex-direction: column;
  gap: 0.7rem;
  align-items: flex-end;
}
.hero-tagline {
  font-size: 1.35rem;
  color: #fde68a;
  border-radius: 1.15rem;
  padding: 1.2rem 1.5rem;
  background: rgba(15, 23, 42, 0.5);
  border: 1px solid rgba(248, 250, 252, 0.08);
}
.hero-small {
  color: rgba(226, 232, 240, 0.6);
  font-size: 0.78rem;
}

/* ===== section base ===== */
.section {
  width: min(1100px, 100%);
  margin: 5.7rem auto 0;
  padding: 0 1.5rem;
}
.section-head {
  margin-bottom: 2.4rem;
}
.center {
  text-align: center;
}
.eyebrow {
  font-size: 0.68rem;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  color: rgba(252, 211, 77, 0.9);
}
.section-title {
  font-size: clamp(1.9rem, 3.1vw, 2.3rem);
  margin-bottom: 0.7rem;
}
.section-desc {
  color: #94a3b8;
  line-height: 1.65;
  max-width: 46rem;
  margin: 0 auto;
}
.section-desc--spaced {
  margin-bottom: 2.8rem;
}

/* ===== grids ===== */
.story-grid,
.card-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  gap: 1.8rem;
}

/* ===== story cards ===== */
.story-card {
  background: radial-gradient(circle at top, rgba(15, 23, 42, 0.35), rgba(2, 6, 23, 0));
  border: 1px solid rgba(148, 163, 184, 0.14);
  border-radius: 1.1rem;
  padding: 1.35rem 1.35rem 1.25rem;
  backdrop-filter: blur(10px);
  transition: 0.15s ease;
}
.story-card:hover {
  transform: translateY(-2px);
  border-color: rgba(248, 250, 252, 0.12);
}
.story-card h3 {
  margin-bottom: 0.4rem;
}

/* ===== foods ===== */
.food-card {
  background: rgba(15, 23, 42, 0.35);
  border: 1px solid rgba(148, 163, 184, 0.12);
  border-radius: 1.25rem;
  overflow: hidden;
  transition: 0.25s ease;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.25);
}
.food-card:hover {
  transform: translateY(-4px);
  border-color: rgba(252, 211, 77, 0.25);
  box-shadow: 0 14px 35px rgba(249, 115, 22, 0.2);
}
.food-img {
  width: 100%;
  height: 240px;
  object-fit: cover;
  background-color: rgba(30, 41, 59, 0.4);
}
.food-body {
  padding: 1.5rem 1.5rem 1.8rem;
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
  text-align: left;
}
.food-body h3 {
  font-size: 1.1rem;
  color: #fefce8;
}
.food-body p {
  font-size: 0.92rem;
  color: #cbd5e1;
  line-height: 1.7;
}

/* ===== play ===== */
.play-card {
  background: rgba(15, 23, 42, 0.35);
  border: 1px solid rgba(148, 163, 184, 0.12);
  border-radius: 1.25rem;
  overflow: hidden;
  transition: 0.25s ease;
}
.play-card:hover {
  transform: translateY(-4px);
  border-color: rgba(252, 211, 77, 0.25);
}
.play-thumb img {
  width: 100%;
  height: 240px;
  object-fit: cover;
}
.play-body {
  padding: 1.5rem 1.5rem 1.8rem;
  text-align: left;
}
.play-body h3 {
  margin-bottom: 0.5rem;
}
.play-body p {
  color: #cbd5e1;
  font-size: 0.9rem;
  line-height: 1.6;
}

/* ===== footer ===== */
.footer {
  text-align: center;
  padding: 4rem 1.5rem 3.4rem;
  color: rgba(226, 232, 240, 0.5);
  font-size: 0.8rem;
  margin-top: 5rem;
}

/* ===== responsive ===== */
@media (max-width: 940px) {
  .hero-inner {
    grid-template-columns: 1fr;
    text-align: center;
  }
  .hero-left {
    align-items: center;
  }
  .hero-right {
    display: none;
  }
  .hero-moon {
    right: -25vw;
    width: 70vw;
  }
  .hero {
    padding-top: 5rem;
  }
}
@media (max-width: 900px) {
  .story-grid,
  .card-grid {
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  }
}
@media (max-width: 640px) {
  .story-grid,
  .card-grid {
    grid-template-columns: 1fr;
  }
  .hero-actions {
    flex-direction: column;
    width: min(16rem, 100%);
  }
  .hero-title {
    font-size: 2.35rem;
  }
}

/* ===== 모바일 확장 (overflow fix 포함) ===== */
@media (max-width: 640px) {
  .page {
    background: radial-gradient(circle at 20% 10%, #182235 0%, #0f172a 40%, #020617 85%);
    overflow-x: hidden;
  }

  .section {
    width: 100%;
    max-width: none;
    padding: 0 1rem;
  }

  .food-card,
  .play-card {
    border-radius: 0;
    margin: 0 -1rem;
    width: calc(100% + 2rem); /* ✅ 오른쪽으로 벗어나지 않게 보정 */
  }
}

</style>