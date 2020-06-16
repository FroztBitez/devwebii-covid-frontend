<template>
    <div class="submit-form">
        <div class="form-group">
            <label for="nome">Nome</label>
            <input 
                type="text" 
                class="form-control" 
                id="nome" 
                v-model="paciente.nome" 
                name="nome"
            />
        </div>
        <div class="form-group">
            <label for="email">Email</label>
            <input 
                type="email" 
                class="form-control" 
                id="email" 
                v-model="paciente.email" 
                name="email"
            />
        </div>
        <div class="form-group">
            <label for="data">Data de Internação</label>
            <input 
                type="date" 
                class="form-control" 
                id="data_internacao" 
                v-model="paciente.data_internacao" 
                name="data_internacao"
            />
        </div>

        <button @click="inserirPaciente" class="btn btn-success">
            inserir Paciente
        </button>
    </div>
</template>

<script>

    //import PacienteWS from '../services/PacientesWS';
import PacientesWS from '../services/PacientesWS';
    export default {
        name: "adicionarPaciente",
        data(){
            return {
                paciente: {
                    id: "",
                    nome: "",
                    email: "",
                    data_internacao: new Date()
                }
            }
        },
        methods: {
            inserirPaciente(){
                let dadosPaciente = {
                    nome: this.paciente.nome,
                    email: this.paciente.email,
                    data_internacao: this.paciente.data_internacao
                }

                PacientesWS.criarPaciente(dadosPaciente)
                    .then(resp => {
                        this.paciente.id = resp.data.id;
                        console.log(this.paciente);
                    }).catch(error => {
                        console.log(error.message);
                    })
            }
        }
    }
</script>