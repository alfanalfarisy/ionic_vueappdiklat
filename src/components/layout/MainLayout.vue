<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>{{title}}</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true" class="ion-padding">

      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">{{title}}</ion-title>
        </ion-toolbar>
      </ion-header>


      <slot></slot>
    </ion-content>
  </ion-page>
</template>
  
<script setup >
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent } from '@ionic/vue';
const props = defineProps({
  title: {
    type: String,
    required: true
  },
})
</script>
  