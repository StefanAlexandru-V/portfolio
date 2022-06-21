<template>
  <div id="app">
    <main class="content">
      <Particles
          id="tsparticles"
          :particlesInit="particlesInit"
          :particlesLoaded="particlesLoaded"
          :options="{
                        background: {
                            color: {
                                value: 'rgb(51,77,92)'
                            }
                        },
                        fullScreen: {
                          enable: true,
                          zIndex: -1,
                        },
                        fpsLimit: 120,
                        interactivity: {
                            events: {
                                onClick: {
                                    enable: true,
                                    mode: 'repulse'
                                },
                                onHover: {
                                    enable: true,
                                    mode: 'trail'
                                },
                                resize: true
                            },
                            modes: {
                                bubble: {
                                    distance: 400,
                                    duration: 2,
                                    opacity: 0.8,
                                    size: 40
                                },
                                push: {
                                    quantity: 4
                                },
                                repulse: {
                                    distance: 200,
                                    duration: 0.4
                                }
                            }
                        },
                        particles: {
                            color: {
                                value: ''
                            },
                            links: {
                                color: 'rgba(1,1,1,0.07)',
                                distance: 150,
                                enable: true,
                                opacity: 0.5,
                                width: 1
                            },
                            collisions: {
                                enable: true
                            },
                            move: {
                                direction: 'none',
                                enable: true,
                                outModes: {
                                    default: 'bounce'
                                },
                                random: false,
                                speed: 2,
                                straight: false
                            },
                            number: {
                                density: {
                                    enable: true,
                                    area: 1200
                                },
                                value: 80
                            },
                            opacity: {
                                value: 0.5
                            },
                            shape: {
                                type: 'circle'
                            },
                            size: {
                                value: { min: 1, max: 5 },
                            }
                        },
                        detectRetina: true
                    }"
      />
      <Rocket></Rocket>
    </main>

  </div>
</template>
<style lang="scss">

html, body {
  width: 100%;
  height: 100%;
  overflow: hidden;
}

body {
  display: flex;
  align-items: center;
  justify-content: center;
}
.logo {
  width: 150px;
}


</style>
<script>
import { loadFull } from "tsparticles";
import Rocket from './components/partials/Rocket.vue';
export default {

  components: {
    Rocket,
  },

  data() {
    return {
      particlesInit: false,
      particlesLoaded: false,
    }
  },
  async created() {
     this.particlesInit = async (engine) => {
      await loadFull(engine);
    }
    this.particlesLoaded = async (container) => {
      console.log("Particles container loaded", container);
    }
  },
}
</script>