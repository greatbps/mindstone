---
aliases: [파이썬, RPA, 엑셀]
tags: [보고서, 상시평가, 작성중]
키워드 : [[파이썬 업무 자동화]]
#파이썬 업무 자동화 
---
https://goodthings4me.tistory.com/487


동영상 보고 강의 만든다.
https://www.youtube.com/watch?v=exgO1LFl9x8&ab_channel=%EB%82%98%EB%8F%84%EC%BD%94%EB%94%A9


아래에는 코드만 나와있어 보완 필요함


1. 한글 만들고
2. 각 파일에 맞게 소스 만들고
3. 예제 파일 엑셀로 첨부
4. 자동화 내용에 대해 시나리오 하나 만들어 포장한다.
 
 업무 자동화(RPA)를 위한 툴로 많이 사용되는 것은 엑셀이다. 특히, 엑셀 VBA로 여러 데이터 관련 복잡한 업무를 자동화하는데, 엑셀이 아닌 파이썬으로도 가능한지 찾다가 유튜브에서 영상 하나를 찾았다. 강의 내용이 좋아서 기능 참고가 필요할 때 빨리 찾아볼 수 있도록 간단하게 정리해보았다.


+ 코딩은 비주얼 스튜디오 코드에 파이썬 2022.16.1 버전 사용
+ 폴더는 C:\LGCNS 폴더 생성하여 사용  


### 목차는 다음과 같다

-   엑셀 파일 만들기
-   엑셀 시트 관리
-   엑셀 셀(cell) 관리
-   엑셀 파일, 셀 데이터 불러오기
-   셀 범위(cell range) 다루기
-   엑셀에서 값 찾기
-   엑셀에서 행, 열 삽입, 삭제, 이동
-   엑셀 차트(Chart) 다루기
-   엑셀 셀 스타일(Style) 다루기
-   엑셀 수식(함수) 활용해보기
-   엑셀에서 수식(데이터) 가져오기
-   엑셀 셀(Cell) 병합
-   엑셀에 이미지 추가

■ 엑셀 파일 만들기 - Workbook()

```
from openpyxl import Workbook

wb = Workbook()  # 새 워크북 생성
ws = wb.active  # 현재 활성화된 sheet 가져옴, ws = wb['Sheet']
ws.title = 'NadoSheet'  # sheet 이름 변경
wb.save('nadoCoding_sample.xlsx')
wb.close()
```

■ 엑셀 시트 관리

```
from openpyxl import Workbook

wb = Workbook()
ws = wb.create_sheet()  # 새로운 Sheet를 기본 이름(Sheet1)으로 생성
ws.title = 'MySheet'
ws.sheet_properties.tabColor = 'ff66ff'  # 탭 색을 rgb 형태로 값을 넣어줌

ws1 = wb.create_sheet('YourSheet')  # 주어진 이름으로 Sheet 생성
ws2 = wb.create_sheet('NewSheet', 2)  # 시트 index 2번째에 Sheet 생성

# 시트 접근은 ws1, ws2,..처럼 하는 방법도 있고, wb['시트명'] 처럼 dict 형태로도 접근 가능
print(wb['NewSheet'].title)
new_ws = wb['NewSheet']
print(new_ws.title)

# 모든 시트 확인, 리스트로 반환
print(wb.sheetnames)  # ['Sheet', 'MySheet', 'NewSheet', 'YourSheet']

# Sheet 복사
new_ws['A1'] = 'Test'  # A1 셀에 데이터 넣음
target = wb.copy_worksheet(new_ws)  # 복사된 Sheet가 우측 마지막에 생성됨 (데이터 포함)
target.title = 'Copied_Sheet'
    
wb.save('nadoCoding_sample.xlsx')
```

■ 엑셀 셀(cell) 관리

