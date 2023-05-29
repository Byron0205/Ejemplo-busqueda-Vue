<template>
    <div>
        <input class="buscar" type="text" v-model="searchTerm" placeholder="Buscar" />
        <div class="card-group">
            <div class="card" v-for="card in filteredCards" :key="card.id">
                <h3>
                    {{ card.nombre }}
                </h3>
                <p>
                    ${{ card.precio }}
                </p>
                <p>
                    {{ card.detalle }}
                </p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            searchTerm: "",
            cards: [
                {
                    "id": 1,
                    "detalle": "2000 Chevrolet Malibu LS",
                    "autor": "Juan Perez",
                    "nombre": "Venta de carro",
                    "fecha": "01/02/23",
                    "precio": 3400
                },
                {
                    "id": 2,
                    "detalle": "MSI GX780-011US",
                    "autor": "Marcelo Gomez",
                    "nombre": "Venta de laptop",
                    "fecha": "01/02/23",
                    "precio": 1300
                },
                {
                    "id": 3,
                    "detalle": "Logitech G603",
                    "autor": "Marcelo Gomez",
                    "nombre": "Venta de Mouse",
                    "fecha": "01/02/23",
                    "precio": 80
                },
                {
                    "id": 11,
                    "detalle": "semi-nuevo de 4 puertas",
                    "autor": "Jaime Rosales",
                    "nombre": "Venta de automovil",
                    "fecha": "2023-05-22",
                    "precio": 500
                },
                {
                    "id": 12,
                    "detalle": "Se vende por falta de uso",
                    "autor": "Kendall Madrigal",
                    "nombre": "Venta de moto",
                    "fecha": "2023-05-31",
                    "precio": 1000
                },
                {
                    "id": 15,
                    "detalle": "fdasjgfa",
                    "autor": "Jaime Rosales",
                    "nombre": "Venta de telefono",
                    "fecha": "2023-05-25",
                    "precio": 100
                }
                // Agrega más tarjetas aquí...
            ],
        };
    },
    computed: {
        filteredCards() {
            return this.cards.filter((card) =>
                card.nombre.toLowerCase().includes(this.searchTerm.toLowerCase())
            );
        },
    },
};
</script>