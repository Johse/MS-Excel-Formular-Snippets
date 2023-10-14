# MS-Excel-Formular-Snippets
Usefull Single Cell formulars for MS Excel - without the use of VBA

# Modulus 11 check (Danish CPR)
Returns false if string in cell A1 != 10 digits and if the control digit (10th digit is non-compliant): 
```
=IF(LEN(TRIM(A1))=10,IF(VALUE(TRIM(A1))=VALUE(TEXTJOIN("",TRUE,LEFT(TRIM(A1),9),(11-(SUM(4*MID(A1,1,1),3*MID(A1,2,1),2*MID(A1,3,1),7*MID(A1,4,1),6*MID(A1,5,1),5*MID(A1,6,1),4*MID(A1,7,1),3*MID(A1,8,1),2*MID(A1,9,1))-(TRUNC(SUM(4*MID(A1,1,1),3*MID(A1,2,1),2*MID(A1,3,1),7*MID(A1,4,1),6*MID(A1,5,1),5*MID(A1,6,1),4*MID(A1,7,1),3*MID(A1,8,1),2*MID(A1,9,1))/11)*11))))),TRUE,FALSE),FALSE)
```
