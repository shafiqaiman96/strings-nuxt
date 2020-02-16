<template>
  <div class="wrapper">
    <div class="animated fadeIn">
      <b-row>
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
                <b-carousel-slide caption="First slide"
                                  text="Nulla vitae elit libero, a pharetra augue mollis interdum."
                                  img-src="https://cdn.pixabay.com/photo/2015/12/01/20/28/road-1072823__340.jpg"
                ></b-carousel-slide>

                <!-- Slides with custom text -->
                <b-carousel-slide img-src="https://images.pexels.com/photos/257360/pexels-photo-257360.jpeg?auto=compress&cs=tinysrgb&dpr=1&w=500">
                  <h1>Hello world!</h1>
                </b-carousel-slide>

                <!-- Slides with image only -->
                <b-carousel-slide img-src="https://image.shutterstock.com/image-photo/majestic-view-on-turquoise-water-260nw-266538056.jpg">
                </b-carousel-slide>

                <!-- Slides with img slot -->
                <!-- Note the classes .d-block and .img-fluid to prevent browser default image alignment -->
                <b-carousel-slide>
                  <img slot="img" class="d-block img-fluid w-100" width="1024" height="480"
                       src="https://hips.hearstapps.com/hmg-prod.s3.amazonaws.com/images/nature-quotes-1557340276.jpg?crop=0.666xw:1.00xh;0.168xw,0&resize=640:*" alt="image slot">
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
        <b-card class="card-accent-primary" header="Accounts & Banking">
          Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl ut aliquip ex ea commodo consequat.
        </b-card>
      </b-col>
      <b-col sm="6" md="4">
        <b-card class="card-accent-secondary" header="Investment">
          Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl ut aliquip ex ea commodo consequat.
        </b-card>
      </b-col>
      <b-col sm="6" md="4">
        <b-card class="card-accent-success" header="Insurance">
          Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl ut aliquip ex ea commodo consequat.
        </b-card>
      </b-col>
      <b-col sm="6" md="4">
        <b-card class="card-accent-info" header="Loans">
          Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl ut aliquip ex ea commodo consequat.
        </b-card>
      </b-col>
      <b-col sm="6" md="4">
        <b-card class="card-accent-warning" header="Mobile Banking">
          Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl ut aliquip ex ea commodo consequat.
        </b-card>
      </b-col>
      <b-col sm="6" md="4">
        <b-card class="card-accent-danger" header="Personal Details">
          Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat. Ut wisi enim ad minim veniam, quis nostrud exerci tation ullamcorper suscipit lobortis nisl ut aliquip ex ea commodo consequat.
        </b-card>
      </b-col>
    </b-row>
  </div>
</template>

<script>
  export default {
    title: 'ayam',
    name: 'carousels',
    data () {
      return {
        slide: 0,
        sliding: null
      }
    },
    methods: {
      onSlideStart (slide) {
        this.sliding = true
      },
      onSlideEnd (slide) {
        this.sliding = false
      }
    }
  }
</script>

<script>
export default {
  name: 'cards'
}
</script>