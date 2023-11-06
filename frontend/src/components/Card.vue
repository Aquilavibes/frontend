<template>
    <div class='card'>

        <div class='flexy'>
        <h1>{{ cardtype }}</h1>
        <h2>{{ bankname }}</h2>
        </div>
        <h3>{{ cardnumb }}</h3>
       
        <div class='date'>
        <p id='dd'>{{ dd }}/</p>
        <p id='yy'>{{ yy }}</p>
        </div>

<div class='down'>
        <h4>{{ cardholder }}</h4>
        <small>CVV:{{ cvv }}</small>
</div>
    </div>
    
</template>

<script>
export default {
    props: ['cardtype', 'bankname', 'cardnumb', 'dd', 'yy', 'cvv', 'cardholder'],

  
}


</script>


<style scoped>
.card {
    background-color: black;
    color: white;
    border-radius: 10px;
    height: 250px;
}

.date {
    display: flex;
    margin-left: 300px;
    margin-top: 5px;
}

#dd {
    margin-top: 1px;
}

#yy {
    margin-top: 1px;
}
h3 {
    text-align: center;
    font-size: 35px;
    font-family: 'Courier New', Courier, monospace;
    margin-top: 16px;
}

.flexy {
    display: flex;
    justify-content: space-between;
}

.down {
    display: flex;
    justify-content: space-between;
    margin-top: 20px;
}

small {
    margin-top: 2px;
    margin-right: 20px;
}

h4 {
    margin-top: 2px;
    font-size: 25px;
    font-family:monospace;
    margin-left: 20px;
}

h1 {
    margin-top: 10px;
    font-size: 25px;
    margin-left: 20px;
    font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
}

h2 {
    margin-right: 20px;
}
</style>