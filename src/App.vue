<template>
  <main id="app" :class="!darkMode ? 'dark' : ''">
    <section>
      <h1>We're launching soon</h1>
      <div class="counter">
        <div class="counter-block">
          <div class="counter-block__card">
            {{ countdown.days.toString().padStart(2, "0") }}
            <div class="counter-block__card-divider"></div>
          </div>
          <div class="counter-block__footer">DAYS</div>
        </div>
        <div class="counter-block">
          <div class="counter-block__card">
            {{ countdown.hours.toString().padStart(2, "0") }}
            <div class="counter-block__card-divider"></div>
          </div>
          <div class="counter-block__footer">HOURS</div>
        </div>
        <div class="counter-block">
          <div class="counter-block__card">
            {{ countdown.minutes.toString().padStart(2, "0") }}
            <div class="counter-block__card-divider"></div>
          </div>
          <div class="counter-block__footer">MINUTES</div>
        </div>
        <div class="counter-block">
          <div class="counter-block__card">
            {{ countdown.seconds.toString().padStart(2, "0") }}
            <div class="counter-block__card-divider"></div>
          </div>
          <div class="counter-block__footer">SECONDS</div>
        </div>
      </div>
    </section>
    <div class="dark-mode__toggler">
      <input type="checkbox" id="darkmode-toggle" v-model="darkMode" />
      <label for="darkmode-toggle">
        <svg
          version="1.1"
          class="sun"
          xmlns="http://www.w3.org/2000/svg"
          xmlns:xlink="http://www.w3.org/1999/xlink"
          x="0px"
          y="0px"
          viewBox="0 0 496 496"
          style="enable-background: new 0 0 496 496"
          xml:space="preserve"
        >
          <rect
            x="152.994"
            y="58.921"
            transform="matrix(0.3827 0.9239 -0.9239 0.3827 168.6176 -118.5145)"
            width="40.001"
            height="16"
          ></rect>
          <rect
            x="46.9"
            y="164.979"
            transform="matrix(0.9239 0.3827 -0.3827 0.9239 71.29 -12.4346)"
            width="40.001"
            height="16"
          ></rect>
          <rect
            x="46.947"
            y="315.048"
            transform="matrix(0.9239 -0.3827 0.3827 0.9239 -118.531 50.2116)"
            width="40.001"
            height="16"
          ></rect>

          <rect
            x="164.966"
            y="409.112"
            transform="matrix(-0.9238 -0.3828 0.3828 -0.9238 168.4872 891.7491)"
            width="16"
            height="39.999"
          ></rect>

          <rect
            x="303.031"
            y="421.036"
            transform="matrix(-0.3827 -0.9239 0.9239 -0.3827 50.2758 891.6655)"
            width="40.001"
            height="16"
          ></rect>

          <rect
            x="409.088"
            y="315.018"
            transform="matrix(-0.9239 -0.3827 0.3827 -0.9239 701.898 785.6559)"
            width="40.001"
            height="16"
          ></rect>

          <rect
            x="409.054"
            y="165.011"
            transform="matrix(-0.9239 0.3827 -0.3827 -0.9239 891.6585 168.6574)"
            width="40.001"
            height="16"
          ></rect>
          <rect
            x="315.001"
            y="46.895"
            transform="matrix(0.9238 0.3828 -0.3828 0.9238 50.212 -118.5529)"
            width="16"
            height="39.999"
          ></rect>
          <path
            d="M248,88c-88.224,0-160,71.776-160,160s71.776,160,160,160s160-71.776,160-160S336.224,88,248,88z M248,392
				c-79.4,0-144-64.6-144-144s64.6-144,144-144s144,64.6,144,144S327.4,392,248,392z"
          ></path>
          <rect x="240" width="16" height="72"></rect>
          <rect
            x="62.097"
            y="90.096"
            transform="matrix(0.7071 0.7071 -0.7071 0.7071 98.0963 -40.6334)"
            width="71.999"
            height="16"
          ></rect>
          <rect y="240" width="72" height="16"></rect>

          <rect
            x="90.091"
            y="361.915"
            transform="matrix(-0.7071 -0.7071 0.7071 -0.7071 -113.9157 748.643)"
            width="16"
            height="71.999"
          ></rect>
          <rect x="240" y="424" width="16" height="72"></rect>

          <rect
            x="361.881"
            y="389.915"
            transform="matrix(-0.7071 -0.7071 0.7071 -0.7071 397.8562 960.6281)"
            width="71.999"
            height="16"
          ></rect>
          <rect x="424" y="240" width="72" height="16"></rect>
          <rect
            x="389.911"
            y="62.091"
            transform="matrix(0.7071 0.7071 -0.7071 0.7071 185.9067 -252.6357)"
            width="16"
            height="71.999"
          ></rect>
        </svg>
        <svg
          version="1.1"
          class="moon"
          xmlns="http://www.w3.org/2000/svg"
          xmlns:xlink="http://www.w3.org/1999/xlink"
          x="0px"
          y="0px"
          viewBox="0 0 49.739 49.739"
          style="enable-background: new 0 0 49.739 49.739"
          xml:space="preserve"
        >
          <path
            d="M25.068,48.889c-9.173,0-18.017-5.06-22.396-13.804C-3.373,23.008,1.164,8.467,13.003,1.979l2.061-1.129l-0.615,2.268
       c-1.479,5.459-0.899,11.25,1.633,16.306c2.75,5.493,7.476,9.587,13.305,11.526c5.831,1.939,12.065,1.492,17.559-1.258v0
       c0.25-0.125,0.492-0.258,0.734-0.391l2.061-1.13l-0.585,2.252c-1.863,6.873-6.577,12.639-12.933,15.822
       C32.639,48.039,28.825,48.888,25.068,48.889z M12.002,4.936c-9.413,6.428-12.756,18.837-7.54,29.253
       c5.678,11.34,19.522,15.945,30.864,10.268c5.154-2.582,9.136-7.012,11.181-12.357c-5.632,2.427-11.882,2.702-17.752,0.748
       c-6.337-2.108-11.473-6.557-14.463-12.528C11.899,15.541,11.11,10.16,12.002,4.936z"
          ></path>
        </svg>
      </label>

      <div class="background"></div>
    </div>
    <footer>
      <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24">
        <path
          fill="#8385A9"
          d="M22.675 0H1.325C.593 0 0 .593 0 1.325v21.351C0 23.407.593 24 1.325 24H12.82v-9.294H9.692v-3.622h3.128V8.413c0-3.1 1.893-4.788 4.659-4.788 1.325 0 2.463.099 2.795.143v3.24l-1.918.001c-1.504 0-1.795.715-1.795 1.763v2.313h3.587l-.467 3.622h-3.12V24h6.116c.73 0 1.323-.593 1.323-1.325V1.325C24 .593 23.407 0 22.675 0z"
        />
      </svg>
      <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24">
        <path
          fill="#8385A9"
          d="M12 0C5.373 0 0 5.372 0 12c0 5.084 3.163 9.426 7.627 11.174-.105-.949-.2-2.405.042-3.441.218-.937 1.407-5.965 1.407-5.965s-.359-.719-.359-1.782c0-1.668.967-2.914 2.171-2.914 1.023 0 1.518.769 1.518 1.69 0 1.029-.655 2.568-.994 3.995-.283 1.194.599 2.169 1.777 2.169 2.133 0 3.772-2.249 3.772-5.495 0-2.873-2.064-4.882-5.012-4.882-3.414 0-5.418 2.561-5.418 5.207 0 1.031.397 2.138.893 2.738a.36.36 0 01.083.345l-.333 1.36c-.053.22-.174.267-.402.161-1.499-.698-2.436-2.889-2.436-4.649 0-3.785 2.75-7.262 7.929-7.262 4.163 0 7.398 2.967 7.398 6.931 0 4.136-2.607 7.464-6.227 7.464-1.216 0-2.359-.631-2.75-1.378l-.748 2.853c-.271 1.043-1.002 2.35-1.492 3.146C9.57 23.812 10.763 24 12 24c6.627 0 12-5.373 12-12 0-6.628-5.373-12-12-12z"
        />
      </svg>
      <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24">
        <path
          fill="#8385A9"
          d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zM12 0C8.741 0 8.333.014 7.053.072 2.695.272.273 2.69.073 7.052.014 8.333 0 8.741 0 12c0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98C8.333 23.986 8.741 24 12 24c3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98C15.668.014 15.259 0 12 0zm0 5.838a6.162 6.162 0 100 12.324 6.162 6.162 0 000-12.324zM12 16a4 4 0 110-8 4 4 0 010 8zm6.406-11.845a1.44 1.44 0 100 2.881 1.44 1.44 0 000-2.881z"
        />
      </svg>
    </footer>
    <img
      class="stars"
      alt="stars"
      :src="require(`@/assets/bg-stars${!darkMode ? '-dark' : ''}.svg`)"
    />
    <img
      class="mountains"
      alt="mountains"
      :class="darkMode ? 'mountains-show' : ''"
      :src="require(`@/assets/pattern-hills.svg`)"
    />
    <img
      class="mountains"
      :class="!darkMode ? 'mountains-show' : ''"
      alt="mountains"
      :src="require(`@/assets/pattern-hills-dark.svg`)"
    />
  </main>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      darkMode: true,
      startDate: null,
      targetDate: null,
      countdown: {
        days: 0,
        hours: 0,
        minutes: 0,
        seconds: 0,
      },
      rafId: null,
    };
  },
  mounted() {
    // Postavljamo datum koji predstavlja početni datum odbrojavanja
    this.startDate = new Date();

    // Postavljamo ciljani datum odbrojavanja
    this.targetDate = new Date();
    this.targetDate.setDate(this.targetDate.getDate() + 9);
    this.targetDate.setHours(8);
    this.targetDate.setMinutes(15);
    this.targetDate.setSeconds(48);

    // Postavljamo funkciju koja će ažurirati countdown
    const updateCountdown = () => {
      const timeDiff = this.targetDate.getTime() - new Date().getTime();
      this.countdown = this.calculateCountdown(timeDiff);

      // Pozivamo funkciju ponovo nakon što prođe 1 sekunda
      this.rafId = requestAnimationFrame(updateCountdown);
    };

    // Pokrećemo funkciju za prvi put
    updateCountdown();
  },
  beforeDestroy() {
    // Zaustavljamo ažuriranje kada se komponenta uništi
    cancelAnimationFrame(this.rafId);
  },
  methods: {
    // Metoda koja računa countdown na osnovu vremenske razlike u milisekundama
    calculateCountdown(timeDiff) {
      const days = Math.floor(timeDiff / (1000 * 60 * 60 * 24));
      const hours = Math.floor(
        (timeDiff % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60)
      );
      const minutes = Math.floor((timeDiff % (1000 * 60 * 60)) / (1000 * 60));
      const seconds = Math.floor((timeDiff % (1000 * 60)) / 1000);

      return {
        days: days,
        hours: hours,
        minutes: minutes,
        seconds: seconds,
      };
    },
  },
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Red+Hat+Text:wght@700&display=swap");

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  overflow: hidden;
  font-family: "Red Hat Text", sans-serif;
  -webkit-touch-callout: none; /* iOS Safari */
  -webkit-user-select: none; /* Safari */
  -khtml-user-select: none; /* Konqueror HTML */
  -moz-user-select: none; /* Old versions of Firefox */
  -ms-user-select: none; /* Internet Explorer/Edge */
  user-select: none; /* Non-prefixed version, currently */
}

