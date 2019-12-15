<template>
    <div class="row">
        <app-quote v-for="(quote,index) in quotes" :key="index"
            @click.native="deleteQuote(index)">
            {{ quote }}
        </app-quote>
    </div>
</template>

<script>
import quote from './Quote';

export default {
    props:[ 'quotes'],
    components:{
        'appQuote':quote
    },
    methods:{
        deleteQuote(index){
            this.$emit('deletQuote',index);
        }
    }
}
</script>

<style>

</style>