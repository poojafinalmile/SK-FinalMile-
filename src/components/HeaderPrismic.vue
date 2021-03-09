<template>
  <header class="site-header">
    <nav class="navbar navbar-expand-lg navbar-dark bg-trasparent">
      <div class="container-fluid">
        <router-link to="/" class="logo ms-2 ms-md-3 ms-xl-5 text-white"><strong> final</strong>mile <img src="../assets/img/logo_footprint.png" alt="Finalmile" width="30" height="50"></router-link>
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#mobilenav" aria-controls="mobilenav" aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="mobilenav">
          <ul class="navbar-nav pt-5 px-3 px-sm-4 px-lg-0 pt-lg-0 ms-auto">
            <li v-for="menuLink in menuLinks" :key="menuLink.id" class="nav-item">
              <prismic-link :field="menuLink.link" index class="nav-link fadeInDown">{{ $prismic.richTextAsPlain(menuLink.label) }}</prismic-link>
            </li>
          </ul>
        </div>
      </div>
    </nav>
  </header>
  
</template>


<script>
export default {
  name: 'HeaderPrismic',
  data () {
    return {
      menuContent: [],
      menuLinks: []
    }
  },
  methods: {
    getMenu () {
      //Query to get menu content
      this.$prismic.client.getSingle('menu')
        .then((menuContent) => {
          this.menuContent = menuContent
          this.menuLinks = menuContent.data.menu_links
        })
    },
  },
  created () {
    this.getMenu()
  }
}

// Use only one out of these two
// menu loading funtion one 
// function docReady(fn) {
//     if (document.readyState === "complete" || document.readyState === "interactive") {
//         setTimeout(fn, 1);
//     } else {
//         document.addEventListener("DOMContentLoaded", fn);
//     }
// }  

// docReady(function() {
//     var BtnTarget = document.querySelector('.navbar-toggler-icon');
//     BtnTarget.addEventListener('click',function (){
//       document.querySelector("nav.navbar-expand-lg").classList.toggle("bg-dark");
//     }); 
// });
// menu loading funtion two 
setTimeout(function(){
  var BtnTarget = document.querySelector('.navbar-toggler-icon');
    BtnTarget.addEventListener('click',function (){
      document.querySelector("nav.navbar-expand-lg").classList.toggle("bg-dark");
    }); 
}, 1000); 
</script>

<style>
.logo {
  text-decoration: none;
}
.navbar {
  position: absolute;
  width: 100%;
  top: 15px;
  left: 0;
  z-index:1;
}
@media (min-width: 1400px) {
  .logo {
    font-size: 50px;
  }
}
@media (min-width: 1200px) {
  .logo {
    font-size: 40px;
  }
}
@media (min-width: 992px) {
  .navbar {
    top: 15px;
  }
   .logo {
    font-size: 35px;
  }
}
@media (max-width: 991px) {
  #mobilenav{
    z-index:3;
    height: 100vh;
  }
  .navbar {
    top: 0px;
  }
  .navbar.bg-dark {
    position: fixed;
  }
  .logo {
    font-size: 30px;
  }
}

@-webkit-keyframes fadeInDown {
    from {
        opacity:0;
        -webkit-transform: translatey(-10px);
        -moz-transform: translatey(-10px);
        -o-transform: translatey(-10px);
        transform: translatey(-10px);
    }
    to {
        opacity:1;
        -webkit-transform: translatey(0);
        -moz-transform: translatey(0);
        -o-transform: translatey(0);
        transform: translatey(0);
    }
}
@-moz-keyframes fadeInDown {
    from {
        opacity:0;
        -webkit-transform: translatey(-10px);
        -moz-transform: translatey(-10px);
        -o-transform: translatey(-10px);
        transform: translatey(-10px);
    }
    to {
        opacity:1;
        -webkit-transform: translatey(0);
        -moz-transform: translatey(0);
        -o-transform: translatey(0);
        transform: translatey(0);
    }
}
@keyframes fadeInDown {
    from {
        opacity:0;
        -webkit-transform: translatey(-10px);
        -moz-transform: translatey(-10px);
        -o-transform: translatey(-10px);
        transform: translatey(-10px);
    }
    to {
        opacity:1;
        -webkit-transform: translatey(0);
        -moz-transform: translatey(0);
        -o-transform: translatey(0);
        transform: translatey(0);
    }
}
.fadeInDown {
    -webkit-animation-name: fadeInDown;
    -moz-animation-name: fadeInDown;
    -o-animation-name: fadeInDown;
    animation-name: fadeInDown;
    -webkit-animation-fill-mode: both;
    -moz-animation-fill-mode: both;
    -o-animation-fill-mode: both;
    animation-fill-mode: both;
    -webkit-animation-duration: 1s;
    -moz-animation-duration: 1s;
    -o-animation-duration: 1s;
    animation-duration: 1s;
}
</style>