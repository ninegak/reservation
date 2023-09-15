<template>
  <header>
    <div class="nav-bar">
    <router-link to="/">Home</router-link>
    <router-link to="/event">Events</router-link>
    <router-link to="/reserv">Reservation</router-link>
  </div>
  </header>
</template>

<script>
export default {
  name: 'Navbar',
};
</script>

<style scoped>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

header {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    padding: 20px 100px;
    justify-content: space-between;
    display: flex;
    align-items: center;
    z-index: 100;
    background-color: #6B8A47;
}

a { 
  text-decoration: none; 
  color: #eae3c0;

}

.nav-bar a{
    position: relative;
    font-size: 18px;
    font-weight: 500;
    margin-left: 40px;
}


.nav-bar a:hover,
.nav-bar a.active {
    color: orange;
}

.nav-bar a::before {
    content: '';
    position: absolute;
    top: 100%;
    left: 0;
    width: 0;
    height: 2px;
    background-color: #fff;
    transition: 0.3s;
}

.nav-bar a:hover::before {
    width: 100% ;
}
</style>
