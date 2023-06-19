<template>
    
    <ModalView>
        <ion-content class="ion-padding">
       <ion-item fill="outline">
        <ion-label position="floating">debutconge</ion-label>
        <ion-input type="text"></ion-input>
        <ion-label position="floating">finconge</ion-label>
        <ion-input type="text"></ion-input>
        <ion-button>addconge</ion-button>
       </ion-item>
    </ion-content>
    </ModalView>  
   
  </template>
  
  <script>
 import ModalView from './ModalView.vue';
 import {ionContent,IonItem,IonInput,IonLabel,IonButton} from '@ionic/vue';

  export default{
    components:{
        ModalView,
        ionContent,IonItem,IonInput,IonLabel,IonButton,
    },
    data(){
      return{
        
      }
    }
  }
  </script>
  