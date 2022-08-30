<template>
  <div
    class="_header relative flex flex-col justify-between items-center px-2 h-screen"
  >
    <div
      class="_header_container flex justify-between items-center w-full h-16"
    >
      <div class="_logo font-bold text-xl">
        IBOU <span class="text-blue-700">..</span>
      </div>
      <!-- § -->
      <div class="_nav h-full flex gap-4">
        <div class="h-full flex gap-4">
          <a
            v-for="link in linkS"
            :key="link"
            href="#"
            class="h-full flex items-center px-3 duration-300 _hoverBlack"
          >
            {{ link.name }}
          </a>
        </div>
      </div>
      <div class="_contact h-full">
        <nuxt-link
          to="/contact"
          class="h-full flex items-center px-3 duration-300 _hoverBlack"
          >Contact</nuxt-link
        >
      </div>
    </div>
    <!-- § -->
    <div class="_presentation w-full flex justify-between">
      <div class="_presentationLeft w-full">
        <div class="_leftFirstChild h-3/5 flex justify-center items-center">
          <H1 />
        </div>
        <div
          class="_leftSecondChild flex flex-col items-center"
          data-aos="fade-up"
          data-aos-duration="3000"
        >
          <p class="_citation">
            “N’importe quel idiot peut écrire du code qu'un ordinateur peut
            comprendre. <br />
            Les bons programmeurs écrivent du code que les humains peuvent
            comprendre.”
          </p>
          <span class="font-bold">Martin Fowler</span>
        </div>
      </div>
    </div>
    <a
      href="#"
      class="_scrollToBottom cursor-pointer flex justify-center items-center h-16 w-16 absolute bottom-10"
    >
      <i class="fa-solid fa-arrow-down-long text-2xl"></i>
    </a>
  </div>
</template>

<script>
import { onMounted } from '@nuxtjs/composition-api'
// .
export default {
  name: 'HeaderPage',
  setup() {
    // .
    onMounted(function () {
      AOS.init()
    })
    // .
    return {
      linkS: [
        {
          name: 'Services',
        },
        {
          name: 'About',
        },
        {
          name: "My work's",
        },
        {
          name: "My life's Style",
        },
      ],
      classes: 'text-3xl absolute',
    }
  },
}
</script>

<style lang="scss">
// Var
$primaire: #eeeeee;

._header {
  background: url('https://media.istockphoto.com/photos/white-studio-background-picture-id1040250650?b=1&k=20&m=1040250650&s=616x616&w=0&h=b-ijOD-3NFHSgUW7cwBel6j4ubmIQDS8Q7jOjTO2U08=');
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;
  overflow: hidden;
}

._hoverBlack {
  position: relative;
  transition: 700ms cubic-bezier(0.075, 0.82, 0.165, 1);
  overflow: hidden;
  &::before {
    content: '';
    transition: 700ms cubic-bezier(0.075, 0.82, 0.165, 1);
    position: absolute;
    bottom: 0;
    height: 10%;
    width: 200%;
    transform: translateX(100%);
    background-color: #000000;
  }

  &:hover {
    &::before {
      content: '';
      transform: translateY(0) translateX(-1rem);
    }
  }
}

._leH1 {
  font-size: 7vw;
}

._presentation {
  height: 90vh;

  ._leftSecondChild {
    height: 30%;
  }
}

.fa-arrow-down-long {
  animation-name: fa-arrow-down-long;
  animation-duration: 2s;
  animation-iteration-count: infinite;
  animation-timing-function: ease;
}

@keyframes fa-arrow-down-long {
  0% {
    transform: translateY(1rem);
  }
  50% {
    transform: translateY(0);
  }
  100% {
    transform: translateY(1rem);
  }
}
</style>
