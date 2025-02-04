<script>
  let websiteName = "";
  let description = "";
  let websiteType = "portfolio";
  let color = "#3498db";
  let responsive = false;
</script>

<form class="space-y-4">
  <h2 class="text-xl font-bold">Sayt yaratish uchun ma'lumotlar</h2>

  <!-- Websayt nomi -->
  <div>
    <label class="block font-medium">Websayt nomi:</label>
    <input type="text" bind:value={websiteName} class="w-full p-2 border rounded" placeholder="Misol: MyPortfolio" />
  </div>

  <!-- Tavsif -->
  <div>
    <label class="block font-medium">Tavsif:</label>
    <textarea bind:value={description} class="w-full p-2 border rounded" rows="3" placeholder="Sayt haqida qisqa tavsif"></textarea>
  </div>

  <!-- Websayt turi -->
  <div>
    <label class="block font-medium">Websayt turi:</label>
    <select bind:value={websiteType} class="w-full p-2 border rounded">
      <option value="portfolio">Portfolio</option>
      <option value="blog">Blog</option>
      <option value="e-commerce">E-commerce</option>
      <option value="company">Korporativ</option>
      <option value="custom">Boshqasi</option>
    </select>
  </div>

  <!-- Rang tanlash -->
  <div>
    <label class="block font-medium">Asosiy rang:</label>
    <input type="color" bind:value={color} class="w-full h-10 border rounded cursor-pointer" />
  </div>

  <!-- Responsiv bo‘lishi kerakmi? -->
  <div class="flex items-center">
    <input type="checkbox" bind:checked={responsive} class="mr-2" />
    <label>Mobil uchun moslashtirish kerak</label>
  </div>

  <!-- Submit tugmasi -->
  <button type="submit" class="w-full p-2 bg-blue-500 text-white rounded hover:bg-blue-600">
    Yuborish
  </button>
</form>
