<template>
    <main-layout title="About">

        <ion-card>
            <img alt="Silhouette of mountains" src="../assets/about.jpg" />
            <ion-card-header>
                <ion-card-title>Alfan Alfarisy</ion-card-title>
                <ion-card-subtitle>About App</ion-card-subtitle>
            </ion-card-header>

            <ion-card-content>
                In the digital tapestry of this realm, this piece of text stands as a testament to my craft and expertise. Crafted meticulously, pixel by pixel, by yours truly – Alfan Alfarisy. Regards from an alternate dimension of Juanda.
            </ion-card-content>
        </ion-card>
    </main-layout>
</template>
    
<script setup >
import MainLayout from '../components/layout/MainLayout.vue';
import { IonCard, IonCardContent, IonCardHeader, IonCardSubtitle, IonCardTitle } from '@ionic/vue';

</script>
<style scoped>
/* iOS places the subtitle above the title */
ion-card-header.ios {
  display: flex;
  flex-flow: column-reverse;
}
</style>