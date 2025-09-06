# rauapi

- [Описание на русском](#русская-версия)
- [English discriprion](#english-version)

---

## Русская версия
# rauapi — Анализатор данных по банкротствам компаний
## Обзор проекта

**rauapi** это готовый инструмент (rauapi.exe) для автоматического получения и фильтрации данных о банкротстве компаний с официального портала Федеральной налоговой службы России (rau.nalog.gov.ru
).

Программа применяет фильтры, заданные в req.txt, и генерирует Excel-файл с структурированными результатами за выбранный период (последние 7 дней).

---

## Содержание

- [Возможности](#возможности) 
- [Как использовать](#как-использовать)  
- [Структура](#структура-релиза)  
- [Example файл](#example-файл)  
- [Примечания](#примечания)  

---

## Возможности

- **Готовый исполняемый файл** (rauapi.exe — Python не требуется).
- **Получение данных напрямую** через API ФНС.
- **Настраиваемая фильтрация** по требованиям и банам (настраивается в req.txt).
- **Экспорт в Excel** с автоматической подгонкой ширины колонок.
- **Стабильная работа** с повторными попытками при сетевых ошибках.

---

## Как использовать

1. **Скачайте архив**
2. **Настройте фильтры в req.txt или переименуйте и редактируйте req_example.txt**
  ```bash
businessBaseCost
businessLiquidationCost
repaymentCalc
workingCapitalNeed
solvencyRnk
averageNumber
balanceTotal 500000000 -1
revenue
authorizedCapital
fixedAssets
inventory
receivables
paymentTaxes

region 05 06 07 09 15 20 26
  ```
3. **Запустите программу**
4. **После выполнения вы получите Excel-файл с результатами за последние 7 дней, например:**
  ```bash
 01-09-2025to07-09-2025.xlsx
  ```

---

## Структура релиза
  ```bash
  tg_bot/
  ├── rauapi.exe               # Основной исполняемый файл
  ├── req.txt                  # Фильтры и настройки банов
  └── req_example.txt          # Пример req.txt
  ```

---

## Example файл

- Выбраны только компании с balanceTotal больше 500000000
- Исключены компании из регионов 05, 06, 07, 09, 15, 20, 26
---

## Примечания

- Требуется подключение к интернету (данные берутся с rau.nalog.gov.ru).
- req.txt должен находиться в одной папке с rauapi.exe.
- Программа может работать несколько минут в зависимости от количества компаний.

---

*Разработано [VoskovschukDM](https://github.com/VoskovschukDM)*

---

## English Version
# rauapi — Company Bankruptcy Data Analyzer
## Project Overview

**rauapi** is a ready-to-use tool (rauapi.exe) for automatically retrieving and filtering bankruptcy data of companies from the official Russian Federal Tax Service portal (rau.nalog.gov.ru).

The program applies filters defined in req.txt and generates an Excel file with structured results for the selected period (last 7 days).

---

## Table of Contents

- [Features](#features) 
- [How to Use](#how-to-use)  
- [Structure](#release-package-structure)  
- [Example file](#example-file)  
- [Notes](#notes)  

---

## Features

- **Ready-to-use executable** (rauapi.exe — no Python installation required).
- **Fetch data** directly from the FTS API.
- **Custom filtering** by requirements and bans (configured in req.txt).
- **Excel export** with auto-adjusted column widths.
- **Stable operation** with retry logic on network errors.

---

## How to Use

1. **Download archive**
2. **Configure filters in req.txt or rename and edit req_example.txt**
  ```bash
businessBaseCost
businessLiquidationCost
repaymentCalc
workingCapitalNeed
solvencyRnk
averageNumber
balanceTotal 500000000 -1
revenue
authorizedCapital
fixedAssets
inventory
receivables
paymentTaxes

region 05 06 07 09 15 20 26
  ```
3. **Run the program**
4. **After execution, you’ll get an Excel file with results for the past 7 days, for example**
  ```bash
 01-09-2025to07-09-2025.xlsx
  ```

---

## Release Package Structure
  ```bash
  tg_bot/
  ├── rauapi.exe               # Main executable
  ├── req.txt                  # Filters and bans configuration
  └── req_example.txt          # req.txt example
  ```

---

## Example file

- Filtered companies with balanceTotal more than 500000000
- Hiden companies from 05, 06, 07, 09, 15, 20, 26 regions

---

## Notes

- Internet connection is required (data is fetched from rau.nalog.gov.ru).
- req.txt must be in the same folder as rauapi.exe.
- The program may take several minutes depending on the number of companies.

---

*Powered by [VoskovschukDM](https://github.com/VoskovschukDM)*
