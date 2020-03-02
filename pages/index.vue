<template>
  <div class="wrapper">
    <div class="animated fadeIn">
      <b-row cols="12">
        <b-card border-variant="success" style="color: black">
        <h3><i class="fa fa-user-circle" ></i>&nbsp;&nbsp; Welcome Back<small>&nbsp;Shafiq Jefri</small></h3>
        </b-card>
        <b-col cols="12">
          <b-card
            header-tag="header"
            footer-tag="footer">
            <!-- <div slot="header">
              <i class="fa fa-align-justify"></i> <strong>Bootstrap Carousel</strong>
              <div class="card-actions">
                <a href="https://bootstrap-vue.js.org/docs/components/carousel" target="_blank"><small class="text-muted">docs</small></a>
              </div>
            </div> -->
            <div>
              <b-carousel id="carousel1"
                          style="text-shadow: 1px 1px 2px #333;"
                          controls
                          indicators
                          background="#ababab"
                          :interval="4000"
                          img-width="1024"
                          img-height="480"
                          v-model="slide"
                          @sliding-start="onSlideStart"
                          @sliding-end="onSlideEnd"
              >

                <!-- Text slides with image -->
                <b-carousel-slide caption="Welcome to back to strings"
                                  text="We are constantly changing and improving our Services. We may add or remove functionalities or features, and we may suspend or stop a Service altogether."
                                  img-src="https://www.techfunnel.com/wp-content/uploads/2019/07/12-Digital-Banking-Challenges-and-Opportunities-For-the-Banking-Industry-1.png"
                ></b-carousel-slide>

                <!-- Slides with custom text -->
                <b-carousel-slide img-src="https://www.finextra.com/finextra-images/top_pics/xl/Risks-and-Benefits-of-Open-Banking.jpg">
                  <h1>Easy way with the less risk</h1>
                </b-carousel-slide>

                <!-- Slides with image only -->
                <b-carousel-slide img-src="https://medici-prod.s3-us-west-2.amazonaws.com/uploads/10-risks-in-banking-industry-faced-by-every-bank.jpg">
                </b-carousel-slide>

                <!-- Slides with img slot -->
                <!-- Note the classes .d-block and .img-fluid to prevent browser default image alignment -->
                <b-carousel-slide>
                  <b-jumbotron header="Strings" lead="We Provide openbanking API platform for conventional and shariah banking" style="background-color: #cae3f1; opacity: 0.8;">
                    <!-- <p>For more information visit website</p> -->
                    <b-btn variant="primary" href="https://strings.my">More Info</b-btn>
                  </b-jumbotron>
                  <img slot="img" class="d-block img-fluid w-100" width="1024" height="480"
                       src="https://cdn.hsbc.com.my/content/dam/hsbc/my/images/21-9/online-banking-and-mobile-banking-20210.jpg" alt="image slot">
                </b-carousel-slide>

                <!-- Slide with blank fluid image to maintain slide aspect ratio -->
                <!-- <b-carousel-slide caption="Blank Image" img-blank img-alt="Blank image">
                  <p>
                    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Suspendisse
                    eros felis, tincidunt a tincidunt eget, convallis vel est. Ut pellentesque
                    ut lacus vel interdum.
                  </p>
                </b-carousel-slide> -->

              </b-carousel>

              <!-- <p class="mt-4">
                Slide #: {{ slide }}<br>
                Sliding: {{ sliding }}
              </p> -->

            </div>
          </b-card>
        </b-col>
      </b-row>
    </div>
        <b-row>
      <b-col sm="6" md="4">
        <a href="/base/account">
          <b-card class="card-accent-primary" header="Accounts & Banking" style="color: black">
            View and manage your accounts.
          </b-card>
        </a>
      </b-col>
      <b-col sm="6" md="4">
        <a href="/pages/maintenance">
          <b-card class="card-accent-secondary" header="Investment & Loans" style="color: black">
            Trade and manage using Online Stocks. View and manage your home or car loans.
          </b-card>
        </a>
      </b-col>
      <b-col sm="6" md="4">
        <a href="/pages/maintenance">
          <b-card class="card-accent-success" header="Insurance" style="color: black">
            Renew your insurance policy or purchase PA online.
          </b-card>
        </a>
      </b-col>
      <b-col sm="6" md="4">
        <a href="/base/payment">
          <b-card class="card-accent-info" header="Payment" style="color: black">
            Make a payment using a few types of payment gateway integration.
          </b-card>
        </a>
      </b-col>
      <b-col sm="6" md="4">
        <a href="/base/topup">
          <b-card class="card-accent-warning" header="Top Up" style="color: black">
            Reload your mobile credit balance.
          </b-card>
        </a>
      </b-col>
      <b-col sm="6" md="4">
        <a href="/base/transfer">
          <b-card class="card-accent-danger" header="Transfer" style="color: black">
            Transfer money to other accounts within or different bank.
          </b-card>
        </a>
      </b-col>
    </b-row>
    <!-- <ul class="card-text">
      <li v-for="item in itemNav" v-bind:key="item.id">{{item.name}}</li>
    </ul> -->
  </div>
</template>

<script>
  // export default {
  //   name: 'carousels',
  //   data () {
  //     return {
  //       slide: 0,
  //       sliding: null
  //     }
  //   },
  //   methods: {
  //     onSlideStart (slide) {
  //       this.sliding = true
  //     },
  //     onSlideEnd (slide) {
  //       this.sliding = false
  //     }
  //   }
  // }
</script>

<script>
export default {
  name: 'cards',
   data: () => {
      return {
        showCollapse: true,
    itemNav: [
      {
        name: 'Home',
        url: '/',
      },
      {
        name: 'Account & Banking',
        url: '/base/account',
      },
      {
        name: 'Investment and Loans',
        url: '/pages/maintenance',
      },
      {
        name: 'Insurance',
        url: '/pages/maintenance',
      },
      {
        name: 'Payment',
        url: '/base/payment',
      },
      {
        name: 'Top Up',
        url: '/base/topup',
      },
      {
        name: 'Transfer',
        url: '/base/transfer',
      }
    ]}
      }
    }
</script>