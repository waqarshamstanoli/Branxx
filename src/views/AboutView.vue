<template>

   <v-card>
      <v-card class="scroll">
          <v-card-title>
              <span class="text-h5">Tube</span>
          </v-card-title>
          <v-divider :thickness="3" color="black"></v-divider>

          <div class="container">
             
              <div v-for="items in navBarButtons" :key="items.value">
                  <v-container>
                      <v-row class="ms-16">
                          <v-col class="ms-16">
                              <v-row class="ms-16">
                                  <div class="ms-16 ps-16">
                                      <v-btn
                                          class="btn ms-16"
                                          variant="text"
                                          style="
                                              font-weight: bold;
                                              font-size: 18px;
                                          "
                                          @click="selectTab(items.currentTab)"
                                          :class="{
                                              'bg-black':
                                                  currentTab ==
                                                  items.currentTab,
                                          }"
                                      >
                                          {{ items.material }}

                                          <template v-slot:prepend>
                                              <v-icon
                                                  end
                                                  icon="mdi:mdi-file-outline"
                                                  color="blue lighten-2"
                                              ></v-icon>
                                          </template>
                                      </v-btn>
                                  </div>
                              </v-row>
                          </v-col>
                      </v-row>
                  </v-container>
              </div>
          </div>
         
          <div v-if="currentTab == 1">
              <v-card-text>
                  <v-container>
                      <v-row>
                          <v-col cols="12" sm="5">
                              <span class="text-h5">Inside Diameter</span>
                              <v-text-field
                                  v-model="insideDiameter"
                                  label="inches"
                                  variant="outlined"
                                  @input="calculateWallThickness"
                              >
                                  <v-tooltip
                                      activator="parent"
                                      location="bottom"
                                  >
                                     Please enter format ex.(1 or 3/4) or a Decimal Number
                                  </v-tooltip>
                              </v-text-field>
                          </v-col>

                          <div class="ms-16"></div>
                          <div class="ms-5"></div>

                          <v-col cols="12" sm="5">
                              <span class="text-h5">Wall Thickness</span>
                              <v-text-field
                                  v-model="wallThickness"
                                  readonly
                                  label="inches"
                                  variant="outlined"
                              ></v-text-field>
                             
                          </v-col>

                          <v-col cols="12" sm="2">
                              <span class="text-h5">Length</span>
                              <v-text-field
                                  label="foot"
                                  @keypress="isNumber($event)"
                                  variant="outlined"
                              ></v-text-field>
                          </v-col>

                          <v-col cols="12" sm="2">
                              <div class="mt-8"></div>
                              <v-text-field
                                  label="inches"
                                  @keypress="isNumber($event)"
                                  variant="outlined"
                              ></v-text-field>
                          </v-col>

                          <v-col cols="12" sm="4">
                              <span class="text-h5">Outside Diameter</span>
                              <v-text-field
                                  v-model="outsideDiameter"
                                  label="inches"
                                  variant="outlined"
                                  @input="calculateWallThickness"
                              >
                              
                              <v-tooltip
                                  activator="parent"
                                  location="bottom"
                              >
                                  Please enter format ex.(1 or 3/4) or a Decimal Number
                              </v-tooltip>
                              </v-text-field>
                          </v-col>

                          <v-col cols="12" sm="4">
                              <span class="text-h5">Weight (g) </span>
                              <v-text-field
                                  @keypress="isNumber($event)"
                                  variant="outlined"
                              ></v-text-field>
                          </v-col>

                          <v-col cols="12" sm="4">
                              <span class="text-h5">Color</span>
                              <v-select
                                  :items="[
                                      '',
                                      'BLUE',
                                      'BEIGE',
                                      'BLACK',
                                      'BROWN',
                                      'BRONZE',
                                      'COSMETIC BRIGHT',
                                      'CLEAR',
                                      'CYAN',
                                      'DIFFUSED',
                                      'GOLD',
                                      'GREEN',
                                      'GRAY',
                                      'MAGENTA',
                                      'NATURAL',
                                      'ORANGE',
                                      'PINK',
                                      'PURPLE',
                                      'RED',
                                      'SILVER',
                                      'WHITE',
                                      'YELLOW',
                                  ]"
                                  label="Color"
                                  variant="outlined"
                                  :menu-props="{
                                      maxHeight: 400,
                                  }"
                              ></v-select>
                          </v-col>

                          <v-col cols="12" sm="6" md="4">
                              <span class="text-h5">Manufacturer Color</span>
                              <v-text-field
                                  variant="outlined"
                                  label="Manufacturer Color"
                              ></v-text-field>
                          </v-col>

                          <v-col cols="12" sm="3">
                              <span class="text-h5">Process</span>
                              <v-select
                                  :items="['None', 'Extruded', 'Cast']"
                                  variant="outlined"
                                  label="Process"
                              ></v-select>
                          </v-col>

                          <v-col cols="12" sm="4">
                              <span class="text-h5">Material Type</span>
                              <v-select
                                  :items="[
                                      '',
                                      'PMMA',
                                      'PET/PETG',
                                      'PC',
                                      'PP',
                                      'ABS',
                                      'HIPS',
                                      'STYRENE',
                                      'PE-HD',
                                      'PMMA Mirror',
                                      'PARAPAN',
                                      'PTFE',
                                      'PVC',
                                      'HIPMMA',
                                      'OTHER',
                                  ]"
                                  variant="outlined"
                                  label="Material Type"
                                  :menu-props="{
                                      maxHeight: 400,
                                  }"
                              ></v-select>
                          </v-col>

                          <v-col cols="12" sm="4">
                              <span class="text-h5">Supplier</span>
                              <v-text-field
                                  label="Supplier"
                                  variant="outlined"
                              ></v-text-field>
                          </v-col>

                          <v-col cols="12" sm="4">
                              <span class="text-h5">Supplier Ref#</span>
                              <v-text-field
                                  label="Supplier Ref#"
                                  variant="outlined"
                              ></v-text-field>
                          </v-col>

                          <v-col cols="12">
                              <v-textarea
                                  :maxlength="100"
                                  bg-color="light-blue"
                                  prepend-inner-icon="mdi:mdi-comment"
                                  color="black"
                                  label="Comment Limit 100 Characters"
                              ></v-textarea>
                          </v-col>

                          <v-col cols="12">
                              <v-file-input
                                  color="deep-purple-accent-4"
                                  label="File Input"
                                  placeholder="Select your files"
                                  prepend-inner-icon="mdi:mdi-paperclip"
                                  variant="outlined"
                                  :show-size="1000"
                              ></v-file-input>
                          </v-col>
                          <span class="text-h7 ps-13"
                              >Warning! The transaction will be pushed through
                              to Epicor.</span
                          >
                      </v-row>
                  </v-container>
              </v-card-text>
              <v-card-actions>
                  <v-spacer></v-spacer>
                  <v-btn
                      color="blue-darken-1"
                      variant="text"
                      @click="submitForm()"
                  >
                      Save
                  </v-btn>
              </v-card-actions>
          </div>
          
          <div v-if="currentTab == 2">
              <v-card-text>
                  <v-container>
                      <v-row>
                          <v-col cols="12" sm="2">
                              <span class="text-h5">Length</span>
                              <v-text-field
                                  label="foot"
                                  @keypress="isNumber($event)"
                                  variant="outlined"
                              ></v-text-field>
                          </v-col>

                          <v-col cols="12" sm="2">
                              <div class="mt-8"></div>
                              <v-text-field
                                  label="inches"
                                  @keypress="isNumber($event)"
                                  variant="outlined"
                              ></v-text-field>
                          </v-col>

                          <v-col cols="12" sm="4">
                              <span class="text-h5">Outside Diameter</span>
                              <v-text-field
                                  label="inches"
                                  variant="outlined"
                              >
                              <v-tooltip
                                  activator="parent"
                                  location="bottom"
                              >
                                  Please enter format ex.(1 or 3/4) or a Decimal Number
                              </v-tooltip>
                              </v-text-field>
                          </v-col>

                          <v-col cols="12" sm="4">
                              <span class="text-h5">Weight (g) </span>
                              <v-text-field
                                  @keypress="isNumber($event)"
                                  variant="outlined"
                              ></v-text-field>
                          </v-col>

                          <v-col cols="12" sm="4">
                              <span class="text-h5">Color</span>
                              <v-select
                                  :items="[
                                      '',
                                      'BLUE',
                                      'BEIGE',
                                      'BLACK',
                                      'BROWN',
                                      'BRONZE',
                                      'COSMETIC BRIGHT',
                                      'CLEAR',
                                      'CYAN',
                                      'DIFFUSED',
                                      'GOLD',
                                      'GREEN',
                                      'GRAY',
                                      'MAGENTA',
                                      'NATURAL',
                                      'ORANGE',
                                      'PINK',
                                      'PURPLE',
                                      'RED',
                                      'SILVER',
                                      'WHITE',
                                      'YELLOW',
                                  ]"
                                  label="Color"
                                  variant="outlined"
                                  :menu-props="{
                                      maxHeight: 400,
                                  }"
                              ></v-select>
                          </v-col>

                          <v-col cols="12" sm="6" md="4">
                              <span class="text-h5">Manufacturer Color</span>
                              <v-text-field
                                  variant="outlined"
                                  label="Manufacturer Color"
                              ></v-text-field>
                          </v-col>

                          <v-col cols="12" sm="3">
                              <span class="text-h5">Process</span>
                              <v-select
                                  :items="['None', 'Extruded', 'Cast']"
                                  variant="outlined"
                                  label="Process"
                              ></v-select>
                          </v-col>

                          <v-col cols="12" sm="4">
                              <span class="text-h5">Material Type</span>
                              <v-select
                                  :items="[
                                      '',
                                      'PMMA',
                                      'PET/PETG',
                                      'PC',
                                      'PP',
                                      'ABS',
                                      'HIPS',
                                      'STYRENE',
                                      'PE-HD',
                                      'PMMA Mirror',
                                      'PARAPAN',
                                      'PTFE',
                                      'PVC',
                                      'HIPMMA',
                                      'OTHER',
                                  ]"
                                  variant="outlined"
                                  label="Material Type"
                                  :menu-props="{
                                      maxHeight: 400,
                                  }"
                              ></v-select>
                          </v-col>

                          <v-col cols="12" sm="4">
                              <span class="text-h5">Supplier</span>
                              <v-text-field
                                  label="Supplier"
                                  variant="outlined"
                              ></v-text-field>
                          </v-col>

                          <v-col cols="12" sm="4">
                              <span class="text-h5">Supplier Ref#</span>
                              <v-text-field
                                  label="Supplier Ref#"
                                  variant="outlined"
                              ></v-text-field>
                          </v-col>

                          <v-col cols="12">
                              <v-textarea
                                  :maxlength="100"
                                  bg-color="light-blue"
                                  prepend-inner-icon="mdi:mdi-comment"
                                  color="black"
                                  label="Comment Limit 100 Characters"
                              ></v-textarea>
                          </v-col>

                          <v-col cols="12">
                              <v-file-input
                                  color="deep-purple-accent-4"
                                  label="File Input"
                                  placeholder="Select your files"
                                  prepend-inner-icon="mdi:mdi-paperclip"
                                  variant="outlined"
                                  :show-size="1000"
                              ></v-file-input>
                          </v-col>
                          <span class="text-h7 ps-13"
                              >Warning! The transaction will be pushed through
                              to Epicor.</span
                          >
                      </v-row>
                  </v-container>
              </v-card-text>
              <v-card-actions>
                  <v-spacer></v-spacer>
                  <v-btn
                      color="blue-darken-1"
                      variant="text"
                      @click="submitForm()"
                  >
                      Save
                  </v-btn>
              </v-card-actions>
          </div>
      </v-card>
  </v-card> 

