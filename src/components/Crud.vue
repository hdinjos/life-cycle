<template>
  <div>
    <div class="tab">
      <table>
      <tr>
        <td colspan="5">
          <button @click="addUser">Add</button>
        </td>
      </tr>
        <tr>
          <th>Name</th>
          <th colspan="3">Action</th>
        </tr>
        <tr v-for="(user, index) in users" :key="index">
          <td>{{ user.name }}</td>
          <td v-show="!detail"><button @click="detailUser(index)">Detail</button></td>
          <td v-show="detail"><button @click="close(index)">Tutup</button></td>
          <td><button @click="editUser(index)">Edit</button></td>
          <td><button @click="delUser(index)">Delete</button></td>
        </tr>
        <tr>
          <td v-if="users.length === 0" colspan="6">Data kosong</td>
        </tr>
      </table>
      <div v-if="input" style="margin-top:20px;">
        <label>Name</label>
        <input v-model="name" type="text" /> <br/><br/>
        <label>Age</label>
        <input v-model="age" type="text" /> <br/><br/>
        <label>Address</label>
        <input v-model="address" type="text" /> <br/><br/>

        <button v-show="editable" @click="editUserSave">Save</button>
        <button v-show="!editable" @click="addUserSave">Save</button>
        <button style="margin-left:20px;" @click="cancel">Cancel</button>
      </div>
      <div v-show="detail" style="margin-top: 20px;">
        <h3>Detail</h3>
        <p>Name: {{name}}</p>
        <p>Age: {{age}}</p>
        <p>Address: {{address}}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data: () => {
    return {
      users: [
        { name: "Ardan", age: 22, address: "Klaten" },
        { name: "Hendi", age: 23, address: "Pati" },
        { name: "Arif", age: 22, address: "Padang" },
      ],
      input: false,
      name:'',
      age: '',
      address: '',
      editable: '',
      index:'',
      detail:''
    };
  },
  methods: {
      addUserSave: function(){
          let data = {
              name: this.name,
              age: this.age,
              address: this.address
          };
          this.users.push(data);
      },
      addUser: function(){
        this.name= '';
        this.age= '';
        this.address= '';
        this.input = true;
        this.editable = false;
      },
      delUser: function(index){
          this.users.splice(index,1);
          console.log(this.users);
      },
      editUser: function(index){
          this.name = this.users[index].name;
          this.age = this.users[index].age;
          this.address = this.users[index].address;
          this.input = true;
          this.editable = true;
          this.index = index;
      },
      editUserSave: function(){
        let index = this.index;
        this.users[index].name = this.name;
        this.users[index].age = this.age;
        this.users[index].address = this.address;
        this.input = false;
      },
      cancel: function(){
        this.input = '';
        this.name = '';
        this.age = '';
        this.address = '';
      },
      detailUser: function(index){
        this.name = this.users[index].name
        this.age = this.users[index].age
        this.address = this.users[index].address
        this.detail = true;
        this.index = index;
        console.log(this.detail, this.index +1);
      },
      close: function(){
        this.detail = '';
      }
  }
};
</script>

<style>
table,
th,
td {
  border: 1px solid black;
  padding: 10px;
  text-align: center;
}
</style>