# make_C4_2_3
Создайте фильтр, который будет отбрасывать полученные данные, если они содержат "localhost" в поле "source". Может потребоваться фильтр grep и плагин вывода null.  Тренироваться можно на сообщении ‘json={“source”: “localhost”, “message”: “test”}’.
Конфиг /etc/td-agent/td-agent.conf 
Проверяем работу:
curl -X POST -d 'json={"message":"It works!"}' http://localhost:8888/test1

Пропускает: curl -X POST -d 'json={"message":"now test 22:25"}' http://localhost:8888/test1
Не пропускает: curl -X POST -d 'json={“source”: “localhost 22:24”}' http://localhost:8888/test1

