<div align="center">

<h4>Министерство образования, науки и молодежной политики Республики Коми</h4>
<h4>ГПОУ «Сыктывкарский политехнический техникум»</h4>

<br>

<h2>Курсовая работа</h2>

<br>

<h2>Разработка базы данных для учета домашних финансов</h2>

<br>

</div>

<br><br>

<div align="right">

<b>выполнил:</b><br>
студент 4 курса<br>
414 группы<br>
Малыгин Станислав Александрович

<br><br>

<b>проверил:</b><br>
Пунгин И.В.

<br><br>

<b>дата проверки:</b> ___________

</div>

<br><br><br>

<div align="center">
Сыктывкар, 2025 г.

</div>
---
<h2>Содержание</h2>

<ul>
  <li><a href="#введение">Введение</a></li>
  <li>
<a href="#1-анализ-предметной-области-постановка-задачи">
      1. Анализ предметной области. Постановка задачи
    </a>
    <ul>
      <li>
        <a href="#11-описание-предметной-области-и-функции-решаемых-задач">
          1.1. Описание предметной области и функции решаемых задач
        </a>
      </li>
      <li>
        <a href="#12-перечень-входных-данных">
          1.2. Перечень входных данных
        </a>
      </li>
      <li>
        <a href="#13-перечень-выходных-данных">
          1.3. Перечень выходных данных
        </a>
      </li>
      <li>
        <a href="#14-ограничения-предметной-области-если-таковые-имеются">
          1.4. Ограничения предметной области (если таковые имеются)
        </a>
      </li>
      <li>
        <a href="#15-взаимодействие-с-другими-программами">
          1.5. Взаимодействие с другими программами
        </a>
      </li>
    </ul>
  </li>

  <li>
    <a href="#2-инфологическая-концептуальная-модель-базы-данных">
      2. Инфологическая (концептуальная) модель базы данных
    </a>
    <ul>
      <li>
        <a href="#21-выделение-информационных-объектов">
          2.1. Выделение информационных объектов
        </a>
      </li>
      <li>
        <a href="#22-определение-атрибутов-объектов">
          2.2. Определение атрибутов объектов
        </a>
      </li>
      <li>
        <a href="#23-определение-отношений-и-мощности-отношений-между-объектами">
          2.3. Определение отношений и мощности отношений между объектами
        </a>
      </li>
      <li>
        <a href="#24-построение-концептуальной-модели">
          2.4. Построение концептуальной модели
        </a>
      </li>
    </ul>
  </li>

  <li><a href="#3-логическая-структура-бд">3. Логическая структура БД</a></li>
  <li><a href="#4-физическая-структура-базы-данных">4. Физическая структура базы данных</a></li>

  <li>
    <a href="#5-реализация-проекта-в-среде-конкретной-субд">
      5. Реализация проекта в среде конкретной СУБД
    </a>
    <ul>
      <li><a href="#51-создание-таблиц">5.1. Создание таблиц</a></li>
      <li><a href="#52-создание-запросов">5.2. Создание запросов</a></li>
      <li><a href="#53-разработка-интерфейса">5.3. Разработка интерфейса</a></li>
      <li><a href="#54-назначение-прав-доступа">5.4. Назначение прав доступа</a></li>
      <li><a href="#55-создание-индексов">5.5. Создание индексов</a></li>
      <li>
        <a href="#56-разработка-стратегии-резервного-копирования-базы-данных">
          5.6. Разработка стратегии резервного копирования базы данных
        </a>
      </li>
    </ul>
  </li>

  <li><a href="#заключение">Заключение</a></li>
  <li><a href="#список-использованных-источников">Список использованных источников</a></li>
</ul>

---

<h2 id="введение">Введение</h2>

<p>В современном мире музыкальные инструменты, особенно гитары, пользуются постоянным спросом как среди профессиональных музыкантов, так и среди любителей. Магазин гитар — это специализированное торговое предприятие, которое требует эффективной системы учета товаров, клиентов, поставщиков и продаж.</p>

<p>Автоматизация процессов учета в магазине гитар является важной задачей, которая позволяет оптимизировать работу, снизить вероятность ошибок при учете товаров, улучшить обслуживание клиентов и повысить общую эффективность бизнеса. Ключевым элементом такой автоматизации является база данных, обеспечивающая надежное хранение информации, ее целостность и удобство обработки.</p>

<p><strong>Целью данной курсовой работы</strong> является проектирование и реализация базы данных для магазина гитар с использованием системы управления базами данных PostgreSQL.</p>

<p><strong>Задачи работы:</strong></p>
<ul>
    <li>Изучить предметную область магазина гитар</li>
    <li>Разработать концептуальную, логическую и физическую модели базы данных</li>
    <li>Реализовать базу данных в СУБД PostgreSQL</li>
    <li>Разработать веб-интерфейс для работы с системой</li>
    <li>Обеспечить безопасность данных и резервное копирование</li>
</ul>

<p><strong>Актуальность темы</strong> обусловлена растущим спросом на музыкальные инструменты и необходимостью автоматизации процессов в специализированных магазинах для повышения их конкурентоспособности.</p>

<div class="page-break"></div>

<h2 id="1-анализ-предметной-области">1. Анализ предметной области</h2>

<h3 id="11-описание-предметной-области">1.1. Описание предметной области</h3>

<p>Магазин гитар специализируется на продаже акустических, электрических, бас-гитар, а также сопутствующих товаров: струн, медиаторов, кабелей и аксессуаров. Основные бизнес-процессы включают:</p>
<ul>
    <li>Учет товаров (гитары, струны, аксессуары)</li>
    <li>Управление поставками от производителей и дистрибьюторов</li>
    <li>Продажи товаров клиентам</li>
    <li>Учет клиентов и их покупок</li>
    <li>Управление сотрудниками (продавцы, администраторы)</li>
    <li>Формирование отчетов по продажам, остаткам, прибыли</li>
</ul>

<p>Система должна обеспечивать полный цикл учета: от поступления гитар на склад до их продажи конечному покупателю, включая возможность бронирования инструментов и учета предзаказов.</p>

<h3 id="12-перечень-входных-данных">1.2. Перечень входных данных</h3>

<ul>
    <li><strong>Данные о гитарах:</strong> производитель, модель, тип (акустическая/электрическая), год выпуска, страна производства, материал корпуса, цвет, количество ладов, цена, количество на складе</li>
    <li><strong>Данные о поставщиках:</strong> название, контактное лицо, телефон, email, адрес, рейтинг</li>
    <li><strong>Данные о клиентах:</strong> ФИО, телефон, email, адрес, история покупок</li>
    <li><strong>Данные о сотрудниках:</strong> ФИО, должность, телефон, email, дата найма, зарплата</li>
    <li><strong>Данные о продажах:</strong> дата, клиент, продавец, список товаров, общая сумма</li>
    <li><strong>Данные о поставках:</strong> дата, поставщик, список товаров, общая сумма</li>
    <li><strong>Данные о категориях товаров:</strong> гитары, струны, медиаторы, чехлы, усилители</li>
</ul>

<h3 id="13-перечень-выходных-данных">1.3. Перечень выходных данных</h3>

