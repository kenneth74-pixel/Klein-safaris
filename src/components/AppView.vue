<!-- eslint-disable vue/multi-word-component-names -->
<script >
import M from 'materialize-css';
import axios from 'axios';
export default {
  name: 'Home',
  created() {
    document.addEventListener('DOMContentLoaded', function () {
      // Side Menu
      const sideNav = document.querySelector('.sidenav');
      M.Sidenav.init(sideNav, {});

      // Slider
      const slider = document.querySelector('.slider');
      M.Slider.init(slider, {
        indicators: false,
        height: 900,
        transition: 500,
        interval: 7000
      });

      // Scrollspy
      const ss = document.querySelectorAll('.scrollspy');
      M.ScrollSpy.init(ss, {});

      // Material Boxed
      const mb = document.querySelectorAll('.materialboxed');
      M.Materialbox.init(mb, {});
    });
  },
  methods:{
    sendMessage(){
        const sendEmail = {
          email:this.email,
          name:this.name,
          contact:this.contact,
          message: this.message
        }

        axios
        .post('http://localhost:9002/api/v1/communication/email',sendEmail)
        .then(response => {
          console.log(response.data);
          M.toast({html: 'Message sent successfully ',classes: 'success'});
        })
        .catch(e => {
          console.log(e);
        });
    }
  }
}
</script>

