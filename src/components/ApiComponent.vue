<template >
    <div>
        <div class="row mt-md-5 mt-sm-5 mt-xs-5"   >
            <div class="col-lg-6 col-xs-12 border" v-for="(noticia,index ) of noticias" :key="index">
                <div class="d-flex justify-content-center align-itemscenter" >

                    <div class="p-3">
                        <img v-bind:scr="`${noticia.urlToImage}`" :alt="'image for news ' + index">
                    </div>

                    <div class="p-2">
                        <h2> {{noticia.title}}</h2>
                        <p>
                            {{noticia.description}}
                        </p>
                    </div>

                </div>
                <div class="d-flex container-fluid justify-content-end pb-2 mt-n2">
                    <a :href="noticia.url" > <button type="button" class="btn btn-outlineinfo">Info</button></a>
                </div>
            </div>

               

                <div class="w-100"></div>


            </div>
        </div>
        
</template>

<script>
import ax from 'axios'


export default {
    name: 'ApiComponent',
    data(){
        return{
            noticias: null
        }
    },
    mounted(){
        ax
        .get("http://newsapi.org/v2/top-headlines?country=co&pageSize=4&apiKey=1382cb49d9ed4c32a85c971f2ad85754")
        .then(response => {
            (this.noticias = response.data.articles.slice(0,4))
            console.log('Jenny: ',this.noticias)
        }
        )
    },
    methods: {
    getImage(item) {
      return require(item.img);
    }
  }
 }

</script>

<style scoped>

</style>