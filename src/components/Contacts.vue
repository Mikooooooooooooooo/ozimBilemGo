<template>
    <div class="contacts">
        <div class="contacts__header">
            <div class="contacts__text">
                <div class="contacts__title">
                    Contacts
                </div>  
                <div class="contacts__description">
                    You have 456 contacts
                </div>
            </div>
            <Button title="+" :padding="15"></Button>
        </div>
        <div class="contacts__list">
            <ContactItem v-for="contact in contacts" :iconSrc="contact.iconSrc" :name="contact.name" :job="contact.job" :isHave="contact.isHave"/>
        </div>
        <div class="contact__button" @click="showMore()">
            View More
        </div>
    </div>
</template>

<script>
    import Button from './Button.vue';
    import ContactItem from './ContactItem.vue';
    export default{
        components: {
            Button , 
            ContactItem
        } , 
        data () {
            return {
                contacts: [
                    {iconSrc: 'contact1.jpg' , name: 'Samantha William' , job: 'Marketing Manager' , isHave: false} , 
                    {iconSrc: 'contact2.jpg' , name: 'Tony Soap' , job: 'UI Designer' , isHave: true} , 
                    {iconSrc: 'contact3.jpg' , name: 'Karen Hope' , job: 'Web Developer' , isHave: false} , 
                    {iconSrc: 'contact4.jpg' , name: 'Jordan Nico' , job: 'Graphic Design' , isHave: false} , 
                    {iconSrc: 'contact5.jpg' , name: 'Nadila Adja' , job: 'QA Engineer' , isHave: true} , 

                ] , 
                contactsMore: [
                    { iconSrc: 'contact1.jpg', name: 'Samantha William', job: 'Marketing Manager', isHave: false },
                    { iconSrc: 'contact2.jpg', name: 'Tony Soap', job: 'UI Designer', isHave: true },
                    { iconSrc: 'contact3.jpg', name: 'Karen Hope', job: 'Web Developer', isHave: false },
                    { iconSrc: 'contact4.jpg', name: 'Jordan Nico', job: 'Graphic Design', isHave: false },
                    { iconSrc: 'contact5.jpg', name: 'Nadila Adja', job: 'QA Engineer', isHave: true },
                    { iconSrc: 'contact6.jpg', name: 'John Doe', job: 'Data Scientist', isHave: true },
                    { iconSrc: 'contact1.jpg', name: 'Jane Smith', job: 'Project Manager', isHave: false },
                    { iconSrc: 'contact2.jpg', name: 'Alex Johnson', job: 'Software Engineer', isHave: true },
                    { iconSrc: 'contact3.jpg', name: 'Emily White', job: 'UX Designer', isHave: false },
                ] , 
                show: false
            }
        } , 
        methods: {
            showMore() {
                const temp = this.contacts ; 
                this.contacts = this.contactsMore ; 
                this.contactsMore = temp ; 
        }
        }
    }
</script>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;600;700&family=Open+Sans:ital,wght@0,400;0,500;0,700;1,600&display=swap');

    .contacts{
        margin: 4vh 0; 
        padding: 30px; 
        background: white ;
        font-family: 'Open Sans' , sans-serif ; 
    }
    .contacts__header{
        display: flex; 
        justify-content: space-between;
    }
    .contacts__text{
        padding-bottom: 1vh ; 
    }
    .contacts__title{
        font-weight: 700 ; 
        font-size: 26px; 
        color: navy;
    }
    .contacts__description{
        font-size: 14px;    
        color: rgba(0, 0, 0, 0.7);
    }
    .contact__button{
        margin-top: 2vh ; 
        text-align: center; 
        padding: 15px 0 ; 
        background: rgba(255, 127, 80, 0.3) ;  
        color:  #ef6d4d;
        font-weight: 600 ;
        cursor: pointer;
        transition: background-color 0.3s ease;
        margin-bottom: 2vh ; 
    }
    .contact__button:hover{
        background-color: #d95c3d; 
        box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
        color: white; 
    }
    
</style>
