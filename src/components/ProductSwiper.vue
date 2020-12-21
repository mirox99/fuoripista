<template>
  <div class="product-swiper">
    <div class="swiper-wrapper">
      <div v-for="item in products"
           :key="item.id"
           :class="{home:item.cover}"
           class="swiper-slide">
        <div :class="{animated:contentAnimation}" class="transform-container">
          <div class="text-container">
            <div @mouseover="contentAnimation=true"
                 @mouseleave="contentAnimation=false"
                 class="text-content">
              <div class="header-container">
                <div class="header" v-html="item.header "></div>
              </div>
              <div class="sub-header" v-html="item.subHeader"></div>
              <div v-if="!item.cover" class="discover-container">
                <div class="title" v-html="item.discover"></div>
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 10" class="underline-svg">
                  <path
                      d="M15.5 1c-1.5.5-2.6 1-3.4 1.3-3.2 1.5-6.3 3.2-9.2 5.2C1.2 8.6.9 8.9 1 9c.2.2 1.7-.4 4.6-1.5s5.9-2.2 8.8-3.3c2.5-.9 5-1.7 7.5-2.4.8-.2 2.1-.6 2.4-.3.1.1.2.3-1 1.3-1.1.9-2.2 1.6-3.4 2.4-1.4.9-3.2 2.2-2.8 2.6.3.4 2.1.3 3.2 0 .3-.1.6-.2 1-.3 7.9-2.5 16.1-4 24.5-4.4C57.5 2.8 60.2 5.6 68 6.3c6.6.7 22.3-3 31-2.8"
                      fill="none" stroke="#c39d42" stroke-width="2" stroke-linecap="round" stroke-miterlimit="3.998"
                      style="stroke-dashoffset: 0; stroke-dasharray: 134.176;"></path>
                </svg>
              </div>
            </div>
          </div>
          <div class="image-container">
            <img
                :src="item.src"
                :srcset="item.srcset"
                alt="swiper image"
                class="swiper-image">
            <div class="image-shadow"></div>
          </div>
        </div>
      </div>
    </div>
    <div class="swiper-pagination"></div>
  </div>
</template>

<script>
import Swiper from 'swiper/bundle';
import 'swiper/swiper-bundle.css';

