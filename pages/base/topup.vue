<template>
  <div class="wrapper">
    <div class="animated fadeIn">
          <b-card
            header-tag="header"
            footer-tag="footer">
            <div slot="header">
              <h5>Top Up</h5>
            </div>
            <div role="tablist">
                    <b-row class="justify-content-center">
                      <b-col sm="12" md="6">
                        <b-card no-body :no-block="true">
                          <b-card-body>
                            <b-form-group
                                label="Accounts"
                                label-for="basicSelect"
                                :label-cols="3"
                                :horizontal="true">
                                <b-form-select id="accSelect"
                                :plain="true"
                                :options="['Please select','Saving', 'Current']"
                                value="Please select">
                                </b-form-select>
                             </b-form-group>
                                <b-form-group
                                label="Select Telco"
                                label-for="basicSelect"
                                :label-cols="3"
                                :horizontal="true">
                                <b-form-select id="telSelect"
                                :plain="true"
                                :options="['Please select','Celcom', 'Digi', 'Maxis']"
                                value="Please select">
                                </b-form-select>
                            </b-form-group>
                            <b-form-group
                                label="Phone No."
                                label-for="basicText"
                                :label-cols="3"
                                :horizontal="true">
                                <b-form-input id="phoneNo" type="text" placeholder="0123456789"></b-form-input>
                            </b-form-group>
                            <b-form-group
                                description="Please insert value in RM"
                                label="Amount"
                                label-for="basicText"
                                :label-cols="3"
                                :horizontal="true">
                                <b-form-input id="topupAmount" type="text" placeholder="10"></b-form-input>
                            </b-form-group>
                            <div slot="footer" style="float: right">
                              <b-button type="reset" size="sm" variant="danger"><i class="fa fa-ban"></i> Amend</b-button>
                              <b-button size="sm" variant="success" type="button" @click="warningModal = true"><i class="fa fa-check"></i> Proceed</b-button>
                            </div>
                          </b-card-body>
                        </b-card>
                      </b-col>
                    </b-row>
            </div>
          </b-card>
    </div>
    <b-modal class="modal-warning" v-model="warningModal" @ok="warningModal = false" ok-variant="success">
      Your amount will be deducted for this transaction. Are You confirm to proceed?
    </b-modal>
  </div>
</template>


<script>
  export default {
    name: 'topup',
    data () {
      return {
        showCollapse: true,
        warningModal: false,
      }
    },
  //     name: 'modals',
  // data () {
  //   return {
  //     warningModal: false,
  //   }
  // }
  }
</script>