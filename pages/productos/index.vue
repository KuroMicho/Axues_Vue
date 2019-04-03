<template>
  <div class="overflow-auto">
    <div class="row mt-3">
      <div class="col-xs-6">
        <h4>Lista de Productos</h4>
      </div>
      <div class="col-xs-6 ml-5">
        <b-button variant="primary" href="/productos/nuevo">Nuevo</b-button>
      </div>
    </div>

    <b-pagination
      v-model="pages"
      :total-rows="rows"
      :per_page="perpage"
      aria-controls="my-table"
    ></b-pagination>

    <p class="mt-3">Current Page: {{ page }}</p>
     

    <b-table
      id="my-table"
      responsive
      striped
      hover
      :per_page="perpage"
      :page="pages"
      :fields="fields"
      :items="products.data"
      small
    ></b-table>
  </div>
</template>

<script>
export default {
  asyncData({ $axios }) {
    return $axios.get("http://localhost:4000/api/products").then(result => {
      return {
        products: result.data
      };
    });
  },

  data() {
    return {
     pages:1,
     perpage:3,
  
      fields: {
        Name: {
          label: "Name"
        },
        Amount: {
          label: "Cantidad"
        },
        Price: {
          label: "Precio"
        },
        Image: {
          label: "Image"
        },
        Slug: {
          label: "Slug"
        }
      },
      computed: {
        rows() {
          return this.items.length;
        }
      }
    };
  }
};
</script>

