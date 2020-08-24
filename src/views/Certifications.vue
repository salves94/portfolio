<template>
  <section class="resume-section p-3 p-lg-5 d-flex align-items-center" id="certifications">
    <div class="w-100">
      <h2 class="mb-5">Certifications</h2>

      <div v-for="cert in certifications" :key="cert.key" class="resume-item d-flex flex-column flex-md-row justify-content-between mb-5">
        <div class="resume-content">
          <h3 class="mb-0">{{cert.school}}</h3>
          <div class="subheading mb-3">{{cert.subject}}</div>
          <div v-if="cert.id">
            Credential ID {{cert.id}}
          </div>
          <div v-if="cert.link">
            <a :href="cert.link" target="_BLANK">See credential</a>
          </div>
        </div>
        <div class="resume-date text-md-right">
          <span class="text-primary">{{cert.date}}</span>
        </div>
      </div>

      <div class="resume-item d-flex flex-column flex-md-row justify-content-between">
      </div>

    </div>
  </section>
</template>

<script>
import certs from '@/constants/certifications'
export default {
  name: 'Certifications',
  data(){
    return {
      certifications: certs
    }
  },
  mounted(){
    this.certifications.reverse()
  }
}
</script>

<style>

</style>