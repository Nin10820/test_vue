<template>
  <div class="form">
    <div class="productName">
      <label for>Product name :</label>
      <input type="text" name id placeholder="1235" />
    </div>

    <div class="form-group">
      <label for="exampleInputEmail1">Email address</label>
      <input
        type="email"
        class="form-control"
        id="exampleInputEmail1"
        aria-describedby="emailHelp"
        placeholder="Enter email"
      />
      <small
        id="emailHelp"
        class="form-text text-muted"
      >We'll never share your email with anyone else.</small>
    </div>
    <section class="vertical-tab">
      <div class="tab">
        <button class="tablinks" v-on:click="openCity(catogories)" ref="click">{{catogories}}</button>
        <button class="tablinks" v-on:click="openCity(productInfo)">{{productInfo}}</button>
        <button class="tablinks" v-on:click="openCity(ingredient)" ref="click">{{ingredient}}</button>
        <button class="tablinks" v-on:click="openCity(price)">{{price}}</button>
        <button class="tablinks" v-on:click="openCity(manufacturer)">{{manufacturer}}</button>
        <button class="tablinks" v-on:click="openCity(supplier)">{{supplier}}</button>
        <button class="tablinks" v-on:click="openCity(pack)" ref="click">{{pack}}</button>
        <button class="tablinks" v-on:click="openCity(description)">{{description}}</button>
        <button class="tablinks" v-on:click="openCity(importer)">{{importer}}</button>
      </div>

      <div :id="catogories" class="tabcontent">
        <h3>London</h3>
        <p>London is the capital city of England.</p>
      </div>

      <div :id="productInfo" class="tabcontent">
        <h3>Paris</h3>
        <p>Paris is the capital of France.</p>
      </div>

      <div :id="ingredient" class="tabcontent">
        <h3>London</h3>
        <p>London is the capital city of England.</p>
      </div>

      <div :id="price" class="tabcontent">
        <h3>Tokyo</h3>
        <p>Tokyo is the capital of Japan.</p>
      </div>

      <div :id="manufacturer" class="tabcontent">
        <h3>Paris</h3>
        <p>Paris is the capital of France.</p>
      </div>

      <div :id="supplier" class="tabcontent">
        <h3>Tokyo</h3>
        <p>Tokyo is the capital of Japan.</p>
      </div>

      <div :id="pack" class="tabcontent">
        <h3>pack</h3>
        <p>Paris is the capital of France.</p>
      </div>

      <div :id="description" class="tabcontent">
        <h3>description</h3>
        <p>Tokyo is the capital of Japan.</p>
      </div>

      <div :id="importer" class="tabcontent">
        <h3>importer</h3>
        <p>Tokyo is the capital of Japan.</p>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      catogories: "Catogories",
      productInfo: "Product Info",
      ingredient: "Ingredient",
      price: "Price",
      manufacturer: "Manufacturer",
      supplier: "Supplier",
      pack: "Package",
      description: "Description",
      importer: "Importer"
    };
  },

  methods: {
    openCity(cityName) {
      var i, tabcontent, tablinks;
      tabcontent = document.getElementsByClassName("tabcontent");
      for (i = 0; i < tabcontent.length; i++) {
        tabcontent[i].style.display = "none";
      }
      tablinks = document.getElementsByClassName("tablinks");
      for (i = 0; i < tablinks.length; i++) {
        tablinks[i].className = tablinks[i].className.replace(" active", "");
      }
      document.getElementById(cityName).style.display = "block";

      (event.currentTarget.className += " active"), 1000;
    }
  },

  mounted() {
    // elements have been created, so the `ref` will return an element.
    // but the elements have not necessarily been inserted into the DOM yet.
    // you can use $nextTick() to wait for that to have happened.
    // this is espeically necessary if you want to to get dimensions or position of that element.
    this.$refs.click.click();
  }
};
</script>


<style lang="scss" scoped>
@import url("https://fonts.googleapis.com/css2?family=Poppins&display=swap");
* {
  box-sizing: border-box;
  font-family: "Poppins", sans-serif;
  color: #919aa3;
}

body {
  background: #e5e5e5 !important;
}

.productName {
  padding: 1em;
  transition: 1s;

  font-style: normal;
  font-weight: 500;
  font-size: 18px;
  line-height: 27px;

  input {
    margin-left: 0.5em;
    font-size: 30px;
    letter-spacing: 0.01em;
    color: #00b46e;
    width: 300px;

    border: none;
    border-bottom: 1px solid #d3d8dd;
  }

  input::placeholder {
    color: #919aa3;
    font-size: 26px;
  }
}

.vertical-tab {
  position: relative;
  display: flex;
  width: 100%;
  height: max-content;
  box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.06);
  border-radius: 8px;

  /* Style the tab */
  .tab {
    width: 20%;
    background-color: #ffffff;
    box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.06);
    border-radius: 8px 0 0 8px;
    overflow: hidden;
    z-index: 1;

    /* Style the buttons inside the tab */
    button {
      display: block;
      background-color: inherit;
      color: black;
      padding: 22px 16px;
      width: 100%;
      border: none;
      outline: none;
      text-align: left;
      cursor: pointer;
      transition: 0.4s;
      font-size: 17px;

      /* Change background color of buttons on hover */
      &:hover {
        background-color: #00b46e0a;
        color: #00b46e;
      }

      /* Create an active/current "tab button" class */
      &.active {
        background-color: #00b46e14;
        color: #00b46e;
        font-size: 22px;
      }
    }
  }

  /* Style the tab content */
  .tabcontent {
    width: 80%;
    padding: 0px 12px;
    border-left: none;
    background: #fefefe;
  }
}
</style>
