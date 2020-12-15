# MSSQL 내가 배운거 정리해서 넣기

<code>
LAG(a.DepSAmt, 1,0) OVER (PARTITION BY a.AssCd ORDER BY a.YY )
</code>
a.DepSAmt 전에 값이 있으면 넣고 없으면 0 a.AssCd 를 기준으로 나누고, a.YY로 맞춰 정렬

<code>
ABS((LAG(a.DepSAmt, 1,0) OVER (PARTITION BY a.AssCd ORDER BY a.YY ))
</code>
ABS : 절대값으로 바꿔줌

<code>
CONVERT(INT,(b.AqAmt-(LAG(a.DepSAmt, 1,0) OVER (PARTITION BY a.AssCd ORDER BY a.YY )))
</code>
CONVERT : INT형으로 바꿔줌(소수점 다 잘라냄)

<code>
SUBSTRING(b.AqDate,5,2)
LEFT(b.AqDate,4)
</code>
SUBSTRING : b.AqDate 왼쪽에서 5번째부터 2글자 가져오기
LEFT : b.AqDate 왼쪽에서부터 4개글자 가져오기

<code>
DATEPART(yy,getdate())
</code>
DATEPART : datetime 형식 데이터 년도만 잘라서 가져옴 mm : 월, dd : 일
