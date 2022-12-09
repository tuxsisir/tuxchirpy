---
title: "Cookbook"
date: 2020-05-25
tags: ["python"]
draft: false

---

### Range of dates in list
---


```python
from dateutil.rrule import rrule, MONTHLY, DAILY
from datetime import date, timedelta


start_date = date.today() - timedelta(days=10) # 10 days back

dates = list(rrule(DAILY, dtstart=start_date, until=date.today()))
print(dates)
for date in dates:
    pass
    # print(date.date())
```

    [datetime.datetime(2020, 4, 22, 0, 0), datetime.datetime(2020, 4, 23, 0, 0), datetime.datetime(2020, 4, 24, 0, 0), datetime.datetime(2020, 4, 25, 0, 0), datetime.datetime(2020, 4, 26, 0, 0), datetime.datetime(2020, 4, 27, 0, 0), datetime.datetime(2020, 4, 28, 0, 0), datetime.datetime(2020, 4, 29, 0, 0), datetime.datetime(2020, 4, 30, 0, 0), datetime.datetime(2020, 5, 1, 0, 0), datetime.datetime(2020, 5, 2, 0, 0)]


### upper and lower nearest in a list
---


```python
def upper_nearest_diff(actual_ans):
    ll = [6, 10, 7, 10, 9, 25, 25, 25, 30, 8, 8, 8, 8, 13, 9, 15, 16, 89, 91, 32, 93]
    nearest_ = min(ll, key=lambda x:abs(x-actual_ans))
    print("nearest answer -- >> ", nearest_)
    if actual_ans in ll:
        return
    nearest_diff = actual_ans - nearest_
    upper_nearest = actual_ans + nearest_diff
    return upper_nearest

upper_nearest_diff(18)
```

    nearest answer -- >>  16





    20



### parse string to datetime
---


```python
from datetime import datetime

date_str = "1999-01-02"
new_date = datetime.strptime(date_str, "%Y-%m-%d")

print(new_date)
```

    1999-01-02 00:00:00


### tablib data export
---
```python
import tablib

data = tablib.Dataset()

data.headers = ["Client Name", "Client Manager", "Client Phone", "Contact Info"]

clients = ClientDetail.objects.filter(user__is_blocked=False)

for client in clients:
    cnumber = ""
    contact_info = ""
    for something in loop_:
        cnumber += "append something"
    for something in another_loop_:
        contact_info += "append here as well"
        
    # finally append to data
    data.append((client.name, client.manager, cnumber, contact_info))
    
with open('data.xlsx', 'wb') as f:
    f.write(data.xlsx)
```

### Simple Round Robin
---


```python
# from termcolor import colored

div1 = ["Sisir", "Rajesh", "Abhisek", "Niklesh"]
div2 = ["Keshab", "Subodh", "Elish"]

def create_schedule(list):
    """ Create a schedule for the teams in the list and return it"""
    s = []

    if len(list) % 2 == 1:
        list = list + ["BYE"]

    for i in range(len(list) - 1):

        mid = len(list) // 2
        l1 = list[:mid]
        l2 = list[mid:]
        l2.reverse()

        # Switch sides after each round
        if(i % 2 == 1):
            s = s + [zip(l1, l2)]
        else:
            s = s + [zip(l2, l1)]

        list.insert(1, list.pop())

    return s


def main():
    # for round in create_schedule(div1):
    #     for match in round:
    #         print match[0] + " - " + match[1]
    # print
    # for round in create_schedule(div2):
    #     for match in round:
    #         print match[0] + " - " + match[1]
    # print
    count = 0
    # list = []
    for round in create_schedule(div1 + div2):
        count += 1
        if count == 1:
            print(" - - - - - - - - - Sunday - - - - - - - - - \n")
        elif count == 2:
            print (" - - - - - - - - - Monday - - - - - - - - - \n")
        elif count == 3:
            print (" - - - - - - - - - Tuesday - - - - - - - - - \n")
        elif count == 4:
            print (" - - - - - - - - - Wednesday - - - - - - - - - \n")
        elif count == 5:
            print (" - - - - - - - - - Thursday - - - - - - - - - \n")
        elif count == 6:
            print (" - - - - - - - - - Friday - - - - - - - - - \n")
        elif count == 7:
            print (" - - - - - - - - - Saturday - - - - - - - - - \n")
        for match in round:
            print (" \t\t" + match[0] + " - " + match[1])
        # print " - - - - - - - - - - - - - - - - - - - - - - - - - - - "

# main()
```


```python
!jupyter nbconvert --to markdown cookbook.ipynb
```

    [NbConvertApp] Converting notebook cookbook.ipynb to markdown
    [NbConvertApp] Writing 4476 bytes to cookbook.md



```python
!mv cookbook.md ~/projects/tuxsisir-hugo/content/notes/python_cookbook.md
# !cp -r Untitled_files path/to/static/directory
```


```python

```
