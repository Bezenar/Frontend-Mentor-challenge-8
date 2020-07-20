<template>
  <div id="page">
    <Header></Header>
    <main>
      <section class="introduction" :class="{ mobile: !resolution }">
        <div class="container">
          <div class="flex dir-col ai-center">
            <div class="introduction__image-wrapper">
              <img
                class="introduction__image"
                :src="introduction.img.src"
                :alt="introduction.img.alt"
                :title="introduction.img.title"
              />
            </div>
            <div class="introduction__content">
              <div class="introduction__content__heading-wrapper">
                <h2 class="introduction__content__heading G-heading">
                  {{ introduction.heading }}
                </h2>
              </div>
              <div class="introduction__content__text-wrapper">
                <p class="introduction__content__text">
                  {{ introduction.text }}
                </p>
              </div>
              <Button name="Get Started" link="#"></Button>
            </div>
          </div>
        </div>
      </section>
      <section class="benefits">
        <div class="container container--small">
          <div class="flex wrap jc-center">
            <Benefit
              v-for="item in benefits"
              :key="item.id"
              :icon="item.icon"
              :heading="item.heading"
              :text="item.text"
            ></Benefit>
          </div>
        </div>
      </section>
      <section class="productivity">
        <div class="container">
          <div class="flex">
            <div class="wid-50">
              <div class="productivity__image-wrapper">
                <img
                  :src="productivity.image.src"
                  :alt="productivity.image.alt"
                  :title="productivity.image.title"
                />
              </div>
            </div>
            <div class="wid-50">
              <div class="productivity__content">
                <div class="productivity__heading-wrapper">
                  <h3 class="productivity__heading">
                    {{ productivity.heading }}
                  </h3>
                </div>
                <div class="productivity__text-wrapper">
                  <div class="productivity__text">
                    <p class="productivity__text--paragraph">
                      {{ productivity.text.paragraphOne }}
                    </p>
                    <p class="productivity__text--paragraph">
                      {{ productivity.text.paragraphTwo }}
                    </p>
                  </div>
                </div>
                <div class="productivity__linkContainer-wrapper">
                  <div class="productivity__linkContainer">
                    <a
                      :href="productivity.link.href"
                      class="productivity__link"
                    >
                      {{ productivity.link.text }}
                      <img
                        class="productivity__link__icon"
                        :src="productivity.link.icon.src"
                        :alt="productivity.link.icon.alt"
                        :title="productivity.link.icon.title"
                      />
                    </a>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>
      <section class="testimonials">
        <div class="container">
          <Testimonial></Testimonial>
        </div>
      </section>
    </main>
    <Footer></Footer>
  </div>
</template>

