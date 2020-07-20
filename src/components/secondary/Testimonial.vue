<template>
  <div class="flex" style="position: relative; z-index: 3;">
    <img
      class="testimonials__quotes"
      :src="quotes.src"
      :alt="quotes.alt"
      :title="quotes.title"
    />
    <div class="wid-33" v-for="item in testimonials" :key="item.id">
      <div class="testimonials__testimonial-wrapper">
        <div class="testimonials__testimonial">
          <div class="testimonials__testimonial__text-wrapper">
            <p class="testimonials__testimonial__text">
              {{ item.text }}
            </p>
          </div>
          <div class="flex">
            <div>
              <div class="testimonials__testimonial__profile-image">
                <img
                  :src="item.img.src"
                  :alt="item.img.alt"
                  :title="item.img.title"
                />
              </div>
            </div>
            <div>
              <p class="testimonials__testimonial__profile-fullname">
                {{ item.fullname }}
              </p>
              <p class="testimonials__testimonial__profile-position">
                {{ item.position }}
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      quotes: {
        src: "./images/bg-quotes.png",
        alt: "quotes-icon",
        title: "quotes"
      },
      testimonials: [
        {
          id: 1,
          text:
            "Fylo has improved our team productivity by an order of magnitude. Since making the switch our team has " +
            "become a well-oiled collaboration machine.",
          img: {
            src: "./images/profile-1.jpg",
            alt: "profile photo",
            title: "Satish Patel"
          },
          fullname: "Satish Patel",
          position: "Founder & CEO, Huddle"
        },
        {
          id: 2,
          text:
            "Fylo has improved our team productivity by an order of magnitude. Since making the switch our team has " +
            "become a well-oiled collaboration machine.",
          img: {
            src: "./images/profile-2.jpg",
            alt: "profile photo",
            title: "Bruce McKenzie"
          },
          fullname: "Bruce McKenzie",
          position: "Founder & CEO, Huddle"
        },
        {
          id: 3,
          text:
            "Fylo has improved our team productivity by an order of magnitude. Since making the switch our team has " +
            "become a well-oiled collaboration machine.",
          img: {
            src: "./images/profile-3.jpg",
            alt: "profile photo",
            title: "Iva Boyd"
          },
          fullname: "Iva Boyd",
          position: "Founder & CEO, Huddle"
        }
      ]
    };
  }
};
</script>

<style lang="scss">
.testimonials {
  &__quotes {
    position: absolute;
    left: 1.2rem;
    top: -1.45rem;
    width: 3.3rem;
    height: 3rem;
    z-index: -1;
  }
  &__testimonial {
    background-color: $darkBlue-testimonials;
    padding: 2.4rem 1.5rem 1.5rem 1.75rem;
    &-wrapper {
      padding: 1rem 1rem 1rem 1.5rem;
    }
    &__text {
      &-wrapper {
        padding-bottom: 1.7rem;
      }
      color: $white;
      line-height: 20px;
      word-spacing: 3px;
    }
    &__profile {
      &-image {
        border-radius: 50%;
        width: 1.5rem;
        height: 1.5rem;
        overflow: hidden;
        margin-right: 0.5rem;
        img {
          width: 100%;
          object-fit: cover;
        }
      }
      &-fullname {
        color: $white;
        font-size: 10px;
        letter-spacing: 1px;
      }
      &-position {
        color: $white;
        font-size: 6px;
        letter-spacing: 1px;
        padding-top: 4px;
      }
    }
  }
}
</style>
