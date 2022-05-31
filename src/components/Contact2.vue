<template>
    <section id="contact" class="container-fluid section section2 bg-primary-dark px-0">
        <div class="h-100 py-5 font-light" id="patternContact" >
            <div class="container">
            <h2 class="text-center gluten fontSmallH">Because We Really Care About Your Pets</h2>
            <h2 class="text-center gluten">Services of Four Paws</h2>
            <div class="contactsForm row">
                <div class="col-6">
                    <input type="text" class="outlineNone form-control d-block w-100" placeholder="Name and surname" v-model="fulName">
                    <p>Full Name is: {{ fulName }}</p>
                </div>
                <div class="col-6">
                    <input v-model="email" placeholder="Email" class="outlineNone form-control d-block w-100" type="email">
                    <p>Email is: {{ email }}</p>
                </div>
                <div class="col-6">
                    <input v-model="phoneNumber" placeholder="Phone Number" class="outlineNone form-control d-block w-100" type="number">
                    <p>Phone Number is: {{ phoneNumber }}</p>
                </div>
                <div class="col-6">
                    <input v-model="namePet" placeholder="Name Pet" class="outlineNone form-control d-block w-100" type="text">
                    <p>Name Pet is: {{ namePet }}</p>
                </div>
                <div class="col-6">
                    <input v-model="petCategory" placeholder="Pet Category" class="outlineNone form-control d-block w-100" type="text">
                    <p>Pet Category is: {{ petCategory }}</p>
                </div>
                <div class="col-6">
                    <input v-model="serviceType" placeholder="Service Type" class="outlineNone form-control d-block w-100" type="text">
                    <p>Service Type is: {{ serviceType }}</p>
                </div>
                <div class="col-12">
                    <textarea placeholder="Your message" name="" id="" cols="30" rows="5" class="outlineNone form-control d-block w-100"></textarea>
                </div>
            </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: 'contact',
    data() {
        return {
            fulName: '',
            email: '',
            phoneNumber: 0,
            namePet: '',
            petCategory: '',
            serviceType: '',
            yourMessage: '',
        }
    },
    created() {
        
    },
    methods: {
        
    },
}
</script>