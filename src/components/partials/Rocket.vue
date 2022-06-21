<template>
  <div class="rocket">
    <div class="rocket-body">
      <div class="body"></div>
      <div class="fin fin-left"></div>
      <div class="fin fin-right"></div>
      <div class="window"></div>
    </div>
<!--    TODO: implement animation when rocket is clicked -> remove exhaust fumes and swap exhaust-flame with flame-wrapper-->
<!--    <div class="exhaust-flame"></div>-->
    <div class="flame-wrapper">
      <div class="flame red"></div>
      <div class="flame orange"></div>
      <div class="flame gold"></div>
      <div class="flame white"></div>
    </div>
    <ul class="exhaust-fumes">
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
    </ul>
  </div>
</template>
<style lang="scss">
$white: #f5f5f5;
$lightgrey: #dadada;
$midgrey: #b4b2b2;
$darkgrey: #554842;
$red: #f01a19;
$darkred: #a75248;


.rocket {
  position: absolute;
  top: 20%;
  width: 80px;
  left: calc(50% - 60px);
.rocket-body {
  width: 80px;
  left: calc(50% - 50px);
  animation: bounce 0.5s infinite;
.body {
  background-color: $lightgrey;
  height: 180px;
  left: calc(50% - 50px);
  border-top-right-radius: 100%;
  border-top-left-radius: 100%;
  border-bottom-left-radius: 50%;
  border-bottom-right-radius: 50%;
  border-top: 5px solid $white;
}
&:before {
   content: '';
   position: absolute;
   left: calc(50% - 24px);
   width: 48px;
   height: 13px;
   background-color: $darkgrey;
   bottom: -13px;
   border-bottom-right-radius: 60%;
   border-bottom-left-radius: 60%;
 }
}
.window {
  position: absolute;
  width: 40px;
  height: 40px;
  border-radius: 100%;
  background-color: $darkred;
  left: calc(50% - 25px);
  top: 40px;
  border: 5px solid $midgrey;
}
.fin {
  position: absolute;
  z-index: -100;
  height: 55px;
  width: 50px;
  background-color: $darkred;
}
.fin-left {
  left: -30px;
  top: calc(100% - 55px);
  border-top-left-radius: 80%;
  border-bottom-left-radius: 20%;
}
.fin-right {
  right: -30px;
  top: calc(100% - 55px);
  border-top-right-radius: 80%;
  border-bottom-right-radius: 20%;
}
.exhaust-flame {
  position: absolute;
  top: 90%;
  width: 28px;
  background: linear-gradient(to bottom, transparent 10%, $white 100%);
  height: 150px;
  left: calc(50% - 14px);
  animation: exhaust 0.2s infinite;
}

.exhaust-fire {
  position: absolute;
  top: 90%;
  width: 28px;
  background-color: #ff4e00;
  background-image: linear-gradient(315deg, #ff4e00 0%, #ec9f05 74%);
  height:150px;
  left: calc(50% - 14px);
  animation: exhaust 0.2s infinite;
}

.exhaust-fumes li {
  width: 60px;
  height: 60px;
  background-color: $white;
  list-style: none;
  position: absolute;
  border-radius: 100%;
&:first-child {
   width: 200px;
   height: 200px;
   bottom: -300px;
   animation: fumes 5s infinite;
 }
&:nth-child(2) {
   width: 150px;
   height: 150px;
   left: -120px;
   top: 260px;
   animation: fumes 3.2s infinite;
 }
&:nth-child(3) {
   width: 120px;
   height: 120px;
   left: -40px;
   top: 330px;
   animation: fumes 3s 1s infinite;
 }
&:nth-child(4) {
   width: 100px;
   height: 100px;
   left: -170px;
   animation: fumes 4s 2s infinite;
   top: 380px;
 }
&:nth-child(5) {
   width: 130px;
   height: 130px;
   left: -120px;
   top: 350px;
   animation: fumes 5s infinite;
 }
&:nth-child(6) {
   width: 200px;
   height: 200px;
   left: -60px;
   top: 280px;
   animation: fumes2 10s infinite;
 }
&:nth-child(7) {
   width: 100px;
   height: 100px;
   left: -100px;
   top: 320px;
 }
&:nth-child(8) {
   width: 110px;
   height: 110px;
   left: 70px;
   top: 340px;
 }
&:nth-child(9) {
   width: 90px;
   height: 90px;
   left: 200px;
   top: 380px;
   animation: fumes 20s infinite;
 }
}
}

@keyframes fumes {
  50% {
    transform: scale(1.5);
    background-color: transparent;
  }
  51% {
    transform: scale(0.8);
  }
  100% {
    background-color: $white;
    transform: scale(1)
  }
}

@keyframes bounce {
  0% {
    transform: translate3d(0px, 0px, 0);
  }
  50% {
    transform: translate3d(0px, -4px, 0);
  }
  100% {
    transform: translate3d(0px, 0px, 0);
  }
}

@keyframes exhaust {
  0% {
    background: linear-gradient(to bottom, transparent 10%, $white 100%);
  }
  50% {
    background: linear-gradient(to bottom, transparent 8%, $white 100%);
  }
  75% {
    background: linear-gradient(to bottom, transparent 12%, $white 100%);
  }
}

@keyframes fumes2 {
  50% {
    transform: scale(1.1);
  }
}

@keyframes twinkle {
  80% {
    transform: scale(1.1);
    opacity: 0.7;
  }
}

.red {
  width: 80px;
  height: 80px;
  background: orangered;
  box-shadow: 0px 0px 10px 5px orangered;
}
.orange {
  left:10px;
  width: 60px;
  height: 60px;
  background: orange;
  box-shadow: 0px 0px 12px 6px orange;
}
.gold {
  left:18px;
  width: 45px;
  height: 45px;
  background: gold;
  box-shadow: 0px 0px 9px 4px gold;
}
.white {
  left:22px;
  width: 35px;
  height: 35px;
  background: lightyellow;
  box-shadow: 0px 0px 9px 4px lightyellow;
}
.blue {
  left:32px;
  width: 15px;
  height: 15px;
  background: darkblue;
  box-shadow: 0px 0px 15px 10px darkblue;
}
.black {
  left:20px;
  width: 40px;
  height: 40px;
  bottom:-50px;
  background: black;
  box-shadow: 0px 0px 15px 10px black;
}
.base {
  border-radius: 50%;
  position: absolute;
}
.flame-wrapper {
  position: relative;
  animation: flicker 3ms ease-in infinite;
}
.flame {
  bottom: 0;
  position: absolute;
  border-radius: 50% 0% 50% 50%;
  transform:rotate(135deg);
  top: 3px;
}
@keyframes flicker {
  0% {transform: rotate(-1deg);}
  20% {transform: rotate(2deg) scaleY(1.05);}
  40% {transform: rotate(-1deg);}
  60% {transform: rotate(1deg);}
  80% {transform: rotate(-1deg) scaleY(0.90);}
  100% {transform: rotate(1deg);}
}
</style>
<script>

export default {
  props: {
    isDisabled: {
      type: Boolean,
      required: false,
      default: false,
    },
  },

  data() {
    return {}
  },
}
</script>
