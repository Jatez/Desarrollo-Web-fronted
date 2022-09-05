<template>
    <div>
        <h1>Productos</h1>

        <template>
            <v-form ref="formProduct" v-model="valid" lazy-validation>
                
            <v-text-field 
                v-model="product.id"
                label="Código" 
                :rules="rules.required"
                required
             ></v-text-field>

            <v-text-field 
                v-model="product.name" 
                :rules="rules.required"
                label="Nombre" 
                required
            ></v-text-field>

            <v-text-field 
                v-model="product.price"
                :rules="rules.required" 
                label="Precio" 
                required
            ></v-text-field>

            <v-text-field 
                v-model="product.brand"
                :rules="rules.required" 
                label="Marca" 
                required
            ></v-text-field>

            <v-text-field 
                v-model="product.size" 
                :rules="rules.required" 
                label="Tallas" 
                required
            ></v-text-field>

            <v-text-field 
                v-model="product.colors" 
                :rules="rules.required" 
                label="Colores" 
                required
            ></v-text-field>

            <v-textarea 
                v-model="product.description"
                :rules="rules.required" 
                label="Descripción" 
                required
             ></v-textarea>

            <v-select 
                v-model="product.category" 
                :rules="rules.required" 
                :items="categories"
                label="Categoría"
                required
             ></v-select>

            <v-btn color="success" @click="saveProduct()"> Guardar producto</v-btn>

            </v-form>
          </template>

    </div>
</template>

<script>
    export default {
      data: () => ({
        valid: true,
        product:{
            id:"",
            name:""
        },
        categories:['Deportiva', 'Mujer', 'Hombre', 'Casual'],
        rules:{
            required:[v => !!v || 'El campo es obligatorio',]
        }
      }),
  
      methods: {
        saveProduct(){
            if(this.$refs.formProduct.validate()){
                console.log('-- Inicio guardar producto --')
                let product = Object.assign({},this.product);
                console.log(product);
            }else{
                console.log('Formulario incompleto')
            }
        },
      },
    }
  </script>

<style>

</style>