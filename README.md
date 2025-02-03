1. Развернуть уязвимое веб-приложение bWAPP

![bWAPP](images/FdEXqULNgq.png)

*Скриншот показывает интерфейс VMware после успешного развертывания bWAPP.*

![bWAPP](images/chrome_Q8zpKmjg5O.png)

*Скриншот демонстрирует главную страницу bWAPP с доступными заданиями.*

2. Развернуть виртуальную машину с Kali Linux

![Kali Linux](images/tuJZfeTZU0.png)

*Скриншот показывает рабочий стол Kali Linux после успешного запуска виртуальной машины.*

3. Провести несколько простых кибератак: выполнить задания (уровень low) на OS Command Injection

	3.1 функционал приложения

	![OS Command Injection](images/chrome_0TJoXZdFSl.png)

	*Скриншот демонстрирует форму ввода для выполнения команды в уязвимом приложении.*

	3.2 эксплуатация уязвимости

	`nsa.gov&&cat /etc/passwd`

	![OS Command Injection](images/c1ADXYrIBU.png)

	*Скриншот показывает ввод команды, выводящий содержимое файла /etc/passwd.*

	![OS Command Injection](images/chrome_XMgv8cXpWJ.png)

	*Скриншот демонстрирует успешное выполнение команды, выводящий содержимое файла /etc/passwd*

4. PHP Code Injection

	4.1 функционал приложения

	`http://vuln-4.edtechlab.local/phpi.php?message=felixsta`

	![PHP Code Injection](images/chrome_zuijh0ye2S.png)

	*Скриншот показывает страницу с параметром message и значением `felixsta`, переданным в URL.*

	4.2 эксплуатация уязвимости

	`http://vuln-4.edtechlab.local/phpi.php?message=phpinfo()`

	![PHP Code Injection](images/chrome_WRXY25JBMx.png)

	*Скриншот демонстрирует результат выполнения команды phpinfo(), выводящий информацию о PHP.*

5. SQL-Injection (GET/Search)

	5.1 функционал приложения

	`term`

	![SQL Injection](images/chrome_AblVvH7zy5.png)

	*Скриншот показывает форму поиска, где можно ввести поисковый запрос. И результат выполнения запроса по слову `term`*

	5.2 обнаружение уязвимости

	`'`

	![SQL Injection](images/chrome_wRPil3EGHA.png)

	*Скриншот демонстрирует ошибку SQL, возникающую при вводе одиночной кавычки.*

	5.3 определение структуры запроса для вывода необходимой информации

	`1' UNION SELECT null,null,null,null,null-- `

	![SQL Injection](images/chrome_NzaBaarM0C.png)

	*Скриншот показывает результат выполнения UNION запроса с пятью null значениями.*

	`1' UNION SELECT null,null,null,null,null,null,null-- `

	![SQL Injection](images/chrome_bhyiPkk6ln.png)

	*Скриншот демонстрирует успешное выполнение UNION запроса с семью null значениями.*

	5.4 поиск таблицы с данными пользователя

	`1' UNION SELECT 1,table_name,3,4,5,6,7 FROM information_schema.tables -- `

	![SQL Injection](images/chrome_MDxLhtrCss.png)

	*Скриншот показывает результат запроса, выводящий имена таблиц из базы данных.*

	5.5 определение наименования столбцов таблицы имени пользователя и пароля

	`1' UNION SELECT 1,column_name,3,4,5,6,7 FROM information_schema.columns WHERE table_name = 'users' -- `

	![SQL Injection](images/chrome_v9jpkDqqFf.png)

	*Скриншот демонстрирует результат запроса, выводящий имена столбцов таблицы users.*

	5.6 вывод необходимой информации

	`1' UNION SELECT 1,login,admin,secret,password,6,7 FROM users -- `

	![SQL Injection](images/chrome_GIZ2jvuh9r.png)

	*Скриншот показывает результат запроса, выводящий логины и пароли пользователей.*

6. Drupal SQL-Injection (Drupageddon)

	6.1 функционал приложения

	![Drupal SQL Injection](images/chrome_ullRNEoNe6.png)

	*Скриншот демонстрирует интерфейс уязвимого Drupal сайта.*

	6.2 эксплуатация уязвимости

	![Drupal SQL Injection](images/Termius_MaGQAKuMdE.png)

	*Скриншот показывает поиск и настройку exploit для эксплуатации уязвимости через Metasploit.*

	![Drupal SQL Injection](images/Termius_LfWj8vZpyD.png)

	*Скриншот демонстрирует успешное выполнение exploit и получение доступа.*

	![Drupal SQL Injection](images/Termius_Ko5KSedVab.png)

	*Скриншот показывает дальнейшие шаги по эксплуатации уязвимости.*

	![Drupal SQL Injection](images/Termius_Asz4bl6Uy4.png)

	*Скриншот демонстрирует выполнение дополнительных команд для получения данных.*

	![Drupal SQL Injection](images/Termius_VNxWMdB090.png)

	*Скриншот показывает финальный результат эксплуатации уязвимости.*
