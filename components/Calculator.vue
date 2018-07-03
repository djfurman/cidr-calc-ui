<template>
  <div>
    <input type="text" name="first_octet" id="first_octet" v-model="octets.first">.
    <input type="text" name="second_octet" id="second_octet" v-model="octets.second">.
    <input type="text" name="third_octet" id="third_octet" v-model="octets.third">.
    <input type="text" name="fourth_octet" id="fourth_octet" v-model="octets.fourth">/
    <input type="text" name="subnet" id="subnet" v-model="subnet">
    <input type="button" value="Submit" @click="sendCidr">

  </div>
</template>

<script>
export default {
  computed: {
    cidr() {
      return `${this.octets.first}.${this.octets.second}.${this.octets.third}.${this.octets.fourth}/${this.subnet}`;
    }
  },

  data() {
    return {
      octets: {
        first: '10',
        second: '0',
        third: '0',
        fourth: '0',
      },
      subnet: '16'
    }
  },

  methods: {
    sendCidr() {
      console.log(this.cidr);
    }
  }
}
</script>

