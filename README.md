# search_String
import unittest
import random

def creating_a_line(N):
    S1 = []  
    for i in range (N):                           # Создаем большую строку
        S1.append (str (random.randint (0, 1)))   #  Строка из единичек и ноликов
    St = "".join(S1)                              # Превращение числа (набор 1 и 0) в строку
    return St

def searsch_string(s1, s2):                     # функция поиска подстроки в строке
    if len(s2) == 0:
        return True
    for i in range (len(s1) - len(s2)+1) :     
        for j in range (len(s2)) :           
            if s1[i+j] != s2[j] :            
                break               
            if j == len (s2) - 1:            
                return True               
    return False

class Strings :
    
    def __init__(self, A, B):
        self.stri = creating_a_line(A)
        self.pst = creating_a_line(B)
    
class MyTestCase(unittest.TestCase):    
    
    def test_1(self):
        N = True
        for i in range (10):
            X = Strings (20, 5)
            a = searsch_string (X.stri, X.pst)
            b = X.stri.find(X.pst)
            N = N and self.assertEqual(a, b!= -1)  # Проверка неравенства двух способов поиска
        return N

    def test2(self):
        St = ""                           # Возьмем для теста пустые строки
        Pst = ""
        a = searsch_string(St, Pst)
        b = St.find(Pst)
        self.assertEqual (a, b != -1)     

    def test3(self):
        St = "Маленькой елочке холодно зимой"                            
        Pst = " холодно "                            # Заведомо положительный пример
        a = searsch_string(St, Pst)
        b = St.find(Pst)
        self.assertEqual (a, b != -1)     
    
    def test4(self):
        St = "Маленькой елочке холодно зимой"                            
        Pst = " жарко "                            # Заведомо отрицательный пример
        a = searsch_string(St, Pst)
        b = St.find(Pst)
        self.assertEqual (a, b != -1)         
    
if __name__ == '__main__':
    unittest.main()
