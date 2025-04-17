<template>
  <div class="footer">
    <b-container class="pt-4">
      <b-row>
        <b-col>
          <p>
            <i class="bi bi-geo-alt-fill"></i> Gral. Gervasio Artigas 3985, Agronomía, Capital Federal.
          </p>
          <p><i class="bi bi-telephone"></i> 011 4573-1263</p>
          <p><i class="bi bi-envelope"></i> ferreteriatardini@gmail.com</p>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>
<script>
export default {
  name: "foot",
  components: {},
  data() {
    return {};
  },
};
</script>
<style scoped>
.footer {
  background-color: #3B3B3B
;
  min-height: 200px;
}
p {
  color: #F8F9F9;
}
a {
  color: #F8F9F9 !important;
}
</style>