<ul>
    <li>Отчеты по продажам за период (ежедневные, еженедельные, месячные)</li>
    <li>Отчеты по остаткам товаров на складе</li>
    <li>Отчеты по популярности брендов и моделей гитар</li>
    <li>Финансовые отчеты (выручка, прибыль, затраты)</li>
    <li>История заказов клиентов</li>
    <li>Рейтинг продавцов по объему продаж</li>
    <li>Прогнозы по товарам с низким остатком</li>
</ul>

<h3 id="14-ограничения-предметной-области">1.4. Ограничения предметной области</h3>

<ul>
    <li>Один поставщик может поставлять несколько моделей гитар</li>
    <li>Гитара может иметь только одного производителя</li>
    <li>Продажа может содержать несколько товаров (гитара + аксессуары)</li>
    <li>Клиент может совершать несколько покупок</li>
    <li>Сотрудник может обслуживать несколько продаж</li>
    <li>Цена гитары не может быть отрицательной</li>
    <li>Количество товара на складе не может быть отрицательным</li>
</ul>

<h3 id="15-взаимодействие-с-другими-программами">1.5. Взаимодействие с другими программами</h3>

<ul>
    <li>Интеграция с онлайн-кассой для фискальных операций</li>
    <li>Экспорт данных в бухгалтерские системы (1С)</li>
    <li>Интеграция с системами онлайн-оплаты</li>
    <li>Подключение к CRM-системе для управления клиентами</li>
    <li>API для мобильного приложения продавцов</li>
</ul>

<div class="page-break"></div>

<h2 id="2-концептуальная-модель">2. Концептуальная модель базы данных</h2>

<h3 id="21-выделение-информационных-объектов">2.1. Выделение информационных объектов</h3>

<p>Основные сущности (информационные объекты) системы:</p>
<ol>
    <li><strong>Гитара (Guitar)</strong> - основной товар магазина</li>
    <li><strong>Производитель (Manufacturer)</strong> - бренд гитары</li>
    <li><strong>Категория (Category)</strong> - тип товара (гитара, струны, аксессуар)</li>
    <li><strong>Поставщик (Supplier)</strong> - компания-поставщик товаров</li>
    <li><strong>Клиент (Client)</strong> - покупатель товаров</li>
    <li><strong>Сотрудник (Employee)</strong> - работник магазина</li>
    <li><strong>Продажа (Sale)</strong> - факт продажи товаров</li>
    <li><strong>Позиция продажи (SaleItem)</strong> - товар в продаже</li>
    <li><strong>Поставка (Delivery)</strong> - поступление товаров от поставщика</li>
    <li><strong>Позиция поставки (DeliveryItem)</strong> - товар в поставке</li>
</ol>

<h3 id="22-определение-атрибутов-объектов">2.2. Определение атрибутов объектов</h3>

<table>
    <tr>
        <th>Сущность</th>
        <th>Атрибуты</th>
    </tr>
    <tr>
        <td>Гитара</td>
        <td>id, название, производитель_id, тип, год выпуска, материал корпуса, цвет, количество ладов, цена, количество на складе</td>
    </tr>
    <tr>
        <td>Производитель</td>
        <td>id, название, страна, год основания</td>
    </tr>
    <tr>
        <td>Категория</td>
        <td>id, название, описание</td>
    </tr>
    <tr>
        <td>Поставщик</td>
        <td>id, название, контактное лицо, телефон, email, адрес</td>
    </tr>
    <tr>
        <td>Клиент</td>
        <td>id, ФИО, телефон, email, адрес, дата регистрации</td>
    </tr>
    <tr>
        <td>Сотрудник</td>
        <td>id, ФИО, должность, телефон, email, дата найма, зарплата</td>
    </tr>
    <tr>
        <td>Продажа</td>
        <td>id, дата, клиент_id, сотрудник_id, общая сумма</td>
    </tr>
    <tr>
        <td>Позиция продажи</td>
        <td>id, продажа_id, гитара_id, количество, цена</td>
    </tr>
    <tr>
        <td>Поставка</td>
        <td>id, дата, поставщик_id, общая сумма</td>
    </tr>
    <tr>
        <td>Позиция поставки</td>
        <td>id, поставка_id, гитара_id, количество, цена закупки</td>
    </tr>
</table>

<h3 id="23-определение-отношений">2.3. Определение отношений</h3>

<ul>
    <li><strong>Производитель → Гитары</strong> (1:N) - один производитель выпускает много гитар</li>
    <li><strong>Поставщик → Поставки</strong> (1:N) - один поставщик осуществляет много поставок</li>
    <li><strong>Клиент → Продажи</strong> (1:N) - один клиент совершает много покупок</li>
    <li><strong>Сотрудник → Продажи</strong> (1:N) - один сотрудник обслуживает много продаж</li>
    <li><strong>Продажа → Позиции продажи</strong> (1:N) - одна продажа содержит много товаров</li>
    <li><strong>Поставка → Позиции поставки</strong> (1:N) - одна поставка содержит много товаров</li>
    <li><strong>Гитара → Позиции продаж/поставок</strong> (1:N) - одна гитара может быть в разных продажах/поставках</li>
</ul>

<h3 id="24-построение-концептуальной-модели">2.4. Построение концептуальной модели (ER-диаграмма)</h3>

<div class="mermaid">
ER-диаграмма:
┌─────────────────┐      ┌─────────────────┐
│   Производитель │      │    Категория    │
├─────────────────┤      ├─────────────────┤
│ id (PK)         │      │ id (PK)         │
│ название        │      │ название        │
│ страна          │      │ описание        │
│ год_основания   │      └─────────────────┘
└────────┬────────┘               │
         │ 1                       │ 1
         │ N                       │ N
┌────────▼────────┐      ┌────────▼────────┐
│     Гитара      │      │   Поставщик     │
├─────────────────┤      ├─────────────────┤
│ id (PK)         │      │ id (PK)         │
│ название        │      │ название        │
│ производитель_id│      │ контактное_лицо │
│ тип             │      │ телефон         │
│ год_выпуска     │      │ email           │
│ материал        │      │ адрес           │
│ цвет            │      └────────┬────────┘
│ лады            │               │ 1
│ цена            │               │ N
│ количество      │      ┌────────▼────────┐
└────────┬────────┘      │    Поставка     │
         │ N             ├─────────────────┤
         │ 1             │ id (PK)         │
┌────────▼────────┐      │ дата            │
│ Позиция продажи │      │ поставщик_id    │
├─────────────────┤      │ общая_сумма     │
│ id (PK)         │      └────────┬────────┘
│ продажа_id      │               │ 1
│ гитара_id       │               │ N
│ количество      │      ┌────────▼────────┐
│ цена            │      │Позиция поставки │
└────────┬────────┘      ├─────────────────┤
         │ N             │ id (PK)         │
         │ 1             │ поставка_id     │
┌────────▼────────┐      │ гитара_id       │
│    Продажа      │      │ количество      │
├─────────────────┤      │ цена_закупки    │
│ id (PK)         │      └─────────────────┘
│ дата            │
│ клиент_id       │      ┌─────────────────┐
│ сотрудник_id    │      │    Клиент       │
│ общая_сумма     │      ├─────────────────┤
└────────┬────────┘      │ id (PK)         │
         │ N             │ ФИО             │
         │ 1             │ телефон         │
