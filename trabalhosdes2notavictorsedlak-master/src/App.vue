<script setup>
import { ref } from 'vue'
const nome = ref('')
const email = ref('')
const senha = ref('')
const confirmacaodesenha = ref('')
const dataDeNascimento = ref('')
const endereço = ref('')
const cidade = ref('')
const bio = ref('')
const hob = ref('')
const ativo = ref(false)
const linguagemprograma = ref([])
</script>

<template>
  <form @submit.prevent="ativo = !ativo">
  <h1>Formulário</h1>
  <div>
    <input id="info" type="text" v-model="nome" placeholder="Nome" required/>
    <input id="info" type="email" v-model="email" placeholder="Email" required/>
    <input id="info" type="password" v-model="senha" placeholder="Senha" minlength="8" maxlength="20" required/>
    <input id="info" type="password" v-model="confirmacaodesenha" placeholder="Confirme sua Senha" required/>
    <input id="info" type="date" v-model="dataDeNascimento" placeholder="Data de Nascimento" required/>
    <input id="info" type="number" v-model="endereço" placeholder="Endereço" required/>
    <input id="info" type="text" v-model="cidade" placeholder="Cidade" required/> 
    <label for="estado">Estado:</label>
    <select required>
      <option value="nada"></option>
      <option value="AC">Acre</option>
      <option value="AL">Alagoas</option>
      <option value="AP">Amapá</option>
      <option value="AM">Amazonas</option>
      <option value="BA">Bahia</option>
      <option value="CE">Ceará</option>
      <option value="DF">Distrito Federal</option>
      <option value="ES">Espírito Santo</option>
      <option value="GO">Goiás</option>
      <option value="MA">Maranhão</option>
      <option value="MT">Mato Grosso</option>
      <option value="MS">Mato Grosso do Sul</option>
      <option value="MG">Minas Gerais</option>
      <option value="PA">Pará</option>
      <option value="PB">Paraíba</option>
      <option value="PR">Paraná</option>
      <option value="PE">Pernambuco</option>
      <option value="PI">Piauí</option>
      <option value="RJ">Rio de Janeiro</option>
      <option value="RN">Rio Grande do Norte</option>
      <option value="RS">Rio Grande do Sul</option>
      <option value="RO">Rondônia</option>
      <option value="RR">Roraima</option>
      <option value="SC">Santa Catarina</option>
      <option value="SP">São Paulo</option>
      <option value="SE">Sergipe</option>
      <option value="TO">Tocantins</option>
    </select>
    <br>
    <label for="LinProgramação">Linguagens de programação: 
      <input id="checkdesing" type="checkbox" v-model="linguagemprograma" value="PHP"> PHP
      <input id="checkdesing" type="checkbox" v-model="linguagemprograma" value="JS"> JS
      <input id="checkdesing" type="checkbox" v-model="linguagemprograma" value="C++"> C++
      <input id="checkdesing" type="checkbox" v-model="linguagemprograma" value="Python"> Python     
    </label>  
    <br>
    <textarea class="caixadetexto" v-model="hob" placeholder="Descreva alguns hobbies" cols="70" rows="10" />
    <br>
    <textarea class="caixadetexto" v-model="bio" placeholder="Descreva sua biografia" cols="70" rows="20" />
    <br>
    <button type="submit" >Tudo pronto</button>
  </div>
  <div v-if="ativo" id="resposta">
<p>Nome: {{ nome }}</p>
<p>Email:{{ email }}</p>
<p>Senha: {{ senha }}</p>
<p>Confirmação da senha: {{confirmaçãoDeSenha}}</p>
<p>Data de nascimento: {{dataDeNascimento}}</p>
<p>Endereço: {{endereço}}</p>
<p>Cidade: {{ cidade }}</p>
<p>Linguagem de programação:{{ linguagemprograma }}</p>
<p>Hobbie: {{ hob }}</p>
<p>Biografia: {{ bio }}</p>

</div>
</form>

</template>

<style scoped>
div {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 50px;
}
#info, select {
  width: 300px;
  height: 30px;
  margin-bottom: 10px;
  border: 3px solid black;
  border-radius: 7px;
  font-size: 16px;
  font-family: sans-serif;
  padding-left: 5px;
  box-sizing: border-box;
}
label {
  font-size: 16px;
  font-family: sans-serif;
  margin-bottom: 10px;
}
button {
  background-color: #00cc00;
  color: #fff; 
  border: none; 
  padding: 10px 20px; 
  border-radius: 4px; 
  cursor: pointer; 
}
button:hover {
  background-color: green;
  box-shadow: 0px 5px 0px rgb(0, 53, 0);
  
  cursor: pointer;
}

.checkdesing {
  border-radius: 50px;
}

.caixadetexto {
  border-radius: 15px;
  border: 5px solid black;
  border-color: black;


}

h1 {
  text-align: center;
  font-family: 'Times New Roman', Times, serif;
  text-size-adjust: 15px;
  font-size: 80px;
  }

#resposta {
  border-radius: 15px;
  border: 5px solid black;
  font-family: 'Times New Roman', Times, serif;
  text-align: center;
  box-shadow: 5px;
}
</style>