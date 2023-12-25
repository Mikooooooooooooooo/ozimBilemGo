<template> 
    <div class="review">
        <Card v-for="card in cards" :item="card"></Card>
        <div class="review__buttons">
            <div @click="prev" class="review__prev">
                <img src="../assets/prev.svg" alt="">
            </div>
            <div @click="next" class="review__next">
                <img src="../assets/next.svg" alt="">
            </div>
        </div>
    </div>
</template>

<script>
    import Card from './Card.vue';

    export default{
        data() {
            return {
                index: 0 , 
                cards: [
                {
                    name: 'John Doe',
                    source: 'contact1.jpg',
                    job: 'Web Developer',
                    value: '4.5',
                    description: 'Passionate web developer with a keen eye for detail and a love for creating seamless user experiences.'
                },
                {
                    name: 'Jane Smith',
                    source: 'contact2.jpg',
                    job: 'Graphic Designer',
                    value: '4.8',
                    description: 'Creative graphic designer who transforms ideas into visually stunning and engaging designs.'
                },
                {
                    name: 'Alex Johnson',
                    source: 'contact3.jpg',
                    job: 'UI/UX Designer',
                    value: '4.2',
                    description: 'Experienced UI/UX designer dedicated to crafting intuitive and user-friendly digital interfaces.'
                } 
                ] ,
                cardList: [
                {
                    name: 'John Doe',
                    source: 'contact1.jpg',
                    job: 'Web Developer',
                    value: '4.5',
                    description: 'Passionate web developer with a keen eye for detail and a love for creating seamless user experiences.'
                },
                {
                    name: 'Jane Smith',
                    source: 'contact2.jpg',
                    job: 'Graphic Designer',
                    value: '4.8',
                    description: 'Creative graphic designer who transforms ideas into visually stunning and engaging designs.'
                },
                {
                    name: 'Alex Johnson',
                    source: 'contact3.jpg',
                    job: 'UI/UX Designer',
                    value: '4.2',
                    description: 'Experienced UI/UX designer dedicated to crafting intuitive and user-friendly digital interfaces.'
                },
                {
                    name: 'Emily White',
                    source: 'contact4.jpg',
                    job: 'Software Engineer',
                    value: '4.9',
                    description: 'Innovative software engineer with a passion for developing robust and efficient software solutions.'
                },
                {
                    name: 'Chris Black',
                    source: 'contact5.jpg',
                    job: 'Data Scientist',
                    value: '4.6',
                    description: 'Analytical data scientist skilled in extracting meaningful insights and patterns from complex datasets.'
                },
                {
                    name: 'Sophia Brown',
                    source: 'contact6.jpg',
                    job: 'Marketing Manager',
                    value: '4.7',
                    description: 'Strategic marketing manager with a proven track record of driving successful campaigns and brand growth.'
                }
                ]
            }
        } , 
        components: {
            Card
        } ,
        methods: {
            prev() {
                this.index-- ; 
                if (this.index == -1)
                    this.index = 3 ; 
                    console.log(this.index)

                this.cards = this.cardList.slice(this.index , this.index + 3) 
            } , 
            next() {
                this.index++ ; 
                if (this.index == 4)
                    this.index = 0 ; 
                this.cards = this.cardList.slice(this.index , this.index + 3) 
            }
        }
    }
</script>

<style>
    .review{
        width: 95%; 
        margin: 0 auto 3vh; 
        display: flex; 
        justify-content: space-between ; 
    }
    .review__buttons{
        margin-top: 2vh ;
    }
    .review__prev{
        padding: 15px; 
        background: white; 
        margin-bottom: 2.5vh ; 
        cursor: pointer ; 
    }
    .review__next{
        padding: 15px; 
        cursor: pointer ; 
        background: white ; 
    }
    .review__next:hover{
        background: #f5f7f7 ; 
    }
    .review__prev:hover{
        background: #f5f7f7 ; 
    }
</style>