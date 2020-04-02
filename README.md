'''
# search_String
import unittest
import random

def creating_a_line(N):
    S1 = []  
    for i in range(N):                           
        S1.append(str(random.randint(0, 1)))   
        #  The string consists of 1 and 0
    St = "".join(S1)                               
    return St

def searsch_string(s1, s2):                     
# the search function substring within the string
    if len(s2) == 0:
        return True
    for i in range(len(s1) - len(s2) + 1):     
        for j in range(len(s2)):           
            if s1[i+j] != s2[j]:            
                break               
            if j == len(s2) - 1:            
                return True               
    return False
""" These is a function that require testing
"""
class Strings:
    
    def __init__(self, A, B):
        self.str__ = creating_a_line(A)
        self.pst = creating_a_line(B)
""" This class is designed to create a tuple of two rows
"""
    
class MyTestCase(unittest.TestCase):    
    
    def test_1(self):
        N = True
        for i in range (10):
            X = Strings(20, 5)
            a = searsch_string (X.str__, X.pst)
            b = X.str__.find(X.pst)
            N = N and self.assertEqual(a, b!= -1)      # Check the inequality of methods
        return N
    """ This test performs a variety of audits using random values of the argument
    """
    def test_2(self):
        St = ""                           
        Pst = ""                                      # Empty lines to use in the example
        a = searsch_string(St, Pst)
        b = St.find(Pst)
        self.assertEqual(a, b != -1)     

    def test_3(self):
        St = "Маленькой елочке холодно зимой"                            
        Pst = " холодно "                              # A known positive result
        a = searsch_string(St, Pst)
        b = St.find(Pst)
        self.assertEqual(a, b != -1)     
    
    def test_4(self):
        St = "Маленькой елочке холодно зимой"                            
        Pst = " жарко "                                # A known negative result
        a = searsch_string(St, Pst)
        b = St.find(Pst)
        self.assertEqual(a, b != -1)         
    """These tests check the function's performance with some argument values
    """  
if __name__ == '__main__':
    unittest.main()
