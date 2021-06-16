<template>
  <div class="home">
    <div class="landing bg-pale-blue">
      <div class="container overflow-hidden">
        <Navbar/>

        <div class="row h-100">
          <div class="col-12 col-md-6 d-flex flex-column justify-content-center align-items-start text-center text-md-left mb-0">
            <div class="main-title">Cari tahu informasi kampus impianmu bersama kami.</div>
            <div class="sibtitle">Dapatkan informasi seputar dunia perkuliahan secara terupdate dari kami melalui aplikasi kampus indonesia.</div>
            <button class="btn align-self-md-start align-self-center btn-primary shadow px-5 mt-5 rounded-pill">Mulai</button>
          </div>
          <div class="col-6 mb-0 d-none d-md-flex flex-column justify-content-end">
            <img src="../assets/images/girl.png" alt="" class="img-fluid">
          </div>
        </div>
      </div>
    </div>

    <div class="container">
      <div class="my-5">
        <div class="row">
          <div class="col-12 col-md-6 mb-0">
            <div class="pre-title">Introduction</div>
            <div class="title">Sepintas tentang kami</div>
            <div>Kami merupakan perusahaan di bidang informasi seputar dunia perkuliahan yang memberikan informasi secara terupdate dan dapat dipercaya sepenuhnya</div>
            <div class="jumbotron p-3 d-flex flex-wrap flex-md-nowrap justify-content-around align-items-center my-4">
              <img src="../assets/images/school 1.png" alt="">
              <div class="text-center text-md-left px-4"><div class="display-4 m-0">1045</div>Jumlah Kampus yang Terdata Saat Ini</div>
            </div>
            <div class="jumbotron p-3 d-flex flex-wrap flex-md-nowrap justify-content-around align-items-center my-4">
              <img src="../assets/images/school 2.png" alt="">
              <div class="text-center text-md-left px-4"><div class="display-4 m-0">113</div>Jumlah Kampus yang Sudah Terdaftar di Pintara</div>
            </div>
          </div>
          <div class="col-12 col-md-6 mb-0">
            <div class="h-100 py-md-4">
              <div class="jumbotron h-100 d-flex flex-column justify-content-center">
                <div class="h3"><strong>Website Untuk Mencari Informasi Seputar Kuliah 🎓</strong></div>
                <div>Dapatkan informasi seputar dunia perkuliahan secara terupdate dari kami melalui aplikasi Kampus Indonesia</div>
                <form class="mt-5">
                  <b-input-group class="mb-2">
                    <b-form-input type="search" placeholder="Cari info seputar perkuliahan / cari kampus" class="pill-start"></b-form-input>
                    <b-input-group-append is-text>
                      <b-icon icon="search"></b-icon>
                    </b-input-group-append>
                  </b-input-group>
                </form>
              </div>
            </div>
          </div>
        </div>
      </div>

      <div class="my-5">
        <div class="row">
          <div class="col-12 col-md-6 mb-0">
            <div class="pre-title">Fitur</div>
            <div class="title">Berbagai fitur yang kami tawarkan untuk mengantarkanmu menggapai kesuksesan</div>
          </div>
        </div>
        <div class="row row-flex my-3">
          <div class="col-12 col-md-4 p-3 mb-0" v-for="item in fitur" :key="item.id">
            <div class="my-card rounded d-flex flex-column justify-content-center align-items-center h-100 p-5">
              <img :src="require('../assets/images/' + item.img)" alt="">
              <div class="title text-center my-2">{{ item.title }}</div>
              <div class="subtitle">{{ item.subtitle }}</div>
              <router-link :to="item.link" class="align-self-start rounded-pill my-3 py-2 px-3">Selengkapnya &rarr;</router-link>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="bg-pale-blue">
      <div class="py-5 container">
        <div class="row">
          <div class="col-12 col-md-6">
            <div class="pre-title">Lokasi Kampus Terpopuler</div>
            <div class="title">Berikut ini adalah daftar lokasi kampus terpopuler di Indonesia</div>
          </div>
        </div>
        <div class="row row-flex my-3">
          <div class="col-6 col-md-3 p-3 mb-0" v-for="item in lokasi" :key="item.id">
            <router-link :to="item.link" class="my-card my-rounded d-flex flex-column justify-content-center align-items-center py-5" :style="{ background: 'linear-gradient( rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5) ), url(' + require('../assets/images/' + item.img) + ')', backgroundRepeat: 'no-repeat', backgroundSize: 'cover' }">
              <div class="title zoom text-center p-0">{{ item.title }}</div>
            </router-link>
          </div>
        </div>
        
        <div class="row pt-5 mt-5">
          <div class="col-12 col-md-6">
            <div class="pre-title">Rekomendasi Kampus</div>
            <div class="title">Berikut ini adalah daftar kampus terbaik yang kami rekomendasikan</div>
          </div>
        </div>
        <div class="row row-flex my-3">
          <div class="col-12 col-md-4 p-3 mb-0" v-for="item in kampus" :key="item.id">
            <div class="my-card rounded d-flex flex-column align-items-center bg-white h-100 p-2">
              <img :src="require('../assets/images/' + item.img)" alt="" class="img-fluid rounded">
              <div class="row my-2 small w-100">
                <div class="col d-flex justify-content-center align-items-center">
                  <b-icon-award-fill style="color: #ff7a36"></b-icon-award-fill>&nbsp;{{ item.status }}
                </div>
                <div class="col d-flex justify-content-center align-items-center">
                  <b-icon-star-fill style="color: #2ea674"></b-icon-star-fill>&nbsp;Akreditasi&nbsp;{{ item.akred }}
                </div>
                <div class="col d-flex justify-content-center align-items-center">
                  <b-icon-bar-chart-fill variant="primary"></b-icon-bar-chart-fill>&nbsp;{{ item.jmlProdi }}&nbsp;Prodi
                </div>
              </div>
              <div class="h4 text-center my-2">{{ item.title }}</div>
              <div class="text-center">{{ item.desc }}</div>
              <router-link :to="item.link" class="rounded-pill my-3 py-2 px-3">Selengkapnya &rarr;</router-link>
            </div>
          </div>
          <div class="d-none d-md-block col-md-4 mt-5"></div>
          <div class="col-12 col-md-4 mt-5">
            <router-link to="cari-kampus" class="btn btn-primary btn-block rounded-pill">Lihat Semua Kampus &rarr;</router-link>
          </div>
          <div class="d-none d-md-block col-md-4 mt-5"></div>
        </div>
      </div>
    </div>

    <div class="container">
      <div class="my-5">
        <div class="row">
          <div class="col-12 col-md-6 mb-0">
            <div class="pre-title">Informasi Seminar & Beasiswa</div>
            <div class="title">Berbagai informasi mengenai seminar dan beasiswa untuk memperluas pengetahuanmu</div>
          </div>
        </div>
        <b-tabs pills content-class="mt-3" align="center">
          <b-tab title="Seminar" active>
            <div class="row row-flex my-3">
              <div class="col-12 col-md-4 p-3 mb-0" v-for="item in seminar" :key="item.id">
                <div class="my-card rounded d-flex flex-column align-items-center h-100">
                  <img :src="require('../assets/images/' + item.img)" alt="" class="img-fluid rounded-top">
                  <div class="badge badge-info font-weight-light align-self-start m-3">{{ item.tipe }}</div>
                  <div class="h5 align-self-start mx-3"><strong>{{ item.title }}</strong></div>
                  <div class="align-self-start mx-3">
                    <b-icon-calendar-date></b-icon-calendar-date> {{ item.tanggal }}
                  </div>
                  <div class="align-self-start mx-3">
                    <b-icon-geo-fill></b-icon-geo-fill> {{ item.tempat }}
                  </div>
                  <router-link :to="item.link" class="rounded-pill my-3 py-2 px-3">Selengkapnya &rarr;</router-link>
                </div>
              </div>
              <div class="d-none d-md-block col-md-4 mt-5"></div>
              <div class="col-12 col-md-4 mt-3">
                <router-link to="cari-event" class="btn btn-primary btn-block rounded-pill">Lihat Semua Event &rarr;</router-link>
              </div>
              <div class="d-none d-md-block col-md-4 mt-3"></div>
            </div>
          </b-tab>
          <b-tab title="Beasiswa">
            <div class="row row-flex my-3">
              <div class="col-12 col-md-4 p-3 mb-0" v-for="item in beasiswa" :key="item.id">
                <div class="my-card rounded d-flex flex-column align-items-center h-100">
                  <img :src="require('../assets/images/' + item.img)" alt="" class="img-fluid rounded-top">
                  <div class="badge badge-success font-weight-light align-self-start m-3">{{ item.negara }}</div>
                  <div class="h5 align-self-start mx-3"><strong>{{ item.title }}</strong></div>
                  <div class="align-self-start small mx-3">
                    <b-icon-calendar-date></b-icon-calendar-date> {{ item.tglDaftar }}
                  </div>
                  <div class="align-self-start mx-3">{{ item.subtitle }}</div>
                  <router-link :to="item.link" class="rounded-pill my-3 py-2 px-3">Selengkapnya &rarr;</router-link>
                </div>
              </div>
              <div class="d-none d-md-block col-md-4 mt-5"></div>
              <div class="col-12 col-md-4 mt-3">
                <router-link to="cari-beasiswa" class="btn btn-primary btn-block rounded-pill">Lihat Semua Beasiswa &rarr;</router-link>
              </div>
              <div class="d-none d-md-block col-md-4 mt-5"></div>
            </div>
          </b-tab>
        </b-tabs>

        <div class="row">
          <div class="col-12 col-md-6 mb-0">
            <div class="pre-title">Artikel Terbaru</div>
            <div class="title">Jangan sampai terlewat informasi terbaru kampus favoritmu</div>
          </div>
          <div class="d-none d-md-block col-12">
            <VueSlickCarousel v-bind="settings">
              <div v-for="item in artikel" :key="item.id" class="p-4">
                <div class="my-card rounded d-flex flex-column align-items-center bg-white h-100 p-2">
                  <img :src="require('../assets/images/' + item.img)" alt="" class="img-fluid rounded">
                  <div class="h4 text-center my-2">{{ item.title }}</div>
                  <div class="text-center">{{ item.excerpt }}</div>
                  <router-link :to="item.link" class="rounded-pill my-3 py-2 px-3">Selengkapnya &rarr;</router-link>
                </div>
              </div>
            </VueSlickCarousel>
          </div>
          <div class="d-md-none d-block col-1"></div>
          <div class="d-md-none d-block col-10">
            <VueSlickCarousel v-bind="settings2">
              <div v-for="item in artikel" :key="item.id" class="p-3">
                <div class="my-card rounded d-flex flex-column align-items-center bg-white h-100 p-2">
                  <img :src="require('../assets/images/' + item.img)" alt="" class="img-fluid rounded">
                  <div class="h4 text-center my-2">{{ item.title }}</div>
                  <div class="text-center">{{ item.excerpt }}</div>
                  <router-link :to="item.link" class="rounded-pill my-3 py-2 px-3">Selengkapnya &rarr;</router-link>
                </div>
              </div>
            </VueSlickCarousel>
          </div>
          <div class="d-md-none d-block col-1"></div>
          <div class="d-none d-md-block col-md-4 mt-5"></div>
          <div class="col-12 col-md-4 mt-3">
            <router-link to="cari-artikel" class="btn btn-primary btn-block rounded-pill">Lihat Semua Artikel &rarr;</router-link>
          </div>
          <div class="d-none d-md-block col-md-4 mt-5"></div>
        </div>

        <hr>
        <div class="row mt-5">
          <div class="col-12 mb-0">
            <div class="main-title text-center font-weight-light px-3">Tunggu Apa Lagi? Ayo Segera Daftar Sekarang Juga!</div>
          </div>
          <div class="col-6 text-right mt-3 pl-0 pr-1">
            <a v-b-modal.modal-1 class="btn btn-light rounded-pill px-5 py-2">
              <div class="d-flex align-items-center">
                <b-icon-box-arrow-in-right class="pr-1"></b-icon-box-arrow-in-right>
                Masuk
              </div>
            </a>
          </div>
          <div class="col-6 text-left mt-3 pl-1 pr-0">
            <a v-b-modal.modal-2 class="btn btn-primary rounded-pill px-5 py-2">
              <div class="d-flex align-items-center">
                <b-icon-pencil-square class="pr-1"></b-icon-pencil-square>
                Daftar
              </div>
            </a>
          </div>
        </div>
      </div>
    </div>
    <Footer/>
  </div>
