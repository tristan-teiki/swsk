<script>
  $: revealNumber = false;
  $: revealEmail = false;
</script>

<div class="contact">
  <div class="container">
    <h1>Contact</h1>
    <div class="contact-form">
      <input type="text" placeholder="Name">
      <input type="email" placeholder="Business Email" id="email">
      <textarea id="message" placeholder="Message" cols="30" rows="3"></textarea>
      <button>Send</button>
    </div>
    <div class="contact-now">
      <div class="reveal"
        on:click={() => revealNumber = true}
        style='background-color: {revealNumber ? 'white' : '#e5e5e5'}'
      >
        <span>{revealNumber ? "+1 123 123 123" : "Reveal Number"}</span>
      </div>
      <div class="reveal" 
        on:click={() => revealEmail = true}
        style='background-color: {revealNumber ? 'white' : '#e5e5e5'}'
        >
          <span>{revealEmail ? "email@scalewhale.com" : "Reveal Email"}</span>
      </div>
    </div>
  </div>
</div>

<style lang=scss>
  .contact {
    h1 {
      font-size: 250%;
      color: white;
      font-weight: 600;
      text-align: center;
      margin: 5px;
    }

    .contact-form {
      @include flex(column, center, center);
      row-gap: 10px;
      max-width: 400px;
      margin: auto;

      input,
      textarea,
      button {
        width: 100%;
        padding: 10px 20px;
        outline: 0;
        border-radius: 5px;
        resize: none;
        background-color: white;
        border: 2px solid #e5e5e5;
      }

      input,
      textarea {
        &:focus {
          caret-color: $bColor2;
        }
      }

      button {
        font-weight: 600;
      }
    }

    .contact-now {
      @include flex(column, center, center);
      max-width: 400px;
      row-gap: 10px;
      margin: 10px auto;
      
      .reveal {
        cursor: pointer;
        font-size: 100%;
        background-color: white;
        width: 100%;
        padding: 10px 20px;
        border-radius: 5px;
        text-align: center;
        background-color: #e5e5e5;
        border: 2px solid #e5e5e5;
      }
    }
  }
</style>