<template>
  <b-form>
        <h1>Nuevo Producto</h1>
    <div class="row">
      <div class="col-sm-12">
        <b-form-group label="Imagen:" label-for="imagen">
          <b-form-file id="imagen" placeholder="Load Image" drop-placeholder="Load Image"/>
        </b-form-group>

        <b-form-group label="Nombre:" label-for="nombre">
          <b-form-input id="nombre" placeholder="Nombre del producto"/>
        </b-form-group>

        <b-form-group label="Precio:" label-for="precio">
          <b-form-input id="precio" type="text" required placeholder="Precio del producto"/>
        </b-form-group>

        <b-form-group label="Cantidad:" label-for="cantidad">
          <b-form-input id="cantidad" type="number" required placeholder="Cantidad del producto"/>
        </b-form-group>
      </div>
    </div>

        <b-button-toolbar>
          <b-button-group right class="mx-2">
            <b-button href="/productos">Volver</b-button>
            <b-button variant="primary" type="submit">Guardar</b-button>
          </b-button-group>
        </b-button-toolbar>
   
  </b-form>
</template>
