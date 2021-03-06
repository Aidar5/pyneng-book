Параметры и аргументы функций
#############################

Цель создания функции, как правило, заключается в том, чтобы вынести
кусок кода, который выполняет определенную задачу, в отдельный объект.
Это позволяет использовать этот кусок кода многократно, не создавая
его заново в программе.

Как правило, функция должна выполнять какие-то действия с входящими
значениями и на выходе выдавать результат.

При работе с функциями важно различать:

-  **параметры** - это переменные, которые используются при создании
   функции.
-  **аргументы** - это фактические значения (данные), которые передаются
   функции при вызове.

Для того, чтобы функция могла принимать входящие значения, ее нужно
создать с параметрами (файл func_check_passwd.py):

.. code:: python

    In [1]: def check_passwd(username, password):
       ...:     if len(password) < 8:
       ...:         print('Пароль слишком короткий')
       ...:         return False
       ...:     elif username in password:
       ...:         print('Пароль содержит имя пользователя')
       ...:         return False
       ...:     else:
       ...:         print(f'Пароль для пользователя {username} прошел все проверки')
       ...:         return True
       ...:

В данном случае, у функции два параметра: username и password.

Функция проверяет пароль и возвращает False, если проверки не прошли и
True если пароль прошел проверки:

.. code:: python

    In [2]: check_passwd('nata', '12345')
    Пароль слишком короткий
    Out[2]: False

    In [3]: check_passwd('nata', '12345lsdkjflskfdjsnata')
    Пароль содержит имя пользователя
    Out[3]: False

    In [4]: check_passwd('nata', '12345lsdkjflskfdjs')
    Пароль для пользователя nata прошел все проверки
    Out[4]: True


При таком определении функции надо обязательно передать оба аргумента.
Если передать только один аргумент, возникнет ошибка:

.. code:: python

    In [5]: check_passwd('nata')
    ---------------------------------------------------------------------------
    TypeError                                 Traceback (most recent call last)
    <ipython-input-5-e07773bb4cc8> in <module>
    ----> 1 check_passwd('nata')

    TypeError: check_passwd() missing 1 required positional argument: 'password'


Аналогично, возникнет ошибка, если передать три и больше аргументов.

.. toctree::
   :maxdepth: 1

   3a_func_params_types.rst
   3a_func_args_types.rst
   3b_func_args_var.rst      
   3b_func_unpacking_args.rst

