<template>
    <div>
        <v-card id="editCard">
            <v-col cols="12" sm="6" lg="4" class="mx-auto">
                <v-text-field v-model.number="EditDrink.id" label="Enter dish id"></v-text-field>
                <v-btn @click="getDrink()">Hent rett</v-btn>
                <v-text-field v-model="EditDrink.drinkType"></v-text-field>
                <v-text-field v-model.number="EditDrink.price" type="number" ></v-text-field>
                <v-text-field v-model="EditDrink.imageSrc"></v-text-field>
                <v-btn @click="editDrink()">Endre rett</v-btn>
            </v-col>
        </v-card>

        <DrinkList/>
        
    </div>
</template>

<script>
import axios from 'axios'
import DrinkList from "@/components/Drink/DrinkList.vue"
export default {
    name: "DrinkEdit",
    data(){
        return{
            EditDrink:{},
            file:null
        }
    },
    methods:{
        //Method to get the specific object from the data base and fill the text fields with the info
        getDrink(){
            console.log(this.EditDrink.id)
            axios.get(`https://localhost:5001/drink/${this.EditDrink.id}`).then( result => {
                    console.log( result.data );

                    this.EditDrink.drinkType=result.data.type
                    this.EditDrink.price=result.data.price
                    this.EditDrink.imageSrc=result.data.imageSrc
                    this.$forceUpdate();
            })
        },
        //Method to change the data in the database with the info in the text fields
        editDrink(){
            let obj= {
                id: this.EditDrink.id,
                type: this.EditDrink.drinkType,
                price: this.EditDrink.price,
                imageSrc: this.EditDrink.imageSrc}
                console.log(obj)

                axios.put(`https://localhost:5001/drink`, obj).then( result => {
                    console.log( result.data );})
        }

    },
    components: {
        DrinkList
    }
}
</script>

<style lang="scss">
#editCard{ 
    background-color: #fff;
    flex: 0 0 auto; margin-right: 30%; margin-top: 20px; margin-left:30%;
    box-shadow: 0 4px 8px 0 rgba($color: #000000, $alpha: 1.0);
    overflow: hidden;
}
</style>