#app {
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  z-index: 1;
  min-height: 100vh;
  background: linear-gradient(
    to bottom,
    hsl(234, 17%, 12%),
    hsl(235, 16%, 14%),
    hsl(236, 21%, 26%)
  );

  overflow: hidden;

  background: linear-gradient(
    to bottom,
    #87ceeb,
    /* svetloplava */ #b0e0e6,
    /* platinska */ #f0f8ff,
    /* bela */ #ffefd5,
    /* bledo narandžasta */ #ffdab9 /* breskvasta */
  );

  &::before {
    position: absolute;
    content: "";
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    background: linear-gradient(
      to bottom,
      hsl(234, 17%, 12%),
      hsl(235, 16%, 14%),
      hsl(236, 21%, 26%)
    );
    z-index: -1;
    transition: opacity 0.8s linear;
    opacity: 0;
  }

  &::before {
    opacity: 1;
  }

  &.dark {
    &::before {
      opacity: 1;
    }

    &::before {
      position: absolute;
      content: "";
      top: 0;
      right: 0;
      bottom: 0;
      left: 0;
      background: linear-gradient(
        to bottom,
        hsl(234, 17%, 12%),
        hsl(235, 16%, 14%),
        hsl(236, 21%, 26%)
      );
      z-index: -1;
      transition: opacity 0.8s linear;
      opacity: 0;
    }

    background: linear-gradient(
      to bottom,
      #87ceeb,
      /* svetloplava */ #b0e0e6,
      /* platinska */ #f0f8ff,
      /* bela */ #ffefd5,
      /* bledo narandžasta */ #ffdab9 /* breskvasta */
    );

    transition: all 0.5s ease;

    footer {
      svg {
        transition: all 0.8s ease;

        path {
          fill: hsl(234, 17%, 12%);
        }
        &:hover path {
          fill: rgb(253, 222, 151);
        }
      }
    }

    h1 {
      color: hsl(234, 17%, 12%);
      transition: color 0.8s linear;
    }

    .counter {
      &-block {
        &__card {
          background-color: rgb(253, 222, 151);
          color: rgb(135, 165, 153);
          transition: background-color 0.8s linear, color 0.8s linear;
        }
        &__footer {
          color: hsl(235, 16%, 14%);
          transition: color 0.8s linear;
        }
      }
    }
  }

  section {
    margin-top: -150px;
  }

  footer {
    display: flex;
    align-items: center;
    gap: 30px;
    justify-content: center;
    position: absolute;
    bottom: 0;
    left: 50%;
    z-index: 999;
    transform: translate(-50%, -93px);

    svg {
      cursor: pointer;
      transition: all 0.8s ease;

      &:hover path {
        fill: hsl(345, 95%, 68%);
        transition: all 0.5s ease;
      }
    }
  }

  h1 {
    color: white;
    text-transform: uppercase;
    font-size: 28px;
    letter-spacing: 8px;
    text-align: center;
    transition: color 0.8s linear;

    @media only screen and (max-width: 713px) {
      font-size: 22px;
    }
  }

  .mountains {
    position: absolute;
    bottom: 0;
    min-width: 100vw;
    opacity: 0;
    transition: opacity 0.8s linear;
    &-show {
      opacity: 1;
    }
  }

  .stars {
    position: absolute;
    top: 0;
    min-width: 100vw;
    animation: moveAround 60s infinite linear;
  }

  @keyframes moveAround {
    0% {
      transform: translate(0, 0);
    }
    5% {
      transform: translate(20px, 20px);
    }
    10% {
      transform: translate(10px, -20px);
    }
    15% {
      transform: translate(25px, -40px);
    }
    20% {
      transform: translate(40px -15px);
    }
    25% {
      transform: translate(20px, 20px);
    }
    30% {
      transform: translate(10px, -20px);
    }
    35% {
      transform: translate(25px, -40px);
    }
    40% {
      transform: translate(40px -15px);
    }
    45% {
      transform: translate(20px, 20px);
    }
    50% {
      transform: translate(10px, -20px);
    }
    55% {
      transform: translate(25px, -40px);
    }
    60% {
      transform: translate(40px -15px);
    }
    65% {
      transform: translate(20px, 20px);
    }
    70% {
      transform: translate(10px, -20px);
    }
    75% {
      transform: translate(25px, -40px);
    }
    80% {
      transform: translate(40px -15px);
    }
    85% {
      transform: translate(20px, 20px);
    }
    90% {
      transform: translate(10px, -20px);
    }
    95% {
      transform: translate(25px, -40px);
    }
    100% {
      transform: translate(0, 0);
    }
  }

  .counter {
    position: relative;
    z-index: 1000;
    display: flex;
    gap: 30px;
    margin-top: 100px;
    align-items: center;
    justify-content: space-between;
    padding: 0 20px;

    @media only screen and (max-width: 713px) {
      margin-top: 75px;
    }

    @media only screen and (max-width: 713px) {
      gap: 16px;
    }

    &-block {
      display: flex;
      align-items: center;
      justify-content: center;
      flex-direction: column;
      gap: 16px;
      position: relative;

      &__card {
        position: relative;
        display: flex;
        justify-content: center;
        align-items: center;
        font-size: 80px;
        color: hsl(345, 95%, 68%);
        background-color: hsl(236, 21%, 26%);
        border-radius: 8px;
        width: 150px;
        height: 140px;
        transition: background-color 0.8s linear, color 0.8s linear;
        overflow: hidden;
        box-shadow: 0px 6px 4px rgba(0, 0, 0, 0.8);

        @media only screen and (max-width: 713px) {
          width: 80px;
          height: 70px;
          font-size: 36px;
        }

        &-divider {
          position: absolute;
          left: 0;
          height: 1px;
          width: 100%;
          background-color: hsl(235, 16%, 14%);
          transition: background-color 0.8s linear;
        }

        &::before {
          content: "";
          position: absolute;
          left: -7px;
          width: 14px;
          height: 14px;
          background: hsl(234, 17%, 12%);
          border-radius: 50%;
        }

        &::after {
          content: "";
          position: absolute;
          right: -7px;
          width: 14px;
          height: 14px;
          background: hsl(234, 17%, 12%);
          border-radius: 50%;
        }
      }
      &__footer {
        font-size: 18px;
        color: hsl(237, 18%, 59%);
        letter-spacing: 6px;
        transition: color 0.8s linear;

        @media only screen and (max-width: 713px) {
          font-size: 12px;
          letter-spacing: 2px;
        }
      }
    }
  }

  .dark-mode__toggler {
    position: absolute;
    top: 0;
    right: 20px;
    label {
      width: 100px;
      height: 50px;
      position: relative;
      display: block;
      background-color: #ebebeb;
      border-radius: 200px;
      transition: background-color 0.8s linear;
      cursor: pointer;
      transition: 0.4s;
    }
    label:after {
      content: "";
      width: 30px;
      height: 30px;
      position: absolute;
      top: 10px;
      left: 10px;
      background: #fdde97;
      border-radius: 180px;
      box-shadow: 0px 5px 10px rgba(0, 0, 0, 0.2);
      transition: 0.8s;
    }
    input {
      width: 0;
      height: 0;
      visibility: hidden;
    }
    input:checked + label {
      background: #242424;
    }
    input:checked + label:after {
      left: 90px;
      transform: translateX(-100%);
      background: #3a3a3a;
    }
    label:active:after {
      width: 45px;
    }

    input:checked + label + .background {
      background: #242424;
    }
    label svg {
      position: absolute;
      width: 19px;
      top: 15px;
      z-index: 100;
    }
    label svg.sun {
      left: 16px;
      fill: #87a598;
      transition: 0.8s;
    }
    label svg.moon {
      left: 66px;
      fill: #7e7e7e;
      transition: 0.8s;
    }
    input:checked + label svg.sun {
      fill: #7e7e7e;
    }
    input:checked + label svg.moon {
      fill: #fb6087;
    }
  }
}
</style>