export default {
  name: 'ProductSlider',

  data() {
    return {
      products: [
        {
          cover: true,
          id: 1,
          src: 'https://api.fuoripista.it/assets/images/home/_1024xAUTO_crop_center-center_none/Fuoripista-Cover-D_200720_151200.jpg',
          srcset: 'https://api.fuoripista.it/assets/images/home/_1024xAUTO_crop_center-center_none/Fuoripista-Cover-D_200720_151200.jpg 1024w,' +
              'https://api.fuoripista.it/assets/images/home/_1280xAUTO_crop_center-center_none/Fuoripista-Cover-D_200720_151200.jpg 1280w,' +
              'https://api.fuoripista.it/assets/images/home/_1440xAUTO_crop_center-center_none/Fuoripista-Cover-D_200720_151200.jpg 1440w,' +
              'https://api.fuoripista.it/assets/images/home/_1920xAUTO_crop_center-center_none/Fuoripista-Cover-D_200720_151200.jpg 1920w',
          header: '<p><span>fitness</span><span>meets design</span>',
          subHeader: '<p>A <em>project</em> of Adriano Design and Elite</p>'

        },
        {
          id: 2,
          src: 'https://api.fuoripista.it/assets/images/home/_1024xAUTO_crop_center-center_none/Fuoripista-Bike-D.jpg',
          srcset: 'https://api.fuoripista.it/assets/images/home/_768xAUTO_crop_center-center_none/Fuoripista-Bike-M.jpg 768w,' +
              'https://api.fuoripista.it/assets/images/home/_640xAUTO_crop_center-center_none/Fuoripista-Bike-M.jpg 640w,' +
              'https://api.fuoripista.it/assets/images/home/_480xAUTO_crop_center-center_none/Fuoripista-Bike-M.jpg 480w,' +
              'https://api.fuoripista.it/assets/images/home/_1024xAUTO_crop_center-center_none/Fuoripista-Bike-D.jpg 1024w,' +
              'https://api.fuoripista.it/assets/images/home/_1280xAUTO_crop_center-center_none/Fuoripista-Bike-D.jpg 1280w,' +
              'https://api.fuoripista.it/assets/images/home/_1440xAUTO_crop_center-center_none/Fuoripista-Bike-D.jpg 1440w,' +
              'https://api.fuoripista.it/assets/images/home/_1920xAUTO_crop_center-center_none/Fuoripista-Bike-D.jpg 1920w',
          header: 'BIKE',
          subHeader: '<p>A new way of <br>working out <em>indoors</em></p>',
          discover: '<p><span data-title="discover">discover</span><span data-title="fuoripista"> fuoripista </span><span data-title="bike">bike</span></p>',
        },
        {
          id: 3,
          src: 'https://api.fuoripista.it/assets/images/home/_1024xAUTO_crop_center-center_none/Fuoripista-Bike-D2.jpg',
          srcset: 'https://api.fuoripista.it/assets/images/home/_768xAUTO_crop_center-center_none/Fuoripista-Tuo-M2.jpg 768w,' +
              'https://api.fuoripista.it/assets/images/home/_640xAUTO_crop_center-center_none/Fuoripista-Tuo-M2.jpg 640w,' +
              'https://api.fuoripista.it/assets/images/home/_480xAUTO_crop_center-center_none/Fuoripista-Tuo-M2.jpg 480w,' +
              'https://api.fuoripista.it/assets/images/home/_1024xAUTO_crop_center-center_none/Fuoripista-Bike-D2.jpg 1024w,' +
              'https://api.fuoripista.it/assets/images/home/_1280xAUTO_crop_center-center_none/Fuoripista-Bike-D2.jpg 1280w,' +
              'https://api.fuoripista.it/assets/images/home/_1440xAUTO_crop_center-center_none/Fuoripista-Bike-D2.jpg 1440w,' +
              'https://api.fuoripista.it/assets/images/home/_1920xAUTO_crop_center-center_none/Fuoripista-Bike-D2.jpg 1920w',
          header: 'TUO',
          subHeader: '<p>A functional solution that combines <br>performance and <em>style</em></p>',
          discover: '<p><span data-title="discover">discover</span><span data-title="tuo"> tuo </span></p>',
        },
        {
          id: 4,
          src: 'https://api.fuoripista.it/assets/images/home/_1280xAUTO_crop_center-center_none/Fuoripista-Mia-D.jpg',
          srcset: 'https://api.fuoripista.it/assets/images/home/_768xAUTO_crop_center-center_none/Fuoripista-Mia-M.jpg 768w,' +
              'https://api.fuoripista.it/assets/images/home/_640xAUTO_crop_center-center_none/Fuoripista-Mia-M.jpg 640w,' +
              'https://api.fuoripista.it/assets/images/home/_480xAUTO_crop_center-center_none/Fuoripista-Mia-M.jpg 480w,' +
              'https://api.fuoripista.it/assets/images/home/_1024xAUTO_crop_center-center_none/Fuoripista-Mia-D.jpg 1024w,' +
              'https://api.fuoripista.it/assets/images/home/_1280xAUTO_crop_center-center_none/Fuoripista-Mia-D.jpg 1280w,' +
              'https://api.fuoripista.it/assets/images/home/_1440xAUTO_crop_center-center_none/Fuoripista-Mia-D.jpg 1440w,' +
              'https://api.fuoripista.it/assets/images/home/_1920xAUTO_crop_center-center_none/Fuoripista-Mia-D.jpg 1920w',
          header: 'MIA',
          subHeader: '<p>A lifestyle concept <br>for everyday <em>well-being</em></p>',
          discover: '<p><span data-title="discover">discover</span><span data-title="mia"> mia </span></p>',
        },
      ],
      contentAnimation: false,
    }
  },
  methods: {
    initialProductSwiper() {
      this.$nextTick(() => {
        let mySwiper = new Swiper('.product-swiper', {
          direction: 'vertical',
          slidesPerView: 1,
          mousewheel: true,
          touchReleaseOnEdges: true,
          pagination: {
            el: '.swiper-pagination',
            clickable: true,
          },

        })

        mySwiper.on('reachEnd', () => {
          setTimeout(() => {
            this.$root.$emit(`slideChange`, true)
          }, 1100)
        });
        mySwiper.on('slidePrevTransitionEnd', () => {
          this.$root.$emit(`slideChange`, false)
          window.scrollTo({top: 0, behavior: 'smooth'});
        });
      })
    },
  },
  mounted() {
    this.initialProductSwiper()
  }
};
</script>

