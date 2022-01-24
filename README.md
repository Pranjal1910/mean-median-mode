# mean-median-mode
#mean
from asyncore import file_dispatcher
import csv
from dataclasses import dataclass
from operator import le
with open('height-weight.csv', newline='') as f:
    reader = csv.reader(f) 
    file_data = list(reader)

file_data.pop(0)
new_data = []
for i in range(len(file_data)):
    n_num = file_data[i][1]
    new_data.append(float(n_num))

n = len(new_data)
total = 0
for x in new data:
    total += x

mean = total/n


print("Mean is : "+str(mean))





#median
from asyncore import file_dispatcher
import csv
from dataclasses import dataclass
from operator import le
with open('height-weight.csv', newline='') as f:
    reader = csv.reader(f) 
    file_data = list(reader)
file_data.pop(0)
new_data = []
for i in range(len(file_data)):
    n_num = file_data[i][1]
    new_data.append(float(n_num))

n = len(new_data)
new_data.sort()

if n % 2 == 0:
    median1 = float(new_data[n//2])
    median2 = float(new_data[n//-1])

    median = (median1 +median2)

else:
    median = new_data[n//2]
    print(n)

print("Median is : "+str(median)) 


#mode
from asyncore import file_dispatcher
from collections import Counter
import csv
from dataclasses import dataclass
from msilib.schema import ODBCSourceAttribute
from operator import le
from statistics import mode
with open('height-weight.csv', newline='') as f:
    reader = csv.reader(f) 
    file_data = list(reader)
file_data.pop(0)
new_data = []
for i in range(len(file_data)):
    n_num = file_data[i][1]
    new_data.append(float(n_num))

data = Counter(new_data)
mode_data_for_range = {
         "50-60":0,
         "60-70":0,
         "70-80":0
      }


for height, occurreence in data.item():
    if 50< float(height) <60:
        mode_data_for_range["50-60"] += occurreence
    elif 60 < float(height) <70:
         mode_data_for_range["60-70"] += occurreence
    elif 70 < float(height) < 80:
         mode_data_for_range["70-80"] += occurreence


mode_range, mode_occurrence = 0,0
for range, occurreence in mode_data_for_range.item():
    if occurreence > mode_occurrence:
        mode_range, mode_occurrence =[int(range.split("-")[0]),int(range.split("-")[1])], occurreence
    
mode = float((mode_range[0] + mode_range[1]) /2)
print("Mode Is : "+str(mode))




