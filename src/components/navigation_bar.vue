<template>
  <div id="navigation">
    <b-navbar toggleable="lg" type="dark" variant="info">
      <b-navbar-brand href="#">
        <router-link to="/" class="nchar1">KNTSport</router-link>
      </b-navbar-brand>

      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav>
          <b-nav-item href="#">
            <router-link to="/" class="nchar2">Home</router-link>
          </b-nav-item>
        </b-navbar-nav>

        <!-- Right aligned nav items -->
        <b-navbar-nav class="ml-auto shearch">
          <b-nav-form>
            <b-form-input size="sm" class="mr-sm-2" placeholder="Search"></b-form-input>
            <b-button size="sm" class="my-2 my-sm-0" type="submit">Search</b-button>
          </b-nav-form>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
  </div>
</template>
 
<script>
export default {};
</script>

<style>
.nchar1 {
  color: #fff;
  padding-left: 150px;
}
.nchar2 {
  color: #fff;
  border-bottom: 2px solid transparent;
  padding-bottom: 20px;
  transition: all 0.3s ease;
}
.nchar1:hover {
  color: #fff;
  text-decoration: none;
}
.nchar2:hover {
  color: #fff;
  text-decoration: none;
  border-bottom: 2px solid #333;
  padding-bottom: 0px;
}

.shearch {
  padding-right: 150px;
}
</style>