<!DOCTYPE html>
<html lang="ru" id="html-lang">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Тестовая страница — Свяжитесь с нами</title>
  <link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  <style>
    .lang-btn {
      padding: 0.2rem 0.5rem;
      border: 1px solid #2F855A;
      border-radius: 0.25rem;
      color: #2F855A;
      font-size: 0.75rem;
      transition: all 0.2s;
    }
    .lang-btn.active, .lang-btn:hover {
      background-color: #2F855A;
      color: white;
    }
    .header-cta {
      padding: 0.6rem 1.2rem;
      font-size: 0.875rem;
      background-color: #2F855A;
      color: white;
      border-radius: 0.25rem;
      transition: background-color 0.2s;
      font-weight: 600;
    }
    .header-cta:hover {
      background-color: #1F6140;
    }
    .modal {
      display: none;
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background-color: rgba(0, 0, 0, 0.5);
      justify-content: center;
      align-items: center;
      z-index: 1000;
    }
    .modal-content {
      background-color: white;
      padding: 2rem;
      border-radius: 0.5rem;
      max-width: 500px;
      width: 90%;
      position: relative;
    }
    .modal-close {
      position: absolute;
      top: 1rem;
      right: 1rem;
      font-size: 1.5rem;
      cursor: pointer;
      color: #4B5563;
    }
    .modal-close:hover {
      color: #2F855A;
    }
    .custom-focus-ring:focus {
      outline: none;
      box-shadow: 0 0 0 2px #2F855A;
    }
    .custom-bg {
      background-color: #2F855A;
    }
    .custom-bg-hover:hover {
      background-color: #1F6140;
    }
  </style>
