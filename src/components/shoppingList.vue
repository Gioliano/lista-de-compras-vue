<template>
    <section>
        <div class="form-container">
            <h1>Adicionar Produtos</h1>
            <form @submit.prevent="addProduct">
                <div>
                    <label>Nome</label>
                    <br />
                    <input v-model="state.input" type="text" />
                </div>
                <div>
                    <button type="submit" class="submit"> Adicionar Produto </button>
                </div>
            </form>
        </div>
        <div class="list-container">
            <ul v-for="(Product,index) in state.Products" :key="index">
                <li>
                    Lista de Compras
                    <span style="float:right;padding-right:10px;">
                    <button @click="removeProduct(index)">X</button>
                    </span>
                </li>
            </ul>
        </div>
    </section>
</template>


<script>
import { reactive } from 'vue';
export default {
setup() {
    const { state, addProduct, removeProduct } = ProductList();
    return { state, addProduct, removeProduct };
    }
};
function ProductList() {
    let state = reactive({ 
        input: "",
        Products: ["Product 1"] 
    });

let addProduct = () => {
    state.Products.push(state.input);
    state.input = "";
};
let removeProduct = (i) => {
    state.Products.splice(i,1);
};

return { state, addProduct, removeProduct };
}
</script>


<style scoped>
    input {
        width: 20%;
        height: 30px;
        border: 2px solid blue;
    }
    .submit {
        margin: 10px;
        padding: 10px;
        border-radius: 0px;
        border: 0px;
        background: aqua;
        color: darkblue;
    }
    ul li {
        list-style: none;
        border: 2px blue;
        width: 30%;
        margin-top:10px;
    }
</style>