```
import openpyxl
from openpyxl import Workbook
from random import *

wb = openpyxl.load_workbook(filename = 'nadoCoding_sample.xlsx')
ws = wb.active  # 첫 번째 Sheet 활성

# 셀에 데이터(값) 입력
ws['A1'] = 1
ws['A2'] = 2
ws['B1'] = 3
ws['B2'] = 4

print(ws['A1'])  # <Cell 'Sheet'.A1> - 셀 객체정보만 출력
print(ws['A1'].value)  # 1 - 입력된 값 출력
print(ws['A10'].value)  # None -  값이 없을 때는 'None' 출력

# 엑셀에서 행(row) = 1, 2, 3,...  / 열(column()은 A, B, C,... 열에 대해 1, 2, 3,.. 지칭 가능
print(ws.cell(row=1, column=1).value)  # 1 - ws['A1'].value와 동일
print(ws.cell(1, 1).value) # 1 - ws['A1'].value와 동일  # cell(R, C) RC순

ws.cell(1, 3).value = 10
ws.cell(2, 3, value=20)
c = ws.cell(3, 3, value=30)
print(c.value)

# 반복문으로 랜덤 숫자 채워보기
for x in range(1, 11):
    for y in range(1, 11):
        ws.cell(x, y).value = randint(0, 100)  # 0~100 사이의 숫자

wb.save('nadoCoding_sample.xlsx')
```

■ 엑셀 파일 불러오기, 셀 데이터 불러오기 - load_workbook()

```
from openpyxl import load_workbook

wb = load_workbook('nadoCoding_sample.xlsx')  # 엑셀 파일 불러옴
ws = wb.active  # 활성화된 Sheet

# cell 데이터 불러오기
for x in range(1, 11):
    for y in range(1, 11):
        print(ws.cell(x, y).value, end=' ')
    print()

# cell 갯수를 모를 때, 
# 행(row)과 열(column)의 최대 행과 열(ws.max_row, ws.max_column)을 구해서 사용할 수 있다
for x in range(1, ws.max_row):
    for y in range(1, ws.max_column):
        print(ws.cell(x, y).value, end=' ')
    print()
```


■ 셀 범위(cell range) 다루기 - append(), ws.max_row, ws.max_column