┌────────▼────────┐      │ email           │
│   Сотрудник     │      │ адрес           │
├─────────────────┤      │ дата_регистрации│
│ id (PK)         │      └─────────────────┘
│ ФИО             │
│ должность       │
│ телефон         │
│ email           │
│ дата_найма      │
│ зарплата        │
└─────────────────┘
</div>

<div class="page-break"></div>

<h2 id="3-логическая-структура">3. Логическая структура БД</h2>

<p>Логическая модель представляет собой реляционную схему базы данных в третьей нормальной форме (3НФ).</p>

<h3>3.1. Таблицы базы данных</h3>

<pre><code>
-- Таблица производителей
CREATE TABLE manufacturers (
    id SERIAL PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    country VARCHAR(50),
    founded_year INTEGER
);

-- Таблица гитар
CREATE TABLE guitars (
    id SERIAL PRIMARY KEY,
    name VARCHAR(200) NOT NULL,
    manufacturer_id INTEGER REFERENCES manufacturers(id),
    type VARCHAR(50) NOT NULL, -- acoustic/electric/bass
    year INTEGER,
    body_material VARCHAR(100),
    color VARCHAR(50),
    frets INTEGER,
    price DECIMAL(10,2) NOT NULL,
    quantity INTEGER DEFAULT 0
);

-- Таблица категорий товаров
CREATE TABLE categories (
    id SERIAL PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    description TEXT
);

-- Таблица поставщиков
CREATE TABLE suppliers (
    id SERIAL PRIMARY KEY,
    name VARCHAR(200) NOT NULL,
    contact_person VARCHAR(100),
    phone VARCHAR(20),
    email VARCHAR(100),
    address TEXT
);

-- Таблица клиентов
CREATE TABLE clients (
    id SERIAL PRIMARY KEY,
    full_name VARCHAR(200) NOT NULL,
    phone VARCHAR(20),
    email VARCHAR(100),
    address TEXT,
    registration_date DATE DEFAULT CURRENT_DATE
);

-- Таблица сотрудников
CREATE TABLE employees (
    id SERIAL PRIMARY KEY,
    full_name VARCHAR(200) NOT NULL,
    position VARCHAR(100),
    phone VARCHAR(20),
    email VARCHAR(100),
    hire_date DATE NOT NULL,
    salary DECIMAL(10,2)
);

-- Таблица продаж
CREATE TABLE sales (
    id SERIAL PRIMARY KEY,
    sale_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    client_id INTEGER REFERENCES clients(id),
    employee_id INTEGER REFERENCES employees(id),
    total_amount DECIMAL(10,2)
);

-- Таблица позиций продаж
CREATE TABLE sale_items (
    id SERIAL PRIMARY KEY,
    sale_id INTEGER REFERENCES sales(id) ON DELETE CASCADE,
    guitar_id INTEGER REFERENCES guitars(id),
    quantity INTEGER NOT NULL,
    price DECIMAL(10,2) NOT NULL
);

-- Таблица поставок
CREATE TABLE deliveries (
    id SERIAL PRIMARY KEY,
    delivery_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    supplier_id INTEGER REFERENCES suppliers(id),
    total_amount DECIMAL(10,2)
);

-- Таблица позиций поставок
CREATE TABLE delivery_items (
    id SERIAL PRIMARY KEY,
    delivery_id INTEGER REFERENCES deliveries(id) ON DELETE CASCADE,
    guitar_id INTEGER REFERENCES guitars(id),
    quantity INTEGER NOT NULL,
    purchase_price DECIMAL(10,2) NOT NULL
);
</code></pre>

<h3>3.2. Нормализация</h3>
<p>Все таблицы приведены к 3НФ:
<ul>
    <li>Устранены повторяющиеся группы данных</li>
    <li>Все неключевые атрибуты зависят только от первичного ключа</li>
    <li>Отсутствуют транзитивные зависимости</li>
</ul>

<div class="page-break"></div>

<h2 id="4-физическая-структура">4. Физическая структура базы данных</h2>

<h3>4.1. Выбор СУБД</h3>
<p>Выбрана СУБД <strong>PostgreSQL 14+</strong> в связи с ее надежностью, производительностью и поддержкой расширенных функций.</p>

<h3>4.2. Типы данных</h3>
<table>
    <tr><th>Тип данных</th><th>Применение</th></tr>
    <tr><td>SERIAL</td><td>Автоинкрементные первичные ключи</td></tr>
    <tr><td>INTEGER</td><td>Количественные данные (лады, год)</td></tr>
    <tr><td>DECIMAL(10,2)</td><td>Денежные значения с точностью до копеек</td></tr>
    <tr><td>VARCHAR</td><td>Текстовые данные переменной длины</td></tr>
    <tr><td>TEXT</td><td>Длинные текстовые описания</td></tr>
    <tr><td>DATE/TIMESTAMP</td><td>Даты и время</td></tr>
</table>

<h3>4.3. Стратегия резервного копирования</h3>
<ul>
    <li>Ежедневные полные резервные копии в 02:00</li>
    <li>Инкрементные копии каждые 4 часа</li>
    <li>Хранение на отдельном сервере и облаке</li>
    <li>Автоматическое тестирование восстановления</li>
</ul>

<h3>4.4. Безопасность данных</h3>
<ul>
    <li>Шифрование паролей с использованием bcrypt</li>
    <li>Ролевая модель доступа:
        <ul>
            <li>admin - полный доступ</li>
            <li>manager - управление товарами и продажами</li>
            <li>seller - только продажи</li>
            <li>viewer - только просмотр отчетов</li>
        </ul>
    </li>
    <li>SSL-шифрование подключений</li>
</ul>

<div class="page-break"></div>

<h2 id="5-реализация-в-postgresql">5. Реализация проекта в среде PostgreSQL</h2>

<h3 id="51-создание-таблиц">5.1. Создание таблиц</h3>

<pre><code>
-- Создание базы данных
CREATE DATABASE guitar_shop;

-- Подключение к базе данных
\c guitar_shop;

