<template>
 
  <div>
      <div v-for="(hobbie, i) in hobbies" v-bind:key="i">
            <div v-for="item in hobbie" v-bind:key="item">
                 Name:{{ item.name }}
                 Hobbies:{{ item.hobby }}
                 Sport:{{ item.sports }}
            </div>
      </div>

  </div>
   
    
</template>



<script>
import axios from 'axios'

export default {
    name: 'Hobbie',
     data(){
        return{
            
            hobbies:[],
        }
    },
    created() {
        axios.get('http://127.0.0.1:8000/api/hobbiess')
        .then(response=>{
            this.hobbies = response.data
        })
        .catch(e=>{
            this.errors.push(e)
        })
    },
    
}
</script>

