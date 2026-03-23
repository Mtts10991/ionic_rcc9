<template>
  <ion-page>
    <ion-header :translucent="true">
      <ion-toolbar>
        <ion-buttons slot="start">
          <ion-menu-button></ion-menu-button>
        </ion-buttons>
        <ion-title>TestPage</ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content :fullscreen="true" class="ion-padding">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">TestPage</ion-title>
        </ion-toolbar>
      </ion-header>

      <div class="card-wrapper">
        <ion-card class="profile-card">
          <div class="card-accent"></div>
          <ion-card-content>
            <div class="avatar-section">
              <div class="avatar">
                <img src="https://pakmud.com/wp-content/uploads/2023/04/funny-images-62.jpg" alt="Nattapon Wongchai" class="avatar-img" />
              </div>
              <div class="status-dot"></div>
            </div>

            <div class="info-section">
              <h1 class="name">Nattapon Wongchai</h1>
              <p class="title">Creative Director & Photographer</p>
              <p class="org">Lumière Studio, Bangkok</p>
            </div>

            <div class="divider"></div>

            <div class="bio-section">
              <p class="bio">
                เกิดและโตที่เชียงใหม่ หลงรักการถ่ายภาพตั้งแต่อายุ 14 ปี เมื่อพ่อมอบกล้องฟิล์มตัวเก่าให้เป็นของขวัญวันเกิด จากเด็กที่ชอบเดินถ่ายรูปตามตลาดเช้า สู่การเรียนต่อด้าน Visual Arts ที่ลอนดอน
              </p>
              <p class="bio">
                กลับมาเปิดสตูดิโอเล็กๆ ย่านอารีย์เมื่อปี 2561 เริ่มจากงานถ่ายภาพบุคคลให้เพื่อนฝูง จนปากต่อปากพาให้ได้ร่วมงานกับแบรนด์ระดับประเทศ ผลงานถูกตีพิมพ์ใน Vogue Thailand, National Geographic ฉบับภาษาไทย และ a]day Magazine
              </p>
              <p class="bio">
                ปัจจุบันใช้ชีวิตอยู่ระหว่างกรุงเทพฯ กับเชียงใหม่ วันว่างชอบปั่นจักรยานริมแม่น้ำปิง ชงกาแฟดริปดื่มเอง และสอนเวิร์กช็อปถ่ายภาพให้เด็กๆ ในชุมชน เชื่อเสมอว่า "ภาพหนึ่งภาพบอกเล่าเรื่องราวที่คำพูดเอื้อมไม่ถึง"
              </p>
            </div>

            <div class="divider"></div>

            <div class="details-section">
              <div class="detail-row">
                <ion-icon :icon="mailOutline" class="detail-icon"></ion-icon>
                <span>nattapon@lumiere.studio</span>
              </div>
              <div class="detail-row">
                <ion-icon :icon="callOutline" class="detail-icon"></ion-icon>
                <span>+66 92 456 7890</span>
              </div>
              <div class="detail-row">
                <ion-icon :icon="locationOutline" class="detail-icon"></ion-icon>
                <span>อารีย์, กรุงเทพฯ</span>
              </div>
              <div class="detail-row">
                <ion-icon :icon="schoolOutline" class="detail-icon"></ion-icon>
                <span>University of the Arts London, BA Visual Arts</span>
              </div>
            </div>

            <div class="tags">
              <ion-chip v-for="tag in tags" :key="tag" outline>
                <ion-label>{{ tag }}</ion-label>
              </ion-chip>
            </div>
          </ion-card-content>
        </ion-card>
      </div>
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import {
  IonButtons,
  IonCard,
  IonCardContent,
  IonChip,
  IonContent,
  IonHeader,
  IonIcon,
  IonLabel,
  IonMenuButton,
  IonPage,
  IonTitle,
  IonToolbar,
} from '@ionic/vue';
import { mailOutline, callOutline, locationOutline, schoolOutline } from 'ionicons/icons';

