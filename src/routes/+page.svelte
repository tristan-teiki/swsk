<script>
  import { Swiper, SwiperSlide } from "swiper/svelte";
  import { Autoplay } from 'swiper';
  import "swiper/css";
</script>

<div class="main-page">
  <section class="hero">
    <video autoplay muted loop id="video">
        <source src="/videos/whales.mp4" type="video/mp4" />
    </video>
    <div class="hero-content">
        <h1>We Tackle Your <br>Growth Problems</h1>
        <p>Scalewhale is a Paid Media agency<br> with expertise in Analytics, and MarOps</p>
        <a id="get-in-touch" href="#">Get in Touch</a>
    </div>
  </section>
  <section class="container">
    <div class="clients">
      <h2>We've had the pleasure<br> of working with:</h2>
      <Swiper
        slidesPerView={3}
        autoplay={{
          delay: 1000,
          disableOnInteraction: false,
        }}
        spaceBetween={30}
        class="slides"
        loop={true}
        modules={[Autoplay]}
        style="width: 60%;"
      >
        <SwiperSlide>
          <a href="#" target="_blank">
            <img src="/images/clients-icons/nzxt.svg" alt="NZXT">
          </a>
        </SwiperSlide>
        <SwiperSlide>
          <a href="#" target="_blank">
            <img src="/images/clients-icons/cushion.svg" alt="Cushion">
          </a>
        </SwiperSlide>
        <SwiperSlide>
          <a href="#" target="_blank">
            <img src="/images/clients-icons/irl.svg" alt="IRL">
          </a>
        </SwiperSlide>
        <SwiperSlide>
          <a href="#" target="_blank">
            <img src="/images/clients-icons/kyla.svg" alt="Kyla">
          </a>
        </SwiperSlide>
        <SwiperSlide>
          <a href="#" target="_blank">
            <img src="/images/clients-icons/outco.svg" alt="Outco">
          </a>
        </SwiperSlide>
        <SwiperSlide>
          <a href="#" target="_blank">
            <img src="/images/clients-icons/fellow.svg" alt="Fellow">
          </a>
        </SwiperSlide>
      </Swiper>
    </div>
  </section>
</div>

<style lang=scss>
  .main-page {
    height: calc(100vh - 100px);
    overflow: hidden;
    width: 100%;
    
    .hero {
      position: relative;
      height: calc(100% - 150px);
      width: 100%;

      #video {
        height: 100%;
        width: 100%;
        object-fit: cover;
      }

      .hero-content {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        color: white;
        @include flex(column, center, center);
        row-gap: 10px;

        h1 {
          font-size: 5vw;
          font-weight: 800;
          text-align: center;
        }

        p {
          font-size: 2.5vw;
          text-align: center;
          font-weight: 600;
        }
      }
    }

    .clients {
      @include flex(row, center, space-between);
      height: 150px;
      
      h2 {
        font-size: 180%;
        color: white;
        font-weight: 600;
        width: 40%;
      }

      .swiper-slide {
        display: -webkit-box;
        display: -ms-flexbox;
        display: -webkit-flex;
        display: flex;
        -webkit-box-pack: center;
        -ms-flex-pack: center;
        -webkit-justify-content: center;
        justify-content: center;
        -webkit-box-align: center;
        -ms-flex-align: center;
        -webkit-align-items: center;
        align-items: center;

        a {
          text-decoration: none;

          img {
            height: 130px;
            width: 130px;
            object-fit: contain;
          }
        }
      }
    }
  }
</style>