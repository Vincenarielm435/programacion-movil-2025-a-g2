<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Gestión de Personal Médico</ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content>
      <ion-card>
        <ion-segment v-model="selectedRole">
        <ion-segment-button value="Médico">Médico</ion-segment-button>
        <ion-segment-button value="Enfermero">Enfermero</ion-segment-button>
        <ion-segment-button value="Recepcionista">Recepcionista</ion-segment-button>
        <ion-segment-button value="Paciente">Paciente</ion-segment-button>
      </ion-segment>
        <ion-card-header>
          <ion-card-title>{{ selectedRole }}</ion-card-title>
        </ion-card-header>

        <ion-card-content>
          <ion-item>
            <ion-label position="floating">Nombre</ion-label>
            <ion-input v-model="form.nombre"></ion-input>
          </ion-item>

          <ion-item>
            <ion-label position="floating">Apellido</ion-label>
            <ion-input v-model="form.apellido"></ion-input>
          </ion-item>

          <ion-item>
            <ion-label position="floating">Edad</ion-label>
            <ion-input v-model="form.Edad"></ion-input>
          </ion-item>

          <ion-item>
            <ion-label position="floating">Correo</ion-label>
            <ion-input v-model="form.Correo"></ion-input>
          </ion-item>
          <!-- Campos adicionales según el rol seleccionado -->
          <template v-if="selectedRole === 'Médico'">
            <ion-item>
              <ion-label position="floating">Especialidad</ion-label>
              <ion-input v-model="form.especialidad"></ion-input>
            </ion-item>
            <ion-item>
              <ion-label position="floating">Número de licencia médica</ion-label>
              <ion-input v-model="form.licencia"></ion-input>
            </ion-item>
          </template>

          <template v-if="selectedRole === 'Enfermero'">
            <ion-item>
              <ion-label position="floating">Turno asignado</ion-label>
              <ion-input v-model="form.turno"></ion-input>
            </ion-item>
            <ion-item>
              <ion-label position="floating">Área de atención</ion-label>
              <ion-input v-model="form.area"></ion-input>
            </ion-item>
          </template>

          <template v-if="selectedRole === 'Recepcionista'">
            <ion-item>
              <ion-label position="floating">Horario laboral</ion-label>
              <ion-input v-model="form.horario"></ion-input>
            </ion-item>
            <ion-item>
              <ion-label position="floating">Extensión telefónica</ion-label>
              <ion-input v-model="form.extension"></ion-input>
            </ion-item>
          </template>

          <template v-if="selectedRole === 'Paciente'">
            <ion-item>
              <ion-label position="floating">Número de historia clínica</ion-label>
              <ion-input v-model="form.historia"></ion-input>
            </ion-item>
            <ion-item>
              <ion-label position="floating">Tipo de afiliación</ion-label>
              <ion-select v-model="form.afiliacion">
                <ion-select-option value="EPS">EPS</ion-select-option>
                <ion-select-option value="Particular">Particular</ion-select-option>
              </ion-select>
            </ion-item>
          </template>

          <ion-button expand="full" @click="agregar">Agregar</ion-button>
          <ion-button expand="full" @click="modificar">Modificar</ion-button>
          <ion-button expand="full" @click="eliminar">Eliminar</ion-button>
          <ion-button expand="full" @click="consultar">Consultar</ion-button>
        </ion-card-content>
      </ion-card>

      
    </ion-content>
  </ion-page>
</template>

<script>
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent, IonCard, IonCardHeader, IonCardTitle, IonCardContent, IonItem, IonLabel, IonInput, IonButton, IonSegment, IonSegmentButton, IonSelect, IonSelectOption } from '@ionic/vue';

export default {
  name: 'GestionPersonal',
  components: {
    IonPage, IonHeader, IonToolbar, IonTitle, IonContent,
    IonCard, IonCardHeader, IonCardTitle, IonCardContent,
    IonItem, IonLabel, IonInput, IonButton, IonSegment, IonSegmentButton,
    IonSelect, IonSelectOption
  },
  data() {
    return {
      selectedRole: 'Médico',
      form: {
        nombre: '',
        apellido: '',
        Edad: '',
        Correo: '',
        especialidad: '',
        licencia: '',
        turno: '',
        area: '',
        horario: '',
        extension: '',
        historia: '',
        afiliacion: ''
      }
    };
  },
  methods: {
    agregar() {
      console.log('Agregar:', this.form);
    },
    modificar() {
      console.log('Modificar:', this.form);
    },
    eliminar() {
      console.log('Eliminar:', this.form);
    },
    consultar() {
      console.log('Consultar:', this.form);
    }
  }
};
</script>
