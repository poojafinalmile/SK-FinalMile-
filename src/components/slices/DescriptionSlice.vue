<template>
<div class="highlight-left">
  <div class="row py-2 py-sm-2 py-md-3 py-lg-5">
    <div class="col-xl-8 col-lg-10 col-md-10 mx-auto text-center">
      <prismic-rich-text class="heading-custom-color pb-md-2 mb-3 mb-md-4" :field="slice.primary.band_name"/>
      <prismic-rich-text class="title-custom-color mb-3 mb-md-4"  :field="slice.primary.title"/>
      <prismic-rich-text class="description mb-3 mb-md-5" :field="slice.primary.description_body"/>
      <template v-if="$prismic.richTextAsPlain(slice.primary.link_label) !== ''">
        <p class="pt-2 pt-md-3">
          <prismic-link  class="'btn btn-circle" :field="slice.primary.link">{{ $prismic.richTextAsPlain(slice.primary.link_label) }}</prismic-link>
        </p>
      </template>
    </div>
  </div>
</div>
</template>

<script>
export default {
  props: ['slice'],
  name: 'description-slice',
    data () {
      return {
        fields: {
         bandNameColor: null
        }
      };
    },
    methods: {
      // This is an example query, the important part is above.
      getContent () {
        this.$prismic.client.getSingle('page')
          .then((document) => {
            this.fields.bandNameColor = document.data.page_content.band_name_color;
            console.log(document.data.band_name_color);
          })
      }
    },
    created () {
      this.getContent();
    }
}
</script>

<style scoped>
.btn-circle {
  text-decoration: none;
  color: #ff009c;
  border:2px solid #ff009c;
  border-radius: 48px;
  padding: 10px 20px;
}
.btn-circle:hover {
  color: #fff;
  border:2px solid #fff;
  background: #ff009c;
}
.title-custom-color{
  color:#5b146f;
}
.heading-custom-color{
  color: #ff009c;
}
.description {
  color: #464646;
}
</style>
