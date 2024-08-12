<template>
  <div>
    <v-container>
      <v-row class="back-color">
        <v-col>
          <div class="request">
            <header>
              <h1>{{ title }}</h1>
            </header>
            <p>{{ text }}</p>
            <form>
              <v-row>
                <v-col cols="12" sm="7">
                  <v-text-field
                    flat
                    variant="solo"
                    rounded="lg"
                    density="compact"
                    type="phone"
                    placeholder="شماره تماس خود را وارد کنید."
                    v-model="phoneNumber"
                  ></v-text-field>
                </v-col>
                <v-col cols="12" sm="5">
                  <v-btn flat @:click="setCellphone" class="button">درخواست مشاوره</v-btn>
                </v-col>
              </v-row>
            </form>
          </div>
        </v-col>
        <v-col class="img-contain" sm="6" cols="12">
          <img :src="imgAddress" class="img" />
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
import { createApp } from 'vue'
import { createVuetify } from 'vuetify'

export default {
  props: {
    title: {
      type: String,
      required: true
    },
    text: {
      type: String,
      required: true
    },
    imgAddress: {
      type: String,
      required: true
    }
  },
  data() {
    return {
      phoneNumber: ''
    }
  },
  methods: {
    setCellphone() {
      this.$emit('setCellphone', this.phoneNumber)
    }
  }
}
</script>

<style scoped>
@font-face {
  font-family: vazir;
  src: url('../../../../public/Vazir.ttf');
}
.back-color {
  background-color: rgb(238, 238, 238);
}
.request {
  direction: rtl;
  font-family: vazir;
}
header h1 {
  font-size: 25px;
}
header,
p {
  margin-bottom: 20px;
  text-align: justify;
}

.img-contain {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: row-reverse;
}
.img {
  width: 70%;
}

form .button {
  background-color: rgb(96, 96, 231);
  color: white;
  padding: 5px 20px;
  border-radius: 10px;
  height: 40px;
}

@media (max-width: 600px) {
}
</style>

<style>
/* form input {
  direction: rtl;
  border-radius: 20px;
  background-color: blue;
  height: 40px;
} */
</style>
