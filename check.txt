// Проверка наличия таймера #time_remaining
            try {
                log("Проверка наличия таймера #time_remaining...");
                await waitForVisibleElement(CONFIG.SELECTORS.TIMER, CONFIG.DELAYS.WAIT_FOR_TIMER, CONFIG.DELAYS.MAX_TIMER_CHECK_ATTEMPTS);
                log("Таймер найден. Продолжаем выполнение.");
            } catch (timerError) {
                log("Таймер не найден. Перезагружаем страницу...", 'error');
                location.reload(); // Перезагрузка страницы
                return; // Выход из текущего цикла, так как страница перезагрузится
            }