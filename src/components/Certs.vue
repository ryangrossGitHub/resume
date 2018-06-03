<template>
  <div id="background">
    <div class="container">
      <div class="row">
        <div id="certLogoCol" class="col">
          <img id="certLogo" src="https://s3.amazonaws.com/resume-host-images/AWS_Certified_Logo_294x230_Black.png">
        </div>
        <div class="col-lg-auto">
          <a v-for="cert in certs" target="_blank" :href="cert">
            <img class="certImage" :src="cert">
          </a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { setTimeout } from 'timers';

export default {
  name: 'Certs',
  data() {
    return {
      certs: [
        'https://s3.amazonaws.com/resume-host-images/AWS+Certified+DevOps+Engineer+-+Professional.PNG',
        'https://s3.amazonaws.com/resume-host-images/AWS+Certified+Solutions+Architect+-+Professional.PNG',
        'https://s3.amazonaws.com/resume-host-images/AWS+Certified+Solutions+Architect+-+Associate.PNG',
        'https://s3.amazonaws.com/resume-host-images/AWS+Certified+Developer+-+Associate.PNG',
        'https://s3.amazonaws.com/resume-host-images/AWS+Certified+SysOps+Administrator+-+Associate.PNG'
      ]
    }
  },
  mounted: function () {
    var timeout = 0;

    Array.from(document.getElementsByClassName('certImage')).forEach(element => {
      timeout += 120;
      setTimeout(function(){
        element.className += " drop";
      }, timeout)
    });  
    
    setTimeout(function(){
      Array.from(document.getElementsByClassName('certImage')).forEach(element => {
        element.className = 'certImage';
        element.style.bottom = '0px';
      }); 
    }, 2000)
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#background {
  background-color: #F89C1C;
}
.row {
  padding: 1rem 0rem;
}
#certLogo {
  width: 150px;
}
#certLogoCol {
  margin: auto 0 auto 1rem;
}
.col-lg-auto {
  overflow: hidden;
}
img {
  width: 150px;
  margin: 1rem 0.5rem;
}
.certImage {
  position: relative;
  bottom: 160px;
}
.drop {
  animation-name: drop;
	animation-duration: 1.2s;
  animation-iteration-count: 1;
  bottom: 0px;
}
.certImage:hover {
  animation-name: grow;
	animation-duration: 0.2s;
  animation-iteration-count: 1;
  transform: scale(1.1);
}
@keyframes grow {
	0% {
		transform: scale(1);
	}
	100% {
		transform: scale(1.1);
    animation-timing-function: ease-out;
	}
}
@keyframes drop {
	0% {
		bottom: 160px;
  }
	100% {
		bottom: 0px;
	}
}
</style>
