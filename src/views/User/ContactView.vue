<template>
    <main-header />
    <sub-header
        heading="#stayintouch"
        subHeading="With our 24/7 hotlines we will attend to you."
    />
    <div class="container">
        <div class="map-section">
            <div class="map-details">
                <span>Get in touch</span>
                <p>Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.</p>
            </div>
        </div>
        <div class="row">
                <h3>List Contacts</h3>
                <div class="col-md-4" v-for="contact in contacts">
                    <div class="card">
                    <svg class="bd-placeholder-img card-img-top" width="100%" height="180" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Placeholder: Image cap" preserveAspectRatio="xMidYMid slice" focusable="false"><title>Placeholder</title><rect width="100%" height="100%" fill="#868e96"></rect><text x="50%" y="50%" fill="#dee2e6" dy=".3em">Image cap</text></svg>
                <div class="card-body">
                    <h5 class="card-title">{{ contact.name }}</h5>
                    <p class="card-text">{{ contact.position }}</p>
                    <p class="card-text">{{ contact.email }}</p>
                    <p class="card-text">{{ contact.phone }}</p>
                    <a href="#" class="btn btn-primary">Go somewhere</a>
                </div>
                </div>
        </div>
        </div>
    </div>
    <main-footer />
</template>

<script>
import SubHeader from "@/components/SubHeader.vue";
import ActionButton from "@/components/ActionButton.vue";
import MainHeader from "@/components/MainHeader.vue";
import MainFooter from "@/components/MainFooter.vue";
export default {
    components: { SubHeader, ActionButton, MainHeader, MainFooter },
    name: "ContactView",
    data() {
        return {
            contacts: [
                {
                    name: "Tung 1",
                    position: "Chief Execution Officer (CEO)",
                    phone: "+1-11111",
                    email: "contact1@gmail.com",
                },
                {
                    name: "Tung 2",
                    position: "Senior Marketing Manager",
                    phone: "+1-1111",
                    email: "contact2@gmail.com",
                },
                {
                    name: "Tung 3",
                    position: "Warehouse Manager",
                    phone: "+1-1111",
                    email: "contact3@gmail.com",
                },
            ],
        };
    },
};
</script>

