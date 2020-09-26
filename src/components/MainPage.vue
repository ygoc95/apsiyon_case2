<template>
 <div>
   <!--Üst Menu-->
   <!-- Üst menü Marka adı, toggleable değil, mobil ekranlarda da görünmesi için-->
  <b-navbar toggleable="lg">
    <b-navbar-brand class="ml-5" href="#">Yiğit Kombi</b-navbar-brand>
    <!-- Küçük ekranlarda "nav-collapse" elementini kapsayacak menü ikonu -->
    <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
    <!-- Üst Menü elementleri -->
    <b-collapse id="nav-collapse" is-nav>      
      <b-navbar-nav class="ml-5">
         <b-navbar-item class="mr-3">
           <a href="#duyurular">Duyurular</a>
         </b-navbar-item>
         <b-navbar-item class="mr-5">
           <a href="#iletisim">İletişim</a>
         </b-navbar-item>
      </b-navbar-nav>
    </b-collapse>
  </b-navbar>
  <!--SAYFA İÇERİĞİ-->
  <div class="container">
    <div class=" mt-3">
      <b-jumbotron header="Kaliteli kombi artık lüks değil!" lead="Ev veya iş yeri için modern havalandırma çözümleri">
        <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Dolorum est autem cum incidunt dicta tempora architecto natus laborum, assumenda qui eum voluptas quam ad in quos dignissimos itaque quasi accusantium.</p>
        <b-button href="#">Göz At</b-button>
      </b-jumbotron>
    </div>
    <!-- DUYURULAR BOLUMU -->
    <div class="duyurular" id="duyurular">
      <h2 class="mb-4">Duyurular</h2>
        <b-card-group deck>
         <b-card title="Duyuru 1" :img-src="require('../assets/images/klima1.png')" img-alt="Image" img-top>
            <b-card-text>
              Lorem, ipsum dolor sit amet consectetur adipisicing elit. Placeat, quibusdam, perspiciatis, quasi accusantium sunt quo blanditiis fuga explicabo molestias ratione architecto consectetur est reprehenderit optio? Quia quo velit quam corporis!            </b-card-text>
            <b-button>Devamını gör</b-button>
          </b-card>

          <b-card title="Duyuru 2" :img-src="require('../assets/images/klima2.png')" img-alt="Image" img-top>
            <b-card-text>
              Lorem ipsum dolor sit amet consectetur, adipisicing elit. Possimus iure perspiciatis, eius deleniti, illum quos sit ipsam quidem tenetur maxime laboriosam nam sed nulla atque voluptatem quaerat quo tempore repudiandae?
            </b-card-text>
            <b-button>Devamını gör</b-button>
          </b-card>

           <b-card title="Duyuru 3" :img-src="require('../assets/images/klima3.png')" img-alt="Image" img-top>
            <b-card-text>
              Lorem ipsum dolor sit, amet consectetur adipisicing elit. Eos rem, labore magnam cupiditate atque magni ipsa odit, mollitia impedit nulla iusto necessitatibus ab minima debitis beatae assumenda aliquam obcaecati. Soluta.
            </b-card-text>
            <b-button>Devamını gör</b-button>
          </b-card>
        </b-card-group>
    </div>

    <!--ILETISIM FORMU-->
    <div class="iletisim mt-4" id="iletisim">
       <h2 class="mb-4">İletişim</h2>
      <b-form>
          <b-form-group 
          id="name-input-group" 
          label="İsminiz:" 
          label-for="name-input">
          <b-form-input
            id="name-input"
            type="text"
            required
          ></b-form-input>
        </b-form-group>
        <b-form-group
          id="email-input-group"
          label="Email adresiniz:"
          label-for="email-input"        >
          <b-form-input
            id="email-input"
            type="email"
            required
          ></b-form-input>
        </b-form-group>
        <b-form-group
          id="note-input-group"
          label="Notunuz:"
          label-for="note-input"        >
          <b-form-input
            id="note-input"
            type="text"
            required
          ></b-form-input>
        </b-form-group>
         <b-form-group
          v-if="show_kurumsal_input"
          id="kurumsal-input-group"
          label="Şirket adı:"
          label-for="kurumsal-input"        >
          <b-form-input
            id="kurumsal-input"
            required
          ></b-form-input>
        </b-form-group>
        <b-form-group>
          <b-form-checkbox-group>
            <b-form-checkbox @change="kurumsalchecked($event)" value="me">Kurumsal temsilciyim.</b-form-checkbox>
          </b-form-checkbox-group>
        </b-form-group>
        <b-button>Gönder</b-button>
    </b-form>
    </div>
     <!--ALT MENU-->
    <footer class=" alt-menu mt-4 mb-4">
      <b-row cols="1">
        <b-col>
          <a href="#duyurular">Duyurular</a>
          <a href="#iletisim">Bize Ulaşın</a>
          <a href="">SSS</a>
          <a href="">Kişisel Verilerin Korunması</a>
        </b-col>
      </b-row>
    </footer>
  </div>
</div>
</template>

<script>
export default {
  name: 'MainPage',
  
  data() {
      return {
        slide: 0,
        sliding: null,
        show_kurumsal_input:false
      }
    },
  
  methods: {
      onSlideStart() {
        this.sliding = true
      },
      onSlideEnd() {
        this.sliding = false
      },
      kurumsalchecked(){
        this.show_kurumsal_input=!this.show_kurumsal_input;
      }
      
    }
}
</script>

<style>
.alt-menu{
  width: 100%;
  text-align: center;
}
.duyurular{
  padding: 20px;
}
.iletisim{
  background-color: black;
  border-radius: 0.5rem;
  padding: 30px;
  color: white;
}
.jumbotron {
  background-color: black !important;
  color: white;
  background-size: cover;
}
.btn-secondary{
  background-color: black !important;
}
.btn-secondary:hover{
  background-color: white !important;
  color: black !important;

}
.navbar-brand{
    color:black !important;
    font-family:'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif
}
b-navbar{
  background-color: white !important;
}
b-navbar-item a{
  padding: 10px;
  border-radius:0.5rem;
  color: black;
}
b-navbar-item :hover{
  text-decoration: none;
  background-color: black;

}
b-navbar-item a:hover{
  text-decoration: none;
  color: white;
}
@media screen and (max-width: 992px) {
  b-navbar-item{
    margin-top:15px;
    margin-bottom: 5px;
  }
}

footer a{
  margin:10px;
  color: black;
}
</style>
