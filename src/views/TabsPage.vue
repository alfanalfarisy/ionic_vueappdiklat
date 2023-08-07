<template>
  <ion-page>
    <ion-tabs>
      <ion-router-outlet></ion-router-outlet>
      <ion-tab-bar slot="bottom">
        <ion-tab-button tab="home" href="/main/home">
          <ion-icon aria-hidden="true" :icon="pizza" />
          <ion-label>Home</ion-label>
        </ion-tab-button>

        <ion-tab-button tab="cuaca" href="/main/cuaca">
          <ion-icon aria-hidden="true" :icon="balloonSharp" />
          <ion-label>Cuaca</ion-label>
        </ion-tab-button>

        <ion-tab-button tab="gempa" href="/main/gempa">
          <ion-icon aria-hidden="true" :icon="cut" />
          <ion-label>Gempa</ion-label>
        </ion-tab-button>
      </ion-tab-bar>
    </ion-tabs>
  </ion-page>
</template>

<script setup >
import { IonTabBar, IonTabButton, IonTabs, IonLabel, IonIcon, IonPage, IonRouterOutlet } from '@ionic/vue';
import { balloonSharp, cut, pizza } from 'ionicons/icons';
</script>
