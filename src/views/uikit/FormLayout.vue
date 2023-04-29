<script>
export default {
    name: 'App',
    data() {
        return {
            formRFC: {
                nombre: '',
                apellidoP: '',
                apellidoM: '',
                fechaNac: '',
                rfc: ''
            }
        }
    },
    methods:{
        generarRFC(){
            this.formRFC.rfc = this.formRFC.apellidoP.substring(0,2)
                        + this.formRFC.apellidoM.substring(0,1)
                        + this.formRFC.nombre.substring(0,1)
                        + this.formRFC.fechaNac.substring(2,4)
                        + this.formRFC.fechaNac.substring(5,7)
                        + this.formRFC.fechaNac.substring(8,10);
            this.formRFC.rfc = this.formRFC.rfc.toUpperCase();
        }
    }
}
</script>
<template>
    <div class="grid">
        <div class="col-12 md:col-12">
            <div class="card p-fluid">
                <h5>Generador de RFC</h5>
                <div class="field">
                    <label for="name">Nombre</label>
                    <InputText id="name"  type="text" v-model="formRFC.nombre"/>
                </div>
                <div class="field">
                    <label for="apellidoP">Apellido Paterno</label>
                    <InputText id="apellidoP"  type="text" v-model="formRFC.apellidoP"/>
                </div>
                <div class="field">
                    <label for="apellidoM">Apellido Materno</label>
                    <InputText id="apellidoM" type="text" v-model="formRFC.apellidoM"/>
                </div>
                <div class="field">
                    <label for="fechaNac">Fecha de Nacimiento</label>
                    <InputText id="fechaNac" type="date" v-model="formRFC.fechaNac"/>
                </div>
                <div class="field">
                    <label for="rfc">RFC</label>
                    <InputText id="rfc" disabled type="text" v-model="formRFC.rfc"/>
                </div>
                <div class="field md:col-12">
                <Button class="p-button-secondary" label="Generar" icon="pi pi-id-card" iconPos="right" @click="generarRFC" />
                </div>
            </div>
        </div>
    </div>
</template>