<script>
import Header from "./components/main/Header";
import Footer from "./components/main/Footer";
import Button from "./components/secondary/Button";
import Benefit from "./components/secondary/Benefit";
import Testimonial from "./components/secondary/Testimonial";
export default {
  name: "App",
  components: { Header, Footer, Button, Benefit, Testimonial },
  data() {
    return {
      resolution: null,
      introduction: {
        img: {
          src: "./images/illustration-intro.png",
          alt: "Illustration",
          title: "All your files in one secure location, accessible anywhere."
        },
        heading: "All your files in one secure location, accessible anywhere.",
        text:
          "Fylo stores all your most important files in one secure" +
          "location. Access them wherever you need, share and collaborate" +
          "with friends family, and co-workers."
      },
      benefits: [
        {
          id: "1",
          icon: {
            src: "./images/icon-access-anywhere.svg",
            alt: "Devices",
            title: "Access anewhere"
          },
          heading: "Access your files, anywhere",
          text:
            "The ability to use a smartphone, tablet, or computer to access your account means your " +
            "files follow you everywhere."
        },
        {
          id: "2",
          icon: {
            src: "./images/icon-security.svg",
            alt: "Shield",
            title: "Security"
          },
          heading: "Security you can trust",
          text:
            "2-factor authentication and user-controlled encryption are just a couple of the security " +
            "features we allow to help secure your files."
        },
        {
          id: "3",
          icon: {
            src: "./images/icon-collaboration.svg",
            alt: "Collaboration",
            title: "Collaboration"
          },
          heading: "Real-time collaboration",
          text:
            "Securely share files and folders with friends, family and colleagues for live collaboration." +
            "No email attachments required."
        },
        {
          id: "4",
          icon: {
            src: "./images/icon-any-file.svg",
            alt: "Folders",
            title: "Store any files"
          },
          heading: "Store any type of file",
          text:
            "Whether you're sharing holidays photos or work documents, Fylo has you covered allowing for all" +
            "file types to be securely stored and shared."
        }
      ],
      productivity: {
        image: {
          src: "./images/illustration-stay-productive.png",
          alt: "image",
          title: "image"
        },
        heading: "Stay productive, wherever you are",
        text: {
          paragraphOne:
            "Never let location be an issue when accessing your files. Fylo has you covered for all of your file " +
            "storage needs.",
          paragraphTwo:
            "Securely share files and folders with friends, family and colleagues for live collaboration. No email " +
            "attachments required."
        },
        link: {
          text: "See how Fylo works",
          href: "#",
          icon: {
            src: "./images/icon-arrow.svg",
            alt: "Arrow-right",
            title: "Arrow"
          }
        }
      }
    };
  },
  methods: {
    windowSize() {
      let w = document.documentElement.clientWidth;
      if (w > 500) {
        this.resolution = true;
      } else {
        this.resolution = false;
      }
    }
  },
  created() {
    this.windowSize();
    window.addEventListener("resize", this.windowSize);
  }
};
</script>

<style lang="scss">
.introduction {
  background-color: $darkBlue-introBg;
  color: $white;
  background-image: url("../public/images/bg-curvy-desktop.svg");
  background-repeat: no-repeat;
  background-position: 0 105%;
  &.mobile {
    background-image: url("../public/images/bg-curvy-mobile.svg");
  }
  &__image {
    &-wrapper {
      padding-top: 3.5rem;
    }
  }
  &__content {
    text-align: center;
    padding-bottom: 8.5rem;
    &__heading {
      &-wrapper {
        padding-top: 2.05rem;
      }
      font-family: $secondFont;
      font-size: 40px;
      word-spacing: 1px;
      line-height: 60px;
      padding: 0 13rem;
    }
    &__text {
      &-wrapper {
        padding: 2rem 20.75rem 0rem;
      }
      font-size: 19px;
      line-height: 30px;
    }
  }
}
.benefits {
  background-color: $darkBlue-mainBg;
}
.productivity {
  background-color: $darkBlue-mainBg;
  padding-top: 3.75rem;
  color: $white;
  &__image {
    &-wrapper {
      padding-left: 1.75rem;
    }
  }
  &__content {
    padding-left: 3.5rem;
    padding-top: 7.2rem;
  }
  &__heading {
    &-wrapper {
      padding-right: 9rem;
    }
    font-size: 40px;
    letter-spacing: 0.5px;
    line-height: 50px;
    font-family: $secondFont;
  }
  &__text {
    &-wrapper {
      line-height: 24px;
      padding-right: 2rem;
      padding-bottom: 1rem;
    }
    &--paragraph {
      padding: 1.1rem 0 0rem;
      font-size: 14px;
      letter-spacing: 0px;
      word-spacing: -0.5px;
    }
  }
  &__linkContainer {
    &-wrapper {
      padding-top: 0.5rem;
    }
  }
  &__link {
    color: $cyan;
    border-bottom: solid 1px $cyan;
    padding-bottom: 0.19rem;
    &__icon {
      vertical-align: middle;
    }
  }
}
.testimonials {
  background: $darkBlue-mainBg;
  padding: 10rem 3.2rem 11rem 2.5rem;
}
</style>
