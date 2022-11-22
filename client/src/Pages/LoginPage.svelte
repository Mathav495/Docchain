<script>
  import axios from "axios"
  let Email, password
</script>

<div class="mx-10 my-5">
  <div class="mx-auto mt-40 flex w-full flex-col gap-8 md:w-1/2 lg:w-1/4">
    <!-- title -->

    <div class="flex items-center justify-center">
      <img
        src="https://app.test.print2block.in/images/icon.svg"
        class=" mr-2 inline-block align-top "
        width="30"
        height="30"
        alt="" />
      <h1 class="text-xl font-medium">DocChain</h1>
    </div>

    <!-- card -->

    <div class=" bg-slate-100 p-2 py-5 shadow-lg ">
      <h1
        class="flex justify-center pt-4 pb-2 text-2xl font-normal text-slate-600">
        Login to your account
      </h1>
      <div class="flex flex-col gap-5 p-5">
        <input
          bind:value={Email}
          type="email"
          placeholder="Email address"
          class="w-full rounded-r-full rounded-l-full border  border-gray-300 bg-white py-1 px-3 text-base leading-8 text-gray-700 outline-none transition-colors duration-200 ease-in-out focus:border-indigo-500 focus:ring-2 focus:ring-indigo-200" />

        <input
          bind:value={password}
          type="password"
          placeholder="Password"
          class="w-full rounded-r-full rounded-l-full border  border-gray-300 bg-white py-1 px-3 text-base leading-8 text-gray-700 outline-none transition-colors duration-200 ease-in-out focus:border-indigo-500 focus:ring-2 focus:ring-indigo-200" />

        <button
          class="rounded-l-full rounded-r-full border-0 bg-indigo-500 py-2 px-6 text-lg text-white hover:bg-indigo-600 focus:outline-none"
          >LOGIN</button>
      </div>
      <h1
        class="flex  cursor-pointer items-center justify-center gap-2 text-base font-normal text-blue-700">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          fill="white"
          viewBox="0 0 24 24"
          stroke-width="1.5"
          stroke="black"
          class="h-4 w-4">
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M16.5 10.5V6.75a4.5 4.5 0 10-9 0v3.75m-.75 11.25h10.5a2.25 2.25 0 002.25-2.25v-6.75a2.25 2.25 0 00-2.25-2.25H6.75a2.25 2.25 0 00-2.25 2.25v6.75a2.25 2.25 0 002.25 2.25z" />
        </svg>
        Forgot Password?
      </h1>

      <h1
        class="flex  cursor-pointer items-center justify-center gap-2 pt-3 text-base font-normal">
        Don't have an account? <span class="text-blue-700">contact-us</span>
      </h1>
    </div>
  </div>
</div>
