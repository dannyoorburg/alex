<template>
  <div class="contact">
    <section class="contact-section">

      <!-- Decorative stamp -->
      <div class="stamp stamp--top-right" aria-hidden="true">
        Reels with Rhythm.<br>Content with Heart.
      </div>

      <!-- "Thanks for visiting" label -->
      <span class="thanks-label" aria-hidden="true">Thanks for visiting</span>

      <!-- Left: polaroid photo frame -->
      <div class="polaroid">
        <div class="polaroid__image" aria-label="Decorative flower photo">
          🌻
        </div>
        <div class="polaroid__dots" aria-hidden="true">
          <span class="pdot" />
          <span class="pdot" />
          <span class="pdot" />
        </div>
      </div>

      <!-- Right: contact content -->
      <div class="contact-content">
        <div class="contact-banner">
          <h1 class="contact-title">Get in touch, let's chat</h1>
          <p class="contact-subtitle">
            Let's bring your story to life – I'd love to hear from you
          </p>
        </div>

        <div class="contact-details">
          <div class="contact-row">
            <span class="contact-icon" aria-hidden="true">
              <svg xmlns="http://www.w3.org/2000/svg" width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
                <rect x="2" y="4" width="20" height="16" rx="2" />
                <path d="m22 7-8.97 5.7a1.94 1.94 0 0 1-2.06 0L2 7" />
              </svg>
            </span>
            <a href="mailto:info@dreaminginreels.com" class="contact-link">info@dreaminginreels.com</a>
          </div>

          <div class="contact-row">
            <span class="contact-icon" aria-hidden="true">
              <svg xmlns="http://www.w3.org/2000/svg" width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
                <circle cx="12" cy="12" r="10" />
                <path d="M2 12h20" />
                <path d="M12 2a15.3 15.3 0 0 1 4 10 15.3 15.3 0 0 1-4 10 15.3 15.3 0 0 1-4-10 15.3 15.3 0 0 1 4-10z" />
              </svg>
            </span>
            <span class="contact-text">Sydney based. Working worldwide.</span>
          </div>
        </div>
      </div>

    </section>
  </div>
</template>

<script setup lang="ts"></script>

<style scoped>
/* ── Page wrapper ─────────────────────────────────────────── */
.contact-section {
  min-height: 100vh;
  padding: 1.5rem 4rem;
  position: relative;
  display: flex;
  align-items: center;
  gap: 3rem;
}

/* ── Stamp ────────────────────────────────────────────────── */
.stamp {
  position: absolute;
  font-family: 'Lato', sans-serif;
  font-size: 0.68rem;
  font-weight: 700;
  letter-spacing: 0.07em;
  text-transform: uppercase;
  color: #7a4028;
  border: 1.5px solid #b08070;
  border-radius: 6px;
  padding: 0.45rem 0.8rem;
  line-height: 1.5;
  text-align: center;
  background: rgba(247, 237, 224, 0.75);
  pointer-events: none;
  user-select: none;
  backdrop-filter: blur(2px);
}

.stamp--top-right {
  top: 3rem;
  right: 5rem;
}

/* ── "Thanks for visiting" ────────────────────────────────── */
.thanks-label {
  position: absolute;
  top: 5.5rem;
  left: 5rem;
  font-family: 'Dancing Script', cursive;
  font-size: clamp(1.6rem, 3vw, 2.2rem);
  font-weight: 700;
  color: #4a2010;
  pointer-events: none;
  user-select: none;
}

/* ── Polaroid photo frame ─────────────────────────────────── */
.polaroid {
  flex: 0 0 380px;
  background: #faf5ef;
  border-radius: 10px;
  padding: 1rem 1rem 0.8rem;
  box-shadow:
    0 6px 28px rgba(92, 42, 20, 0.14),
    0 1.5px 6px rgba(92, 42, 20, 0.08);
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.6rem;
  transform: rotate(-1.5deg);
  margin-top: 3rem;
  position: relative;
}

/* Pin decoration */
.polaroid::before {
  content: '';
  position: absolute;
  top: -10px;
  left: 50%;
  transform: translateX(-50%);
  width: 14px;
  height: 14px;
  border-radius: 50%;
  background: #c0b8ae;
  border: 2px solid #b0a89e;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.15);
  z-index: 2;
}

.polaroid__image {
  width: 100%;
  aspect-ratio: 4 / 5;
  background: #c9a882;
  border-radius: 4px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 5rem;
  overflow: hidden;
}

.polaroid__image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
}

.polaroid__dots {
  display: flex;
  gap: 8px;
  padding: 0.3rem 0;
}

.pdot {
  width: 12px;
  height: 12px;
  border-radius: 50%;
  background: #d4a999;
  opacity: 0.7;
}

/* ── Contact content (right side) ─────────────────────────── */
.contact-content {
  flex: 1;
  display: flex;
  flex-direction: column;
  gap: 2.5rem;
}

.contact-banner {
  background: rgba(245, 242, 238, 0.85);
  backdrop-filter: blur(4px);
  border-radius: 8px;
  padding: 3rem 3.5rem;
  display: flex;
  flex-direction: column;
  gap: 0.75rem;
}

.contact-title {
  font-family: 'Dancing Script', cursive;
  font-size: clamp(2.8rem, 6vw, 5rem);
  font-weight: 700;
  color: #4a2010;
  line-height: 1.15;
}

.contact-subtitle {
  font-family: 'Playfair Display', Georgia, serif;
  font-size: clamp(1rem, 1.8vw, 1.3rem);
  color: #5c2a14;
  font-style: italic;
}

/* ── Contact details rows ─────────────────────────────────── */
.contact-details {
  display: flex;
  flex-direction: column;
  gap: 1.2rem;
  padding-left: 1.5rem;
}

.contact-row {
  display: flex;
  align-items: center;
  gap: 1rem;
}

.contact-icon {
  color: #5c2a14;
  flex-shrink: 0;
  display: flex;
  align-items: center;
}

.contact-link {
  font-family: 'Playfair Display', Georgia, serif;
  font-size: 1.15rem;
  color: #5c2a14;
  text-decoration: none;
  transition: opacity 0.2s;
}

.contact-link:hover {
  opacity: 0.7;
  text-decoration: underline;
  text-underline-offset: 4px;
}

.contact-text {
  font-family: 'Playfair Display', Georgia, serif;
  font-size: 1.15rem;
  color: #5c2a14;
}

/* ── Responsive ───────────────────────────────────────────── */
@media (max-width: 900px) {
  .contact-section {
    flex-direction: column;
    padding: 3rem 2rem 4rem;
    min-height: auto;
    gap: 2rem;
  }

  .polaroid {
    flex: none;
    width: 280px;
    transform: none;
    margin-top: 4rem;
  }

  .thanks-label {
    top: 3.5rem;
    left: 2rem;
    font-size: 1.5rem;
  }

  .stamp--top-right {
    top: 1.5rem;
    right: 1.5rem;
  }

  .contact-banner {
    padding: 2rem 1.5rem;
  }

  .contact-content {
    align-items: center;
    text-align: center;
  }

  .contact-details {
    padding-left: 0;
    align-items: center;
  }
}
</style>