</template>

<script>
import Navbar from '@/components/Navbar.vue'
import VueSlickCarousel from 'vue-slick-carousel'
import Footer from '@/components/Footer.vue'

import 'vue-slick-carousel/dist/vue-slick-carousel.css'
import 'vue-slick-carousel/dist/vue-slick-carousel-theme.css'

export default {
  data() {
    return {
      fitur: [
        {id: 0, img:'fitur1.png', title:'Informasi Kampus', subtitle:'Lorem ipusm dolor sit amet consectur adspicin elit. Nullam ut tincidunt massa.', link:'#'},
        {id: 1, img:'fitur2.png', title:'Informasi Beasiswa', subtitle:'Lorem ipusm dolor sit amet consectur adspicin elit. Nullam ut tincidunt massa.', link:'#'},
        {id: 2, img:'fitur3.png', title:'Informasi Seminar & Workshop', subtitle:'Lorem ipusm dolor sit amet consectur adspicin elit. Nullam ut tincidunt massa.', link:'#'},
        {id: 3, img:'fitur4.png', title:'Informasi Lomba', subtitle:'Lorem ipusm dolor sit amet consectur adspicin elit. Nullam ut tincidunt massa.', link:'#'},
        {id: 4, img:'fitur5.png', title:'Informasi Lowongan', subtitle:'Lorem ipusm dolor sit amet consectur adspicin elit. Nullam ut tincidunt massa.', link:'#'},
        {id: 5, img:'fitur6.png', title:'Informasi UTBK', subtitle:'Lorem ipusm dolor sit amet consectur adspicin elit. Nullam ut tincidunt massa.', link:'#'}
      ],
      lokasi: [
        {id: 0, img:'loc1.jpg', title:'Malang', link:'#'},
        {id: 1, img:'loc2.jpg', title:'Surabaya', link:'#'},
        {id: 2, img:'loc3.jpg', title:'Semarang', link:'#'},
        {id: 3, img:'loc4.jpg', title:'Yogyakarta', link:'#'},
        {id: 4, img:'loc5.jpg', title:'Bandung', link:'#'},
        {id: 5, img:'loc6.jpg', title:'Jakarta', link:'#'},
        {id: 6, img:'loc7.jpg', title:'Medan', link:'#'},
        {id: 7, img:'loc8.jpg', title:'Bali', link:'#'}
      ],
      kampus: [
        {id: 0, img:'k-ipb.jpg', title:'Institut Pertanian Bogor', akred:'A', status:'Negeri', jmlProdi: 39, desc: 'Lorem ipusm dolor sit amet consectur adspicin elit. Nullam ut tincidunt massa.', link:'#'},
        {id: 1, img:'k-ui.jpeg', title:'Universitas Indonesia', akred:'A', status:'Negeri', jmlProdi: 64, desc: 'Lorem ipusm dolor sit amet consectur adspicin elit. Nullam ut tincidunt massa.', link:'#'},
        {id: 2, img:'k-ugm.jpg', title:'Universitas Gadjah Mada', akred:'A', status:'Negeri', jmlProdi: 90, desc: 'Lorem ipusm dolor sit amet consectur adspicin elit. Nullam ut tincidunt massa.', link:'#'},
        {id: 3, img:'k-unair.jpg', title:'Universitas Airlangga', akred:'A', status:'Negeri', jmlProdi: 44, desc: 'Lorem ipusm dolor sit amet consectur adspicin elit. Nullam ut tincidunt massa.', link:'#'},
        {id: 4, img:'k-itb.jpg', title:'Institut Teknologi Bandung', akred:'A', status:'Negeri', jmlProdi: 20, desc: 'Lorem ipusm dolor sit amet consectur adspicin elit. Nullam ut tincidunt massa.', link:'#'},
        {id: 5, img:'k-its.jpg', title:'Institut Teknologi Sepuluh Nopember', akred:'A', status:'Negeri', jmlProdi: 41, desc: 'Lorem ipusm dolor sit amet consectur adspicin elit. Nullam ut tincidunt massa.', link:'#'},
        {id: 6, img:'k-unhas.jpg', title:'Universitas Hasanuddin', akred:'A', status:'Negeri', jmlProdi: 69, desc: 'Lorem ipusm dolor sit amet consectur adspicin elit. Nullam ut tincidunt massa.', link:'#'},
        {id: 7, img:'k-ub.jpg', title:'Universitas Brawijaya', akred:'A', status:'Negeri', jmlProdi: 79, desc: 'Lorem ipusm dolor sit amet consectur adspicin elit. Nullam ut tincidunt massa.', link:'#'},
        {id: 8, img:'k-undip.jpg', title:'Universitas Diponegoro', akred:'A', status:'Negeri', jmlProdi: 52, desc: 'Lorem ipusm dolor sit amet consectur adspicin elit. Nullam ut tincidunt massa.', link:'#'}
      ],
      seminar: [
        {id: 0, img:'BannerSeminar.png', title:'Sharing About UI/UX Design', tipe: 'Seminar', tanggal: '16 September 2020', tempat: 'Zoom Meeting', link:'#'},
        {id: 1, img:'BannerSeminar.png', title:'Sharing About UI/UX Design', tipe: 'Seminar', tanggal: '16 September 2020', tempat: 'Zoom Meeting', link:'#'},
        {id: 2, img:'BannerSeminar.png', title:'Sharing About UI/UX Design', tipe: 'Seminar', tanggal: '16 September 2020', tempat: 'Zoom Meeting', link:'#'}
      ],
      beasiswa: [
        {id: 0, img:'beasiswa.jpg', title:'Mitsui Bussan', negara: 'Jepang', tglDaftar: '16 September - 16 Oktober 2020', subtitle:'Lorem ipusm dolor sit amet consectur adspicin elit. Nullam ut tincidunt massa.', link:'#'},
        {id: 1, img:'beasiswa.jpg', title:'Mitsui Bussan', negara: 'Jepang', tglDaftar: '16 September - 16 Oktober 2020', subtitle:'Lorem ipusm dolor sit amet consectur adspicin elit. Nullam ut tincidunt massa.', link:'#'},
        {id: 2, img:'beasiswa.jpg', title:'Mitsui Bussan', negara: 'Jepang', tglDaftar: '16 September - 16 Oktober 2020', subtitle:'Lorem ipusm dolor sit amet consectur adspicin elit. Nullam ut tincidunt massa.', link:'#'},
      ],
      settings: {
        "dots": true,
        "focusOnSelect": true,
        "infinite": true,
        "speed": 500,
        "slidesToShow": 3,
        "slidesToScroll": 1,
        "touchThreshold": 5
      },
      settings2: {
        "dots": true,
        "focusOnSelect": true,
        "infinite": true,
        "speed": 500,
        "slidesToShow": 1,
        "slidesToScroll": 1,
        "touchThreshold": 5
      },
      artikel: [
        {id: 0, img: 'artikel1.jpg', tanggal: '16 Juni 2021', title: '10 PTN Paling Diminati di SNMPTN 2021', excerpt: 'Lorem ipusm dolor sit amet consectur adspicin elit. Nullam ut tincidunt massa.', link: '#'},
        {id: 1, img: 'artikel2.jpg', tanggal: '16 Juni 2021', title: 'Penyebab Mahasiswa Stress Kuliah Online', excerpt: 'Lorem ipusm dolor sit amet consectur adspicin elit. Nullam ut tincidunt massa.', link: '#'},
        {id: 2, img: 'artikel3.jpg', tanggal: '16 Juni 2021', title: 'Tips Agar Bisa Fokus Ke Pendidikan', excerpt: 'Lorem ipusm dolor sit amet consectur adspicin elit. Nullam ut tincidunt massa.', link: '#'},
        {id: 3, img: 'artikel4.jpg', tanggal: '16 Juni 2021', title: '10 PTN Paling Diminati di SBMPTN 2021', excerpt: 'Lorem ipusm dolor sit amet consectur adspicin elit. Nullam ut tincidunt massa.', link: '#'},
        {id: 4, img: 'artikel5.jpg', tanggal: '16 Juni 2021', title: 'Jurusan Dengan Passing Grade Tertinggi 2021', excerpt: 'Lorem ipusm dolor sit amet consectur adspicin elit. Nullam ut tincidunt massa.', link: '#'},
      ]
    }
  },
  name: 'Home',
  components: {Navbar, VueSlickCarousel, Footer}
}
</script>

<style>
.pill-start {
  border-top-left-radius: 50rem !important;
  border-bottom-left-radius: 50rem !important;
}
.input-group-text {
  border-top-right-radius: 50rem !important;
  border-bottom-right-radius: 50rem !important;
}
</style>