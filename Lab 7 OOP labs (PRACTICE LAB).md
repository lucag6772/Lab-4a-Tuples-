``` python 

class Stack:
    def __init__(self):
        self.__stk = []

    def push(self, val):
        self.__stk.append(val)

    def pop(self):
        val = self.__stk[-1]
        del self.__stk[-1]
        return val


class CountingStack(Stack):
    def __init__(self):
        super().__init__() 
        self.__pop_counter = 0  # hidden property to count pops

    def get_counter(self):
        return self.__pop_counter

    def pop(self):
        val = super().pop()  # call parent pop
        self.__pop_counter += 1
        return val


# Testing
stk = CountingStack()
for i in range(100):
    stk.push(i)
    stk.pop()
print(stk.get_counter())  # Expected output: 100

```

# 2a Implementing a Queue class from scratch 

``` python

class QueueError(Exception):  # custom exception
    pass


class Queue:
    def __init__(self):
        self.__queue = []

    def put(self, elem):
        self.__queue.insert(0, elem)  # add to beginning

    def get(self):
        if not self.__queue:
            raise QueueError("Queue is empty")
        return self.__queue.pop()  # remove from end


# Testing
que = Queue()
que.put(1)
que.put("dog")
que.put(False)
try:
    for i in range(4):
        print(que.get())
except QueueError:
    print("Queue error")

```

# expected output 

  1
dog
False
Queue error

# 2b exteding queue 

``` python 

class SuperQueue(Queue):
    def isempty(self):
        return len(self._Queue__queue) == 0  # access private list from base class


# Testing
que = SuperQueue()
que.put(1)
que.put("dog")
que.put(False)

for i in range(4):
    if not que.isempty():
        print(que.get())
    else:
        print("Queue empty")
```

# expeced output

1
dog
False
Queue empty

# 3 timer class

``` python

def format_time(h, m, s):
    return f"{h:02d}:{m:02d}:{s:02d}"

class Timer:
    def __init__(self, hours=0, minutes=0, seconds=0):
        self.__h = hours
        self.__m = minutes
        self.__s = seconds

    def __str__(self):
        return format_time(self.__h, self.__m, self.__s)

    def next_second(self):
        self.__s += 1
        if self.__s >= 60:
            self.__s = 0
            self.__m += 1
            if self.__m >= 60:
                self.__m = 0
                self.__h += 1
                if self.__h >= 24:
                    self.__h = 0

    def prev_second(self):
        self.__s -= 1
        if self.__s < 0:
            self.__s = 59
            self.__m -= 1
            if self.__m < 0:
                self.__m = 59
                self.__h -= 1
                if self.__h < 0:
                    self.__h = 23


# Testing
timer = Timer(23, 59, 59)
print(timer)
timer.next_second()
print(timer)
timer.prev_second()
print(timer)

```

# expected output 

23:59:59
00:00:00 
23:59:49

# 4-week class

``` python

class WeekDayError(Exception):
    pass


class Weeker:
    days = ["Mon", "Tue", "Wed", "Thu", "Fri", "Sat", "Sun"]

    def __init__(self, day):
        if day not in self.days:
            raise WeekDayError()
        self.__day_index = self.days.index(day)

    def __str__(self):
        return self.days[self.__day_index]

    def add_days(self, n):
        self.__day_index = (self.__day_index + n) % 7

    def subtract_days(self, n):
        self.__day_index = (self.__day_index - n) % 7


# Testing
try:
    weekday = Weeker('Mon')
    print(weekday)
    weekday.add_days(15)
    print(weekday)
    weekday.subtract_days(23)
    print(weekday)
    weekday = Weeker('Monday')  # Should raise exception
except WeekDayError:
    print("Sorry, I can't serve your request.")

```
# expectation 

Mon
Tue
Sun
Sorry, I can't serve your request.


# challenges 
During the lab, I faced challenges managing private attributes and accessing them in subclasses, such as in SuperQueue. Additionally, handle time overflow and underflow in the Timer class, which calculates the correct week using careful logic with wrapping. Designing custom expectations like queueerror and weekdayerror also helped me understand when and how to raise errors properly.





