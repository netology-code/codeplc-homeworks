# Домашнее задание к занятию «Программирование на языке FBD»

### Цель задания

Получить опыт создания программ на языке FBD в программном проекте в TIA Portal 13.

В результате выполнения этого задания вы сможете:

- вносить изменения в программный код на языке FBD в соответствии с заданием;
- получить опыт работы с системой TIA Portal в части программирования на языке FBD и программой PLCSIM в части разработки, загрузки и отладки программ.

------

### Чек-лист готовности к домашнему заданию

1. Зарегистрируйтесь на [портале Siemens](https://mall.industry.siemens.com/goos/WelcomePage.aspx?regionUrl=/ru&language=ru) и получите персональный логин и пароль для входа в систему. Процесс регистрации описан в [инструкции](https://docs.google.com/presentation/d/1RPHvCE2OxBbHRMWSAV2E-HxscZvR2nRIZVHCy8hvjJE/edit?usp=sharing).
2. Загрузите с [официального ресурса Siemens](https://support.industry.siemens.com/cs/document/78793685/simatic-step-7-(tia-portal)-v13-trial-download?dti=0&lc=en-DE) и установите программное обеспечение для создания проекта PLC Siemens, входящее в состав пакета TIA Portal. 
3. Скачайте [архив программного проекта Netology_Project_FBD](https://drive.google.com/file/d/1Vv-Og1fiGtf0ASwlg_1x_4nLln-yFu7U/view?usp=sharing) и распакуйте его, используя функцию Retrieve среды программирования TIA Portal.


<details>
  <summary> Подсказка по установке.</summary>
  
  
1. Скачайте все файлы по [ссылке](https://support.industry.siemens.com/cs/document/109745155/simatic-step-7-including-plcsim-v13-sp2-trial-download?dti=0&lc=en-DE) в две отдельные папки:
 
  - STEP 7 Professional V13 SP2 (DVD 1, DVD 2, SHA-256 checksum).
 
  ![image](https://github.com/netology-code/phd-homeworks/blob/main/6.6/Step7_1.png)

  - SIMATIC STEP 7 PLCSIM V13 SP2 for STEP 7 Basic and STEP 7 Professional (включая SHA-256 checksum).
 
    ![image](https://github.com/netology-code/phd-homeworks/blob/main/6.6/Step7_2.png)

2. Запустите установочный файл SIMATIC_STEP_7_Professional_V13_SP2_Upd4.exe, пройдите стандартную процедуру установки.
3. Запустите установочный файл SIMATIC_S7_PLCSIM_V13_SP2.exe, пройдите стандартную процедуру установки.

    ---
  
</details>
  
**Обратите внимание.** Устанавливается демо-версия программы. Её функционал будет ограничен через 21 день после установки. Рекомендуем установку софта на виртуальной машине. Как это сделать, описано в [инструкции](https://docs.google.com/presentation/d/1psnSlotXT7cr8ECnaZaTCDLnIyYOGUzCArLeydeRztY/edit?usp=sharing).



------

### Инструкция к заданию

1. Сделайте копию файла [«Шаблон для домашнего задания»](https://docs.google.com/document/d/1MiwldIkT0D7OWcygHadT0PwvF4M3eY3FKipRuTsttIs/edit?usp=sharing) на свой Google Диск.
2. В названии файла введите корректное название лекции и ваши фамилию и имя.
3. Зайдите в «Настройки доступа» и выберите доступ «Просматривать могут все в интернете, у кого есть ссылка». Инструкция «Как предоставить доступ к файлам и папкам на Google Диске» [по ссылке](https://support.google.com/docs/answer/2494822?hl=ru&co=GENIE.Platform%3DDesktop).
4. Скопируйте текст задания в свой документ.
5. Выполните задание, запишите ответы и приложите необходимые скриншоты в свой Google Doc.
6. Для проверки домашнего задания отправьте ссылку на ваш документ в личном кабинете.
7. Любые вопросы по решению задач задавайте в чате учебной группы.


------

### Инструменты и дополнительные материалы для выполнения задания

1. [TIA Portal 13, PLCSIM 13](https://support.industry.siemens.com/cs/document/109745155/simatic-step-7-including-plcsim-v13-sp2-trial-download?dti=0&lc=en-WW).
2. [Архив проекта Netology_Project_FBD](https://drive.google.com/file/d/1Vv-Og1fiGtf0ASwlg_1x_4nLln-yFu7U/view?usp=sharing).
3. [Инструкция по созданию виртуальной машины](https://docs.google.com/presentation/d/1psnSlotXT7cr8ECnaZaTCDLnIyYOGUzCArLeydeRztY/edit?usp=sharing).
4. [Шаблон для домашнего задания](https://docs.google.com/document/d/178B47bzn1EpAnIus6CENF2T5WhJeYAqxpfcolAxQ5l4/edit?usp=sharing).

------

### Задание 1

В [проекте Netology_Project_FBD](https://drive.google.com/file/d/1Vv-Og1fiGtf0ASwlg_1x_4nLln-yFu7U/view?usp=sharing) проделайте операции:

1. Внесите в программный код функционального блока FBD_ValveCtrl_FB изменения:

  - переименуйте выход Err в ErrMon;
  - добавьте новый выход ErrHardware (тип: Bool);
  - добавьте новые входы TimeMon (тип: Time), TimeHardware (тип: Time).
  
2. Измените логику работы следующим образом:

  - сформируйте выход ErrMon, как результат несовпадения команды (вход CMDIN) и состояния (вход FBO), время формирования сигнала задайте входом TimeMon;
  - сформируйте выход ErrHardware, как результат недопустимого положения клапана (одинаковое состояние входов FBO, FBC), время формирования сигнала задайте входом TimeHardware;
  - сбрасывайте каждый из сигналов ошибки  при помощи сигнала Reset, если причина ошибки неактивна.

2. Произведите в организационном блоке FBD_Program_OB процедуру «Update block call» для экземпляра FBD_ValveCtrl_FB.
3. Присвойте новым входам TimeMon, TimeHardware значения 10 и 15 секунд соответственно.
4. Привяжите новый выход ErrHardware к неиспользуемому биту внутренней памяти — найдите его с помощью Assignment List.
5. Произведите компиляцию проекта и его загрузку в PLCSIM.

Сделайте скриншоты измененного функционального блока FBD_ValveCtrl_FB и его вызова в FBD_Program_OB (режим онлайн) и приложите их к заданию.

------

### Задание 2

Внесите в программный код функционального блока FBD_AnalogValve_FB изменения:

1. Добавьте новые выходы Opened (тип: Bool) и Closed (тип: Bool), значения которых формируются следующим образом:
 - Closed = 1 (TRUE), если показания обратной связи с позиционера < 2%, и 0 (FALSE) в противоположном случае;
 - Opened = 1 (TRUE), если показания обратной связи с позиционера > 98%, и 0 (FALSE) в противоположном случае.
2. Произведите в организационном блоке FBD_Program_OB процедуру «Update block call» для экземпляра FBD_AnalogValve_FB.
3. Привяжите новые выходы Opened, Closed к неиспользуемым битам внутренней памяти — найдите их с помощью Assignment List).
4. Произведите компиляцию проекта и его загрузку в PLCSIM.

Сделайте скриншоты изменённого функционального блока FBD_AnalogValve_FB и его вызова в FBD_Program_OB — режим онлайн, при подаче команды 0%, 50%, 100% и получении аналогичного сигнала с позиционера — и приложите их к заданию.

------

### Правила приёма работы

1. Отправлена ссылка на документ (Google Doc) с выполненным заданием в личном кабинете.
2. Документ размещён на личном Google Диске.
3. К документу настроены права доступа «Просматривать могут все в интернете, у кого есть ссылка».

------

### Критерии оценки

1. Задание 1 считается выполненным, если:

- на приложенных скриншотах приведён корректный программный код функционального блока FBD_ValveCtrl_FB;
- присутствуют корректные значения выходов ErrMon, ErrHardware при активном признаке ошибки, сброшенном признаке ошибки для каждого выхода, и отсутствие сигналов ошибки после активации сигнала Reset.

2. Задание 2 считается выполненным, если:

- на приложенных скриншотах приведён корректный программный код функционального блока FBD_AnalogValve_FB;
- присутствуют корректные значения выходов Opened, Closed для каждого из значений сигналов от позиционера. 
