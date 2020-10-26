  <template>
  <div>
    <table class="table">
                <thead>
                    <tr class="trHeader">
                      <th>
                        Gender
                      </th>
                      <th>
                        Name
                      </th>
                      <th>
                        City
                      </th>
                    </tr>
                </thead>
                <tbody>
                  <tr class="row" v-for="(value, key) in contact" :key="key">
                    <td>{{value.gender}}</td>
                    <td>{{value.name.first}}</td>
                    <td>{{value.location.city}}</td>
                  </tr>
                </tbody>
    </table>
     
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      contact: null
    };
  },
  created: function() {
    axios
      .get("https://randomuser.me/api/?results=20")
      .then(res => {
        this.contact = res.data.results;
      });
  }
};
</script>
<style lang="scss">
.container-table {
    overflow-x: auto;
    max-width: 100%;
}
.table {
    width: auto;
    border-collapse: collapse;
    background: white;
    border-radius: 10px;
    width: 100%;
    min-width: 900px;
    margin: 0 auto;
    position: relative;

    .trHeader{
      th{
        text-align: center;
      }
    }

    thead {
        background-color: #ccc;
    }
    .row {
    color: #808080;
    height: 50px;
    border-bottom: 1px solid #ccc;

    td {
        text-align: center;
    }
}
.row:nth-child(odd) {
    background-color: #f5f5f5;
}
}

@media (min-width: 768px) {
    .table {
        width: 100%;
        overflow-x: hidden;
        .trHeader {
            height: 60px;
        }
    }
}
</style>