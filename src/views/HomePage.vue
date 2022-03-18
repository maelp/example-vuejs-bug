<template>
  <ion-page>
    <ion-header :translucent="true">
      <ion-toolbar>
        <ion-title>Inbox</ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content :fullscreen="true">
      <ion-refresher slot="fixed" @ionRefresh="refresh($event)">
        <ion-refresher-content></ion-refresher-content>
      </ion-refresher>

      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Inbox</ion-title>
        </ion-toolbar>
      </ion-header>

      <ion-list>
        <ion-item>
          <ion-label>Some text</ion-label>
        </ion-item>
        <ion-item>
          <ion-label>Some text</ion-label>
          <ion-button slot="end">action</ion-button>
        </ion-item>
      </ion-list>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import {
  IonContent,
  IonHeader,
  IonList,
  IonPage,
  IonRefresher,
  IonButton,
  IonItem,
  IonLabel,
  IonRefresherContent,
  IonTitle,
  IonToolbar,
} from "@ionic/vue";
import { defineComponent } from "vue";
import { getMessages } from "@/data/messages";

export default defineComponent({
  name: "HomePage",
  data() {
    return {
      messages: getMessages(),
    };
  },
  methods: {
    refresh: (ev: CustomEvent) => {
      setTimeout(() => {
        ev.detail.complete();
      }, 3000);
    },
  },
  components: {
    IonContent,
    IonHeader,
    IonList,
    IonPage,
    IonRefresher,
    IonRefresherContent,
    IonTitle,
    IonToolbar,
    IonButton,
    IonItem,
    IonLabel,
  },
});
</script>
