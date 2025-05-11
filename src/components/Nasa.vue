<script setup>
import { ref } from 'vue';
const myText = ref('')
const resultText = ref('')
const convertText = () => {
     resultText.value = ""
    if(myText.value != ""){
        let textArr = myText.value.split('')
        for(let i = 0; i < textArr.length; i++){
           textArr[i] = nasaPhoneticAlphabet[textArr[i]]
          
        }
        for(let i = 0; i < textArr.length; i++){
          resultText.value +=  textArr[i] + " "
        }
        myText.value = ""
        console.log(resultText.value)
    }
}
const reset = () => {
    resultText.value = ""
}
const nasaPhoneticAlphabet = {
    'a': 'Alpha',
    'b': 'Bravo',
    'c': 'Charlie',
    'd': 'Delta',
    'e': 'Echo',
    'f': 'Foxtrot',
    'g': 'Golf',
    'h': 'Hotel',
    'i': 'India',
    'j': 'Juliet',
    'k': 'Kilo',
    'l': 'Lima',
    'm': 'Mike',
    'n': 'November',
    'o': 'Oscar',
    'p': 'Papa',
    'q': 'Quebec',
    'r': 'Romeo',
    's': 'Sierra',
    't': 'Tango',
    'u': 'Uniform',
    'v': 'Victor',
    'w': 'Whiskey',
    'x': 'Xray',
    'y': 'Yankee',
    'z': 'Zulu',
    '0': 'Zero',
    '1': 'One',
    '2': 'Two',
    '3': 'Three',
    '4': 'Four',
    '5': 'Five',
    '6': 'Six',
    '7': 'Seven',
    '8': 'Eight',
    '9': 'Nine',
    ' ': ' ', // Keep spaces
};
</script>

<template>
    
    <div class="container">
        <h1>Text to Nasa Phonetic Alphabet</h1>
        <input type="text" v-model="myText">
        <div class="cta">
            <button @click="convertText">Convert to NASA</button>
            <button @click="reset" class="reset-btn">Reset</button>
        </div>
        <div class="result">
            {{ resultText }}
        </div>
        <p>This app converts text to the NASA/NATO phonetic alphabet.</p>
    </div>
</template>