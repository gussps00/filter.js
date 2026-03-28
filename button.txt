const buttons = document.querySelectorAll('.category-menu button');
const items = document.querySelectorAll('.my-item');

buttons.forEach(button => {
  button.addEventListener('click', () => {
    // active 버튼 처리
    buttons.forEach(btn => btn.classList.remove('active'));
    button.classList.add('active');

    const category = button.dataset.category;

    items.forEach(item => {
      if (category === 'all' || item.dataset.category === category) {
        item.style.display = 'block';
      } else {
        item.style.display = 'none';
      }
    });
  });
});