<template>
  <div class="navbar-fixed">
    <nav class="teal">
      <!-- <div class="container"> -->
      <div class="nav-wrapper">
          <img class="logo" src="./images/kleinsf.jpg">
        <a href="#!" class="brand-logo p-3">Klein Safaris</a>
        <a href="#" data-target="mobile-demo" class="sidenav-trigger"><i class="material-icons">menu</i></a>
        <ul class="right hide-on-med-and-down">
          <li>
            <a href="#home">Home</a>
          </li>
          <li>
            <a href="#popular">Popular Places</a>
          </li>
          <li>
            <a href="#gallery">Gallery</a>
          </li>
          <li>
            <a href="#contact">Contact</a>
          </li>
        </ul>
      </div>
      <!-- </div> -->
    </nav>
  </div>
  <ul class="sidenav teal" id="mobile-demo" >
    <li>
      <a href="#home">Home</a>
    </li>
    <li>
      <a href="#popular">Popular Places</a>
    </li>
    <li>
      <a href="#gallery">Gallery</a>
    </li>
    <li>
      <a href="#contact">Contact</a>
    </li>
  </ul>

  <!-- Section: Slider -->
  <section class="slider ">
    <ul class="slides">
      <li>
        <img src="./images/gunya.jpg" alt="">
        <div class="caption center-align">
          <h2>Take Your Dream Vacation</h2>
          <h5 class="dark grey-text text-lighten-3 hide-on-small-only">Your dream vacation starts here, Explore excitig
            places and game park in Uganda!</h5>
          <a href="#contact" class="btn btn-large grey darken-3">
            <i class="material-icons left">send</i> Contact For Booking
          </a>
        </div>
      </li>
      <li>
        <img src="./images/tourist1.jpg" alt="">
        <div class="caption center-align">
          <h2>We Work With All Budgets</h2>
          <h5 class="dark grey-text text-lighten-3 hide-on-small-only">Our packages are tailored to fit all budgets !</h5>
          <a href="#contact" class="btn btn-large grey darken-3">
            <i class="material-icons left">send</i> Contact For Booking
          </a>
        </div>
      </li>
      <li>
        <img src="./images/tourists.jpg" alt="">
        <div class="caption center-align">
          <h2>Group & Individual Getaways</h2>
          <h5 class="dark grey-text text-lighten-3 hide-on-small-only">Our services caters for all, we give quality
            services for group and individual vacation!</h5>
          <a href="#contact" class="btn btn-large grey darken-3">
            <i class="material-icons left">send</i> Contact For Booking
          </a>
        </div>
      </li>
    </ul>
  </section>

  <!-- Section: Icon Boxes -->
  <section class="section section-icons grey lighten-4 center">
    <div class=" box">
      <div class="row">
        <div class="col s12 m4">
          <div class="card-panel">
            <i class="material-icons large teal-text">star</i>
            <h5>PERSONALIZED APPROACH OF DEALING WITH GUESTS</h5>
            <p>
              We offer exclusive custom made tour packages that take into consideration the needs of guests. Loremi Tours
              also has a team of young, friendly and enthusiastic staff that are very supportive.
            </p>
          </div>
        </div>
        <div class="col s12 m4">
          <div class="card-panel">
            <i class="material-icons large teal-text">thumb_up</i>
            <h5>BENEFITING LOCAL COMMUNITIES DIRECTLY</h5>
            <p>
              We offer local interactive experiences that are developed with the community, train community members to be
              guides and ensure fair pay for the participants. 
            </p>
          </div>
        </div>
        <div class="col s12 m4">
          <div class="card-panel">
            <i class="material-icons large teal-text">diversity_1</i>
            <h5>GREAT CUSTOMER CARE SERVICE</h5>
            <p>
              We support guests in recommending experiences, decision making and answering questions. We have a supportive
              an professional team of staff to guide you when planning and conducting trips with us.
            </p>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Section: Popular -->
  <div id="popular" class="section section-popular scrollspy">
    <!-- <div class="container"> -->
    <div class="row">
      <h4 class="center">
        <span class="teal-text">Popular</span> Places
      </h4>
      <div class="col s12 m3">
        <div class="card">
          <div class="card-image">
            <img src="./images/gunya.jpg" alt="">
            <span class="card-title">
              <p class="flow-text">Bwindi & Mgahinga</p>
            </span>
          </div>
          <div class="card-content">
            <p>
              The Bwindi Impenetrable Forest is a large primeval forest located in south-western Uganda
            </p>
          </div>
        </div>
      </div>
      <div class="col s12 m3">
        <div class="card">
          <div class="card-image">
            <img src="./images/gallery/murchison.jpg" alt="">
            <span class="card-title">
              <p class="flow-text">The Murchison Fall</p>
            </span>
          </div>
          <div class="card-content">
            <p>
              The Murchison Falls National Park is popularly known for having the world’s most powerful waterfall that
              causes the place to tremble
            </p>
          </div>
        </div>
      </div>
      <div class="col s12 m3">
        <div class="card">
          <div class="card-image">
            <img src="./images/gallery/kidepo.jpg" alt="">
            <span class="card-title">
              <p class="flow-text">Kidepo Valley National Park</p>
            </span>
          </div>
          <div class="card-content">
            <p>
              Kidepo Valley National Park lies in the rugged, semi arid valleys between Uganda’s borders with south Sudan
              in the north west .
            </p>
          </div>
        </div>
      </div>

      <div class="col s12 m3">
        <div class="card">
          <div class="card-image">
            <img src="./images/gallery/wellSpring.jpg" alt="">
            <span class="card-title">
              <p class="flow-text">Semuliki & Sempaya</p>
            </span>
          </div>
          <div class="card-content">
            <p>
              Semuliki National Park sprawls across the floor of the Semuliki Valley on the remote, western side of the
              Rwenzori.
            </p>
          </div>
        </div>
      </div>

      <div class="col s12 m3">
        <div class="card">
          <div class="card-image">
            <img src="./images/gallery/jinja.jpg" alt="">
            <span class="card-title">
              <p class="flow-text">Jinja</p>
            </span>
          </div>
          <div class="card-content">
            <p>
              Jinja is popularly known as the adventure for her long list of andrenaline activities like white water
              rafting,kayaking, bungee jumping,tubing etc.
            </p>
          </div>
        </div>
      </div>

      <div class="col s12 m3">
        <div class="card">
          <div class="card-image">
            <img src="./images/gallery/queen-elizabeth.jpg" alt="">
            <span class="card-title ">
              <p class="flow-text">Queen Elizabeth</p>
            </span>
          </div>
          <div class="card-content">
            <p>
              This is the most popular safari itinerary for those with limited time and it will give you a full day of
              adventure with game drives and a boat ride.
            </p>
          </div>
        </div>
      </div>

      <div class="col s12 m3">
        <div class="card">
          <div class="card-image">
            <img src="./images/gallery/elgon.jpg" alt="">
            <span class="card-title ">
              <p class="flow-text">Elgon & Sipi Falls</p>
            </span>
          </div>
          <div class="card-content">
            <p>
              Sipi Falls is a series of three waterfalls found at the foothills of Mountain Elgon just at the edge of
              Mount Elgon National Park near the Kenyan border
            </p>
          </div>
        </div>
      </div>

      <div class="col s12 m3">
        <div class="card">
          <div class="card-image">
            <img src="./images/gallery/mburu.jpg" alt="">
            <span class="card-title ">
              <p class="flow-text">Lake Mburu National Park</p>
            </span>
          </div>
          <div class="card-content">
            <p>
              Lake Mburo National Park is a compact gem, located conveniently close to the highway that connects Kampala
              to the parks of western Uganda
            </p>
          </div>
        </div>
      </div>
    </div>
    <div class="row">
      <div class="col s12 center">
        <a href="#contact" class="btn btn-large grey darken-3">
          <i class="material-icons left">send</i> Contact For Booking
        </a>
      </div>
    </div>
    <!-- </div> -->
  </div>

  <!-- Section: Follow -->
  <!-- <section class="section section-follow teal darken-2 white-text center">
    <div class="container">
      <div class="row">
        <div class="col s12">
          <h4>Follow Klein Safar's</h4>
          <p>Follow us on social media for special offers</p>
          <a href="htttps://facebook.com" target="_blank" class="white-text">
            <i class="fab fa-facebook fa-4x"></i>
          </a>
          <a href="htttps://twitter.com" target="_blank" class="white-text">
            <i class="fab fa-twitter fa-4x"></i>
          </a>
          <a href="htttps://linkedin.com" target="_blank" class="white-text">
            <i class="fab fa-linkedin fa-4x"></i>
          </a>
          <a href="htttps://googleplus.com" target="_blank" class="white-text">
            <i class="fab fa-google-plus fa-4x"></i>
          </a>
          <a href="htttps://pinterest.com" target="_blank" class="white-text">
            <i class="fab fa-pinterest fa-4x"></i>
          </a>
        </div>
      </div>
    </div>
  </section> -->

  <!-- Section: Gallery -->
  <section id="gallery" class="section section-gallery scrollspy">
    <!-- <div class="container"> -->
    <h4 class="center">
      <span class="teal-text">Photo </span> Gallery
    </h4>
    <div class="row">
      <div class="col s12 m3">
        <img class="materialboxed responsive-img" src="./images/gallery/riv.jpg" alt="">
      </div>
      <div class="col s12 m3">
        <img class="materialboxed responsive-img" src="./images/tourist1.jpg" alt="">
      </div>
      <div class="col s12 m3">
        <img class="materialboxed responsive-img" src="./images/tourists.jpg" alt="">
      </div>
      <div class="col s12 m3">
        <img class="materialboxed responsive-img" src="./images/gallery/spring.jpg" alt="">
      </div>
    </div>

    <div class="row">
      <div class="col s12 m3">
        <img class="materialboxed responsive-img" src="./images/gallery/offroad.jpg" alt="">
      </div>
      <div class="col s12 m3">
        <img class="materialboxed responsive-img" src="./images/gallery/leo.jpg" alt="">
      </div>
      <div class="col s12 m3">
        <img class="materialboxed responsive-img" src="./images/gallery/trek.jpg" alt="">
      </div>
      <div class="col s12 m3">
        <img class="materialboxed responsive-img" src="./images/gallery/trip.jpg" alt="">
      </div>
    </div>

    <div class="row">
      <div class="col s12 m3">
        <img class="materialboxed responsive-img" src="./images/gallery/swimmers.jpg" alt="">
      </div>
      <div class="col s12 m3">
        <img class="materialboxed responsive-img" src="./images/gallery/lounge.jpg" alt="">
      </div>
      <div class="col s12 m3">
        <img class="materialboxed responsive-img" src="./images/gallery/air-baloon.jpg" alt="">
      </div>
      <div class="col s12 m3">
        <img class="materialboxed responsive-img" src="./images/gallery/dinner1.jpg" alt="">
      </div>
    </div>
    <!-- </div> -->
  </section>

  <!-- Section: Contact -->
  <section id="contact" class="section section-contact scrollspy">
    <div class="container">
      <div class="row">
        <div class="col s12 m6">
          <div class="card-panel teal white-text center">
            <i class="material-icons medium">email</i>
            <h5>Contact Us For Booking</h5>
            <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Repellendus sed praesentium delectus. Sit,
              mollitia
              quo. Veniam repellat voluptas ipsum doloremque?</p>
          </div>
          <ul class="collection with-header">
            <li class="collection-header">
              <h4>Location</h4>
            </li>
            <li class="collection-item">Klein Safaris Africa Limited</li>
            <li class="collection-item">Kampala Uganda</li>
            <li class="collection-item">sinoleadugj58@gmail.com</li>
            <li class="collection-item">+256(0)787992425</li>
          </ul>
        </div>
        <div class="col s12 m6">
          <div class="card-panel grey lighten-3">
            <h5>Please fill out this form</h5>
            <div class="input-field">
              <input type="text" placeholder="Name" v-model="name" id="name">
              <label for="name">Name</label>
            </div>
            <div class="input-field">
              <input type="email" placeholder="Email" v-model="email" id="email">
              <label for="email">Email</label>
            </div>
            <div class="input-field">
              <input type="text" placeholder="Phone" v-model="contact" id="phone">
              <label for="phone">Phone</label>
            </div>
            <div class="input-field">
              <textarea class="materialize-textarea" v-model="message" placeholder="Enter Message" id="message"></textarea>
              <label for="message">Message</label>
            </div>
            <input type="submit" value="Submit" @click="sendMessage" class="btn">
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Footer -->
  <footer class="section teal darken-2 white-text center">
    <p class="flow-text">Klein Safaris Africa Limited &copy; 2023</p>
  </footer>
</template>
<style>
.slider .btn {
  margin-top: 20px;
}

.section-search input {
  padding: 5px !important;
  font-size: 18px !important;
  width: 90% !important;
  border: #f4f4f4 3px solid !important;
}

.section-follow .fa-4x {
  margin: 5px 10px;
}

.section-contact h5 {
  margin-bottom: 30px;
}

.logo {
  display: inline-block;
  height: 100%;
}

.logo>img {
  vertical-align: middle;
  padding-left: 30px;
}
.nav-wrapper{
  margin-left:5px;
}
nav ul li:hover {
   background-color: white;
}
</style>
