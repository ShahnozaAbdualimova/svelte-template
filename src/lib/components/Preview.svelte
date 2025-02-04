<script>
  let images = [
    { src: "https://i.pinimg.com/736x/c9/8b/80/c98b809f148ab60e13e8d7c99cd17891.jpg", text: "Portfolio saytlari shaxsiy brendingizni yaratishda yordam beradi." },
    { src: "https://i.pinimg.com/736x/c9/8b/80/c98b809f148ab60e13e8d7c99cd17891.jpg", text: "E-commerce do‘konlari mahsulotlarni onlayn sotish uchun kerak." },
    { src: "https://i.pinimg.com/736x/c9/8b/80/c98b809f148ab60e13e8d7c99cd17891.jpg", text: "Bloglar kontent yaratish va foydalanuvchilar bilan bo‘lishish uchun ishlatiladi." }
  ];
</script>

<div class="flex flex-col items-center space-y-4">
  {#each images as img}
    <div class="text-center">
      <img src={img.src} alt="Preview" class="w-64 rounded-lg shadow" />
      <p class="text-gray-600 mt-2">{img.text}</p>
    </div>
  {/each}
</div>
