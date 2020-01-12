<template>
  <div class="container">
    <Navbar />
    <Table />
  </div>
</template>

<script>
// @ is an alias to /src
import Navbar from '@/components/Navbar'
import Table from '@/components/Table'
export default {
  name: 'home',
  components: {
    Navbar,
    Table
  }
}
</script>
