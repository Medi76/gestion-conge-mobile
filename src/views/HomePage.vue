<template>
  <ion-page>
    <ion-header :translucent="true">
      <ion-toolbar color="primary">
        <ion-title>Liste des employées</ion-title>
        <ion-icon :icon="person" size="large" slot="end"></ion-icon>
      </ion-toolbar>
    </ion-header>

    <ion-content :fullscreen="true" class="ion-padding">
      <ion-list>
        <ion-item v-for="i in 10" :key="i">
          <ion-avatar slot="start" ><img  src="../assets/blackmamba.jpg"></ion-avatar>
          <ion-label>
            <h2> employe num :{{i}}</h2>
            <p>bonjour</p>
          </ion-label>
          <ion-button slot="end" color="primary" @click="add_conge=true">
            <ion-icon :icon="add"></ion-icon>
            congé
          </ion-button>
          <ion-item fill="outline">
        <ion-label position="floating">Username</ion-label>
        <ion-input type="text"></ion-input>
       </ion-item>
        </ion-item>
      </ion-list>
    </ion-content>
    <AddConge v-if="add_conge"></AddConge>
  </ion-page>
 
</template>

<script>
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar,IonIcon,IonList,
  IonItem,IonAvatar,IonLabel,IonButton,modalController } from '@ionic/vue';
import{person,add} from "ionicons/icons";
import ModalView from '../components/ModalView.vue';
import AddConge from '../components/AddConge.vue';
export default{
  components:{
    IonContent, 
    IonHeader, 
    IonPage,
     IonTitle,
      IonToolbar,
      IonIcon,IonAvatar,IonLabel,IonButton,
      IonList,IonItem,modalController,AddConge,
  },
  data(){
    return{
      person,
      add,
      add_conge:false,
    }
  },
    methods: {
      async add_conge() {
        const modal = await modalController.create({
          component: Modal,
        });
        modal.present();

        const { data, role } = await modal.onWillDismiss();
        if (role === 'confirm') {
          this.message = `Hello, ${data}!`;
        }
      }
  }
}
</script>

<style scoped>
#container {
  text-align: center;
  
  position: absolute;
  left: 0;
  right: 0;
  top: 50%;
  transform: translateY(-50%);
}

#container strong {
  font-size: 20px;
  line-height: 26px;
}

#container p {
  font-size: 16px;
  line-height: 22px;
  
  color: #8c8c8c;
  
  margin: 0;
}

#container a {
  text-decoration: none;
}
</style>
