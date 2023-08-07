<script setup>
import { ref } from "vue";

const lokasiUser = ref('');

function submitLokasi() {
  console.log('ok');
}
</script>

<template>
  <section>
    <div class="cuaca p-3">
      <div class="row mb-4">
        <div class="col-8">
          <!-- Use the value directly when working with ref in the template -->
          <input type="text" v-model="lokasiUser" class="form-control" id="pilih-lokasi" />
        </div>
        <div class="col-4">
          <button @click="submitLokasi" class="btn bg-cuaca-siang form-control text-light">
            Submit
          </button>
        </div>
      </div>

      <div class="card p-2 d-flex flex-col text-center shadow rounded">
        <div class="fw-bold">Kemayoran</div>
        <div>13:00</div>
        <img
          class="mx-auto d-block img-cuaca"
          src="https://bmkg.go.id/asset/img/icon-cuaca/cerah%20berawan-am.png"
          alt="icon-cuaca"
        />
        <div class="m-2">Cerah Berawan</div>
        <div>27<span>&#176;</span>C 100%</div>
      </div>
    </div>
  </section>
</template>

<style lang=""></style>
