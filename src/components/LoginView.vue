<template>
   <ion-page>
    <ion-content class="ion-padding">
       <ion-item fill="outline">
        <ion-label position="floating">Username</ion-label>
        <ion-input type="text"></ion-input>
       </ion-item>
       <br>
       <ion-item fill="outline"> 
        <ion-label position="floating">Password</ion-label>
        <ion-input type="password"></ion-input>
       </ion-item>
       <ion-button expand="block" @click="$emit('loginemitted')">connexion</ion-button>
    </ion-content>
   </ion-page> 
</template>

<script>
import {IonItem,IonLabel,IonInput,IonPage,IonContent,IonButton} from "@ionic/vue";
export default{
   components:{
    IonItem,
    IonLabel,
    IonInput,
    IonPage,
    IonContent,
    IonButton
   }

}



</script>