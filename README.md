# Lesson_6_2
Урок_6
...
------------------------------------1-----------------------------
Создать класс TrafficLight (светофор) и определить у него один атрибут color (цвет) и метод running (запуск). Атрибут реализовать как приватный. В рамках метода реализовать переключение светофора в режимы: красный, желтый, зеленый. Продолжительность первого состояния (красный) составляет 7 секунд, второго (желтый) — 2 секунды, третьего (зеленый) — на ваше усмотрение. Переключение между режимами должно осуществляться только в указанном порядке (красный, желтый, зеленый). Проверить работу примера, создав экземпляр и вызвав описанный метод. Задачу можно усложнить, реализовав проверку порядка режимов, и при его нарушении выводить соответствующее сообщение и завершать скрипт. '''

время от времени импортируйте сон

класс светофора: __color = ['Красный', 'Желтый', 'Зеленый']

def running(self):
    i = 0
    пока я < 3:
        print(f'Светофор переключается \n '
              f'{TrafficLight.__color[i]}')
        if i == 0:
            sleep(7)
        elif i == 1:
            sleep(5)
        elif i == 2:
            sleep(3)
        i += 1
Светофор = Светофор() Светофор.Выполняется()

'''

------------------------------------2-----------------------------
Реализовать класс Road (дорога), в котором определить атрибуты: length (длина), width (ширина). Значения данных атрибутов должны передаваться при создании экземпляра класса. Атрибуты сделать защищенными. Определить метод расчета массы асфальта, необходимого для покрытия всего дорожного полотна. Использовать формулу: длинаширинамасса асфальта для покрытия одного кв метра дороги асфальтом, толщиной в 1 смчисло см толщины полотна. Проверить работу метода. Например: 20м5000м25кг5см = 12500 т '''

классная дорога: def init(self, _length, _width): сам._length = _length сам._width = _width

def mass(self):
    return self._length * self._width
класс массовости (дорожный): def init(self, _length, _width, volume): супер().init(_length, _width) сам.volume = громкость

r = массовое количество(25, 10000, 125) печать(r. mass())

'''

------------------------------------3-----------------------------
Реализовать базовый класс Worker (работник), в котором определить атрибуты: name, surname, position (должность), income (доход). Последний атрибут должен быть защищенным и ссылаться на словарь, содержащий элементы: оклад и премия, например, {"заработная плата": заработная плата," бонус": бонус}. Создать класс Position (должность) на базе класса Worker. В классе Position реализовать методы получения полного имени сотрудника (get_full_name) и дохода с учетом премии (get_total_income). Проверить работу примера на реальных данных (создать экземпляры класса Position, передать данные, проверить значения атрибутов, вызвать методы экземпляров). '''

классный работник:

def __init__(self, name, surname, position, wage, bonus):
    self.name = name
    self.surname = surname
    self.position = position
    self._income = {"wage": wage, "bonus": bonus}
class Position(Worker):

def __init__(self, name, surname, position, wage, bonus):
    super().__init__(name, surname, position, wage, bonus)

def get_full_name(self):
    return self.name + ' ' + self.surname

def get_total_income(self):
    return self._income.get('wage') + self._income.get('bonus')
    # return f'{sum(self._income.values())}'
a = Position('Peter', 'The Great', 'Beekeeper', 100000, 25000) print(a.get_full_name()) print(a.position) print(a.get_total_income())

'''

