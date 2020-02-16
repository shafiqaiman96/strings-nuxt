<template>
  <b-card :header="caption">
    <b-table :hover="hover" :striped="striped" :bordered="bordered" :small="small" :fixed="fixed" responsive="sm" :items="items" :date="date" :current-page="currentPage" :per-page="perPage">
      <template slot="status" slot-scope="data">
        <b-badge :variant="getBadge(data.item.status)">{{data.item.status}}</b-badge>
      </template>
    </b-table>
    <nav>
      <b-pagination :total-rows="getRowCount(items)" :per-page="perPage" v-model="currentPage" prev-text="Prev" next-text="Next" hide-goto-end-buttons/>
    </nav>
  </b-card>
</template>

<script>
  /**
   * Randomize array element order in-place.
   * Using Durstenfeld shuffle algorithm.
   */
  const shuffleArray = (array) => {
    for (let i = array.length - 1; i > 0; i--) {
      let j = Math.floor(Math.random() * (i + 1))
      let temp = array[i]
      array[i] = array[j]
      array[j] = temp
    }
    return array
  }

  export default {
    name: 'c-table',
    props: {
      caption: {
        type: String,
        default: 'Transaction History'
      },
      hover: {
        type: Boolean,
        default: false
      },
      striped: {
        type: Boolean,
        default: false
      },
      bordered: {
        type: Boolean,
        default: false
      },
      small: {
        type: Boolean,
        default: false
      },
      fixed: {
        type: Boolean,
        default: false
      }
    },
    data: () => {
      return {
        items: shuffleArray([
          {username: 'Samppa Nori', date: '2012/01/01', time: '10:32:41', status: 'Active'},
          {username: 'Estavan Lykos', date: '2012/02/01', time: '20:43:57', status: 'Banned'},
          {username: 'Chetan Mohamed', date: '2012/02/01', time: '08:16:27', status: 'Inactive'},
          {username: 'Derick Maximinus', date: '2012/03/01', time: '10:32:41', status: 'Pending'},
          {username: 'Friderik Dávid', date: '2012/01/21', time: '15:23:13', status: 'Active'},
          {username: 'Yiorgos Avraamu', date: '2012/01/01', time: '18:51:07', status: 'Active'},
          {username: 'Avram Tarasios', date: '2012/02/01', role: '08:16:27', status: 'Banned'},
          {username: 'Quintin Ed', date: '2012/02/01', time: '15:23:13', status: 'Inactive'},
          {username: 'Enéas Kwadwo', date: '2012/03/01', time: '10:32:41', status: 'Pending'},
          {username: 'Agapetus Tadeáš', date: '2012/01/21', time: '08:16:27', status: 'Active'},
          {username: 'Carwyn Fachtna', date: '2012/01/01', time: '18:51:07', status: 'Active'},
          {username: 'Nehemiah Tatius', date: '2012/02/01', time: '10:32:41', status: 'Banned'},
          {username: 'Ebbe Gemariah', date: '2012/02/01', time: '18:51:07', status: 'Inactive'},
          {username: 'Eustorgios Amulius', date: '2012/03/01', time: '08:16:27', status: 'Pending'},
          {username: 'Leopold Gáspár', date: '2012/01/21', time: '15:23:13', status: 'Active'},
          {username: 'Pompeius René', date: '2012/01/01', time: '08:16:27', status: 'Active'},
          {username: 'Paĉjo Jadon', date: '2012/02/01', time: '10:32:41', status: 'Banned'},
          {username: 'Micheal Mercurius', date: '2012/02/01', time: '18:51:07', status: 'Inactive'},
          {username: 'Ganesha Dubhghall', date: '2012/03/01', role: '20:43:57', status: 'Pending'},
          {username: 'Hiroto Šimun', date: '2012/01/21', time: '15:23:13', status: 'Active'},
          {username: 'Vishnu Serghei', date: '2012/01/01', time: '10:32:41', status: 'Active'},
          {username: 'Zbyněk Phoibos', date: '2012/02/01', time: '20:43:57', status: 'Banned'},
          {username: 'Einar Randall', date: '2012/02/01', time: '18:51:07', status: 'Inactive'},
          {username: 'Félix Troels', date: '2012/03/21', time: '15:23:13', status: 'Active'},
          {username: 'Aulus Agmundr', date: '2012/01/01', time: '20:43:57', status: 'Pending'}
        ]),
        fields: [
          {key: 'username'},
          {key: 'date'},
          {key: 'time'},
          {key: 'status'}
        ],
        currentPage: 1,
        perPage: 5,
        totalRows: 0
      }
    },
    methods: {
      getBadge (status) {
        return status === 'Active' ? 'success'
          : status === 'Inactive' ? 'secondary'
            : status === 'Pending' ? 'warning'
              : status === 'Banned' ? 'danger' : 'primary'
      },
      getRowCount (items) {
        return items.length
      }
    }
  }
</script>
