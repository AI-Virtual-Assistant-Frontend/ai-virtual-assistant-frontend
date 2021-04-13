<template>
<div id="Recommand">
    <input type="button" name="Recommand" value="Recommand" @click="toggleDisplay"/>
    <div id = "welcomeDiv" class="backdrop" style="display:none;">
        <div class = "Sidebar">
            <h2>Sidebar content</h2>
            <button class = "button2" >Add Data</button>
            <input type = "text"  ref = "name">
            <button class = "button1" @click="handleclick">Submit</button>
            <div class = "slider">   
                <datalist id="custom-list">
                    <option value="1"></option>
                    <option value="2"></option>
                    <option value="3"></option>
                    <option value="4"></option>
                    <option value="5"></option>
                    <option value="6"></option>
                    <option value="7"></option>
                    <option value="8"></option>
                    <option value="9"></option>
                    <option value="10"></option>
                    <option value="11"></option>
                </datalist>
                <div class = "Quality">          
                 <input type = "range" id= "Quality" min = "1" max = "10" step = "1" list="custom-list">
                 <label for ="Quality"> Quality </label>
                 </div>
                 <div class = "Relevance"> 
                 <input type = "range" id= "Relevance" min = "1" max = "10" step = "1" list="custom-list">
                 <label for ="Relevance"> Relevance </label>
                 </div>
                 <div class = "Accuracy">
                 <input type = "range" id= "Accuracy" min = "1" max = "10" step = "1" list="custom-list">
                 <label for ="Accuracy"> Accuracy </label>
                 </div>
            </div>
        </div>  
    </div>
    
</div>
</template>

<script>
export default {
    name: 'Sidebar',
    methods: {
        handleclick(){
          console.log(this.$ref.name)
          this.$ref.name.classList.add('active')
        },
        showdiv(){
            document.getElementById("welcomeDiv").style.display = "";
        },
        toggleDisplay() {
                this.display = !this.display;
        }
    },
    data() {
        return {
            display: false
        }
    }
}

</script>

<style scoped>
.Sidebar{
    position:absolute;
    right:-100px;
    width:280px;
    height:800px;
    margin: 100px;
    padding: 20px;
    background:wheat;
}
.backdrop{
    position:absolut;
    right:100px;
    background: transparent;
    width: 10%;
    height: 10%;
}
.slider{
    display: inline-block;
    vertical-align: text-top;
    height: 0px;
}
label{
    position:absolute;
    display: inline-block;
    vertical-align: text-top;
    padding: none;
    font-size: 14px;
}
input[type = "text"]{
  text-align:top;
  vertical-align: bottom;
  position: absolute;
  bottom: 5px;
  right:80px;
  padding: 10px,0px;
  width: 150px;
  height: 250px;
  font-size: 20px;
}
input[type = "range"]{
    width: 90%;
}

.Quality{
    position: absolute;
    top:380px;
    right: 100px;
}
.Relevance{
    position: absolute;
    top:420px;
    right: 100px;
}
.Accuracy{
    position: absolute;
    top:460px;
    right: 100px;
}

button{
  border: none;
  color: black;
  padding: 4px 4px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 12px;
  margin: 4px 2px;
  transition-duration: 0.4s;
  cursor: pointer;
}
.button1{
    position:absolute;
    bottom:5px;
    right: 80px;
}
.button2{
    position: absolute;
    top: 150px;
    right:100px;
    font-size: 16px;
    padding: 10px 10px;
}
</style>
