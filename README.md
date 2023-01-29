# Tableau-

Formulas de tableau
1. el año mas reciente : {FIXED : SUM(IF YEAR([Order Date])= {MAX(YEAR([Order Date]))} THEN [Sales] 
END
) } esta formula calcula las ventas del año actual
