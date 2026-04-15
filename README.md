
# 📊 Домашнее задание 8.04: Система мониторинга Zabbix

<div align="center">

**Выполнил:** Сыч Кирилл  
**Группа:** HV-02  
**Дата:** 14 апреля 2026

[![Zabbix](https://img.shields.io/badge/Zabbix-7.4-green)](https://www.zabbix.com/)

</div>

---

## 📋 Содержание

- [Задание 1: Создание шаблона](#задание-1-создание-шаблона)
- [Задание 2: Добавление хостов](#задание-2-добавление-хостов)
- [Задание 3: Привязка шаблонов](#задание-3-привязка-шаблонов)
- [Задание 4: Кастомный дашборд](#задание-4-кастомный-дашборд)

---

## 🎯 Задание 1: Создание шаблона

### ✅ Выполненные действия

1. В веб-интерфейсе Zabbix Server создан новый шаблон `Custom-CPU-RAM`
2. Создан Item для мониторинга загрузки CPU в процентах
3. Создан Item для мониторинга загрузки RAM в процентах

### 📊 Элементы данных шаблона

| № | Имя элемента | Key | Тип данных | Единицы |
|---|-------------|-----|------------|---------|
| 1 | CPU Usage Total % | `system.cpu.util[0,user,avg5]` | Numeric (float) | % |
| 2 | RAM Usage % | `vm.memory.size[pused]` | Numeric (float) | % |

### 📸 Скриншот шаблона

![Custom Template Items](https://github.com/sychnepticaowl-spec/8-04-Sych-Kirill/raw/main/screenshots/screenshots-latest-data-cpu.png)
*Рисунок 1 - Элементы данных шаблона Custom-CPU-RAM в разделе Latest Data*

![Custom Template Items](https://github.com/sychnepticaowl-spec/8-04-Sych-Kirill/blob/main/screenshots/zadanie1.png)
*Рисунок 2 Таблица с название шаблона и привязкой*
---

## 🖥️ Задание 2: Добавление хостов

### ✅ Выполненные действия

1. Установлен Zabbix Agent 2 на две виртуальные машины (Ubuntu 24.04)
2. Добавлен Zabbix Server (10.0.3.4) в список разрешенных серверов
3. Хосты добавлены в раздел Configuration > Hosts
4. К каждому хосту прикреплен шаблон `Linux by Zabbix Agent`
5. Проверено поступление данных в разделе Latest Data

### 📋 Информация о хостах

| Хост | IP адрес | Имя в Zabbix | ОС |
|------|----------|--------------|-----|
| **Host 1** | 10.0.3.5 | `sychkp-1` | Ubuntu 24.04.3 LTS |
| **Host 2** | 10.0.3.6 | `sychkp-2` | Ubuntu 24.04.3 LTS |

### 📸 Скриншот хостов

![Hosts Configuration]([https://github.com/sychnepticaowl-spec/8-04-Sych-Kirill/raw/main/screenshots/screenshots-hosts.png](https://github.com/sychnepticaowl-spec/8-04-Sych-Kirill/blob/main/screenshots/zadanie3.png))
*Рисунок 2 - Раздел Configuration > Hosts с добавленными агентами `sychkp-1` и `sychkp-2`*

---

## 🔗 Задание 3: Привязка шаблонов

### ✅ Выполненные действия

1. К каждому хосту (`sychkp-1` и `sychkp-2`) привязан созданный шаблон `Custom-CPU-RAM`
2. К каждому хосту также привязан стандартный шаблон `Linux by Zabbix Agent`
3. Проверено поступление данных в раздел Latest Data

### 📸 Скриншоты данных

**📊 CPU Usage:**

![Latest Data - CPU](https://github.com/sychnepticaowl-spec/8-04-Sych-Kirill/raw/main/screenshots/screenshots-latest-data-cpu.png)
*Рисунок 3 - Данные о загрузке CPU в разделе Latest Data для хостов `sychkp-1` и `sychkp-2`*

**💾 RAM Usage:**

![Latest Data - RAM](https://github.com/sychnepticaowl-spec/8-04-Sych-Kirill/raw/main/screenshots/screenshots-latest-data-ram.png)
*Рисунок 4 - Данные о загрузке RAM в разделе Latest Data для хостов `sychkp-1` и `sychkp-2`*

---

## 📈 Задание 4: Кастомный дашборд

### ✅ Выполненные действия

1. В разделе Dashboards создан новый дашборд `My Custom Dashboard`
2. Размещены графики мониторинга CPU и RAM для обоих хостов
3. Настроено отображение данных за последний час

### 📸 Скриншот дашборда

![Custom Dashboard]([https://github.com/sychnepticaowl-spec/8-04-Sych-Kirill/raw/main/screenshots/screenshots-dashboard.png](https://github.com/sychnepticaowl-spec/8-04-Sych-Kirill/blob/main/screenshots/zadanie4.png))
*Рисунок 5 - Кастомный дашборд с графиками CPU и RAM для хостов `sychkp-1` и `sychkp-2`*


