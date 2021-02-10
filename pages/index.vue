<template>
  <div>
    <title-stisla title="JUDUL HALAMAN"></title-stisla>
    <div class="row">
      <input-text val="Han" name="username"></input-text>
      <input-text val="Terusan Menang" name="address"></input-text>
      <input-text val="0813xxxxxxx" name="phone"></input-text>

      <div class="col-12">
        <label for="inputEmail">Email address</label>
        <input type="email" class="form-control" id="inputEmail" v-model="inputEmail" placeholder="name@example.com">
        <p>{{inputEmail}}</p>
      </div>

      <div class="col-12">
        <label for="inputEmail">Description</label>
        <textarea name="description" class="form-control" cols="30" rows="10" v-model="description" />
        <p>{{description}}</p>
      </div>
    </div>

    <div class="col-12">
      <label for="inputSelect">Faculty</label>
      <select class="form-control" id="inputSelect" v-model="inputSelect">
        <option value = "Matematika">Matematika</option>
        <option value = "Ilmu Komputer">Ilmu Komputer</option>
        <option value = "Ekonomi">Ekonomi</option>
      </select>
      <p>{{inputSelect}}</p>
    </div>

    <div class="col-12">
      <label for="inputSelect">Faculty</label>
      <select class="form-control" id="inputSelect" v-model="inputSelectVFor">
        <option v-for="(item, index) in faculty" :key="index" :value = item>
          {{index + " -- " + item}}
        </option>
      </select>
      <p>{{inputSelectVFor}}</p>
    </div>

    <div class="col-12">
      <label for="inputSelect">University</label>
      <select class="form-control" id="inputSelect" v-model="inputUniversity">
        <option v-for="item in university" :key="item.id" :value = item.id>
          {{item.name}}
        </option>
      </select>
      <p>{{inputUniversity}}</p>
    </div>

    <div class="row">
      <div class="col-6">
        <h4 v-if="inputUniversity==0">Aku kuliah di UNSRI</h4>
        <h4 v-else-if="inputUniversity==1">Aku kuliah di UI</h4>
        <h4 v-else-if="inputUniversity==2">Aku kuliah di UGM</h4>
        <h4 v-else>Belum dipilih</h4>
      </div>

      <div class="col-6">
        <h4 v-show="inputUniversity==0">Aku kuliah di UNSRI</h4>
        <h4 v-show="inputUniversity==1">Aku kuliah di UI</h4>
        <h4 v-show="inputUniversity==2">Aku kuliah di UGM</h4>
        <h4 v-show="inputUniversity=='Belum'">Belum dipilih</h4>
      </div>
    </div>
    
  
    <div class="d-flex justify-content-center vh-100">
      <div class="d-flex align-items-center">
        {{title}} <br> {{student.name}} <br> {{faculty[0]}}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  asyncData() {
    return {
      title: 'TITLE ADMIN',
      description: 'lorem ipsum',
      student: {
        name: 'Ramadhan Pratama',
        faculty: 'Matematika'
      }
    }
  },
  data() {
    return {
      inputEmail: '',
      inputSelect: 'Matematika',
      inputSelectVFor: 'Matematika',
      inputUniversity: 'Belum',
      faculty: ['Matematika', 'Ilmu Komputer', 'Ekonomi'],
      university: [{id: 0, name: 'Unsri'}, {id: 1, name: 'UI'}, {id: 2, name: 'UGM'}]
    }
  }
  }
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family:
    'Quicksand',
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
