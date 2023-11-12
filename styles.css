// Отримання елемента для вставки часового відліку
const countdownElement = document.getElementById('countdown');

// Дата, до якої відбувається відлік
const targetDate = new Date('2023-12-27T17:00:00+01:00'); // Берлінський час

// Оновлення відліку кожної секунди
function updateCountdown() {
    const currentDate = new Date();
    const timeDifference = targetDate - currentDate;

    if (timeDifference > 0) {
        const seconds = Math.floor(timeDifference / 1000) % 60;
        const minutes = Math.floor(timeDifference / (1000 * 60)) % 60;
        const hours = Math.floor(timeDifference / (1000 * 60 * 60)) % 24;
        const days = Math.floor(timeDifference / (1000 * 60 * 60 * 24));

        // Виведення відліку
        countdownElement.innerHTML = `${days}д ${hours}г ${minutes}хв ${seconds}с`;
    } else {
        // Виведення повідомлення, якщо термін вже минув
        countdownElement.innerHTML = 'Термін вже минув';
    }
}

// Виклик функції для оновлення відліку кожну секунду
setInterval(updateCountdown, 1000);

// Виклик функції для оновлення відліку при завантаженні сторінки
updateCountdown();