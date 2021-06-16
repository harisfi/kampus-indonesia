<template>
  <div>
    <b-navbar toggleable="lg" type="light">
      <b-navbar-brand to="/">
        <img src="../assets/images/logo-kampus-indonesia.png" alt="" />
      </b-navbar-brand>

      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav class="m-auto text-center">
          <b-nav-item to="/" class="active">Beranda</b-nav-item>
          <b-nav-item-dropdown text="Fitur">
            <b-dropdown-item to="cari-kampus">Cari Kampus/Prodi</b-dropdown-item>
            <b-dropdown-item to="cari-event">Cari Event</b-dropdown-item>
            <b-dropdown-item to="cari-beasiswa">Cari Beasiswa</b-dropdown-item>
            <b-dropdown-item to="cari-magang">Cari Magang</b-dropdown-item>
            <b-dropdown-item to="cari-artikel">Cari Artikel</b-dropdown-item>
          </b-nav-item-dropdown>
          <b-nav-item to="blog">Blog</b-nav-item>
          <b-nav-item to="tentang">Tentang Kami</b-nav-item>
          <b-nav-item to="kontak">Hubungi Kami</b-nav-item>
        </b-navbar-nav>

        <!-- Right aligned nav items -->
        <b-navbar-nav class="ml-auto text-center">
          <div class="mb-2 mb-md-0">
            <b-button v-b-modal.modal-1 pill class="px-4 py-2" variant="light">
              <div class="d-flex align-items-center">
                <b-icon-box-arrow-in-right class="pr-1"></b-icon-box-arrow-in-right>
                Masuk
              </div>
            </b-button>
            <b-modal id="modal-1" size="lg" title="Selamat Datang Kembali!" hide-footer no-stacking>
              <div>Belum punya akun? <b-button v-b-modal.modal-2 variant="link">Klik disini untuk daftar</b-button></div>
              <div class="row my-3 mx-0">
                <div class="col-12 col-md-6 pl-md-0 pr-md-2 mb-2">
                  <a href="#" class="btn btn-light btn-block border-primary"><img src="../assets/images/google-logo.png" alt="google" height="24" width="24"> Masuk dengan Google</a>
                </div>
                <div class="col-12 col-md-6 pl-md-2 pr-md-0 mb-2">
                  <a href="#" class="btn btn-light btn-block border-primary"><img src="../assets/images/facebook-logo.png" alt="facebook" height="24" width="24"> Masuk dengan Facebook</a>
                </div>
              </div>
              <p class="text-primary text-center font-weight-bold">Atau</p>
              <form>
                <input class="form-control my-1" type="email" name="email" placeholder="Alamat Email" required>
                <input class="form-control my-1" type="pass" name="pass" placeholder="Password" required>
                <div class="d-flex flex-column flex-md-row justify-content-between my-2 mx-1">
                  <div class="form-group form-check">
                    <input type="checkbox" class="form-check-input" name="tetap_masuk" id="tetap_masuk">
                    <label class="form-check-label" for="tetap_masuk">Biarkan saya tetap masuk</label>
                  </div>
                  <a href="#">Lupa Password?</a>
                </div>
                <button class="form-control btn btn-primary my-3" type="submit">Masuk</button>
              </form>
            </b-modal>
          </div>
          <div class="ml-md-3">
            <b-button v-b-modal.modal-2 pill class="px-4 py-2" variant="primary">
              <div class="d-flex align-items-center">
                <b-icon-pencil-square class="pr-1"></b-icon-pencil-square>
                Daftar
              </div>
            </b-button>
            <b-modal id="modal-2" size="lg" title="Daftar Sekarang" hide-footer no-stacking>
              <div>Sudah punya akun? <b-button v-b-modal.modal-1 variant="link">Klik disini untuk masuk</b-button></div>
              <p class="font-weight-bold">Daftar sekarang juga agar dapat informasi - informasi seputar kampus favorit anda.</p>
              <form>
                <input class="form-control my-1" type="email" name="email" placeholder="Alamat Email" required>
                <input class="form-control my-1" type="pass" name="pass" placeholder="Password" required>
                <input class="form-control my-1" type="verify_pass" name="verify_pass" placeholder="Ketik Ulang Password" required>
                <div class="form-group form-check">
                  <input type="checkbox" class="form-check-input" name="tetap_masuk" id="tetap_masuk" required>
                  <label class="form-check-label small" for="tetap_masuk">Dengan membuat akun, Anda telah menyetujui Syarat dan Ketentuan yang berlaku</label>
                </div>
                <button class="form-control btn btn-primary my-3" type="submit">Buat Akun</button>
              </form>
            </b-modal>
          </div>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
  </div>
</template>

<script>
export default {
  name: "Navbar",
};
</script>