<template>
    <div class="contacts">
        <table>
            <tr>
                <th>имя</th>
                <th>контакты</th>
                <th>фото точки</th>
            </tr>
            <tr v-for="item in catalog" :key="item.id">
                <td>{{item.name}}</td>
                <td>
                    <p><strong>Phone:</strong></p>
                    <p v-for="phone in item.contacts.phone" :key="phone">{{ phone }}</p>
                    
                    <p><strong>WhatsApp:</strong></p>
                    <p v-for="whatsapp in item.contacts.whatsapp" :key="whatsapp">{{ whatsapp }}</p>
                    
                    <p><strong>Telegram:</strong></p>
                    <p v-for="telegram in item.contacts.telegram" :key="telegram">{{ telegram }}</p>
                </td>
                <th><img :src="item.image"></th>
            </tr>
        </table>
    </div>
</template>

<script>

export default {
    name: "ContactsSeller",
    data:() => {
      return {
          catalog: [
            {id:1, name: 'пользователь 1', contacts: {phone: ['+7(999)999-99-99', '+7(999)999-99-99'], whatsapp: ['+7(999)999-99-99', '+7(999)999-99-99'], telegram: ['+7(999)999-99-99', '+7(999)999-99-99']}, image: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTidJg8UJ4145gajC0mJa6zi83nKnTeKj6Tqw&s'}, 
            {id:2, name: 'пользователь 2', contacts: {phone: ['+7(999)999-99-99', '+7(999)999-99-99'], whatsapp: ['+7(999)999-99-99', '+7(999)999-99-99'], telegram: ['+7(999)999-99-99', '+7(999)999-99-99']}, image: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTidJg8UJ4145gajC0mJa6zi83nKnTeKj6Tqw&s'}, 
            {id:3, name: 'пользователь 3', contacts: {phone: ['+7(999)999-99-99', '+7(999)999-99-99'], whatsapp: ['+7(999)999-99-99', '+7(999)999-99-99'], telegram: ['+7(999)999-99-99', '+7(999)999-99-99']}, image: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTidJg8UJ4145gajC0mJa6zi83nKnTeKj6Tqw&s'}, 
            {id:4, name: 'пользователь 4', contacts: {phone: ['+7(999)999-99-99', '+7(999)999-99-99'], whatsapp: ['+7(999)999-99-99', '+7(999)999-99-99'], telegram: ['+7(999)999-99-99', '+7(999)999-99-99']}, image: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTidJg8UJ4145gajC0mJa6zi83nKnTeKj6Tqw&s'}, 
            {id:5, name: 'пользователь 5', contacts: {phone: ['+7(999)999-99-99', '+7(999)999-99-99'], whatsapp: ['+7(999)999-99-99', '+7(999)999-99-99'], telegram: ['+7(999)999-99-99', '+7(999)999-99-99']}, image: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTidJg8UJ4145gajC0mJa6zi83nKnTeKj6Tqw&s'}, 
      ]
      }
  },
}

</script>

<style scoped>
/* Основной стиль таблицы */
table {
  width: 100%;
  border-collapse: collapse;
  margin-bottom: 20px;
  font-family: Arial, sans-serif;
}

/* Заголовок таблицы */
th {
  background-color: #f4f4f4;
  text-align: left;
  padding: 12px;
  font-weight: bold;
  font-size: 16px;
}

/* Ячейки таблицы */
td {
  padding: 12px;
  border-bottom: 1px solid #ddd;
  vertical-align: top;
}

/* Стиль для изображений */
td img {
  max-width: 100px;
  height: auto;
  border-radius: 5px;
}

/* Чередование фона для строк */
tr:nth-child(even) {
  background-color: #f9f9f9;
}

/* Адаптивный дизайн для мобильных устройств */
@media (max-width: 768px) {
  table, th, td {
    display: block;
    width: 100%;
  }

  /* Заголовки скрыты на мобильных устройствах */
  th {
    display: none;
  }

  /* Ячейки выглядят как блоки с отступами */
  td {
    display: block;
    text-align: right;
    padding-left: 50%;
    position: relative;
  }

  td::before {
    content: attr(data-label); /* Добавляем псевдоэлемент с названием поля */
    position: absolute;
    left: 15px;
    width: 45%;
    white-space: nowrap;
    text-align: left;
    font-weight: bold;
  }

  /* Стиль для изображений на мобильных устройствах */
  td img {
    max-width: 150px;
    margin-bottom: 10px;
  }
}
</style>
