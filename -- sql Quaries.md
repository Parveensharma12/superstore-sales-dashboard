\-- Table Creation

CREATE TABLE orders (...);



\-- Data Import

LOAD DATA LOCAL INFILE '...' INTO TABLE orders ...;



\-- Query 1: Category-wise Total Sales

SELECT category, ROUND(SUM(sales), 2) AS total\_sales

FROM orders GROUP BY category ORDER BY total\_sales DESC;



**Category        Total\_Sales**   

**Technology	827455.94**

**Furniture	728658.75**

**Office Supplies	705422.28**



\-- Query 2: Monthly Sales Trend

SELECT YEAR(order\_date) AS yr, MONTH(order\_date) AS mth, ROUND(SUM(sales), 2) AS total\_sales

FROM orders GROUP BY YEAR(order\_date), MONTH(order\_date) ORDER BY yr, mth;



**Year   Month    Sales**

**2015	1	14205.71**

**2015	2	4519.92**

**2015	3	55205.83**

**2015	4	27906.86**

**2015	5	23644.30**

**2015	6	34322.94**

**2015	7	33781.52**

**2015	8	27117.53**

**2015	9	81623.52**

**2015	10	31453.37**

**2015	11	77907.69**

**2015	12	68167.08**

**2016	1	18066.96**

**2016	2	11951.40**

**2016	3	32339.32**

**2016	4	34154.51**

**2016	5	29959.56**

**2016	6	23599.39**

**2016	7	28608.25**

**2016	8	36818.33**

**2016	9	63133.56**

**2016	10	31011.71**

**2016	11	75249.35**

**2016	12	74543.60**

**2017	1	18542.52**

**2017	2	22978.82**

**2017	3	51165.04**

**2017	4	38679.77**

**2017	5	56656.93**

**2017	6	39724.49**

**2017	7	38320.81**

**2017	8	30542.18**

**2017	9	69193.44**

**2017	10	59583.09**

**2017	11	79066.56**

**2017	12	95739.15**

**2018	1	43476.47**

**2018	2	19920.98**

**2018	3	58863.41**

**2018	4	35541.90**

**2018	5	43825.95**

**2018	6	48190.73**

**2018	7	44825.12**

**2018	8	62837.81**

**2018	9	86152.90**

**2018	10	77448.17**

**2018	11	117938.14**

**2018	12	83030.38**



\-- Query 3: Region-wise Sales

SELECT region, ROUND(SUM(sales), 2) AS total\_sales

FROM orders GROUP BY region ORDER BY total\_sales DESC;



**Region  Sales**

**West	710219.77**

**East	669518.85**

**Central	492646.90**

**South	389151.45**



\-- Query 4: Top 10 Customers

SELECT customer\_name, ROUND(SUM(sales), 2) AS total\_sales

FROM orders GROUP BY customer\_name ORDER BY total\_sales DESC LIMIT 10;



**Customer Name           Sales**

**Sean Miller	        25043.07**

**Tamara Chand	        19052.22**

**Raymond Buch	        15117.35**

**Tom Ashbrook	        14595.62**

**Adrian Barton	        14473.57**

**Ken Lonsdale	        14175.23**

**Sanjit Chand	        14142.34**

**Hunter Lopez	        12873.30**

**Sanjit Engle	        12209.44**

**Christopher Conant	12129.08**



\-- Query 5: Subquery — Above Average Orders

SELECT order\_id, customer\_name, sales

FROM orders WHERE sales > (SELECT AVG(sales) FROM orders)

ORDER BY sales DESC LIMIT 20;



**Order\_id        Customer\_name           Sales** 

**CA-2015-145317	Sean Miller	        22638.48**

**CA-2017-118689	Tamara Chand	        17499.95**

**CA-2018-140151	Raymond Buch	        13999.96**

**CA-2018-127180	Tom Ashbrook	        11199.97**

**CA-2018-166709	Hunter Lopez	        10499.97**

**CA-2017-117121	Adrian Barton	        9892.74**

**CA-2015-116904	Sanjit Chand	        9449.95**

**US-2017-107440	Bill Shonely	        9099.93**

**CA-2017-158841	Sanjit Engle	        8749.95**

**CA-2017-143714	Christopher Conant	8399.98**

**CA-2015-143917	Ken Lonsdale	        8187.65**

**CA-2015-139892	Becky Martin	        8159.95**

**US-2018-168116	Grant Thornton	        7999.98**

**CA-2015-145541	Tom Boeckenhauer	6999.96**

**CA-2016-145352	Christopher Martinez	6354.95**

**CA-2018-138289	Andy Reiter	        5443.96**

**US-2017-140158	Daniel Raglin	        5399.91**

**CA-2018-143112	Todd Sumrall	        5199.96**

**CA-2018-135909	Jane Waco	        5083.96**

**CA-2017-136301	Edward Hooks	        4912.59**



\-- Query 6: Sub-Category Performance

SELECT sub\_category, ROUND(SUM(sales), 2) AS total\_sales, COUNT(\*) AS num\_orders

FROM orders GROUP BY sub\_category ORDER BY total\_sales DESC; 



**Sub\_Category    Total\_Sales             Num\_orders**

**Phones	        327782.49	         876**

**Chairs	        322822.75	         607**

**Storage	        219343.37	         832**

**Tables	        202810.77	         314**

**Binders	        200028.82	         1492**

**Machines	189238.68	         115**

**Accessories	164186.70	         756**

**Copiers	        146248.07	          66**

**Bookcases	113813.25	         226**

**Appliances	104618.38	         459**

**Furnishings	89211.98	         931**

**Paper	        76828.34	         1338**

**Supplies	46420.29	         184**

**Art	        26705.42	         785**

**Envelopes	16128.02	         248**

**Labels	        12347.71	         357**

**Fasteners	3001.93	                 214**



