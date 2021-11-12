<template>
    <div class="container">
        <div>
            <form class="temperature">
                <label for="degrees">Degrees</label>
                <input type="text" v-model="temperature">
                    <label class="left" for="type">From</label>
                    <select name="Temperatures" id="Temperature" @change="changeTemp" v-model="myChoice">
                            <option v-for='type in selected' :key='type'>{{ type }}</option>
                    </select>
                    <button @click.prevent="cToF" class="convert" value="submit" type="submit">Convert</button>
            </form> 
            <div class="result">
                            <p>Result</p>
                            <h2 class="inset">{{result}}</h2>
                 </div>       
        </div>
    </div>
</template>

<script>

export default {
    name: 'Main',

    data() {
        return {
            temperature: '',
            result: '',
            selected: ['Celsius', 'Fahrenheit'],
            myChoice: 'Celsius',
            disable: false
        };
    },
    methods: {
        changeTemp() {
                if (this.myChoice == 'Fahrenheit') {
                   console.log('fahrenheit')
                }
                else if (this.myChoice === 'Celsius') {
                    console.log('Celsius')
                }
            },

        cToF() {


            if(isNaN(this.temperature)) {
                return alert('What happened to inputing a value for degrees!!');
            }
            else if(this.myChoice == 'Fahrenheit') {
                this.Celsius = this.temperature;
                this.result = Math.round((this.temperature -32) * 5/9) +'\xB0C';
                this.result;
                console.log(this.result);
            }
            else if(this.myChoice === 'Celsius'){
                
                this.Fahrenheit = this.temperature;
                this.result = Math.round(this.temperature * 9/5 +32) +'\xB0F';
                this.result;
                console.log(this.result);
            }
        }
    },

}  
</script>       

<style scoped>
.container {
    padding: 2px 16px;
    margin: auto;
    width: 500px;    
    height: 400px;
    transition: 0.3s;
    /* box shadow made the box */
    box-shadow: 0 0 1rem 0 rgba(0, 0, 0, .2); 
    border-radius: 5px;
    z-index: 1;
    background: inherit;
    overflow: hidden;
	background-position: right;
    backdrop-filter: blur(5px);
    margin-top: -2rem;
}

.result {
    display: flex;
    margin: auto;
    margin-top: 6rem;
}

result p {
     margin-bottom: 1px;
}

.result h2 {
    margin: auto;
    margin-bottom: 1rem;
    margin-left: .4rem;
    text-align: center;
}

temperature {
    display: flex;
    justify-content: space-between;
    height: 3rem;
    margin-top: 2rem;
}

p {
    color: rgb(133, 124, 118);
    font-size: 1rem;
    color: rgb(34, 52, 112);
    margin-left: 5px;
}

label {
    font-size: 1rem;
    color: rgb(34, 52, 112);
    margin: 10px 10px 0 0px;
}

.left {
    margin-left: 7px;
}
.temperature select {
    padding: 11px 5px;
    background-color: #959fd4;
    color: rgb(239, 236, 243);
    border: 1px solid #959fd4;
    font-weight: 750;
    border-radius: 5px;
    margin: 0 10px  20px 0;
    margin-top: 2rem;
}

h1 {
    text-align: center;
    margin: auto;
    margin-top: 2rem;
    padding: 2rem;
    color: rgb(45, 50, 66);
}

h3 {
    margin-top: 17rem;
    text-align: center;
    color: rgb(54, 50, 54);
    
}

input[type="text"] {
  padding: 12px;
  border: 1px solid #eef0f5;
  outline: 0;
  border-radius: 5px;
  border-style: inset;
  background: rgb(247, 245, 242);
  color: #303a6d;
  font-weight: 530;
  /* font-size: 12px; */
}

.convert {
    background: #8d97ca;
    color: #fff;
    padding: 11px 5px;
    background-color: #959fd4;
    color: rgb(239, 236, 243);
    border: 1px solid #959fd4;
    font-weight: 750;
    border-radius: 5px;
    border: 1px white solid;
    cursor: pointer;
    width: 67px;
    height: 2.7rem;
    margin: 10px;
}

#Temperature {
    width: 80px;
    border: #959fd4;
    border-style: solid;
}

h2.inset {
    border-radius: 5px;
    border-style: inset;
    width: 300px;
    height: 3rem;
    padding: 4px;
    background: rgb(247, 245, 242);
    color: #303a6d;
    margin-left: 30px;
}

</style>