-- Создание таблицы производителей
CREATE TABLE manufacturers (
    manufacturer_id SERIAL PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    country VARCHAR(50),
    founded_year INTEGER,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Создание таблицы гитар
CREATE TABLE guitars (
    guitar_id SERIAL PRIMARY KEY,
    manufacturer_id INTEGER REFERENCES manufacturers(manufacturer_id),
    model VARCHAR(100) NOT NULL,
    type VARCHAR(20) CHECK (type IN ('acoustic', 'electric', 'bass', 'classical')),
    price NUMERIC(10,2) NOT NULL CHECK (price > 0),
    quantity INTEGER DEFAULT 0 CHECK (quantity >= 0),
    color VARCHAR(50),
    body_material VARCHAR(50),
    neck_material VARCHAR(50),
    frets INTEGER,
    scale_length NUMERIC(4,1),
    year INTEGER,
    description TEXT,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Создание таблицы клиентов
CREATE TABLE clients (
    client_id SERIAL PRIMARY KEY,
    first_name VARCHAR(50) NOT NULL,
    last_name VARCHAR(50) NOT NULL,
    email VARCHAR(100) UNIQUE,
    phone VARCHAR(20),
    address TEXT,
    registration_date DATE DEFAULT CURRENT_DATE,
    discount NUMERIC(3,2) DEFAULT 0.00
);

-- Создание таблицы сотрудников
CREATE TABLE employees (
    employee_id SERIAL PRIMARY KEY,
    first_name VARCHAR(50) NOT NULL,
    last_name VARCHAR(50) NOT NULL,
    position VARCHAR(50) CHECK (position IN ('seller', 'manager', 'admin')),
    email VARCHAR(100) UNIQUE,
    phone VARCHAR(20),
    hire_date DATE NOT NULL,
    salary NUMERIC(10,2) NOT NULL
);

-- Создание таблицы продаж
CREATE TABLE sales (
    sale_id SERIAL PRIMARY KEY,
    client_id INTEGER REFERENCES clients(client_id),
    employee_id INTEGER REFERENCES employees(employee_id),
    sale_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    total_amount NUMERIC(10,2) NOT NULL,
    payment_method VARCHAR(20) CHECK (payment_method IN ('cash', 'card', 'online')),
    status VARCHAR(20) DEFAULT 'completed' CHECK (status IN ('pending', 'completed', 'cancelled'))
);

-- Создание таблицы позиций продаж
CREATE TABLE sale_items (
    sale_item_id SERIAL PRIMARY KEY,
    sale_id INTEGER REFERENCES sales(sale_id) ON DELETE CASCADE,
    guitar_id INTEGER REFERENCES guitars(guitar_id),
    quantity INTEGER NOT NULL CHECK (quantity > 0),
    unit_price NUMERIC(10,2) NOT NULL,
    subtotal NUMERIC(10,2) GENERATED ALWAYS AS (quantity * unit_price) STORED
);

-- Создание таблицы поставщиков
CREATE TABLE suppliers (
    supplier_id SERIAL PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    contact_person VARCHAR(100),
    phone VARCHAR(20),
    email VARCHAR(100),
    address TEXT,
    rating INTEGER CHECK (rating BETWEEN 1 AND 5)
);

-- Создание таблицы поставок
CREATE TABLE deliveries (
    delivery_id SERIAL PRIMARY KEY,
    supplier_id INTEGER REFERENCES suppliers(supplier_id),
    delivery_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    total_amount NUMERIC(10,2) NOT NULL,
    status VARCHAR(20) DEFAULT 'delivered' CHECK (status IN ('ordered', 'shipped', 'delivered'))
);

-- Создание таблицы позиций поставок
CREATE TABLE delivery_items (
    delivery_item_id SERIAL PRIMARY KEY,
    delivery_id INTEGER REFERENCES deliveries(delivery_id) ON DELETE CASCADE,
    guitar_id INTEGER REFERENCES guitars(guitar_id),
    quantity INTEGER NOT NULL CHECK (quantity > 0),
    unit_cost NUMERIC(10,2) NOT NULL
);
</code></pre>

<h3 id="52-создание-запросов">5.2. Создание запросов</h3>

<h4>5.2.1. Запрос на получение продаж за период</h4>
<pre><code>
SELECT 
    s.sale_id,
    s.sale_date,
    c.first_name || ' ' || c.last_name as client,
    e.first_name || ' ' || e.last_name as employee,
    s.total_amount,
    s.payment_method
FROM sales s
JOIN clients c ON s.client_id = c.client_id
JOIN employees e ON s.employee_id = e.employee_id
WHERE s.sale_date BETWEEN '2025-01-01' AND '2025-12-31'
ORDER BY s.sale_date DESC;
</code></pre>

<h4>5.2.2. Запрос на остатки гитар</h4>
<pre><code>
SELECT 
    g.model,
    m.name as manufacturer,
    g.type,
    g.color,
    g.price,
    g.quantity
FROM guitars g
JOIN manufacturers m ON g.manufacturer_id = m.manufacturer_id
WHERE g.quantity > 0
ORDER BY g.quantity DESC;
</code></pre>

<h4>5.2.3. Запрос на топ-продаваемых гитар</h4>
<pre><code>
SELECT 
    g.model,
    m.name as manufacturer,
    COUNT(si.sale_item_id) as total_sold,
    SUM(si.quantity) as units_sold,
    SUM(si.subtotal) as revenue
FROM sale_items si
JOIN guitars g ON si.guitar_id = g.guitar_id
JOIN manufacturers m ON g.manufacturer_id = m.manufacturer_id
GROUP BY g.guitar_id, g.model, m.name
ORDER BY units_sold DESC
LIMIT 10;
</code></pre>

<h4>5.2.4. Триггер для обновления остатков</h4>
<pre><code>
CREATE OR REPLACE FUNCTION update_guitar_quantity()
RETURNS TRIGGER AS $$
BEGIN
    -- При продаже уменьшаем количество
    IF TG_OP = 'INSERT' AND TG_TABLE_NAME = 'sale_items' THEN
        UPDATE guitars 
        SET quantity = quantity - NEW.quantity
        WHERE guitar_id = NEW.guitar_id;
    -- При поставке увеличиваем количество
    ELSIF TG_OP = 'INSERT' AND TG_TABLE_NAME = 'delivery_items' THEN
        UPDATE guitars 
        SET quantity = quantity + NEW.quantity
        WHERE guitar_id = NEW.guitar_id;
    END IF;
    RETURN NEW;
END;
$$ LANGUAGE plpgsql;

-- Триггер для продаж
CREATE TRIGGER trg_sale_item
AFTER INSERT ON sale_items
FOR EACH ROW
EXECUTE FUNCTION update_guitar_quantity();

-- Триггер для поставок
CREATE TRIGGER trg_delivery_item
AFTER INSERT ON delivery_items
FOR EACH ROW
EXECUTE FUNCTION update_guitar_quantity();
</code></pre>

<h3 id="53-разработка-интерфейса">5.3. Разработка интерфейса</h3>
<p>Веб-интерфейс реализован на Flask (Python) с использованием:</p>
<ul>
    <li>HTML/CSS/JavaScript + Bootstrap 5</li>
    <li>Аутентификация через сессии</li>
    <li>Chart.js для графиков и диаграмм</li>
    <li>REST API для мобильного приложения</li>
</ul>

<h3 id="54-назначение-прав-доступа">5.4. Назначение прав доступа</h3>
<pre><code>
-- Создание ролей
CREATE ROLE guitar_admin WITH LOGIN PASSWORD 'admin123';
CREATE ROLE guitar_manager WITH LOGIN PASSWORD 'manager123';
CREATE ROLE guitar_seller WITH LOGIN PASSWORD 'seller123';
CREATE ROLE guitar_viewer WITH LOGIN PASSWORD 'viewer123';

-- Права для администратора
GRANT ALL PRIVILEGES ON ALL TABLES IN SCHEMA public TO guitar_admin;
GRANT ALL PRIVILEGES ON ALL SEQUENCES IN SCHEMA public TO guitar_admin;

-- Права для менеджера
GRANT SELECT, INSERT, UPDATE ON guitars, manufacturers, suppliers, deliveries TO guitar_manager;
GRANT SELECT ON sales, clients, employees TO guitar_manager;

-- Права для продавца
GRANT INSERT, SELECT ON sales, sale_items TO guitar_seller;
GRANT SELECT ON guitars, clients TO guitar_seller;

-- Права для просмотра
GRANT SELECT ON guitars, manufacturers, sales TO guitar_viewer;
</code></pre>

<h3 id="55-создание-индексов">5.5. Создание индексов</h3>
<pre><code>
-- Индексы для ускорения поиска
CREATE INDEX idx_guitars_manufacturer ON guitars(manufacturer_id);
CREATE INDEX idx_guitars_price ON guitars(price);
CREATE INDEX idx_sales_date ON sales(sale_date);
CREATE INDEX idx_sales_client ON sales(client_id);
CREATE INDEX idx_sales_employee ON sales(employee_id);
CREATE INDEX idx_clients_email ON clients(email);
CREATE INDEX idx_employees_position ON employees(position);

-- Составной индекс для часто используемых запросов
CREATE INDEX idx_guitars_search ON guitars(model, type, price);
</code></pre>

<h3 id="56-резервное-копирование">5.6. Разработка стратегии резервного копирования</h3>
<pre><code>
#!/bin/bash
# Скрипт резервного копирования для PostgreSQL

BACKUP_DIR="/var/backups/postgresql"
DATE=$(date +%Y%m%d_%H%M%S)
DB_NAME="guitar_shop"

# Полное резервное копирование
pg_dump -U postgres -F c -b -v -f "$BACKUP_DIR/full_$DATE.backup" $DB_NAME

# Удаление старых резервных копий (старше 30 дней)
find $BACKUP_DIR -name "*.backup" -mtime +30 -delete

# Проверка целостности резервной копии
pg_restore -l "$BACKUP_DIR/full_$DATE.backup" > /dev/null
if [ $? -eq 0 ]; then
    echo "Резервная копия от $DATE создана успешно"
else
    echo "Ошибка при создании резервной копии"
fi
</code></pre>

<h3 id="57-защита-данных">5.7. Защита базы данных</h3>
<ul>
    <li>Шифрование паролей с помощью bcrypt</li>
    <li>Ограничение доступа по IP-адресам</li>
    <li>Регулярное обновление паролей</li>
    <li>Аудит изменений критических данных</li>
    <li>Шифрование конфиденциальных данных клиентов</li>
</ul>

<h3 id="58-разработка-api">5.8. Разработка API</h3>
<pre><code>
from flask import Flask, jsonify, request
from flask_sqlalchemy import SQLAlchemy
from flask_jwt_extended import JWTManager, jwt_required, create_access_token

app = Flask(__name__)
app.config['SQLALCHEMY_DATABASE_URI'] = 'postgresql://user:password@localhost/guitar_shop'
db = SQLAlchemy(app)
jwt = JWTManager(app)

# Модель гитары
class Guitar(db.Model):
    __tablename__ = 'guitars'
    guitar_id = db.Column(db.Integer, primary_key=True)
    model = db.Column(db.String(100))
    type = db.Column(db.String(20))
    price = db.Column(db.Numeric(10,2))
    quantity = db.Column(db.Integer)

# API endpoints
@app.route('/api/guitars', methods=['GET'])
def get_guitars():
    guitars = Guitar.query.all()
    return jsonify([{
        'id': g.guitar_id,
        'model': g.model,
        'type': g.type,
        'price': float(g.price),
        'quantity': g.quantity
    } for g in guitars])

@app.route('/api/sales', methods=['POST'])
@jwt_required()
def create_sale():
    data = request.json
    # Логика создания продажи
    return jsonify({'message': 'Продажа создана'})

@app.route('/api/reports/sales', methods=['GET'])
@jwt_required()
def get_sales_report():
    # Логика формирования отчета
    return jsonify({'report': 'данные отчета'})
</code></pre>

<div class="page-break"></div>

<h2 id="заключение">Заключение</h2>

<p>В ходе выполнения курсовой работы была разработана и реализована база данных для магазина гитар на СУБД PostgreSQL. Были выполнены следующие задачи:</p>

<ol>
    <li>Проведен анализ предметной области магазина гитар</li>
    <li>Разработана концептуальная модель с выделением основных сущностей и их взаимосвязей</li>
    <li>Создана логическая структура базы данных в третьей нормальной форме</li>
    <li>Реализована физическая структура с выбором оптимальных типов данных и индексов</li>
    <li>Разработаны SQL-запросы для основных операций</li>
    <li>Созданы триггеры для автоматического обновления остатков товаров</li>
    <li>Реализована система безопасности с ролевой моделью доступа</li>
    <li>Разработана стратегия резервного копирования</li>
    <li>Создано API для интеграции с другими системами</li>
</ol>

<p><strong>Основные результаты работы:</strong></p>
<ul>
    <li>Спроектирована нормализованная структура БД (3НФ)</li>
    <li>Реализованы бизнес-правила через триггеры и ограничения</li>
    <li>Обеспечена безопасность данных через ролевую модель</li>
    <li>Создана документация по проекту</li>
</ul>

<p>Разработанная система готова к использованию в реальном магазине гитар и может быть расширена дополнительными модулями: онлайн-каталог, система бронирования, модуль ремонта гитар, программа лояльности для клиентов.</p>

<div class="page-break"></div>

<h2 id="список-литературы">Список литературы</h2>

<ol>
    <li>PostgreSQL Documentation. [Электронный ресурс]. URL: https://www.postgresql.org/docs/</li>
    <li>Коннолли Т., Бегг К. Базы данных: проектирование, реализация и сопровождение. – М.: Вильямс, 2020. – 1440 с.</li>
    <li>Гарсиа-Молина Г., Ульман Д., Уидом Дж. Системы баз данных. Полный курс. – М.: Вильямс, 2019. – 1088 с.</li>
    <li>Flask Documentation. [Электронный ресурс]. URL: https://flask.palletsprojects.com/</li>
    <li>ГОСТ Р ИСО/МЭК 12207-99. Информационная технология. Процессы жизненного цикла программных средств.</li>
    <li>Кузнецов С.Д. Основы баз данных. – М.: Интернет-Университет Информационных Технологий, 2018. – 484 с.</li>
    <li>Рейтц К., Шлюссер Т. Автостопом по Python. – СПб.: Питер, 2021. – 592 с.</li>
    <li>Документация по SQL. [Электронный ресурс]. URL: https://www.w3schools.com/sql/</li>
</ol>

<h2 id="приложения">Приложения</h2>

<h3>Приложение 1: Полный SQL-скрипт создания базы данных</h3>
<pre><code>
-- Создание базы данных для магазина гитар
CREATE DATABASE guitar_shop_db;

\c guitar_shop_db;

-- Таблица производителей
CREATE TABLE manufacturers (
    manufacturer_id SERIAL PRIMARY KEY,
    name VARCHAR(100) NOT NULL UNIQUE,
    country VARCHAR(50),
    founded_year INTEGER,
    website VARCHAR(200),
    description TEXT,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Таблица категорий
CREATE TABLE categories (
    category_id SERIAL PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    description TEXT,
    parent_id INTEGER REFERENCES categories(category_id)
);

-- Таблица гитар
CREATE TABLE guitars (
    guitar_id SERIAL PRIMARY KEY,
    manufacturer_id INTEGER NOT NULL REFERENCES manufacturers(manufacturer_id),
    category_id INTEGER REFERENCES categories(category_id),
    model VARCHAR(100) NOT NULL,
    type VARCHAR(20) NOT NULL CHECK (type IN ('acoustic', 'electric', 'bass', 'classical', 'ukulele')),
    year INTEGER,
    body_material VARCHAR(100),
    neck_material VARCHAR(100),
    fingerboard_material VARCHAR(100),
    frets INTEGER,
    scale_length NUMERIC(4,1),
    nut_width NUMERIC(4,2),
    color VARCHAR(50),
    price NUMERIC(10,2) NOT NULL CHECK (price > 0),
    cost_price NUMERIC(10,2),
    quantity INTEGER DEFAULT 0 CHECK (quantity >= 0),
    min_quantity INTEGER DEFAULT 5,
    is_available BOOLEAN DEFAULT TRUE,
    description TEXT,
    specifications JSONB,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    CONSTRAINT chk_year CHECK (year BETWEEN 1900 AND EXTRACT(YEAR FROM CURRENT_DATE))
);

-- Таблица клиентов
CREATE TABLE clients (
    client_id SERIAL PRIMARY KEY,
    first_name VARCHAR(50) NOT NULL,
    last_name VARCHAR(50) NOT NULL,
    email VARCHAR(100) UNIQUE,
    phone VARCHAR(20) UNIQUE,
    address TEXT,
    city VARCHAR(50),
    country VARCHAR(50),
    postal_code VARCHAR(20),
    registration_date DATE DEFAULT CURRENT_DATE,
    last_purchase_date DATE,
    total_purchases NUMERIC(10,2) DEFAULT 0,
    discount_rate NUMERIC(3,2) DEFAULT 0.00 CHECK (discount_rate BETWEEN 0 AND 1),
    notes TEXT,
    is_active BOOLEAN DEFAULT TRUE
);

-- Таблица сотрудников
CREATE TABLE employees (
    employee_id SERIAL PRIMARY KEY,
    first_name VARCHAR(50) NOT NULL,
    last_name VARCHAR(50) NOT NULL,
    position VARCHAR(50) NOT NULL CHECK (position IN ('seller', 'manager', 'admin', 'storekeeper')),
    email VARCHAR(100) UNIQUE NOT NULL,
    phone VARCHAR(20),
    hire_date DATE NOT NULL,
    salary NUMERIC(10,2) NOT NULL CHECK (salary > 0),
    commission_rate NUMERIC(3,2) DEFAULT 0.05 CHECK (commission_rate BETWEEN 0 AND 1),
    username VARCHAR(50) UNIQUE NOT NULL,
    password_hash VARCHAR(255) NOT NULL,
    is_active BOOLEAN DEFAULT TRUE,
    last_login TIMESTAMP
);

-- Таблица продаж
CREATE TABLE sales (
    sale_id SERIAL PRIMARY KEY,
    sale_number VARCHAR(20) UNIQUE NOT NULL,
    client_id INTEGER REFERENCES clients(client_id),
    employee_id INTEGER NOT NULL REFERENCES employees(employee_id),
    sale_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    total_amount NUMERIC(10,2) NOT NULL CHECK (total_amount > 0),
    discount_amount NUMERIC(10,2) DEFAULT 0,
    final_amount NUMERIC(10,2) NOT NULL CHECK (final_amount > 0),
    payment_method VARCHAR(20) NOT NULL CHECK (payment_method IN ('cash', 'card', 'online', 'credit')),
    payment_status VARCHAR(20) DEFAULT 'pending' CHECK (payment_status IN ('pending', 'paid', 'partial', 'refunded')),
    sale_status VARCHAR(20) DEFAULT 'completed' CHECK (sale_status IN ('draft', 'reserved', 'completed', 'cancelled')),
    notes TEXT,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Таблица позиций продаж
CREATE TABLE sale_items (
    sale_item_id SERIAL PRIMARY KEY,
    sale_id INTEGER NOT NULL REFERENCES sales(sale_id) ON DELETE CASCADE,
    guitar_id INTEGER NOT NULL REFERENCES guitars(guitar_id),
    quantity INTEGER NOT NULL CHECK (quantity > 0),
    unit_price NUMERIC(10,2) NOT NULL CHECK (unit_price > 0),
    discount_percent NUMERIC(3,2) DEFAULT 0,
    subtotal NUMERIC(10,2) GENERATED ALWAYS AS (quantity * unit_price * (1 - discount_percent)) STORED
);

-- Таблица поставщиков
CREATE TABLE suppliers (
    supplier_id SERIAL PRIMARY KEY,
    name VARCHAR(100) NOT NULL UNIQUE,
    contact_person VARCHAR(100),
    phone VARCHAR(20),
    email VARCHAR(100),
    address TEXT,
    city VARCHAR(50),
    country VARCHAR(50),
    tax_id VARCHAR(50),
    payment_terms VARCHAR(100),
    delivery_terms VARCHAR(100),
    rating INTEGER CHECK (rating BETWEEN 1 AND 5),
    is_active BOOLEAN DEFAULT TRUE,
    notes TEXT,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Таблица поставок
CREATE TABLE deliveries (
    delivery_id SERIAL PRIMARY KEY,
    delivery_number VARCHAR(20) UNIQUE NOT NULL,
    supplier_id INTEGER NOT NULL REFERENCES suppliers(supplier_id),
    delivery_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    expected_date DATE,
    total_amount NUMERIC(10,2) NOT NULL CHECK (total_amount > 0),
    shipping_cost NUMERIC(10,2) DEFAULT 0,
    tax_amount NUMERIC(10,2) DEFAULT 0,
    status VARCHAR(20) DEFAULT 'ordered' CHECK (status IN ('ordered', 'shipped', 'delivered', 'partial', 'cancelled')),
    notes TEXT,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Таблица позиций поставок
CREATE TABLE delivery_items (
    delivery_item_id SERIAL PRIMARY KEY,
    delivery_id INTEGER NOT NULL REFERENCES deliveries(delivery_id) ON DELETE CASCADE,
    guitar_id INTEGER NOT NULL REFERENCES guitars(guitar_id),
    quantity INTEGER NOT NULL CHECK (quantity > 0),
    unit_cost NUMERIC(10,2) NOT NULL CHECK (unit_cost > 0),
    subtotal NUMERIC(10,2) GENERATED ALWAYS AS (quantity * unit_cost) STORED
);

-- Таблица заказов на ремонт
CREATE TABLE repairs (
    repair_id SERIAL PRIMARY KEY,
    repair_number VARCHAR(20) UNIQUE NOT NULL,
    client_id INTEGER NOT NULL REFERENCES clients(client_id),
    guitar_description TEXT,
    issue_description TEXT NOT NULL,
    estimated_cost NUMERIC(10,2),
    actual_cost NUMERIC(10,2),
    estimated_completion_date DATE,
    actual_completion_date DATE,
    status VARCHAR(20) DEFAULT 'received' CHECK (status IN ('received', 'in_progress', 'completed', 'cancelled')),
    notes TEXT,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Таблица бронирований
CREATE TABLE reservations (
    reservation_id SERIAL PRIMARY KEY,
    guitar_id INTEGER NOT NULL REFERENCES guitars(guitar_id),
    client_id INTEGER NOT NULL REFERENCES clients(client_id),
    employee_id INTEGER REFERENCES employees(employee_id),
    reservation_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    expiration_date TIMESTAMP NOT NULL,
    status VARCHAR(20) DEFAULT 'active' CHECK (status IN ('active', 'completed', 'cancelled', 'expired')),
    notes TEXT,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Индексы для оптимизации производительности
CREATE INDEX idx_guitars_manufacturer ON guitars(manufacturer_id);
CREATE INDEX idx_guitars_category ON guitars(category_id);
CREATE INDEX idx_guitars_type ON guitars(type);
CREATE INDEX idx_guitars_price ON guitars(price);
CREATE INDEX idx_guitars_availability ON guitars(is_available) WHERE is_available = TRUE;

CREATE INDEX idx_sales_date ON sales(sale_date);
CREATE INDEX idx_sales_client ON sales(client_id);
CREATE INDEX idx_sales_employee ON sales(employee_id);
CREATE INDEX idx_sales_status ON sales(sale_status);

CREATE INDEX idx_clients_email ON clients(email);
CREATE INDEX idx_clients_phone ON clients(phone);
CREATE INDEX idx_clients_active ON clients(is_active) WHERE is_active = TRUE;

CREATE INDEX idx_employees_position ON employees(position);
CREATE INDEX idx_employees_active ON employees(is_active) WHERE is_active = TRUE;
CREATE INDEX idx_employees_username ON employees(username);

CREATE INDEX idx_sale_items_sale ON sale_items(sale_id);
CREATE INDEX idx_sale_items_guitar ON sale_items(guitar_id);

CREATE INDEX idx_deliveries_supplier ON deliveries(supplier_id);
CREATE INDEX idx_deliveries_status ON deliveries(status);

-- Функция для обновления времени изменения
CREATE OR REPLACE FUNCTION update_updated_at_column()
RETURNS TRIGGER AS $$
BEGIN
    NEW.updated_at = CURRENT_TIMESTAMP;
    RETURN NEW;
END;
$$ LANGUAGE plpgsql;

-- Триггеры для обновления updated_at
CREATE TRIGGER update_guitars_updated_at BEFORE UPDATE ON guitars
    FOR EACH ROW EXECUTE FUNCTION update_updated_at_column();

CREATE TRIGGER update_sales_updated_at BEFORE UPDATE ON sales
    FOR EACH ROW EXECUTE FUNCTION update_updated_at_column();

CREATE TRIGGER update_deliveries_updated_at BEFORE UPDATE ON deliveries
    FOR EACH ROW EXECUTE FUNCTION update_updated_at_column();

-- Функция и триггер для обновления остатков
CREATE OR REPLACE FUNCTION update_guitar_quantity()
RETURNS TRIGGER AS $$
BEGIN
    IF TG_TABLE_NAME = 'sale_items' THEN
        IF TG_OP = 'INSERT' THEN
            UPDATE guitars SET quantity = quantity - NEW.quantity
            WHERE guitar_id = NEW.guitar_id;
        ELSIF TG_OP = 'UPDATE' THEN
            UPDATE guitars SET quantity = quantity + OLD.quantity - NEW.quantity
            WHERE guitar_id = NEW.guitar_id;
        ELSIF TG_OP = 'DELETE' THEN
            UPDATE guitars SET quantity = quantity + OLD.quantity
            WHERE guitar_id = OLD.guitar_id;
        END IF;
    ELSIF TG_TABLE_NAME = 'delivery_items' THEN
        IF TG_OP = 'INSERT' THEN
            UPDATE guitars SET quantity = quantity + NEW.quantity
            WHERE guitar_id = NEW.guitar_id;
        ELSIF TG_OP = 'UPDATE' THEN
            UPDATE guitars SET quantity = quantity - OLD.quantity + NEW.quantity
            WHERE guitar_id = NEW.guitar_id;
        ELSIF TG_OP = 'DELETE' THEN
            UPDATE guitars SET quantity = quantity - OLD.quantity
            WHERE guitar_id = OLD.guitar_id;
        END IF;
    END IF;
    RETURN NULL;
END;
$$ LANGUAGE plpgsql;

CREATE TRIGGER trg_sale_items_quantity
AFTER INSERT OR UPDATE OR DELETE ON sale_items
FOR EACH ROW EXECUTE FUNCTION update_guitar_quantity();

CREATE TRIGGER trg_delivery_items_quantity
AFTER INSERT OR UPDATE OR DELETE ON delivery_items
FOR EACH ROW EXECUTE FUNCTION update_guitar_quantity();

-- Функция для генерации номера продажи
CREATE OR REPLACE FUNCTION generate_sale_number()
RETURNS TRIGGER AS $$
BEGIN
    NEW.sale_number = 'SALE-' || TO_CHAR(CURRENT_DATE, 'YYYYMMDD-') || LPAD(NEXTVAL('sales_sale_number_seq')::TEXT, 6, '0');
    RETURN NEW;
END;
$$ LANGUAGE plpgsql;

CREATE TRIGGER trg_generate_sale_number
BEFORE INSERT ON sales
FOR EACH ROW EXECUTE FUNCTION generate_sale_number();

-- Представление для отчета по продажам
CREATE VIEW sales_report AS
SELECT 
    s.sale_id,
    s.sale_number,
    s.sale_date,
    c.first_name || ' ' || c.last_name as client_name,
    e.first_name || ' ' || e.last_name as employee_name,
    s.total_amount,
    s.final_amount,
    s.payment_method,
    s.sale_status,
    COUNT(si.sale_item_id) as items_count,
    SUM(si.quantity) as total_quantity
FROM sales s
LEFT JOIN clients c ON s.client_id = c.client_id
LEFT JOIN employees e ON s.employee_id = e.employee_id
LEFT JOIN sale_items si ON s.sale_id = si.sale_id
GROUP BY s.sale_id, s.sale_number, s.sale_date, c.client_id, e.employee_id;

-- Представление для отчета по остаткам
CREATE VIEW inventory_report AS
SELECT 
    g.guitar_id,
    g.model,
    m.name as manufacturer,
    g.type,
    g.color,
    g.price,
    g.quantity,
    g.min_quantity,
    CASE 
        WHEN g.quantity = 0 THEN 'Нет в наличии'
        WHEN g.quantity <= g.min_quantity THEN 'Мало'
        ELSE 'Достаточно'
    END as stock_status
FROM guitars g
JOIN manufacturers m ON g.manufacturer_id = m.manufacturer_id;

-- Вставка тестовых данных
INSERT INTO manufacturers (name, country, founded_year) VALUES
('Fender', 'USA', 1946),
('Gibson', 'USA', 1902),
('Ibanez', 'Japan', 1957),
('Yamaha', 'Japan', 1887),
('Taylor', 'USA', 1974);

INSERT INTO categories (name, description) VALUES
('Акустические гитары', 'Гитары с полым корпусом'),
('Электрогитары', 'Гитары для подключения к усилителю'),
('Бас-гитары', 'Низкочастотные гитары'),
('Классические гитары', 'Гитары с нейлоновыми струнами');

INSERT INTO guitars (manufacturer_id, category_id, model, type, price, quantity) VALUES
(1, 2, 'Stratocaster', 'electric', 45000.00, 10),
(2, 2, 'Les Paul', 'electric', 55000.00, 5),
(3, 2, 'RG550', 'electric', 40000.00, 8),
(4, 1, 'FG800', 'acoustic', 25000.00, 15),
(5, 1, '314ce', 'acoustic', 75000.00, 3);

INSERT INTO clients (first_name, last_name, email, phone) VALUES
('Иван', 'Петров', 'ivan@mail.ru', '+79101234567'),
('Мария', 'Сидорова', 'maria@mail.ru', '+79107654321'),
('Алексей', 'Иванов', 'alex@mail.ru', '+79109876543');

INSERT INTO employees (first_name, last_name, position, email, hire_date, salary, username, password_hash) VALUES
('Анна', 'Смирнова', 'manager', 'anna@shop.ru', '2023-01-15', 80000.00, 'asmirnova', 'hashed_password_1'),
('Дмитрий', 'Козлов', 'seller', 'dmitry@shop.ru', '2023-03-20', 60000.00, 'dkozlov', 'hashed_password_2');

-- Тестовая продажа
INSERT INTO sales (sale_number, client_id, employee_id, total_amount, final_amount, payment_method) 
VALUES ('SALE-TEST', 1, 2, 45000.00, 45000.00, 'card');

INSERT INTO sale_items (sale_id, guitar_id, quantity, unit_price) 
VALUES (1, 1, 1, 45000.00);

COMMENT ON TABLE guitars IS 'Основная таблица с информацией о гитарах';
COMMENT ON TABLE sales IS 'Таблица продаж магазина';
COMMENT ON TABLE clients IS 'Клиенты магазина';
COMMENT ON TABLE employees IS 'Сотрудники магазина';

-- Создание пользователя для приложения
CREATE USER guitar_app WITH PASSWORD 'secure_password_123';
GRANT CONNECT ON DATABASE guitar_shop_db TO guitar_app;
GRANT USAGE ON SCHEMA public TO guitar_app;
GRANT SELECT, INSERT, UPDATE ON ALL TABLES IN SCHEMA public TO guitar_app;
GRANT USAGE ON ALL SEQUENCES IN SCHEMA public TO guitar_app;
</code></pre>

<h3>Приложение 2: Примеры сложных запросов</h3>

<pre><code>
-- 1. Отчет по продажам за месяц с детализацией
SELECT 
    TO_CHAR(s.sale_date, 'YYYY-MM') as month,
    COUNT(DISTINCT s.sale_id) as sales_count,
    COUNT(si.sale_item_id) as items_sold,
    SUM(si.quantity) as total_units,
    SUM(s.final_amount) as revenue,
    AVG(s.final_amount) as avg_sale_amount,
    MAX(s.final_amount) as max_sale_amount,
    MIN(s.final_amount) as min_sale_amount
FROM sales s
JOIN sale_items si ON s.sale_id = si.sale_id
WHERE s.sale_status = 'completed'
    AND s.sale_date >= DATE_TRUNC('month', CURRENT_DATE - INTERVAL '1 year')
GROUP BY TO_CHAR(s.sale_date, 'YYYY-MM')
ORDER BY month DESC;

-- 2. Топ-10 самых продаваемых гитар
WITH guitar_sales AS (
    SELECT 
        g.guitar_id,
        g.model,
        m.name as manufacturer,
        g.type,
        SUM(si.quantity) as total_sold,
        SUM(si.subtotal) as total_revenue,
        COUNT(DISTINCT s.sale_id) as sales_count
    FROM sale_items si
    JOIN guitars g ON si.guitar_id = g.guitar_id
    JOIN manufacturers m ON g.manufacturer_id = m.manufacturer_id
    JOIN sales s ON si.sale_id = s.sale_id
    WHERE s.sale_status = 'completed'
    GROUP BY g.guitar_id, g.model, m.name, g.type
)
SELECT 
    manufacturer,
    model,
    type,
    total_sold,
    total_revenue,
    sales_count,
    RANK() OVER (ORDER BY total_sold DESC) as rank_by_quantity,
    RANK() OVER (ORDER BY total_revenue DESC) as rank_by_revenue
FROM guitar_sales
ORDER BY total_sold DESC
LIMIT 10;

-- 3. Анализ клиентов по объему покупок
SELECT 
    c.client_id,
    c.first_name || ' ' || c.last_name as client_name,
    c.email,
    c.phone,
    COUNT(DISTINCT s.sale_id) as total_purchases,
    SUM(s.final_amount) as total_spent,
    MAX(s.sale_date) as last_purchase_date,
    AVG(s.final_amount) as avg_purchase_amount,
    CASE 
        WHEN SUM(s.final_amount) >= 100000 THEN 'VIP'
        WHEN SUM(s.final_amount) >= 50000 THEN 'Постоянный'
        WHEN SUM(s.final_amount) >= 10000 THEN 'Обычный'
        ELSE 'Новый'
    END as client_category
FROM clients c
LEFT JOIN sales s ON c.client_id = s.client_id AND s.sale_status = 'completed'
GROUP BY c.client_id, c.first_name, c.last_name, c.email, c.phone
ORDER BY total_spent DESC NULLS LAST;

-- 4. Анализ прибыльности по производителям
SELECT 
    m.name as manufacturer,
    COUNT(DISTINCT g.guitar_id) as models_count,
    SUM(g.quantity) as total_stock,
    SUM(CASE WHEN g.quantity > 0 THEN 1 ELSE 0 END) as in_stock_models,
    SUM(si.quantity) as total_sold,
    SUM(si.subtotal) as total_revenue,
    SUM(di.quantity) as total_purchased,
    SUM(di.subtotal) as total_cost,
    COALESCE(SUM(si.subtotal), 0) - COALESCE(SUM(di.subtotal), 0) as gross_profit,
    ROUND(
        (COALESCE(SUM(si.subtotal), 0) - COALESCE(SUM(di.subtotal), 0)) / 
        NULLIF(COALESCE(SUM(di.subtotal), 1), 0) * 100, 2
    ) as profit_margin_percent
FROM manufacturers m
LEFT JOIN guitars g ON m.manufacturer_id = g.manufacturer_id
LEFT JOIN sale_items si ON g.guitar_id = si.guitar_id
LEFT JOIN delivery_items di ON g.guitar_id = di.guitar_id
GROUP BY m.manufacturer_id, m.name
ORDER BY gross_profit DESC NULLS LAST;

-- 5. Предупреждение о низких остатках
SELECT 
    g.guitar_id,
    g.model,
    m.name as manufacturer,
    g.quantity as current_stock,
    g.min_quantity as min_stock,
    g.quantity - g.min_quantity as stock_difference,
    CASE 
        WHEN g.quantity = 0 THEN 'Требуется срочный заказ'
        WHEN g.quantity <= g.min_quantity THEN 'Требуется заказ'
        WHEN g.quantity <= g.min_quantity * 2 THEN 'Следить за остатком'
        ELSE 'Достаточно'
    END as action_required,
    -- Расчет времени до истощения запасов (на основе средних продаж)
    ROUND(
        g.quantity / NULLIF(
            AVG(daily_sales.avg_daily_sales) OVER (
                PARTITION BY g.guitar_id
            ), 0
        ), 1
    ) as days_until_out_of_stock
FROM guitars g
JOIN manufacturers m ON g.manufacturer_id = m.manufacturer_id
LEFT JOIN (
    SELECT 
        si.guitar_id,
        AVG(si.quantity) as avg_daily_sales
    FROM sale_items si
    JOIN sales s ON si.sale_id = s.sale_id
    WHERE s.sale_date >= CURRENT_DATE - INTERVAL '30 days'
    GROUP BY si.guitar_id
) daily_sales ON g.guitar_id = daily_sales.guitar_id
WHERE g.is_available = TRUE
ORDER BY stock_difference ASC;
</code></pre>