```
from openpyxl import Workbook
from openpyxl.utils.cell import coordinate_from_string

wb = Workbook()
ws = wb.active

# 한 줄씩 입력하기 - append(iterable) list|tuple|range|generator 즉, 리스트나 튜플 등 형태
ws.append(['번호', '영어', '수학'])  # 제목 리스트
for i in range(1, 11):
    ws.append([i, randint(0, 100), randint(0, 100)])

# 워크시트에서 B열(영어)만 가져오기
col_B = ws['B']
print(col_B)  # (<Cell 'Sheet'.B1>, <Cell 'Sheet'.B2>,... <Cell 'Sheet'.B11>) 튜플 형태
for cell in col_B:
    print(cell.value, end=' ')


# 워크시트에서 2개 열, B열(영어), C열(수학) 가져오기
col_range = ws['B:C']
print(col_range)
# 튜플 ((), ()) 형태
# ((<Cell 'Sheet'.B1>,... <Cell 'Sheet'.B11>), (<Cell 'Sheet'.C1>,... <Cell 'Sheet'.C11>))
for cols in col_range:
    for cell in cols:  # 안쪽 튜플 B열, C열 각각 지정
        print(cell.value)

# 워크시트에서 행(row) 가져오기
row_title = ws['1']
print(row_title)  # (<Cell 'Sheet'.A1>, <Cell 'Sheet'.B1>, <Cell 'Sheet'.C1>) 튜플
for cell in row_title:
    print(cell.value, end=' ')
     
row_range = ws['2:6']  # 2번째 줄(row)에서 6번째 줄(row)까지 가져오기
print(row_range)
# ((<Cell 'Sheet'.A2>, <Cell 'Sheet'.B2>, <Cell 'Sheet'.C2>), 
#  (<Cell 'Sheet'.A3>, <Cell 'Sheet'.B3>, <Cell 'Sheet'.C3>), 
#  (<Cell 'Sheet'.A4>, <Cell 'Sheet'.B4>, <Cell 'Sheet'.C4>), 
#  (<Cell 'Sheet'.A5>, <Cell 'Sheet'.B5>, <Cell 'Sheet'.C5>), 
#  (<Cell 'Sheet'.A6>, <Cell 'Sheet'.B6>, <Cell 'Sheet'.C6>))

for rows in row_range:
    for cell in rows:
        print(cell.value, end=' ')
    print()

# 몇 번째 줄(row)부터 마지막 줄까지 가져오기
row_range = ws[2:ws.max_row]
for rows in row_range:
    for cell in rows:
        print(cell.value, end=' ')
    print()

# 어떤 데이터가 몇 번째 셀에 있는지 정보를 필요로 할 때 
# 모듈 from openpyxl.utils.cell import coordinate_from_string 사용
for rows in row_range:
    for cell in rows:
        print(cell.coordinate, end=' ')  # cell.coordinate --> A2 B2 C2 ....
    print()

for rows in row_range:
    for cell in rows:
        xy = coordinate_from_string(cell.coordinate)
        print(xy, end=' ')  
        # cell.coordinate를 R C로 분리한 튜플 형태 ('A', 2) ('B', 2) ('C', 2) ...로 반환
        print(xy[0], end=' ')  # A B ...
        print(xy[1], end=' ')  # 2 3 ...
    print()

for rows in row_range:
    for cell in rows:
        xy = coordinate_from_string(cell.coordinate)
        print(xy[0], end='')  # A B ...
        print(xy[1], end=' ')  # 2 3 ...
        # print(cell.coordinate, end=' ') 과 동일한 형태로 출력
    print()
    
# 전체 rows - 전체 셀을 row 기준으로 튜플로 반환
print(ws.rows)  # <generator object Worksheet._cells_by_row at 0x000001681A1DB270>
print(tuple(ws.rows))  # 튜플 ((), (),...)) 가로(row) 방향 A1 B1 C1
print(list(ws.rows))  # 리스트 [(), (),...]

for row in tuple(ws.rows):  # row[0] row[1] row[2]
    print(row[1].value)  # 각 row에 대해 index 1인 영어 점수 출력
    

# 전체 columns - 전체 셀을 column 기준으로 튜플로 반환
print(ws.columns)  # <generator object Worksheet._cells_by_col at 0x000001681A1D4510>
print(tuple(ws.columns))  # 튜플 ((), (),...)) 세로(column) 방향 A1 A2 A3 A4 ... A11
print(list(ws.columns))

for col in tuple(ws.columns):  # col[0] col[1] col[2] ... col[11]
    print(col[1].value)  # 각 column에 대해 index 1 (row 2번째)인 번호 영어 수학 점수 출력

# 전체 row 반복하면서 가져오는 ws.iter_rows()
for row in ws.iter_rows():
    print(row)
    print(row[0].value, row[1].value, row[2].value)    

# 전체 column 반복하면서 가져오는 ws.iter_cols()
for col in ws.iter_cols():
    print(col)
    for cell in col:
        print(cell.value, end=' ')
    print()

# ws.iter_rows(min_row, min_col, max_row, max_col) --> 슬라이싱과 유사
for row in ws.iter_rows(min_row=1, max_row=5):
    print(row[1].value)

for row in ws.iter_rows(min_row=2, max_row=11, min_col=2, max_col=3):
    print(row)
    print(row[0].value, row[1].value)  # 영어, 수학

# ws.iter_cols(min_row, min_col, max_row, max_col)
for col in ws.iter_cols(min_row=2, max_row=11, min_col=2, max_col=3):
    print(col)
    for cell in col:
        print(cell.value, end=' ')
    print()

wb.save('nadoCoding_sample2.xlsx')
```


■ 엑셀에서 값 찾기

```
from openpyxl import load_workbook

wb = load_workbook('nadoCoding_sample2.xlsx')
ws = wb.active

for row in ws.iter_rows(min_row=2):  # 제목 row 제외하고 전체 row 대상
     # 번호, 영어, 수학
     if int(row[1].value) > 90:  # 영어
         print(f'{row[0].value}번째 학생 영어는 {row[1].value}점, 천재 인증')
         
# 셀 내용 변경하고 다른 파일명으로 저장하기 - '영어'를 '컴퓨터'로 수정
for row in ws.iter_rows(max_row=1):
    for cell in row:
        if cell.value == '영어':
            cell.value = '컴퓨터'
wb.save('nadoCoding_sample3.xlsx')
```


■ 엑셀에서 행, 열 삽입, 삭제, 이동

