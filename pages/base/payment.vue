<template>
  <div class="wrapper">
    <div class="animated fadeIn">
          <b-card
            header-tag="header"
            footer-tag="footer">
            <div slot="header">
              <h5>User Profile</h5>
            </div>
            <div role="tablist">
              <b-card no-body class="mb-1">
                <b-card-header header-tag="header" class="p-1" role="tab">
                  <b-btn block href="#" v-b-toggle.accordion1 variant="info">JomPAY</b-btn>
                </b-card-header>
                <b-collapse id="accordion1" visible accordion="my-accordion" role="tabpanel">
                  <b-card-body>
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
                                label="Biller Code"
                                label-for="basicText"
                                :label-cols="3"
                                :horizontal="true">
                                <b-form-input id="billerCode" type="text" placeholder="Biller Code or Nickname"></b-form-input>
                            </b-form-group>
                            <b-form-group
                                description="Please insert value in RM"
                                label="Amount"
                                label-for="basicText"
                                :label-cols="3"
                                :horizontal="true">
                                <b-form-input id="transAmount" type="text" placeholder="10"></b-form-input>
                            </b-form-group>
                            <div slot="footer" style="float: right">
                                <b-button size="sm" variant="success" type="button" @click="warningModal = true"><i class="fa fa-check"></i> Proceed</b-button>
                                <b-button type="reset" size="sm" variant="danger"><i class="fa fa-ban"></i> Amend</b-button>
                            </div>
                          </b-card-body>
                        </b-card>
                      </b-col>
                    </b-row>
                  </b-card-body>
                </b-collapse>
              </b-card>
              <!-- <b-card no-body class="mb-1">
                <b-card-header header-tag="header" class="p-1" role="tab">
                  <b-btn block href="#" v-b-toggle.accordion2 variant="info">Contact Info</b-btn>
                </b-card-header>
                <b-collapse id="accordion2" accordion="my-accordion" role="tabpanel">
                  <b-card-body>
                    <b-row class="justify-content-center">
                      <b-col sm="12" md="6">
                        <b-card no-body :no-block="true">
                          <b-card-body>
                            <b-form-group>
                              <b-input-group>
                                <b-input-group-prepend>
                                  <b-input-group-text><i class="fa fa-phone"></i></b-input-group-text>
                                </b-input-group-prepend>
                                <b-form-input type="text" placeholder="Phone Number" :disabled="true"></b-form-input>
                              </b-input-group>
                            </b-form-group>
                            <b-form-group>
                              <b-input-group>
                                <b-input-group-prepend>
                                  <b-input-group-text><i class="fa fa-envelope"></i></b-input-group-text>
                                </b-input-group-prepend>
                                <b-form-input type="email" placeholder="Email" :disabled="true"></b-form-input>
                              </b-input-group>
                            </b-form-group>
                          </b-card-body>
                        </b-card>
                      </b-col>
                    </b-row>
                  </b-card-body>
                </b-collapse>
              </b-card>
              <b-card no-body class="mb-1">
                <b-card-header header-tag="header" class="p-1" role="tab">
                  <b-btn block href="#" v-b-toggle.accordion3 variant="info">Update Profile</b-btn>
                </b-card-header>
                <b-collapse id="accordion3" accordion="my-accordion" role="tabpanel">
                  <b-card-body>
                    <b-row class="justify-content-center">
                      <b-col sm="12" md="6">
                        <b-card no-body :no-block="true">
                          <b-card-body>
                            <b-form-group
                              label="New Username"
                              label-for="userName"
                              :label-cols="3"
                              :horizontal="true">
                              <b-form-input id="userName" type="text" placeholder="Enter your new username"></b-form-input>
                            </b-form-group>
                            <b-form-group
                              label="User ID"
                              label-for="basicInputDisabled"
                              :label-cols="3"
                              :horizontal="true">
                              <b-form-input id="basicInputDisabled" type="text" :disabled="true" placeholder="xxxx"></b-form-input>
                            </b-form-group>
                            <b-form-group
                              label="Phone Number"
                              label-for="phoneNum"
                              :label-cols="3"
                              :horizontal="true">
                              <b-form-input id="phoneNum" type="text" placeholder="0123456789"></b-form-input>
                            </b-form-group>
                            <b-form-group
                              label="New Email"
                              label-for="basicEmail"
                              :label-cols="3"
                              :horizontal="true">
                              <b-form-input id="basicEmail" type="email" placeholder="Enter your new email"></b-form-input>
                            </b-form-group>
                          </b-card-body>
                        </b-card>
                      </b-col>
                    </b-row>
                  </b-card-body>
                </b-collapse>
              </b-card>
              <b-card no-body class="mb-1">
                <b-card-header header-tag="header" class="p-1" role="tab">
                  <b-btn block href="#" v-b-toggle.accordion4 variant="info">Change Password</b-btn>
                </b-card-header>
                <b-collapse id="accordion4" accordion="my-accordion" role="tabpanel">
                  <b-card-body>
                    <b-row class="justify-content-center">
                      <b-col sm="12" md="6">
                        <b-card no-body :no-block="true">
                          <b-card-body>
                            <b-form-group>
                              <label class="col-form-label" for="inputIsValid">Old Password</label>
                              <input type="text" class="form-control is-valid" id="inputIsValid">
                              <b-form-valid-feedback>
                                Input is valid.
                              </b-form-valid-feedback>
                            </b-form-group>
                            <b-form-group>
                              <label class="col-form-label" for="inputIsValid">New Password</label>
                              <input type="text" class="form-control is-valid" id="inputIsValid">
                              <b-form-valid-feedback>
                                Input is valid.
                              </b-form-valid-feedback>
                            </b-form-group>
                            <b-form-group>
                              <label class="col-form-label" for="inputIsInvalid">Confirm Password</label>
                              <input type="text" class="form-control is-invalid" id="inputIsInvalid">
                              <b-form-invalid-feedback>
                                Please provide a valid information.
                              </b-form-invalid-feedback>
                            </b-form-group>
                            <b-button type="button" variant="warning" @click="warningModal = true" style="float: right">Change</b-button>
                          </b-card-body>
                        </b-card>
                      </b-col>
                    </b-row>
                  </b-card-body>
                </b-collapse>
              </b-card> -->
            </div>
          </b-card>
    </div>
    <b-modal class="modal-warning" v-model="warningModal" @ok="warningModal = false" ok-variant="success">
      Your password will be change. Are you confirm to change your password?
    </b-modal>
  </div>
</template>


<script>
  export default {
    name: 'profile',
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