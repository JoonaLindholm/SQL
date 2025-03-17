# SQL harjoittelua  

### Esimerkkejä  

Haetaan kaikki työntekijätiedot  

**SELECT * FROM** employees;  
**SELECT** = haetaan // * = kaikki // employees  = tämän nimisestä taulusta haetaan tiedot  

**SELECT** firstname, lastname from employees;

hae tyontekijoiden etu- ja sukunimet  
select firstname, lastname from employees;  

hae kaikkien tuotteiden nimet  
select productname from products;  

hae tuotteiden nimet aakkosjarjestyksessa  
select productname from products order by productname asc;  

hae tuotteiden nimet ja hinnat, kallein tuote ensin  
select productname, unitprice from products order by unitprice desc;  

hae kaikki tuotteet, joiden hinta > 60  
select * from products where unitprice>60  

hae kaikki tuotteet, joiden hinta on valilla 30 ja 50  
select * from products  

where unitprice>=30 and unitprice<=50;  
select * from products  
where unitprice between 30 and 50;  

hae kaikki Ranskalaiset tavarantoimittajat  
select * from suppliers where country='France';  

hae uusimman tilauksen perustiedot  
select * from orders where orderid=  
(select max(orderid) from orders);  

laske myynnissa olevien tuotteiden keskihinta  
select avg(unitprice) from products  
where Discontinued=0;  

laske myyntimme summa alennukset huomioiden  
select sum((UnitPrice*Quantity)*(1-discount)) from [Order Details]  

mika on Maxilakun id?  
select productid from Products where ProductName='Maxilaku';  

milla summalla Maxilakua on myyty?  
select sum((UnitPrice*Quantity)*(1-discount)) from [Order Details]  
where productid=  
(select productid from Products where ProductName='Maxilaku');  

kuka on Robert Kingin esimies?  
select * from employees where employeeid=  
(select ReportsTo from Employees  
where FirstName='Robert' and LastName='King');  

listaa kaikki Saksalaiset asiakkaat  
select * from customers where Country='Germany';  

kuinka monta tilausta Speedy Express on rahdannut?  
select count(*) as lkm from orders where shipvia=  
(select shipperid from Shippers where CompanyName='Speedy Express');  

Kuka on vanhin tyontekijamme?  
select * from employees where birthdate=  
(select min(birthdate) from Employees)  

---

### Kotitehtävät  

<img width="909" alt="image" src="https://github.com/user-attachments/assets/25ff05c7-e7a1-401e-a3f6-068ef1c44bf1" />  

Hae kaikki työntekijätiedot  
**SELECT * FROM employees;**  

Hae kaikki työntekijätiedot sukunimen mukaan laskevassa järjestyksessä  
SELECT * FROM Employees ORDER BY LastName DESC;  

Hae kaikkien Lontoossa työskentelevien työntekijöiden nimet ja toimipisteet    
SELECT FirstName, LastName FROM Employees WHERE Country = 'London'; // Toimipisteet?  

Hae kaikki tuotetiedot hinnan mukaan laskevassa järjestyksessä  
SELECT * FROM Products ORDER BY UnitPrice DESC;  

Hae kaikki myynnistä poistuneet tuotteet  
SELECT * FROM Products WHERE Discontinued =1;  

Hae kaikkien yli 10 $ maksavien tuotteiden nimet  
SELECT ProductName FROM Products WHERE UnitPrice > 10;  

Hae kaikkien 10-20 $ maksavien tuotteiden nimet ja tuoteryhmät  
SELECT ProductName, CategoryID FROM Products WHERE UnitPrice>=10 AND UnitPrice<=20;  

Hae Queso Cabralesin hinta ja varastosaldo  
SELECT UnitPrice, UnitsInStock FROM Products WHERE ProductName='Queso Cabrales';  

Hae kaikki tiedot Steven Buchanan alaisista  
SELECT * FROM Employees Where ReportsTo=(SELECT EmployeeID FROM Employees WHERE FirstName = 'Steven' AND LastName = 'Buchana');   

Tulosta sen tuoteryhmän nimi, jonka id on 8  
SELECT CategoryName FROM Categories WHERE CategoryID=8;  

Laske ryhmään 8 kuuluvien tuotteiden lukumäärä  

Laske ryhmään "Seafood" kuuluvien tuotteiden lukumäärä
Laske ryhmään "Seafood" kuuluvien tuotteiden keskihinta
Laske ryhmään "Seafood" kuuluvien tuotteiden hintojen summa
Hae kaikki Karkki Oy:n maahantuomat tuotteet
Laske Karkki Oy:n maahantuomien tuotteiden keskihinta
Laske kuinka monessa tilauksessa on tuotetta "Valkoinen suklaa"
Laske millä summalla tuotetta "Valkoinen suklaa" on myyty
Etsi halvin tuote
Laske United Packagen rahtaamien tilausten lukumäärä



