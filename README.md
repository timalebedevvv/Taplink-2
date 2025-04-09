
<style>
  .scrolling-container {
    position: relative;
    height: 200vh; /* Увеличиваем высоту контейнера для прокрутки */
    width: 100%;
    overflow: hidden;
  }

  .star {
    position: absolute;
    font-size: 100px; /* Размер звезды */
    color: #ffcc00;
    top: 0;
    left: 0;
    transition: transform 0.1s ease-out;
  }
</style>

<div class="scrolling-container">
  <div class="star" id="star">*</div>
</div>

<script>
  window.addEventListener("scroll", () => {
    const star = document.getElementById("star");
    const scrollY = window.scrollY;
    const scrollX = window.scrollX;

    // Максимальное смещение по диагонали
    const maxOffset = 50;

    // Двигаем звезду пропорционально прокрутке
    const moveX = (scrollX * maxOffset) / 100;
    const moveY = (scrollY * maxOffset) / 100;

    // Применяем смещение
    star.style.transform = `translate(${moveX}px, ${moveY}px)`;
  });
</script>
