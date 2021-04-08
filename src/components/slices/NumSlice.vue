<template>
 <div class="row py-4 py-md-3 py-lg-5 mt-4 mt-sm-5 mb-4 mb-md-3 custom-bg-color">
    <template  v-if="$prismic.richTextAsPlain(slice.primary.number_slice_title) !== ''">
      <div class="col-xxl-8 col-xl-8 col-lg-10 col-md-12 mx-auto text-center">
        <prismic-rich-text :field="slice.primary.number_slice_title" :class="'pb-3 pb-lg-5 text-white'"/>
      </div>
    </template>
    <div class="col-xxl-8 col-xl-8 col-lg-10 col-md-12 mx-auto text-center">
      <div class="row">
          <div v-for="(item,index) in slice.items" :key="item.id" class="col-xl-4 col-lg-4 col-md-4 text-center">
             <div :class="'counter-'+ index"></div>
             <P class="text-white pt-2">{{ item.title }}</p>
          </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['slice'],
  name: 'num-slice',
}
</script>

<style scoped>
.custom-bg-color {
  background:#5b146f;
}
.counter-0, .counter-1, .counter-2 {
  font: 700 50px system-ui;
}
@media (min-width: 1200px) { 
  .counter-0, .counter-1, .counter-2 {
    font: 700 70px system-ui;
  }
 }

.counter-0 {
   -webkit-animation: counterzero 10s ;
  -moz-animation: counterzero 10s ;
  -ms-animation: counterzero 10s ;
  animation: counterzero 10s ;
  counter-reset: num var(--num);
  animation-iteration-count: 1;
  animation-fill-mode: forwards;
  padding: 0rem;
  color:#ffffff;
}
.counter-0::after {
  content: counter(num);
}

.counter-1 {
   -webkit-animation: counterone 10s ;
  -moz-animation: counterone 10s ;
  -ms-animation: counterone 10s ;
  animation: counterone 10s ;
  counter-reset: num var(--num);
  animation-iteration-count: 1;
  animation-fill-mode: forwards;
  padding: 0rem;
  color:#ffffff;
}
.counter-1::after {
  content: counter(num);
}
.counter-2 {
    -webkit-animation: countertwo 10s ;
  -moz-animation: countertwo 10s ;
  -ms-animation: countertwo 10s ;
  animation: countertwo 10s ;
  counter-reset: num var(--num);
  animation-iteration-count: 1;
  animation-fill-mode: forwards;
  padding: 0rem;
  color:#ffffff;
}
.counter-2::after {
  content: counter(num);
}
@property --num {
  syntax: "<integer>";
  initial-value: 0;
  inherits: false;
}
@-webkit-keyframes counterzero {
  from {
    --num: 0;
  }
  to {
    -webkit--num: 500000;
  }
}

@-moz-keyframes counterzero {
  from {
    --num: 0;
  }
  to {
    --num: 500000;
  }
}

@keyframes counterzero {
  from {
    --num: 0;
  }
  to {
    --num: 500000;
  }
}

@-webkit-keyframes counterone {
  from {
    --num: 0;
  }
  to {
    -webkit--num: 374000;
  }
}

@-moz-keyframes counterone {
  from {
    --num: 0;
  }
  to {
    --num: 374000;
  }
}

@keyframes counterone {
  from {
    --num: 0;
  }
  to {
    --num: 374000;
  }
}

@-webkit-keyframes countertwo {
  from {
    --num: 0;
  }
  to {
    -webkit--num: 130000;
  }
}

@-moz-keyframes countertwo {
  from {
    --num: 0;
  }
  to {
    --num: 130000;
  }
}

@keyframes countertwo {
  from {
    --num: 0;
  }
  to {
    --num: 130000;
  }
}
</style>




