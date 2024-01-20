<script setup>
</script>

<template>
    <div class="absolute z-30">
        <img src="../assets/DinoRosieKSubscribe.png" alt="" class="rounded-3xl shadow-slate-900 shadow-2xl drop-shadow-2xl">
        <div class="absolute bottom-0 mb-8 grid grid-cols-5 gap-4 w-full">
            <form>
                <p>Name</p>
                <input type="text" v-model="name" />
                <p>Email</p>
                <input type="text" v-model="emal" />
                <div>
                    <div>Gender:</div>
                    <input name="gendersel" type="radio" id="male" value="1" v-model="gender" />
                    <label for="male">Male</label>
                    <br>
                    <input name="gendersel" type="radio" id="female" value="2" v-model="gender" />
                    <label for="female">Female</label>
                    <br>
                    <input name="gendersel" type="radio" id="unknown" value="3" v-model="gender" checked />
                    <label fo="unknown">Rather not Say</label>
                </div>
            </form>
        </div>
    </div>
</template>