</head>
<body class="font-sans antialiased bg-gray-100">
  <!-- Header -->
  <header class="bg-white shadow sticky top-0 z-50">
    <nav class="container mx-auto px-4 py-3 flex justify-between items-center">
      <a href="#" class="text-xl font-bold text-[#2F855A]">NaPol.kz</a>
      <div class="flex items-center space-x-3">
        <div class="flex space-x-1">
          <button class="lang-btn active" data-lang="ru">RU</button>
          <button class="lang-btn" data-lang="kk">KZ</button>
        </div>
        <button id="open-modal" class="header-cta" data-lang-key="hero-calculate">Рассчитать стоимость</button>
      </div>
    </nav>
  </header>

  <!-- Modal -->
  <div id="modal" class="modal">
    <div class="modal-content">
      <span class="modal-close">×</span>
      <h2 class="text-2xl font-bold mb-4" data-lang-key="contact-title">Свяжитесь с нами</h2>
      <div class="space-y-4">
        <div>
          <label for="modal-name" class="block text-gray-700" data-lang-key="form-name">Имя</label>
          <input type="text" id="modal-name" class="w-full px-4 py-2 border rounded-lg custom-focus-ring" required>
        </div>
        <div>
          <label for="modal-phone" class="block text-gray-700" data-lang-key="form-phone">Телефон</label>
          <input type="tel" id="modal-phone" class="w-full px-4 py-2 border rounded-lg custom-focus-ring" required>
        </div>
        <button id="modal-submit" class="w-full custom-bg text-white px-4 py-2 rounded-lg custom-bg-hover" data-lang-key="form-submit">Отправить</button>
      </div>
    </div>
  </div>

  <!-- Contact Form -->
  <section id="contact" class="py-16 bg-gray-200">
    <div class="container mx-auto px-4">
      <h2 class="text-3xl font-bold text-center mb-8" data-lang-key="contact-title">Свяжитесь с нами</h2>
      <div class="max-w-lg mx-auto bg-white p-8 rounded-lg shadow">
        <div class="space-y-4">
          <div>
            <label for="name" class="block text-gray-700" data-lang-key="form-name">Имя</label>
            <input type="text" id="name" class="w-full px-4 py-2 border rounded-lg custom-focus-ring" required>
          </div>
          <div>
            <label for="phone" class="block text-gray-700" data-lang-key="form-phone">Телефон</label>
            <input type="tel" id="phone" class="w-full px-4 py-2 border rounded-lg custom-focus-ring" required>
          </div>
          <button id="submit-form" class="w-full custom-bg text-white px-4 py-2 rounded-lg custom-bg-hover" data-lang-key="form-submit">Отправить</button>
        </div>
      </div>
    </div>
  </section>

  <!-- JavaScript -->
  <script>
    const translations = {
      ru: {
        'hero-calculate': 'Рассчитать стоимость',
        'contact-title': 'Свяжитесь с нами',
        'form-name': 'Имя',
        'form-phone': 'Телефон',
        'form-submit': 'Отправить',
        'form-success': 'Спасибо, {name}! Мы свяжемся с вами по телефону {phone}.',
        'form-error': 'Пожалуйста, заполните имя и телефон.',
        'form-submit-error': 'Ошибка отправки данных. Попробуйте снова.',
        'form-invalid-phone': 'Введите корректный номер телефона.'
      },
      kk: {
        'hero-calculate': 'Құнын есептеу',
        'contact-title': 'Бізбен байланысыңыз',
        'form-name': 'Аты',
        'form-phone': 'Телефон',
        'form-submit': 'Жіберу',
        'form-success': 'Рақмет, {name}! Біз сізге {phone} телефоны арқылы хабарласамыз.',
        'form-error': 'Аты мен телефонды толтырыңыз.',
        'form-submit-error': 'Деректерді жіберу қатесі. Қайтадан көріңіз.',
        'form-invalid-phone': 'Дұрыс телефон нөмірін енгізіңіз.'
      }
    };

    const langButtons = document.querySelectorAll('.lang-btn');
    const htmlLang = document.getElementById('html-lang');

    function setLanguage(lang) {
      localStorage.setItem('language', lang);
      htmlLang.setAttribute('lang', lang === 'ru' ? 'ru' : 'kk');
      document.querySelectorAll('[data-lang-key]').forEach(element => {
        const key = element.getAttribute('data-lang-key');
        if (translations[lang][key]) {
          element.textContent = translations[lang][key];
        }
      });
      langButtons.forEach(btn => {
        btn.classList.toggle('active', btn.getAttribute('data-lang') === lang);
      });
    }

    langButtons.forEach(button => {
      button.addEventListener('click', () => {
        const lang = button.getAttribute('data-lang');
        setLanguage(lang);
      });
    });

    const savedLang = localStorage.getItem('language') || 'ru';
    setLanguage(savedLang);

    // Modal functionality
    const modal = document.getElementById('modal');
    const openModalBtn = document.getElementById('open-modal');
    const closeModalBtn = document.querySelector('.modal-close');
    const modalSubmitBtn = document.getElementById('modal-submit');

    openModalBtn.addEventListener('click', () => {
      modal.style.display = 'flex';
    });

    closeModalBtn.addEventListener('click', () => {
      modal.style.display = 'none';
    });

    window.addEventListener('click', (e) => {
      if (e.target === modal) {
        modal.style.display = 'none';
      }
    });

    // Form submission handler
    function handleFormSubmit(nameInput, phoneInput, successCallback) {
      const name = nameInput.value.trim();
      const phone = phoneInput.value.trim();
      const currentLang = localStorage.getItem('language') || 'ru';
      const phoneRegex = /^\+?[1-9]\d{1,14}$/;

      if (!name || !phone) {
        alert(translations[currentLang]['form-error']);
        return;
      }

      if (!phoneRegex.test(phone)) {
        alert(translations[currentLang]['form-invalid-phone']);
        return;
      }

      const now = new Date();
      const timestamp = now.toLocaleString('ru-RU', { timeZone: 'Asia/Almaty' });

      const formData = new URLSearchParams();
      formData.append('name', name);
      formData.append('phone', phone);
      formData.append('timestamp', timestamp);

      const googleScriptUrl = 'https://script.google.com/macros/s/AKfycbyy4BY5fj3RFRtys0OV0CnjmZNlq7r8jmPSOhQ0LTk2IuNw11Bnu4v7SiUJSkIRaW4r/exec';

      fetch(googleScriptUrl, {
        method: 'POST',
        body: formData
      })
        .then(response => {
          if (!response.ok) {
            throw new Error(`Сервер вернул статус: ${response.status}`);
          }
          return response.json();
        })
        .then(data => {
          if (data.status === 'success') {
            const successMessage = translations[currentLang]['form-success']
              .replace('{name}', name)
              .replace('{phone}', phone);
            alert(successMessage);
            nameInput.value = '';
            phoneInput.value = '';
            successCallback();
          } else {
            throw new Error(data.message || 'Неизвестная ошибка сервера');
          }
        })
        .catch(error => {
          console.error('Ошибка отправки:', error);
          alert(translations[currentLang]['form-submit-error']);
        });
    }

    // Modal form submission
    modalSubmitBtn.addEventListener('click', () => {
      handleFormSubmit(
        document.getElementById('modal-name'),
        document.getElementById('modal-phone'),
        () => { modal.style.display = 'none'; }
      );
    });

    // Contact form submission
    document.getElementById('submit-form').addEventListener('click', () => {
      handleFormSubmit(
        document.getElementById('name'),
        document.getElementById('phone'),
        () => {}
      );
    });
  </script>
</body>
</html>
