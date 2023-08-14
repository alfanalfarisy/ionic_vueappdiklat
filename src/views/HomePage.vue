<template>
  <main-layout title="Home">
    <ion-card>
      <img alt="Silhouette of mountains"
        src="../assets/warning.jpeg" />
      <ion-card-header>
        <ion-card-title>Warning Cuaca</ion-card-title>
        <ion-card-subtitle>Sidoarjo, Jawa Timur</ion-card-subtitle>
      </ion-card-header>



      <ion-card-content>
        Peringatan dini terhadap beberapa kota berikut, Klik untuk selengkapnya.
      </ion-card-content>
    </ion-card>
    <ion-card>
      <ion-input label="Kecamatan" label-placement="floating" fill="outline" placeholder="Enter text" style="margin-left: 10px;"></ion-input>
    </ion-card>
    <ion-card>
      <ion-card-header>
        <ion-card-title>Prakiraan Cuaca</ion-card-title>
      </ion-card-header>

      <ion-card-content>
        <swiper>
          <swiper-slide>
            <ion-item>
              <ion-label>
                <h2>Lumajang</h2>
                <p>28°C - Clear</p>
              </ion-label>
              <ion-thumbnail slot="start">
                <img alt="Weather icon" src="../assets/berawanmalam.png" />
              </ion-thumbnail>
            </ion-item>
          </swiper-slide>
          <swiper-slide>
            <ion-item>
              <ion-label>
                <h2>Surabaya</h2>
                <p>30°C - Cloudy</p>
              </ion-label>
              <ion-thumbnail slot="start">
                <img alt="Weather icon" src="../assets/berawansiang.png" />
              </ion-thumbnail>
            </ion-item>
          </swiper-slide>
          <swiper-slide>
            <ion-item>
              <ion-label>
                <h2>Malang</h2>
                <p>27°C - Rainy</p>
              </ion-label>
              <ion-thumbnail slot="start">
                <img alt="Weather icon" src="../assets/hujanringan.png" />
              </ion-thumbnail>
            </ion-item>
          </swiper-slide>
        </swiper>
      </ion-card-content>
    </ion-card>

  </main-layout>
</template>

<script setup >
import MainLayout from '../components/layout/MainLayout.vue';
import { IonCard, IonCardContent, IonCardHeader, IonCardSubtitle, IonCardTitle, IonLabel, IonThumbnail, IonItem, IonInput } from '@ionic/vue';

import { Swiper, SwiperSlide } from 'swiper/vue';

import 'swiper/css';
import '@ionic/vue/css/ionic-swiper.css';



</script>