<style lang="scss" scoped>
.product-swiper /deep/ {
  width: 100%;
  height: 100%;
  overflow: hidden;

  .swiper-wrapper {
    width: 100%;
    height: 100%;
    transition-duration: 1000ms !important;

    .swiper-slide {
      overflow: hidden;
      height: 100.03% !important;

      &.home {
        .swiper-image {
          transform: scale(1, 1) !important;
        }
      }

      &.swiper-slide-prev {
        .transform-container {
          transform: translate3d(0px, 60%, 0px);
          @media screen and (min-width: 769px) and (max-width: 1024px) {
            transform: translate3d(0px, 30%, 0px);
          }
          @media screen and (max-width: 768px) {
            transform: translate3d(0px, 0, 0px);
          }

          .text-container {
            transform: translateY(-100%);
          }
        }
      }

      &.swiper-slide-next {
        .transform-container {
          transform: translate3d(0px, -60%, 0px);
          @media screen and (min-width: 769px) and (max-width: 1024px) {
            transform: translate3d(0px, -30%, 0px);
          }
          @media screen and (max-width: 768px) {
            transform: translate3d(0px, 0, 0px);
          }

          .text-container {
            transform: translateY(100%);
          }
        }
      }

      &.swiper-slide-active {
        .header {
          transform: translateY(0) !important;
          transition: transform 1s cubic-bezier(0, .55, .45, 1) !important;
          transition-delay: 1100ms !important;
        }

        .sub-header, .discover-container {
          transform: translate(0, 0) !important;
          opacity: 1 !important;
        }

        .sub-header {
          transition: opacity 1s 1380ms ease, transform 1s 1350ms ease !important;
        }

        .discover-container {
          transition: opacity 1s 1680ms ease, transform 1s 1630ms ease !important;
        }
      }

      .text-container {
        position: absolute;
        padding: 0 80px;
        width: 100%;
        height: 100%;
        display: flex;
        align-items: center;
        justify-content: center;
        color: white;
        z-index: 100;
        text-align: center;
        transition: transform 900ms linear;

        @media screen and (min-width: 769px) and (max-width: 1024px) {
          padding: 0 60px;
        }
        @media screen and (max-width: 768px) {
          padding: 0 30px;
        }

        br {
          @media screen and (max-width: 768px) {
            display: none;
          }
        }

        .text-content {
          cursor: pointer;

          .header-container {
            display: inline-block;
            overflow: hidden;
            vertical-align: middle;
            margin-bottom: 10px;

            .header {
              text-transform: uppercase;
              font-family: "DomaineSansDisplay-Light";
              font-weight: 300;
              font-style: normal;
              font-size: 70px;
              transition: transform .1ms .5s cubic-bezier(0, .55, .45, 1);
              transform: translateY(100%);
              line-height: 1;
              @media screen and (min-width: 1025px) and (max-width: 1440px) {
                font-size: 55px;
              }
              @media screen and (min-width: 769px) and (max-width: 1024px) {
                font-size: 50px;
              }
              @media screen and (max-width: 768px) {
                font-size: 30px;
              }

              span {
                display: block;
              }
            }
          }

          .sub-header {
            font-family: "DomaineSansDisplay-Light";
            font-weight: 300;
            font-style: normal;
            font-size: 40px;
            line-height: 1.1;
            opacity: 0;
            transform: translate(0, 20px);
            transition: opacity .1ms .5s linear, transform .5s linear;
            margin-bottom: 30px;
            @media screen and (min-width: 1025px) and (max-width: 1440px) {
              font-size: 35px;
            }
            @media screen and (min-width: 769px) and (max-width: 1024px) {
              font-size: 28px;
              margin-bottom: 25px;
            }
            @media screen and (max-width: 768px) {
              font-size: 23px;
              margin-bottom: 20px;
              line-height: 1.3;
            }

            em {
              display: inline-block;
              font-family: "Hijrnotes";
              font-weight: 400;
              font-style: normal;
              color: #c39d42;
              font-size: 170%;
              vertical-align: middle;
              position: relative;
              top: -.2em;
              margin-left: .1em;
              margin-right: .1em;
            }
          }

          .discover-container {
            opacity: 0;
            transform: translate(0, 20px);
            transition: opacity .1ms .5s ease, transform .5s ease;

            .title {
              display: block;
              position: relative;
              text-transform: uppercase;
              letter-spacing: 0.8px;
              font-family: "Grot10-Light";
              font-weight: 300;
              font-style: normal;
              font-size: 16px;

              p {
                overflow: hidden;
                position: relative;
                display: flex;
                align-items: center;
                grid-gap: 5px;
                justify-content: center;

                span {
                  display: inline-block;

                  &:nth-child(1) {
                    animation-delay: 0s;
                  }

                  &:nth-child(2) {
                    animation-delay: 200ms;
                  }

                  &:nth-child(3) {
                    animation-delay: 400ms;
                  }

                  &:before {
                    content: attr(data-title);
                    position: absolute;
                    top: 100%;
                  }
                }

              }
            }

            .underline-svg {
              width: 100px;
              height: 20px;
              margin-top: 4px;

              path {
                stroke-dasharray: 134.176;
              }
            }
          }
        }

      }

      .image-container {
        width: 100%;
        height: 100%;
      }

      .transform-container {
        width: 100%;
        height: 100%;
        transition: all 1000ms ease 0s;

        &.animated {
          .title {
            span {
              animation: word-animation .6s ease-out;
            }
          }

          .underline-svg {
            path {
              animation: svg-animation 1.5s cubic-bezier(0, 0, 0.15, 0.7) forwards;
            }
          }

          .image-container {
            .swiper-image {
              transform: scale(1, 1);
            }
          }
        }
      }


      .swiper-image {
        width: 100%;
        height: 100% !important;
        display: block;
        object-fit: cover;
        transform: scale(1.3, 1.3);
        transition: all 1600ms cubic-bezier(0.27, 0.15, 0.66, 1.03);
      }

      .image-shadow {
        display: block;
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background-image: radial-gradient(transparent, #000 100%);
      }
    }


  }

  .swiper-pagination {
    bottom: 50px;
    left: 40px;
    right: unset;
    top: unset;
    display: flex;
    align-items: center;
    @media screen and (max-width: 768px) {
      flex-direction: column;
      grid-gap: 10px;
      margin: 0;
      bottom: 15px;
      left: 20px;
    }

    .swiper-pagination-bullet {
      background: #fff;
      transition: all .6s;
      width: 4px;
      height: 4px;
      margin: 3px 8px;
      outline: none;

      &.swiper-pagination-bullet-active {
        background: #c39d42;
        transform: scale(2);
      }
    }
  }
}

@keyframes word-animation {
  0% {
    transform: translateY(0%);
  }
  100% {
    transform: translateY(-100%);
  }
}

@keyframes svg-animation {
  0% {
    stroke-dashoffset: 130px;
  }
  100% {
    stroke-dashoffset: 0;
  }
}
</style>