<template>
    <div>
          <p>Nome: {{ nome }}</p>
          <p>E-mail: {{ email }}</p>

          <h1 v-show="isPalmeirasCampeao">Palmeiras Campeão</h1>

           <imagem-component 
                    @visibilidadeImg="exibirMsgPalmeiras"
                    nomeImagem="Imagem Teste" 
                    urlImagem="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcReUeTNUXUJXxJrwgLK_6NF35wICWebV3pB1q4kjAf-2A&s"/>

           <imagem-component 
                    nomeImagem="Time feio" 
                    urlImagem="data:image/png;base64,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"/>

    </div>
</template>

<script>
import ImagemComponent from './ImagemComponent.vue'




    export default {
        name: "UsuarioComponent",
        components: {
            ImagemComponent 
            },
        data(){
            return {
                nome : "Fernando",
                email : "fernando.dias@ifb.edu.br",
                isPalmeirasCampeao : false
            }
        },
        methods: {
            exibirMsgPalmeiras(isImagemVisivel){
                if(isImagemVisivel === true){
                    this.isPalmeirasCampeao = true;
                }else{
                    this.isPalmeirasCampeao = false;
                }
            }
        }
    }

</script>