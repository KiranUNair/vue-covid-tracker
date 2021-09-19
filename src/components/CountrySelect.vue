<template>
    <select v-model="selected" class="form-select mt-10 block w-full rounded border p-3" @change="onChange">
        <option value="0">Select Country</option>
        <option v-for="country in countries" :key="country.Country" :value="country.ID">{{country.Country}}</option>
    </select>
</template>

<script>
export default {
    name: 'CountrySelect',
    props: ['countries'],
    data(){
        return {
            selected: 0
        }    
    },
    methods: {
        onChange(){
            const selectedCountry = this.countries.find((item) => item.ID === this.selected);
            this.$emit('get-country', selectedCountry);
        }
    }
}
</script>