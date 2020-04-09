<template>
  <header class="v-fall-header grid">
    <div class="v-fall__container grid grid-v-center grid-v-between">
      <Logo />
      <Navbar />
      <Form />
    </div>
  </header>
</template>

<script>
import Logo from "@/components/Logo"
import Navbar from "@/components/Navbar"
import Form from "@/components/Form"

export default {
  components: {
    Logo,
    Navbar,
    Form
  }
}
</script>