------------------------------------4-----------------------------
Реализуйте базовый класс Car. У данного класса должны быть следующие атрибуты: speed, color, name, is_police (булево). А также методы: go, stop, turn(direction), которые должны сообщать, что машина поехала, остановилась, повернула (куда). Опишите несколько дочерних классов: TownCar, SportCar, WorkCar, PoliceCar. Добавьте в базовый класс метод show_speed, который должен показывать текущую скорость автомобиля. Для классов TownCar и WorkCar переопределите метод show_speed. При значении скорости свыше 60 (TownCar) и 40 (WorkCar) должно выводиться сообщение о превышении скорости. Создайте экземпляры классов, передайте значения атрибутов. Выполните доступ к атрибутам, выведите результат. Выполните вызов методов и также покажите результат. '''

class Car: # atributes def init(self, speed, color, name, is_police): self.speed = speed self.color = color self.name = name self.is_police = is_police

# methods
def go(self):
    return f'{self.name} is started'

def stop(self):
    return f'{self.name} is stopped'

def turn_right(self):
    return f'{self.name} is turned right'

def turn_left(self):
    return f'{self.name} is turned left'

def show_speed(self):
    return f'Current speed {self.name} is {self.speed}'
class TownCar(Car): def init(self, speed, color, name, is_police): super().init(speed, color, name, is_police)

def show_speed(self):
    print(f'Current speed of town car {self.name} is {self.speed}')

    if self.speed > 40:
        return f'Speed of {self.name} is higher than allow for town car'
    else:
        return f'Speed of {self.name} is normal for town car'
класс спорткар(автомобиль): def init(self, speed, color, name, is_police): супер().init(скорость, цвет, имя, is_police)

класс WorkCar (автомобиль): def init(self, speed, color, name, is_police): супер().init(скорость, цвет, имя, is_police)

def show_speed(self):
    print(f'Current speed of work car {self.name} is {self.speed}')

    if self.speed > 60:
        return f'Speed of {self.name} is higher than allow for work car'
класс PoliceCar(автомобиль): def init(self, speed, color, name, is_police): супер().init(скорость, цвет, имя, is_police)

def police(self):
    if self.is_police:
        return f'{self.name} is from police department'
    else:
        return f'{self.name} is not from police department'
audi = SportCar (100, 'Red', 'Audi', False) oka = TownCar (30, 'White',' Oka', False) lada = WorkCar (70, 'Rose',' Lada', True) ford = полицейская машина (110, 'синий', 'Форд', True) печать(Лада.повернуть налево()) print (f ' When {oka.turn_right ()}, затем {audi.остановить()}') print (f ' {lada.go ()} со скоростью ровно {lada.show_speed ()}') print (f ' {lada.name} есть {Лада.цвет}') print (f ' is {audi.name} полицейская машина? {audi. is_police}') print (f ' is {lada.name} полицейская машина? {lada. is_police}') печать(Ауди.show_speed()) печать(ока.show_speed()) печать(ford.полиция()) печать(ford.show_speed())

'''

------------------------------------5-----------------------------
Реализовать класс Stationery (канцелярская принадлежность). Определить в нем атрибут title (название) и метод draw (отрисовка). Метод выводит сообщение “Запуск отрисовки.” Создать три дочерних класса Pen (ручка), Pencil (карандаш), Handle (маркер). В каждом из классов реализовать переопределение метода draw. Для каждого из классов методы должен выводить уникальное сообщение. Создать экземпляры классов и проверить, что выведет описанный метод для каждого экземпляра. '''

класс стационарный: def _ _ init__(self, title): самость.title = название

def draw(self):
    return f'Запуск отрисовки {self.название}'
ручка класса(стационарная): def _ _ init__(self, title): супер()._ _ init__(название)

def draw(self):
    return f'Вы взяли {self.название}. Запуск отрисовки ручкой'
класс карандаша(стационарный): def _ _ init__(self, title): супер()._ _ init__(название)

def draw(self):
    return f'Вы взяли {self.название}. Запуск отрисовки карандашом'
ручка класса(стационарная): def _ _ init__(self, title): супер()._ _ init__(название)

def draw(self):
    return f'Вы взяли {self.название}. Запуск отрисовки маркером'
pen = Pen('Ручка') pencil = Pencil('Карандаш') handle = Handle('Маркер') печать(пер.ничья()) печать(карандашом.ничья()) печать(ручка.ничья())
