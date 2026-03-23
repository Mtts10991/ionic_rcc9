<template>
  <ion-app>
    <ion-split-pane content-id="main-content">
      <ion-menu content-id="main-content" type="overlay">
        <ion-content>
          <ion-list id="menu-list">
            <ion-list-header>เมนู</ion-list-header>
            <ion-note>Ionic App</ion-note>

            <ion-menu-toggle
              v-for="(item, index) in menuItems"
              :key="index"
              :auto-hide="false"
            >
              <ion-item
                router-direction="root"
                :router-link="item.url"
                lines="none"
                :detail="false"
                :class="{ selected: selectedIndex === index }"
                @click="selectedIndex = index"
              >
                <ion-icon
                  aria-hidden="true"
                  slot="start"
                  :ios="item.iosIcon"
                  :md="item.mdIcon"
                ></ion-icon>
                <ion-label>{{ item.title }}</ion-label>
              </ion-item>
            </ion-menu-toggle>
          </ion-list>
        </ion-content>
      </ion-menu>

      <ion-router-outlet id="main-content"></ion-router-outlet>
    </ion-split-pane>
  </ion-app>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import {
  IonApp,
  IonContent,
  IonIcon,
  IonItem,
  IonLabel,
  IonList,
  IonListHeader,
  IonMenu,
  IonMenuToggle,
  IonNote,
  IonRouterOutlet,
  IonSplitPane,
} from '@ionic/vue';
import { homeOutline, homeSharp, informationCircleOutline, informationCircleSharp, flaskOutline, flaskSharp } from 'ionicons/icons';

const selectedIndex = ref(0);

const menuItems = [
  {
    title: 'หน้าแรก',
    url: '/home',
    iosIcon: homeOutline,
    mdIcon: homeSharp,
  },
  {
    title: 'TestPage',
    url: '/test',
    iosIcon: flaskOutline,
    mdIcon: flaskSharp,
  },
  {
    title: 'เกี่ยวกับ',
    url: '/about',
    iosIcon: informationCircleOutline,
    mdIcon: informationCircleSharp,
  },
];

// Set selected index based on current path
const path = window.location.hash.replace('#', '');
const index = menuItems.findIndex((item) => path.startsWith(item.url));
if (index >= 0) {
  selectedIndex.value = index;
}
</script>

<style scoped>
ion-menu ion-content {
  --background: var(--ion-item-background, var(--ion-background-color, #fff));
}

ion-menu.md ion-content {
  --padding-start: 8px;
  --padding-end: 8px;
  --padding-top: 20px;
  --padding-bottom: 20px;
}

ion-menu.md ion-list {
  padding: 20px 0;
}

ion-menu.md ion-note {
  margin-bottom: 30px;
}

ion-menu.md ion-list-header,
ion-menu.md ion-note {
  padding-left: 10px;
}

ion-menu.md ion-list#menu-list {
  border-bottom: 1px solid var(--ion-color-step-150, #d7d8da);
}

ion-menu.md ion-list#menu-list ion-list-header {
  font-size: 22px;
  font-weight: 600;

  min-height: 20px;
}

ion-menu.md ion-item {
  --padding-start: 10px;
  --padding-end: 10px;
  border-radius: 4px;
}

ion-menu.md ion-item.selected {
  --background: rgba(var(--ion-color-primary-rgb), 0.14);
}

ion-menu.md ion-item.selected ion-icon {
  color: var(--ion-color-primary);
}

ion-menu.md ion-item ion-icon {
  color: #616e7e;
}

ion-menu.md ion-item ion-label {
  font-weight: 500;
}

ion-menu.ios ion-content {
  --padding-bottom: 20px;
}

ion-menu.ios ion-list {
  padding: 20px 0 0 0;
}

ion-menu.ios ion-note {
  line-height: 24px;
  margin-bottom: 20px;
}

ion-menu.ios ion-item {
  --padding-start: 16px;
  --padding-end: 16px;
  --min-height: 50px;
}

ion-menu.ios ion-item.selected ion-icon {
  color: var(--ion-color-primary);
}

ion-menu.ios ion-item ion-icon {
  font-size: 24px;
  color: #73849a;
}

ion-item.selected {
  --color: var(--ion-color-primary);
}
</style>
