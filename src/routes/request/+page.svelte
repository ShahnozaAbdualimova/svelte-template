<script>
  import RequestForm from '$lib/components/RequestForm.svelte';
  import Preview from '$lib/components/Preview.svelte';
</script>

<div class="flex h-screen">
  <!-- Chap tomon (So‘rov va inputlar) -->
  <div class="w-1/2 p-6 bg-gray-100">
    <RequestForm />
  </div>

  <!-- O'ng tomon (Rasmlar yoki gif tavsiflar) -->
  <div class="w-1/2 p-6 bg-white flex items-center justify-center">
    <Preview />
  </div>
</div>
