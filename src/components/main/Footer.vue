<template>
  <footer class="footer">
    <div class="container">
      <div class="footer__upperLine">
        <div class="footer__upperLine__subscribe">
          <div class="footer__upperLine__subscribe__heading-wrapper">
            <h3 class="footer__upperLine__subscribe__heading">
              {{ subscribe.heading }}
            </h3>
          </div>
          <div class="footer__upperLine__subscribe__text-wrapper">
            <p class="footer__upperLine__subscribe__text">
              {{ subscribe.text }}
            </p>
          </div>
          <form
            action="#"
            method="POST"
            class="footer__upperLine__subscribe__form"
          >
            <input
              class="footer__upperLine__subscribe__input"
              type="text"
              placeholder="email@example.com"
            />
            <Button name="Get Started For Free" link="#"></Button>
          </form>
        </div>
      </div>
      <div class="footer__bottomLine">
        <div class="flex">
          <div class="footer__bottomLine__aboutUs">
            <Logo></Logo>
            <div class="flex">
              <div class="footer__bottomLine__aboutUs__icon-wrapper">
                <img
                  class=".footer__bottomLine__aboutUs__icon"
                  :src="aboutUs.icon.src"
                  :alt="aboutUs.icon.alt"
                  :title="aboutUs.icon.title"
                />
              </div>
              <div class="footer__bottomLine__aboutUs__text-wrapper">
                <p class="footer__bottomLine__aboutUs__text">
                  {{ aboutUs.text }}
                </p>
              </div>
            </div>
          </div>
          <div class="footer__bottomLine__contactInfo">
            <ContactLine
              v-for="item in contactInfo"
              :key="item.id"
              :icon="item.icon"
              :text="item.text"
            ></ContactLine>
          </div>
          <ColumnNav
            v-for="item in footerNav"
            :key="item.id"
            :navItem="item.navItems"
          ></ColumnNav>
          <div class="footer__bottomLine__socialLinks">
            <SocialLinks></SocialLinks>
          </div>
        </div>
      </div>
    </div>
  </footer>
</template>

<script>
import Button from "../secondary/Button";
import Logo from "../secondary/Logo";
import ContactLine from "../secondary/iconPlusTextInline";
import ColumnNav from "../secondary/FooterColumnNav";
import SocialLinks from "../secondary/SocialLinks";
export default {
  name: "Footer",
  components: { Button, Logo, ContactLine, ColumnNav, SocialLinks },
  data() {
    return {
      subscribe: {
        heading: "Get early access today",
        text:
          "It only takes a minute to sign up and our free starter tier is extremely generous. If you have any " +
          "questions, our support team would be happy to help you."
      },
      aboutUs: {
        icon: {
          src: "./images/icon-location.svg",
          alt: "Map pin",
          title: "Location"
        },
        text:
          "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et " +
          "dolore magna aliqua"
      },
      contactInfo: [
        {
          id: 1,
          icon: {
            src: "./images/icon-phone.svg",
            alt: "phone",
            title: "Phone"
          },
          text: "+1-543-123-4567"
        },
        {
          id: 2,
          icon: {
            src: "./images/icon-email.svg",
            alt: "email",
            title: "Email"
          },
          text: "example@fylo.com"
        }
      ],
      footerNav: [
        {
          id: 1,
          navItems: [
            {
              id: 1,
              text: "About Us",
              link: "link"
            },
            {
              id: 2,
              text: "Jobs",
              link: "link"
            },
            {
              id: 3,
              text: "Press",
              link: "link"
            },
            {
              id: 4,
              text: "Blog",
              link: "link"
            }
          ]
        },
        {
          id: 2,
          navItems: [
            {
              id: 1,
              text: "Contact Us",
              link: "link"
            },
            {
              id: 2,
              text: "Terms",
              link: "link"
            },
            {
              id: 3,
              text: "Privacy",
              link: "link"
            }
          ]
        }
      ]
    };
  }
};
</script>
<style lang="scss">
.footer {
  &__upperLine {
    &__subscribe {
      &__heading {
        &-wrapper {
        }
      }
      &__text {
        &-wrapper {
        }
      }
      &__form {
      }
      &__input {
      }
    }
  }
  &__bottomLine {
    &__aboutUs {
      &__icon {
        &-wrapper {
        }
      }
      &__text {
        &-wrapper {
        }
      }
    }
  }
}
</style>
