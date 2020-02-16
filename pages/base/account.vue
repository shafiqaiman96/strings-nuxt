<template>
  <div class="wrapper">
    <div class="animated fadeIn">
          <b-card
            header-tag="header"
            footer-tag="footer">
            <div slot="header">
              <h5>User Account Details</h5>
            </div>
            <div role="tablist">
              <b-card no-body class="mb-1">
                <b-card-header header-tag="header" class="p-1" role="tab">
                  <b-btn block href="#" v-b-toggle.accordion1 variant="info">Account Balance</b-btn>
                </b-card-header>
                  <b-card-body>
                    <b-row class="justify-content-center">
                      <b-col sm="12" md="6">
                        <b-card no-body :no-block="true">
                          <b-card-body>
                            <b-form-group
                                label="Current"
                                label-for="basicText"
                                :label-cols="3"
                                :horizontal="true">
                                <b-form-input id="curBal" type="text" placeholder="RM9999.99" :disabled="true"></b-form-input>
                            </b-form-group>
                            <b-form-group
                                label="Saving"
                                label-for="basicText"
                                :label-cols="3"
                                :horizontal="true">
                                <b-form-input id="savBal" type="text" placeholder="RM9999.99" :disabled="true"></b-form-input>
                            </b-form-group>
                            <b-form-group
                                label="Last Transfer"
                                label-for="basicText"
                                :label-cols="3"
                                :horizontal="true">
                                <b-form-input id="LastTrans" type="text" placeholder="RM9999.99" :disabled="true"></b-form-input>
                            </b-form-group>
                            <a>Transaction History</a><b-btn style="float: right" variant="green" href="/base/history"><a>Search <i class="fa fa-search fa-lg" aria-hidden="true"></i></a></b-btn>
                          </b-card-body>
                        </b-card>
                        
                      </b-col>
                    </b-row>
                  </b-card-body>
              </b-card>
            </div>
          </b-card>
    </div>
  </div>
</template>


<script>
  export default {
    name: 'account',
    data () {
      return {
        showCollapse: true,
      }
    },
      name: 'modals',
  data () {
    return {
      warningModal: false,
    }
  }
  }
</script>