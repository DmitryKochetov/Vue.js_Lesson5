<!-- Вы разрабатываете приложение для интернет-магазина и у вас есть компонент Vue под названием "ProductDetails". 
Компонент отображает детали о конкретном продукте, включая его название, цену и статус доступности.

Внутри компонента "ProductDetails" создайте свойство "product" с объектом, представляющим информацию 
о продукте. Объект должен иметь свойства "name" (название продукта), "price" (цена продукта) и "available" 
(флаг, указывающий на доступность продукта).
Используя вычисляемое свойство, назовите его "formattedPrice", которое будет возвращать форматированную цену 
продукта со знаком валюты. Например, если цена равна 99.99, вычисляемое свойство должно вернуть строку "$99.99".
В компоненте "ProductDetails" отобразите название продукта, его форматированную цену и статус доступности.
Если продукт доступен, отобразите текст "Available", в противном случае - "Out of stock". -->

<template>
    <div class="ProductDetails">
        <div>Product name: {{ product.name }}</div>
        <div>Product price: {{ formattedPrice }}</div>
        <div v-if="product.available">Available</div>
        <div v-else>Out of stock</div>
        <br>
        <button @click="changeProductAvailableStatus()">Change available status</button>

    </div>
</template>
  
<script>
export default {
    name: 'HelloWorld',
    props: {
    },
    data() {
        return {
            product:
            {
                name: 'Happiness',
                price: 99.99,
                available: true,
            }

        }
   
    },
    computed: {
        formattedPrice() {
            return '$' + this.product.price;
        },
    },
    methods: {
        changeProductAvailableStatus() {
            this.product.available = !this.product.available;
        },
        
    },

}
</script>
  
  
<style scoped></style>
  