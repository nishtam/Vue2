<template>
  <div class="hello">
<div class="offset-md-1 col-md-10 offset-md-1 border border-primary" style="padding: 10px">

    <form @submit.prevent="handleSubmit">
      <div class="form-group">
        <label for="customer">Customer</label>
        <input
          type="text"
          v-model="customerInfo.customer"
          id="customer"
          name="customer"
          class="form-control"
          
        />
        
      </div>
      <div class="form-group">
        <label for="department">Department</label>
        <input
          type="text"
          v-model="customerInfo.department"
          id="department"
          name="department"
          class="form-control"
          
        />
        
      </div>
      <div class="form-group">
        <label for="country">Country</label>
        <input
          type="country"
          v-model="customerInfo.country"
          id="country"
          name="country"
          class="form-control"
          
        />
        
      </div>
      
      <div class="form-group">
        <button class="btn btn-primary">Register</button>
      </div>
    </form>
    </div>
    <div class="offset-md-1 col-md-10 offset-md-1" style="padding: 10px">
      <table id="customers" class="table table-striped table-bordered">
        <thead>
          <tr>
            <th>Customer</th>
            <th>Department</th>
            <th>Country</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="customer in customers" :key="customer.id">
            <td>{{ customer.customer }}</td>
            <td>{{ customer.department }}</td>
            <td>{{ customer.country }}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
import { ref } from "vue";
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data() {
    return {
      customerInfo: {
        customer: "",
        department: "",
        country: "",
      },
      submitted: false,
    };
  },
  methods: {
    handleSubmit() {
      this.submitted = true;
      this.customers.push(
      this.customerInfo
      )
      alert("SUCCESS!! :-)\n\n" + "Company created successful")
      
    },
  },
  setup() {
    // make customers variable reactive with the ref() function
    const customers = ref([
      {
        customer: "Nishant",
        department: "IT",
        country: "Germany",
      },
      {
        customer: "Ajay",
        department: "Electronics",
        country: "Germany",
      },
      {
        customer: "Alfreds Futterkiste",
        department: "Electrical",
        country: "Canada",
      },
      
      
    ]);

    return {
      customers,
    };
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
