<script>
  import {onMount} from 'svelte';

  $: showMessages = false;

  onMount(() => {
    const messages = document.getElementById("messages");

    function getOffset(el) {
      const rect = el.getBoundingClientRect();
      return {
        left: rect.left + window.scrollX,
        top: rect.top + window.scrollY
      };
    }

    window.addEventListener('scroll', (event) => {
      if (window.scrollY >= getOffset(messages).top) {
        setTimeout(() => showMessages = true, 700);
      }
    });
	});
</script>

<div class="banner">
  <div class="container">
    <div class="banner-hero">
      <div class="banner-hero-content">
        <h1 id="banner-title">
          I'm tired of marketing agencies & their bullshit!
        </h1>
        <p id="banner-description">Marketing agencies remind us of online dating. Curious?</p>
      </div>
      <div class="scroll">
        <img src="/images/mouse-icon.svg" alt="Mouse Icon">
        <span>Scroll to hear this dumb analogy.</span>
      </div>
    </div>
  </div>
</div>
<div class="messages" id="messages">
  <div class="container">
    <div class="one">
      <h2 class="message-title">Agencies will say anything to get your business</h2>
      <div class="dots {showMessages ? "min" : ""}">
        <div class="dot"></div>
        <div class="dot"></div>
        <div class="dot"></div>
      </div>
      <p class="message {showMessages ? "show" : ""}">
        Hire me as your agency, and I'll 5x your ROAs so hard.
      </p>
    </div>
    <div class="two">
      <h2 class="message-title">Then, they make excuses for why they underperformed</h2>
      <div class="dots {showMessages ? "min" : ""}">
        <div class="dot"></div>
        <div class="dot"></div>
        <div class="dot"></div>
      </div>
      <p class="message {showMessages ? "show" : ""}">
        Website was horrible, how could you expect my ads to convert?
      </p>
    </div>
  </div>
</div>

<style lang=scss>
  .min {
    transform: scale(0);
  }

  .show {
    transform: scale(1) !important;
  }

  .dots {
    @include flex(row, center, space-between);
    width: 100px;
    padding: 10px;
    background-color: white;
    border-radius: 10px;
    position: relative;
    top: 10px;
    
    .dot {
      height: 15px;
      width: 15px;
      border-radius: 50%;
      background-color: rgba(0, 0, 0, 0.2);
    }
  }
  
  .banner-hero {
    height: calc(100vh - 100px);
    @include flex(column, flex-start, space-between);
    color: #fff;

    .banner-hero-content {
      #banner-title {
        font-size: 6vw;
        font-weight: 800;
      }

      #banner-description {
        font-size: 2.5vw;
        font-weight: 600;
      }
    }

    .scroll {
      position: relative;
      @include flex(row, center, center);
      margin: 30px auto;
      column-gap: 10px;
      animation-name: scrollAnimation;
      animation-duration: 1.5s;
      animation-iteration-count: infinite;

      img {
        height: 40px;
      }

      span {
        font-size: 1.5vw;
        font-weight: 600;
      }
    }

    @keyframes scrollAnimation {
      0% {
        top: -10px;
      }

      50% {
        top: 10px;
      }

      100% {
        top: -10px;
      }
    }
  }

  .messages {
    height: 100vh;
    color: white;

    .one {
      margin-top: 50px;
    }

    .container {
      display: flex;
      flex-direction: column;
      row-gap: 50px;
    }

    .message-title {
      font-size: 3.5vw;
      font-weight: 700;
    }

    .message {
      transform: scale(0);
      background-color: white;
      width: 60%;
      color: $bColor;
      padding: 20px;
      font-size: 1.6vw;
      border-radius: 10px;
      position: relative;
      top: -20px;
    }
  }
</style>