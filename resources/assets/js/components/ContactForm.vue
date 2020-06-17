<template>
	<div id="customer">
		<div class="row justify-content-center">
			<div class="col-md-12">
				<div class="card">
					<div class="card-header">Customer</div>
		<div class="table-responsive">
    <table class="table table-hover table-bordered table-striped">
  <thead>
    <tr>
      <th scope="col">Sl</th>
      <th scope="col">Name</th>
      <th scope="col">Email</th>
      <th scope="col">Phone</th>
      <th scope="col">Address</th>
      <th scope="col">Total</th>
      <th scope="col" class="text-center">Action</th>
    </tr>
  </thead>
  <tbody>

    <tr v-for="customers, index) in customer" :key="customers.id">
      <th scope="row">{{customers.id}}</th>
      <td>{{ customers.name }}</td>
      <td>{{ customers.email }}</td>
      <td>{{ customers.phone }}</td>
      <td>{{ customers.address }}</td>
      <td>{{ customers.total }}</td>
      <td>
        <button type="button" class="btn btn-success">Edit</button>
        <button type="button" class="btn btn-danger">Delete</button>
      </td>
    </tr>
    
  </tbody>
</table>
</div>
</div>
</div>
</div>
</div>
</template>

<script>
   export default {

    data(){
      return{
        customer:[],
      }
    },
       mounted() {
        console.log('component mounted.')
        this.getData();
       },
       methods:{
        getData(){
        axios.get('/api/customer')
        .then(response=>{
          this.customer=response.data.data
        })
        
        .catch(e=>{
          console.log(e)
        })
        }
       }
   }
</script>