const tags = ['Photography', 'Creative Direction', 'Film', 'Portrait', 'Editorial'];
</script>

<style scoped>
.card-wrapper {
  display: flex;
  justify-content: center;
  align-items: flex-start;
  padding-top: 24px;
}

.profile-card {
  max-width: 600px;
  width: 100%;
  border-radius: 20px;
  overflow: hidden;
  box-shadow:
    0 4px 24px rgba(0, 0, 0, 0.06),
    0 1px 4px rgba(0, 0, 0, 0.04);
  border: 1px solid rgba(0, 0, 0, 0.04);
  margin: 0;
}

.card-accent {
  height: 6px;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
}

ion-card-content {
  padding: 36px 36px;
}

.avatar-section {
  display: flex;
  justify-content: center;
  position: relative;
  margin-bottom: 24px;
}

.avatar {
  width: 120px;
  height: 120px;
  border-radius: 50%;
  background: linear-gradient(135deg, #f5f7fa 0%, #e4e8f0 100%);
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 4px 16px rgba(102, 126, 234, 0.18);
}

.avatar-img {
  width: 100%;
  height: 100%;
  border-radius: 50%;
  object-fit: cover;
}

.status-dot {
  width: 18px;
  height: 18px;
  background: #34d399;
  border-radius: 50%;
  border: 3px solid #fff;
  position: absolute;
  bottom: 4px;
  left: calc(50% + 38px);
  box-shadow: 0 1px 4px rgba(52, 211, 153, 0.4);
}

.info-section {
  text-align: center;
  margin-bottom: 24px;
}

.name {
  font-size: 26px;
  font-weight: 700;
  color: #1a1a2e;
  margin: 0 0 8px 0;
  letter-spacing: -0.3px;
}

.title {
  font-size: 16px;
  font-weight: 500;
  color: #667eea;
  margin: 0 0 4px 0;
}

.org {
  font-size: 14px;
  color: #9ca3af;
  margin: 0;
  font-weight: 400;
}

.divider {
  height: 1px;
  background: linear-gradient(90deg, transparent 0%, #e5e7eb 50%, transparent 100%);
  margin: 0 0 24px 0;
}

.bio-section {
  margin-bottom: 24px;
}

.bio {
  font-size: 15px;
  line-height: 1.75;
  color: #4b5563;
  margin: 0 0 14px 0;
  text-align: justify;
}

.bio:last-child {
  margin-bottom: 0;
}

.details-section {
  display: flex;
  flex-direction: column;
  gap: 16px;
  margin-bottom: 28px;
}

.detail-row {
  display: flex;
  align-items: center;
  gap: 14px;
  font-size: 15px;
  color: #4b5563;
}

.detail-icon {
  font-size: 20px;
  color: #667eea;
  opacity: 0.8;
  flex-shrink: 0;
}

.tags {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
  justify-content: center;
}

.tags ion-chip {
  --background: transparent;
  --color: #667eea;
  --border-color: rgba(102, 126, 234, 0.25);
  font-size: 13px;
  font-weight: 500;
  height: 34px;
}

@media (prefers-color-scheme: dark) {
  .profile-card {
    border-color: rgba(255, 255, 255, 0.06);
    box-shadow:
      0 4px 24px rgba(0, 0, 0, 0.3),
      0 1px 4px rgba(0, 0, 0, 0.2);
  }

  .avatar {
    background: linear-gradient(135deg, #2a2a3e 0%, #1e1e32 100%);
  }

  .name {
    color: #f1f5f9;
  }

  .bio {
    color: #d1d5db;
  }

  .detail-row {
    color: #d1d5db;
  }

  .divider {
    background: linear-gradient(90deg, transparent 0%, #374151 50%, transparent 100%);
  }

  .status-dot {
    border-color: var(--ion-card-background, #1e1e2e);
  }

  .tags ion-chip {
    --border-color: rgba(102, 126, 234, 0.35);
  }
}
</style>
