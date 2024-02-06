<script setup>
    import CtaButton from "./CtaButton.vue"
</script>


<template>
    <div class="absolute z-30" >
        <img src="../assets/DinoRosieKSubscribe.png" alt="" class="rounded-3xl shadow-slate-900 shadow-2xl drop-shadow-2xl">
        <div class="absolute bottom-0 top-0 left-0 right-0 mt-40">
            <div class="absoloute m-10  text-2xl text-purple-900">
                <form @submit.prevent="handleSubmit" class="bg-yellow-300">
                    <div class="absolute grid grid-cols-2 ml-4 w-full">
                        <div >
                            <p><b>Name:</b></p>
                            <input type="text" required v-model="name" class=" text-lg w-10/12 bg-white bg-opacity-50 mb-3"  />

                            <p><b>Email:</b></p>
                            <input type="text" required v-model="email" class=" text-lg w-10/12 bg-white bg-opacity-50 mb-3"/>
                            <p class="text-red-600 text-sm font-semibold">{{  emailError }}</p>
                        </div>
                        <div>
                            <div class="">
                                <p><b>Gender:</b></p>
                                <input name="gendersel" type="radio" class="h-5 w-8" value="1" v-model="gender" />
                                <label for="male">Male</label>
                                <br>
                                <input name="gendersel" type="radio" class="h-5 w-8" value="2" v-model="gender" />
                                <label for="female">Female</label>
                                <br>
                                <input name="gendersel" type="radio" class="h-5 w-8" value="3" v-model="gender" checked />
                                <label fo="unknown">Rather not Say</label>
                            </div>
                        </div>
                        <div class="mt-20 ml-20">
                            <CtaButton label="Cancel" dest="https://www.redbubble.com/people/RosieDino32/shop" 
                                class="px-8 hover:bg-purple-950 "
                            />
                        </div>
                        <div class="mt-20 ml-20">
                            <button 
                                class="py-2 px-16 bg-purple-600 hover:bg-purple-950 text-white font-bold rounded-full text-2xl" 
                                type="submit">
                                Go
                            </button>
                        </div>
                    </div>
                </form>
            </div>``
            <div class="bg-white bg-opacity-50 ml-8 mr-8 mt-[50%] text-2xl text-purple-700">
                {{ returnData }}
            </div>
        </div>
    </div>

</template>


<script>
export default {
    data() {
        return {
            subscribeUrl: 'http://localhost/lists/?p=asubscribe&id=1',
            listNo: 1,
            name: '',
            email: '',
            gender: 3,
            emailError: '',
            returnData: null
        }
    },
    computed() {
        return{
            subscribeData: {
                email:      this.email,
                list:       this.listNo,
                htmlemail:  1,                
            }
        }
    },
    methods: {
        handleSubmit() {
            this.emailError = /^\w+([\.-]?\w+)*@\w+([\.-]?\w+)*(\.\w{2,3})+$/.test(this.email) 
                ? ''
                : 'Please provide valid email address!'
        
            if( this.emailError.length == 0 ) {
                // No errors let's go
                fetch(this.subscribeUrl, {
                    "method": 'POST',
                    "Content-Type": 'application/json',
                    "data": this.subscribeData
                })
                    .then(res => res.json())
                    .then(data => this.returnData = data )
                    .catch((err) => {
                        console.log(err.message)
                        this.returnData = 'Unable to subscribe at this moment.  Please try again later'
                    })
            }
        }
    }
}
</script>