</template>

<script>
export default {
  //emits: ["closeModal"],
  props: {
      material: {
          type: Object,
          default: null,
      },
  },
  watch: {
      material(item) {},
      shouldSelectCheckbox(newValue) {
          this.isChecked = newValue;
      },
  },
  computed: {
      shouldSelectCheckbox() {
          return (
              this.selectedOption.includes("GREEN CAST") ||
              this.selectedOption.includes("RECYCLED MATERIAL")
          );
      },
  },

  methods: {
      
      selectTab(selectedTab) {
          this.currentTab = selectedTab;
      },
      calculateWallThickness() {
          if(this.insideDiameter.includes("/")){
          this.test = this.insideDiameter.split('/');
          this.test = Number(this.test[0]) / Number(this.test[1]);
          this.test =  parseFloat(this.test)
          console.log(this.test)
          }

          if(this.outsideDiameter.includes("/")){
            this.test2 = this.outsideDiameter.split('/');
            this.test2 = Number(this.test2[0]) / Number(this.test2[1]);
            this.test2 =  parseFloat(this.test2)
          console.log(this.test2)
          }
          console.log('inside',this.test)
          console.log('outside',this.test2)
          console.log('result',this.wallThickness)
          this.wallThickness = parseFloat(this.test) + parseFloat(this.test2);
          return this.wallThickness;
      },
      closeModal() {
          this.$emit("closeModal");
      },
      //Check to see if the user is entering a number. Only accepts numbers
      isNumber: function (evt) {
          evt = evt ? evt : window.event;
          var charCode = evt.which ? evt.which : evt.keyCode;
          if (
              charCode > 31 &&
              (charCode < 48 || charCode > 57) &&
              charCode !== 46
          ) {
              evt.preventDefault();
          } else {
              return true;
          }
      },
  },
  
  data() {
      return {
          currentTab: 1,
          editedItem: {},
          wallThickness: 0,
          insideDiameter: 0,
          outsideDiameter: 0,
          defaultItem: {},
          dialogConvertCalculator: false,
          dialogGenerateCodeAcrylicMaterialSheets: false,
test:'',
test2:'',
          selectedOption: [],
          isChecked: false,
          nature: [
              "NONE",
              "ABRASION RESISTANT",
              "CHEMICAL RESISTANT",
              "GREEN CAST",
              "RECYCLED MATERIAL",
          ],

          navBarButtons: [
              {
                  value: 0,
                  material: "Tube",
                  currentTab: 1,
              },

              {
                  value: 1,
                  material: "Rod",
                  currentTab: 2,
              },
          ],
      };
  },
};
</script>

<style lang="css" scoped>
.detail-css {
  color: steelblue;
}
.scroll {
  overflow-y: auto;
}
.text-h7 {
  color: red;
}
</style>
