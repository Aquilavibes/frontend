<template>
<Modal>
  <div class='backdrop'>
    <div class='sidebar'>
      <img src='./assets/profile.png' id='profile'>
      <p id='username'>Aquila Brama</p>
      <hr>
      <div class='flex-load1'>
    <img src='./assets/loading.png' id='load'> <h2 id='settings'>Privacy & settings</h2>
      </div>
      <div class='flex-load2'>
        <img src='./assets/support.png' id='support-img'><h2 id='support'>Contact Support</h2>
      </div>

      
    
      <p id='logout'>Log Out</p>
    </div>
  </div>
 </Modal>

<div v-if='showModal'>
 <Modal @close='handleModal'>

<div class='modal'>

    <button @click='closeModal' id="closy">X</button>

    <h1> Card Details</h1>
    <p id='note'>
      Note: Be sure to write your details correctly.
    </p>
    <form>
      <div class='flex'>
      <label>Card type</label>
  <input type='text' id='cardtype' v-model='cardtype'>
      </div>
<br>

<div class='flex'>
  <label>bank name</label>
  <input type='text' id='bankname' v-model='bankname'>
</div>
<br>

<div class='flex'>
  <label>Card number</label>
  <input type='tel' id='cardnumb' v-model='cardnumb'>
</div>
<br>
<br>

<div class='flex'>
  <label>Card Holder</label>
  <input type='text' id='cardholder' v-model='cardholder'><br>
 </div>
 <br>

 <div class='down-flex'>
 <div class='daty'>
  <label>date: </label>
  <input type='tel' id='dd' placeholder="dd" v-model='dd'>
/
  <input type='tel' id='yy' placeholder="yy" v-model='yy'>
 </div>
 <br>
 

 <div class='flex'>
  <input type='tel' id='cvv' placeholder="cvv" v-model='cvv'>
 </div>
 </div>
 <br>
 <br>
 <br>
 <button id='add'>Add card </button>
    </form>
  </div>

 </Modal>
</div>
  
  <Navbar>
<nav>
        <h1>{{ save }}</h1>
        <img src='./assets/menu.png' id="menu">
         </nav>
        <button @click='handleModal' id='open'>{{ btn }}</button>
  <br>
   <br>
  </Navbar>
  

   <Card :cardtype='cardtype' :cardnumb='cardnumb' :bankname='bankname' :dd='dd' :cardholder='cardholder' :yy='yy' :cvv='cvv'/>
 
 
</template>

<script>
import Navbar from './components/Navbar.vue'
import Card from './components/Card.vue'
import Modal from './components/Modal.vue'


export default {

  name: 'App',
  data() {
    return {
save: 'SaveCards',
btn: '+',
showModal: false,
cardtype: 'h',
cardnumb: '',
bankname: '',
dd: '',
yy: '',
cardholder: '',
cvv: ''




    }
  },
  components: { Navbar, Card, Modal },


methods: {
handleModal() {
  this.showModal = !this.showModal

},


closeModal() {

    this.showModal = !this.showModal
   }
}
}
</script>

<style scoped>
#support {
  color: white;
  margin-left: 19px;
  font-size: 13px;
}
#support-img {
  height: 28px;
  border-radius: 20px;
  margin-left: 18px;
  margin-top: 4px;
}
.flex-load2 {
  display: flex;
 
}
.flex-load1 {
  display: flex;
 
}
#load {
  height: 28px;
  border-radius: 20px;
  margin-left: 18px;
  margin-top: 4px;
}
#settings{
  color: white;
  margin-left: 19px;
  font-size: 13px;

}


#username {
  color: white;
  margin-left: 70px;
}
#logout {
  color: red;
  text-align: center;
  margin-right: 50px;
}
.backdrop {
  background-color: rgba(0,0,0,0.5);
  width: 100%;
  position: fixed;
  height: 100%;
}

.sidebar {
  background-color: black;
  width: 200px;
  margin-left: 290px;
  height: 600px;
}

#profile {
  width: 80px;
  border: solid white;
  border-radius: 80px;
  margin-left: 80px;

}
.modal {
  background-color: white;
  position: fixed;
  height: 100%;
  width: 100%;
}

h1 {
  text-align: center;
  font-size: 50px;
   font-family:Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
}

#note {
  text-align: center;
  font-size: 18px;
  font-weight: bold;
  margin-top: 3px;
}

#closy {
   border-radius: 50px;
  height: 35px;
  width: 35px;
  font-size: 29px;
}


label {
  font-size: 20px;
  font-weight: bold;
  font-family:'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
}

#cardtype {
  border-top: 10px;
  border-bottom: solid black; 
  border-left: 10px;
  border-right: 10px; 
  width: 250px;
  height: 30px;
 font-size: 27px;
}

#bankname {
  border-top: 10px;
  border-bottom: solid black; 
  border-left: 10px;
  border-right: 10px; 
  width: 250px;
  height: 30px;
 font-size: 27px;
}


#menu {
  height: 35px;
  margin-top: 13px;
}

#cardnumb {
  border-top: 10px;
  border-bottom: solid black; 
  border-left: 10px;
  border-right: 10px; 
  width: 230px;
  height: 30px;
  font-size: 27px;
 
}


#open {
  margin-left: 360px;
  border-radius: 50px;
  height: 35px;
  width: 35px;
  font-size: 29px;
}

#dd { 
  width: 30px;
  border: solid black;
 height: 30px;
 font-size: 20px;
}

#yy { 
  width: 30px;
  border: solid black;
 height: 30px;
 font-size: 20px;
}

#cvv{ 
  width: 50px;
  height: 30px;
  border: solid black;
  font-size: 20px;
  margin-right: 20px;
 
}

.flex {
  display: flex;
}

.down-flex {
  display: flex;
  justify-content: space-between;
}

#add {
    margin-left: 150px;
    width: 100px;
    height: 60px;
    background-color: black;
    color: white;
    border-radius: 20px;
    font-weight: bold;
    font-size: 16px;
}
button {
  border-radius: 80px;
  font-size: 30px;
  height: 50px;
  color: white;
  background-color: black;
  
}

nav {
  display: flex;
  justify-content: space-between;
}

h1 {
    font-size: 30px;
    margin-top: 10px;
    font-weight: bolder;
    font-family:system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
}

#cardholder {
  border-top: 10px;
  border-bottom: solid black; 
  border-left: 10px;
  border-right: 10px; 
  width: 230px;
  height: 30px;
  font-size: 27px;
}

</style>



