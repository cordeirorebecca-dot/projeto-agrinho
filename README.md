# let currentSlide = 0;
const slides = document.querySelectorAll('.slide');

function showSlide(index) {
    // Remove a classe 'active' de todos os slides
    slides.forEach(slide => slide.classList.remove('active'));
    
    // Ajusta o índice se passar do limite
    if (index >= slides.length) currentSlide = 0;
    if (index < 0) currentSlide = slides.length - 1;
    
    // Adiciona a classe 'active' no slide atual
    slides[currentSlide].classList.add('active');
}

function nextSlide() {
    currentSlide++;
    showSlide(currentSlide);
}

function prevSlide() {
    currentSlide--;
    showSlide(currentSlide);
}

// Atalho: Mudar slide com as setas do teclado
document.addEventListener('keydown', (e) => {
    if (e.key === "ArrowRight") nextSlide();
    if (e.key === "ArrowLeft") prevSlide();
});
