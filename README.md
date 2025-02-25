О проекте

Тема проекта:
Сравнение различных подходов к реализации асинхронного программирования: asyncio, threading и multiprocessing: Реализовать асинхронные задачи с использованием asyncio, threading и multiprocessing, сравнить их производительность и уместность для различных типов задач.

Суть проекта:
Суть проекта заключается в практическом исследовании и сравнении трёх основных способов организации конкурентного выполнения кода в Python

Как работает код:
Код разбит на 3 дирректории в соответсвии с количеством методов ассинхронного программирования. В каждой дирректории находится по два файля формата ".py". В первом файле предстваленна работа метода с 3 текстовыми файлами, в которых содержится большое кол-во числовых данных. Код делает подсчет среднего числа и выводит время за которое он справился с задачей. Во вторых файлах представлен код, который более наглядко показывает преимущества того или иного метода перед другими.

Работа кода:

asyncio

1) ![Снимок экрана 2025-01-16 в 19 25 30](https://github.com/user-attachments/assets/3d4d3dae-79d1-45d7-85b9-04f6c5c44dc5)

   ![Снимок экрана 2025-01-16 в 19 28 56](https://github.com/user-attachments/assets/2e05f445-e623-4894-b27f-a21c0d54e575)

2) ![Снимок экрана 2025-01-16 в 19 26 15](https://github.com/user-attachments/assets/f48884f8-eced-4b79-be81-c7c99df86503)

   ![Снимок экрана 2025-01-16 в 19 29 32](https://github.com/user-attachments/assets/ffa805ed-f59e-4923-b8a2-c90942c06907)
   
threading

1) ![Снимок экрана 2025-01-16 в 19 26 37](https://github.com/user-attachments/assets/b80a9028-73c8-4694-8ba5-09764ea9e1b1)

   ![Снимок экрана 2025-01-16 в 19 29 53](https://github.com/user-attachments/assets/36c0cb31-fa21-4482-8d85-def267e11e66)

2) ![Снимок экрана 2025-01-16 в 19 26 59](https://github.com/user-attachments/assets/20965513-6934-4227-ba98-a5c199e77f77)

   ![Снимок экрана 2025-01-16 в 19 31 52](https://github.com/user-attachments/assets/414cbfb6-e34a-4363-8662-65440dd09e0d)

multiprocessing

1) ![Снимок экрана 2025-01-16 в 19 27 19](https://github.com/user-attachments/assets/da3210a1-71fe-4913-895c-b1598bf5fe97)

   ![Снимок экрана 2025-01-16 в 19 32 19](https://github.com/user-attachments/assets/d8a049f0-27ad-4dc1-8156-28bada1a4244)

2) ![Снимок экрана 2025-01-16 в 19 27 35](https://github.com/user-attachments/assets/ff68fe00-f7a4-41ef-8130-1b7d8e9a959e)

   ![Снимок экрана 2025-01-16 в 19 33 03](https://github.com/user-attachments/assets/4fa5519e-1e16-4c9c-91bc-efb0bc6dd927)


Подведение итогов:

<img width="1045" alt="Снимок экрана 2025-01-16 в 14 24 11" src="https://github.com/user-attachments/assets/205d6f86-45a6-4fa5-8ce0-3144214c43e3" />

asyncio: Использует кооперативную многозадачность в одном потоке. Идеально подходит для задач, связанных с ожиданием (например, сетевые запросы), где большую часть времени программа проводит в ожидании ответа.

threading: Создает несколько потоков выполнения в рамках одного процесса. Подходит для I/O-bound задач, но из-за GIL истинный параллелизм для CPU-bound задач ограничен.

multiprocessing: Создает несколько процессов, каждый со своим интерпретатором Python и памятью. Обходит ограничения GIL и обеспечивает истинный параллелизм, идеально подходит для CPU-bound задач. Однако, межпроцессное взаимодействие сложнее и потребляет больше ресурсов.

Какой из методов выбрать, зависит от конкретной задачи. Если задача связана с большим количеством операций ввода/вывода, asyncio часто является лучшим выбором. Для CPU-bound задач, требующих максимальной производительности, multiprocessing предпочтительнее. threading может быть полезен для I/O-bound задач и в случаях, когда asyncio слишком сложен для реализации.
