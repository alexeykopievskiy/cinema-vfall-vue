<template>
  <footer class="v-fall-footer grid">
    <div class="v-fall__container grid grid-v-center grid-v-between">
      <Logo />
      <Form />
    </div>
  </footer>
</template>

<script>
import Logo from "@/components/Logo"
import Form from "@/components/Form"

export default {
  components: {
    Logo,
    Form
  }
}
</script>