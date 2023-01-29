# Tableau-

Formulas de tableau
1. Año Actual : {FIXED : SUM(IF YEAR([Order Date])= {MAX(YEAR([Order Date]))} THEN [Sales] END) } esta formula calcula las ventas del año actual

2. Año Anterior = {FIXED : SUM(IF YEAR([Order Date])= {MAX(YEAR([Order Date]))} THEN [Sales] END ) }

Otra forma es la siguiente:
    1. craemos la columna de fecha reciente = { MAX([Order Date])}
    2. fecha Año Anterior = DATEADD('year',-1, [fecha reciente])
    3. Jan Fecha reciente = DATETRUNC('year',[fecha reciente])
    4. Jan Fecha Año Anterior = DATEADD('year', -1, [Jan Fecha reciente])
    5. ventas Actual = if  [Order Date] >= [Jan Fecha reciente]  and [Order Date] <= [fecha reciente] then [Sales]END
    6. Ventas Año Anterior = if  [Order Date] >= [Jan Fecha Año Anterior] and [Order Date] <= [fecha Año Anterior] then [Sales]END


3. Ultimo 12 meses = DATETRUNC('month' , [Order Date])>= DATEADD('month',-11,{max(DATETRUNC('month' , [Order Date]))})


## Realizar calculos de comparación entre día actual y día anterior

1. Se crea el campo día a partir de la fecha : 
  1. clic derecho  a la fecha
  2. Create custum date
  3. date value
  4. Dia actual = {max(day)}
  5. Dia anterior = [ Dia actual] -1
  6. ventas Dia Actual = INT([Day]=[Dia actual]) * [Sales]
  7. ventas dia anterior = INT([Day]= [Dia anterior])*[Sales]
  8. Ventas Diferencia D/D = SUM([ventas Dia Actual]) - SUM([ventas dia anterior])
  9. Ventas D ferencia D/D% = [Ventas Diferencia D/D] / SUM([ventas dia anterior])
  10. Dar formato a % +0.00%;-0.00%
  11. color pos/ neg = SIGN([Sales D/D]) 
  
  
 
  
