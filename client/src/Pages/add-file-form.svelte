<script>
  import Axios from 'axios';
  import { createEventDispatcher } from 'svelte';
  const dispatch = createEventDispatcher();

  let documentID,
    file,
    disabled = false,
    error = '';

  const addFile = async () => {
    if (documentID == null) {
      error = "documentID can't be empty";
    } else {
      const sample = {
        documentID: documentID,
        file: file,
      };
      const { data } = await Axios.post('https://test.swagger.print2block.in/docs/add-file', sample);
      console.log(data);
      dispatch('push', data);
    }
  };
</script>

<!-- drag and drop form -->
<div class="min-h-screen flex-col justify-center bg-gray-100 py-12 px-6 lg:px-8">
  <div class="mt-8 sm:mx-auto sm:w-full sm:max-w-4xl">
    <div class="rounded-lg bg-white py-8 px-6 shadow-lg sm:px-10">
      <form class="mb-0 space-y-6 " action="#" method="POST" on:submit|preventDefault={addFile}>
        <div>
          <label for="text" class="block text-lg font-medium text-gray-700">DocumentID:</label>
          <div class="mt-1">
            <input bind:value={documentID} id="id" name="id" type="text" class=" w-full rounded-lg border-2 border-gray-500 p-4 py-3" placeholder="enter your documentID" />
          </div>
        </div>
        <h1 class="text-base font-semibold text-rose-500">{error}</h1>

        <label for="text" class="block text-lg font-medium text-gray-700">Upload File:</label>
        <div class=" flex justify-center rounded-md border-2 border-dashed border-gray-300 px-2 pt-5 pb-6">
          <div class="space-y-1 text-center">
            <svg class="mx-auto h-12 w-12 text-gray-400" stroke="currentColor" fill="none" viewBox="0 0 48 48" aria-hidden="true">
              <path d="M28 8H12a4 4 0 00-4 4v20m32-12v8m0 0v8a4 4 0 01-4 4H12a4 4 0 01-4-4v-4m32-4l-3.172-3.172a4 4 0 00-5.656 0L28 28M8 32l9.172-9.172a4 4 0 015.656 0L28 28m0 0l4 4m4-24h8m-4-4v8m-12 4h.02" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" />
            </svg>
            <div class="flex text-sm text-gray-600">
              <label for="file" class="relative cursor-pointer rounded-md bg-white font-medium text-indigo-600 focus-within:outline-none focus-within:ring-2 focus-within:ring-indigo-500 focus-within:ring-offset-2 hover:text-indigo-500">
                <span>Upload a file</span>
                <input id="file-upload" name="file-upload" type="file" />
              </label>
              <p class="pl-1">or drag and drop</p>
            </div>
            <p class="text-xs text-gray-500">PNG, JPG, GIF up to 5MB</p>
          </div>
        </div>

        <button {disabled} class="button  ">Submit</button>
      </form>
    </div>
  </div>
</div>

<style lang="postcss">
  button {
    @apply mx-auto flex w-2/3 items-center justify-center rounded-md border border-transparent bg-indigo-600 py-2 px-4 text-sm font-medium text-white shadow-sm  shadow-lg focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2 disabled:cursor-not-allowed;
  }
</style>
