<template>
  <div class="container">
    <div class="row">
      <div class="col-md-auto">
        <h1>{{ name }}</h1>
        <h5>{{ descriptor }}<i class="fas fa-code"></i></h5>
      </div>
      <div class="col secondary">
        <span>{{ credential }}</span>
        <br>
        <i class="fas fa-address-card"></i>
      </div>
      <div class="col-md-auto secondary">
        <span>{{ degree }}</span>
        <br>
        <span>{{ university }}</span>
        <i class="fas fa-graduation-cap"></i>
      </div>
      <div class="col secondary">
        <span><a :href="'mailto:' + email">{{ email }}</a></span>
        <br>
        <span><a :href="'tel:' + phoneNumber">{{ phoneNumber }}</a></span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Header',
  data() {
    return {
      name: 'Ryan Gross',
      descriptor: 'Full Stack Developer',
      credential: 'Active TS Clearance',
      degree: 'BS, Computer Engineering',
      university: 'West Virginia University, 2012',
      email: 'ryan.gross.01@gmail.com',
      phoneNumber: '301-788-8032'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h5 {
  font-weight: 900;
  padding-left: 25px;
}
.row {
  margin-top: 3rem;
}
.col {
  margin-bottom: 1rem;
}
span {
  margin-top: 1rem;
}
.secondary {
  padding-top: 1rem;
}
.fa-address-card {
  font-size: 1.5rem;
}
.fa-code {
  margin-left: 8px;
  color: #F89C1C;
}
</style>
