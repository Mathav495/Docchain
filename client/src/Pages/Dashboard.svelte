<script>
import Header from "../components/Header.svelte"
import Navbar from "../components/Navbar.svelte"
</script>

<div class="h-screen w-screen bg-black text-gray-300">
  <Header />
  <div class="flex flex-row">
    <Navbar />
    <div class="flex w-3/4 px-5 py-5 lg:w-5/6">content</div>
  </div>
</div>
