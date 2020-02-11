<template>
  <div id="tampilanList">
      <div class="judulTabel">
          <h2>Daftar List Tugas</h2>
      </div>
      <br>
      <div class="btnTambah">
          <div class="container">
          <button class="btn btn-success" mt-5 mb-5 @click="tambahkan">Tambahkan Tugas</button>

      </div>

    <div class="inputan">
        <div class="card mb-3" v-for="(datas,index) in allData" :key="index">
          <div class="card-body">
              <span class="float-right" style="cursor: pointer">
                  <button class="btn btn-danger" @click="hapus(index)">hapus</button>
              </span>

              <h4 class="card-title">Tugas ke-{{index+1}}</h4>

              <div class="employee-form">
                  <input type="text" class="form-control mb-2" placeholder="Nama Tugas" v-model="datas.namaTugas"><br><br>
                  <input type="text" class="form-control mb-2" placeholder="Mata Kuliah" v-model="datas.mataKuliah"><br><br>
                  <input type="date" class="form-control mb-2" placeholder="Deadline" v-model="datas.deadline"><hr>
                  <textarea class="form-control" cols="30" rows="10" placeholder="Deskripsi" v-model="datas.deskripsi"></textarea>
              </div>
              <br>
              <p>
                    <a class="btn btn-primary" data-toggle="collapse" href="#collapseExample" role="button" aria-expanded="false" aria-controls="collapseExample">
                        Detail
                    </a>
                    </p>

                        <div class="collapse" id="collapseExample">
                    <div class="card card-body">
                        <h2>Detail Tugas ke-{{index+1}}</h2>
                        <hr>
                        <div class="detail">
                        <h4>Nama Tugas  : {{datas.namaTugas}}</h4>
                        <h4>Mata Kuliah : {{datas.mataKuliah}}</h4>
                        <h4>Deadline    : {{datas.deadline}}</h4>
                        <h4>Deskripsi   : {{datas.deskripsi}}</h4>
                        </div>
                    </div>
                    </div>
          </div>
      </div>
    </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'tampilanList',
  components: {

  },
  data () {
    return {
      allData: [
        {
          namaTugas: '',
          mataKuliah: '',
          deadline: '',
          deskripsi: ''
        }
      ]
    }
  },
  methods: {
    tambahkan () {
      this.allData.push({
        namaTugas: '',
        mataKuliah: '',
        deadline: '',
        deskripsi: ''
      })
    },
    hapus (index) {
      this.allData.splice(index, 1)
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center ;
  color: #2c3e50;
}
.inputan{
    text-align: center;
    margin-left: 100px;
    margin-right: 100px;
    margin-top: 30px;
    background-color: whitesmoke;
}
.judulTabel{
    color: black;
    border-style: solid;
    border-color: black;
    padding-top: 10px;
    align-content: center;

}
div.btnTambah{
    position: -webkit-sticky;
  position: sticky;
  top: 0;
  padding: 5px;
  background-color: #f5f12d;
  border: 2px solid rgb(12, 12, 9);
}
.detail{
    text-align: left;
    background: rgb(88, 78, 175);
    padding: 10px;
}
</style>