```
from openpyxl import load_workbook

wb = load_workbook('nadoCoding_sample3.xlsx')
ws = wb.active

# 행(row) 추가하기 ws.insert_rows(idx, amount)
ws.insert_rows(8)  # 8번쨰 row 비워짐
ws.insert_rows(8, 5)  # 8번째 row 위치에서 아래로 5row 추가

# 열(column) 추가하기 ws.insert_cols(idx, amount)
ws.insert_cols(2)  # B번째 열이 비워짐
ws.insert_cols(2, 3)  # B번째 열로부터 우측에 3열 추가

wb.save('nadoCoding_sample3_insert.xlsx')

# 행(row) 삭제하기 ws.delete_rows(idx, amount)
ws.delete_rows(8)
ws.delete_rows(8, 3)

# 열(column) 삭제하기 ws.delete_cols(idx, amount)
ws.delete_cols(2)
ws.delete_cols(2, 2)

wb.save('nadoCoding_sample3_delete.xlsx')


# 잘라내고 이동하기 - 번호 (국어) 영어 수학
# ws.move_range(cell_range, rows=0, cols=0, translate=False)

wb2 = load_workbook('nadoCoding_sample2.xlsx')
ws2 = wb2.active

# 영어, 수학 전체를 row는 그대로 col는 1칸 이동
ws2.move_range('B1:C11', rows=0, cols=1)  # move>range()
ws2['B1'].value = '국어'   # ws2['B1'] = '국어'

wb2.save('nadoCoding_sample2_move.xlsx')
```

■ 엑셀 차트(Chart) 다루기 - BarChart, LineChart 그리고 Reference

```
from openpyxl import load_workbook
from openpyxl.chart import BarChart, Reference, LineChart

wb = load_workbook('nadoCoding_sample2.xlsx')
ws = wb.active

# value 설정  - 어떤 데이터를 차트로 만들 것인지 정의하는 것
# Reference에 차트 만들 현재 워트시트와 워크시트의 범위 지정
# Reference(worksheet, min_col, min_row, max_col, max_row, range_string)
# var_value = Reference(ws, 'B1:C11')  # 영어, 수학
# 계열 > 영어, 수학 (제목에서 가져오기 --> titles_from_data=True)

var_value = Reference(ws, min_row=1, max_row=11, min_col=2, max_col=3)  # 영어, 수학
bar_chart = BarChart()  # 차트 종류 설정 (Bar, Line, Pie, ...)
bar_chart.add_data(var_value, titles_from_data=True)  # 차트 데이터 추가, add_data()

# 차트를 워트시트에 넣어주기 - add.chart()
ws.add_chart(bar_chart, 'E1')  # 차트 넣을 위치 정의

# LineChart 만들기
line_value = Reference(ws, min_row=1, max_row=11, min_col=2, max_col=3)  # 영어, 수학
line_chart = LineChart()  # 차트 종류 설정 (Bar, Line, Pie, ...)
line_chart.add_data(var_value, titles_from_data=True)  # 차트 데이터 추가, add_data()
line_chart.title = '성적표'  # 제목
line_chart.style = 10  # 미지 정의된 스타일 적용
line_chart.y_axis.title = '점수'  # Y축의 제목
line_chart.x_axis.title = '번호'  # X축의 제목

ws.add_chart(line_chart, 'E15')  # 차트 넣을 위치 정의
wb.save('nadoCoding_sample2_Chart.xlsx')
```


■ 엑셀 셀 스타일(Style) 다루기 - Font, Border, Side, PatternFill, Alignment

