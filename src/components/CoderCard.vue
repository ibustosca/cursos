<template>
  <div class="div--container">
    <table v-for="article in articles" :key="article.id">
      <tr>
        <th class="table--tr" colspan="2">{{ article.name }}</th>
      </tr>
      <tr>
        <td colspan="2" class="table--tr">
          <img :src="article.image" alt="article image">
        </td>
      </tr>
      <tr>
        <th>Código</th>
        <td>: {{ article.id }}</td>
      </tr>
      <tr>
        <th>Nivel</th>
        <td>: {{ article.level }}</td>
      </tr>
      <tr>
        <th>Precio</th>
        <td>: ${{ article.price }}</td>
      </tr>
        <tr>
          <td colspan="2" class="table--tr">
            <CoderButton :label="discount" :price="article.price" />
          </td>
        </tr>
      <tr v-show="discountMessage">
        <td colspan="2"
          class="table--td"
          v-if="article.price > 600"
          :style="{ color: discountColor }">
          Con descuento!
        </td>
        <td colspan="2"
          class="table--td"
          v-else
          :style="{ color: reducedColor }">
          Precio rebajado
        </td>
      </tr>
    </table>
  </div>
</template>

<script>
import CoderButton from '@/components/CoderButton.vue';

export default {
  name: 'CoderCard',
  components: {
    CoderButton,
  },
  data() {
    return {
      discountMessage: true,
      discountColor: 'red',
      reducedColor: 'blue',
      discount: 'Buy with discount',
      articles: [
        {
          id: 1,
          name: 'Vue.js',
          image: 'https://drive.google.com/uc?export=view&id=1uRgHxHW1PCuTRuxFvbFwlPSBAyd0Mjmd',
          level: 'Básico',
          price: 500,
        },
        {
          id: 2,
          name: 'React',
          image: 'https://drive.google.com/uc?export=view&id=1fcCR_U8QwNLFEYhM_YBbxOiBkd6bJAiR',
          level: 'Avanzado',
          price: 1000,
        },
        {
          id: 3,
          name: 'Angular',
          image: 'https://drive.google.com/uc?export=view&id=1SD4QU5vkKVvN4Du4V1WD6w_m3NJ-H8vC',
          level: 'Intermedio',
          price: 700,
        },
        {
          id: 4,
          name: 'JavaScript',
          image: 'https://drive.google.com/uc?export=view&id=1U_pgr2S8MBXeUzkBiMU9x0ZaQ9cGzCDj',
          level: 'Avanzado',
          price: 1000,
        },
        {
          id: 5,
          name: 'Node.js',
          image: 'https://drive.google.com/uc?export=view&id=12CNE4wc9ENxtD_QQ5PumDu_6u1-bEW-7',
          level: 'Avanzado',
          price: 1000,
        },
        {
          id: 6,
          name: 'Nest.js',
          image: 'https://drive.google.com/uc?export=view&id=1N4BT8Lenb-GkV4Calz4GyCLVrYv9vV9I',
          level: 'Básico',
          price: 500,
        },
      ],
    };
  },
};
</script>

<style scoped>
.div--container {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  gap: 10px;
  width: 100%;
  padding-top: 20px;
}
img {
  width: 100px;
  height: 100px;
  padding: 10px 0px 10px 0px;
}
table {
  width: 220px;
  margin: auto;
  padding: 25px;
  margin-bottom: 20px;
  border-radius: 15px;
  box-shadow: 2px 2px 10px rgb(142, 142, 142);
  transition: 0.3s;
  color: #2c3e50;
  text-align: left;
}
table:hover {
  transform: scale(1.05);
}
th {
  text-align: left;
  font-size: 16px;
  padding-left: 10px;
}
.table--tr {
  color: #555555;
  text-align: center;
  font-size: 2.1rem;
}
.table--td {
  padding-top: 10px;
  color: #555555;
  text-align: center;
  font-size: 16px;
}
</style>
