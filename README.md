# Java
Задание:
Реализовать методы, имитирующие класс ArrayList:
a. Добавление в конец (принимает массив, заполненность массива, элемент,
возвращает массив)
b. Добавление по индексу (принимает массив, элемент, заполненность массива,
индекс, возвращает массив)
c. Получение по индексу (принимает массив, заполненность массива, индекс,
возвращает массив)

Объяснение:
3 файла. 

List - инициализатор (названия методов);

ArrayList - описание методов;

TestArrayList - тестирование;


Файл ArrayList:


private - потому что мы не хотим чтобы он был изменен за пределами этого класса.
- настраиваем начальную ёмкость
- а также нужно что-то для хранения данных, назовём её Дата (equals element =общие)
- переменная для отслеживания текущего размера нашего массива
- для возможности заполнения массива ещё и другими данными вводим capacity (ёмкость)


Даём открытый конструктор (таккак это конкретный класс)
13 - инициализировать наш массив данных в новый массив объектов. Для совместимости данных приводим к общему виду


Первым методом в нашем списке будет логический метод добавления. Метод добавляет указанный эл-т в конец. Этот метод всегда будет возвращать true, так как в ArrayList вы всегда можете добавить новый эл-т.

Первое, что делаем, это проверяем если наш размер меньше, чем размер нашей ёмкости, это означает что мы можем просто установить наши новые данные в индексе. Затем мы увеличиваем наш размер. Иначе мы всё ещё устанавливаем наши данные , но в уже увеличенный в 2 раза ёмкость методом rellocate (перераспределение) . Этот метод увеличивает в 2 раза ёмкость и затем берет данные , которые мы добавили, и копируем их в новый массив, превышающий предыдущую в 2 раза.

ВТОРОЙ add. Он берёт эл-т и добавляет его в указанный индекс, а затем сдвигает оставшиеся эл-ты вниз. Для начала проверяем границы нашего массива, если индекс меньше 0 или индекс большеен или равен размера , то в этом случае мы не можем добавить эл-т с индексом -5 или что-то большее чем размер нашего массива. И если это так то выбрасываем исключение, т.е. мы сообщаем нашему пользователю что мы не можем добавить этот эл-т в тот индекс (потому что этот индекс в массиве не сущ.). Далее мы должны убедить что есть место если наш размер больше или равен ёмкости , тогда нам придётся снова перераспределить , создав больше места, вызвав метод rellocate. И после этого мы можем сместить эл-ты вниз . Этот цикл for сдвинет эл-ты текущего массива вниз на один индекс, затем после этого мы можем мирно добавить наш текущий эл-т, который мы можем вставить. Собственно, увеличиваем размер.

ТРЕТИЙ метод get возвращает эл-т в указанной позиции, поэтому этот метод принимает целое число в качестве параметра и возвращает эл-т по этому индексу. Проверяем если индекс меньше 0 или индекс больше или равен размеру. Мы выходим за пределы и выбрасываем исключение, где мы указываем индекс в котором возникаает проблема. И если этот оператор не запускается это значит что всё хорошо и поэтому мы можем просто вернууть данные по индексу. Поэтому мы снова проверяем границы если границы явл.отрицательными мы не можем получить данные или если индекс больше размера то мы не можем получить какие-либо данные оттуда.

ЧЕТВЁРТЫЙ Size возвращает кол-во эл-тов в массиве. В самом начале мы проинициализировали size переменного размера, далее его изменяли исходя из кол-ва эл-ов . Каждый раз когда мы увеличиваем размер массива, мы реализуем size, Чтобы получить фактический размер нашего ArrayList (класс) мы просто возвращаем значение.
Для того, чтобы переопределить наш строковый метод по умолчанию, мы создаём свой, создав наш собственный метод обзедоступным.
Здесь мы создаём временную строку , назовём её результатом , добавляем открытую скобку , первый эл-т и присоединяем все оставшиеся эл-ты к нашей переменной реультат . Добавляем закрывающую скобку. И после этого возвращаем рукзультат.


Файл TestArrayList:

Определяем массив int.
Далее мы просматриваем этот массив и добаавляем каждое число, каждую цифру из этого массива в ArrayList.
Создаём список массивов на основе интерфейса List и класса ArrayList.
Так, чтобы добавить наши эл-ты мы можем просто создать цикл в котором добавим все эл-ты массива в наш объект ArrayList.