```
from openpyxl import load_workbook
from openpyxl.styles import Font, Border, Side, PatternFill, Alignment
wb = load_workbook('nadoCoding_sample2.xlsx')
ws = wb.active

# 번호(A1), 영어(B1), 수학(C1)
a1 = ws['A1']  
b1 = ws['B1']
c1 = ws['C1']

# 너비 조정 - A열의 너비 5로 설정 dimensions
ws.column_dimensions['A'].width = 5

# 1행의 높이를 20으로 설정
ws.row_dimensions[1].height = 30

# font
a1.font = Font(color='FF0000', italic=True, bold=True)
b1.font = Font(color='CC33FF', name='Arial', strike=True)
c1.font = Font(color='0000FF', size=20, underline='single')

# 테두리
thin_border = Border(left=Side(style='thin'), right=Side(style='thin'), top=Side(style='thin'), bottom=Side(style='thin'))
a1.border = thin_border
b1.border = thin_border
c1.border = thin_border

# 셀에 색상 적용 - 90점 넘는 경우, 얼라이먼트 설정
for row in ws.rows:
    for cell in row:
        # 모든 셀에 대해 중앙 정렬 - 정렬값(center, left, right, top, bottom)
        cell.alignment = Alignment(horizontal='center', vertical='center')
        
        if cell.column == 1: # A 번호열은 제외:
            continue
        
        # cell이 정수형 데이터이고, 점수 > 90 이면 
        if isinstance(cell.value, int) and cell.value > 90:
            cell.fill = PatternFill(fgColor='00FF00', fill_type='solid')  # 배경
            cell.font = Font(color='FF0000')  # 폰트
            
# 틀고정하기 - B2 기준으로 틀고정
ws.freeze_panes = 'B2'
            
wb.save('nadoCoding_sample2_style.xlsx')
```

■ 엑셀 수식(함수) 활용해보기 - '=sum()' 'average()'

```
from openpyxl import Workbook
import datetime

wb = Workbook()
ws = wb.active

ws['A1'] = datetime.datetime.today()
ws['A2'] = '=sum(1, 2, 3)'  # 1 + 2 + 3 = 6
ws['A3'] = '=average(1, 2, 3)'
ws['A4'] = 10
ws['A5'] = 20
ws['A6'] = '=sum(a4:a5)'

wb.save('nadoCoding_formula.xlsx')
```

■ 엑셀에서 수식(데이터) 가져오기

```
from openpyxl import load_workbook

wb = load_workbook('nadoCoding_formula.xlsx')
ws = wb.active

# 파일에 있는 모든 정보 - 각 셀의 셀 객체가 아닌 value 정보 가져오기
for row in ws.values:  # ws.values
    for cell in row:
        print(cell)

# 2021-06-30 14:20:51.398000
# =sum(1, 2, 3)
# =average(1, 2, 3)
# 10
# 20
# =sum(a4:a5)


# 수식 그대로 불러오는 것이 아니라 값만 불러오게 하기 - data_only=True
# 단, 계산(evaluate) 되지 않은 상태(함수 수식 있는 셀)의 데이터는 None이라고 표시됨 (수식만 들어있기 때문임)
# 엑셀 파일 열고 저장을 한 후 다시 실행하면 제대로 된 값이 출력됨
wb2 = load_workbook('nadoCoding_formula.xlsx', data_only=True)
ws2 = wb2.active

for row in ws2.values:  # ws.values
    for cell in row:
        print(cell)

# 2021-06-30 14:20:51.398000
# None
# None
# 10
# 20
# None

## 파일 열고 저장 후 재 실행 결과
# 2021-06-30 14:20:51.398000
# 6
# 2
# 10
# 20
# 30
```

■ 엑셀 셀(Cell) 병합 - merge, unmerge

```
from openpyxl import Workbook
from openpyxl.styles import Alignment

wb = Workbook()
ws = wb.active

# 병합하기 - merge_cells(range_string, start_row, start_column, end_row, end_column)
ws.merge_cells('B2:D2')
ws['B2'].value = 'Merged Cell'

ws.merge_cells('B4:D6')
ws['B4'].value = 'Merged Cell 2'
ws['B4'].alignment = alignment = Alignment(horizontal='right', vertical='center')

# 병합 셀 해제
ws.unmerge_cells('B2:D2')

wb.save('nadoCoding_merge.xlsx')
```

■ 엑셀에 이미지 추가 - Image

```
from openpyxl import Workbook
from openpyxl.drawing.image import Image

wb = Workbook()
ws = wb.active

# 이미기 객체
img = Image('./image/aoi.png')

# C3 위치에 이미지 삽입
ws.add_image(img, 'H3')

img = Image('./image/img.jpg')
ws.add_image(img, 'A1')

wb.save('nadoCoding_insert_image.xlsx')
```



