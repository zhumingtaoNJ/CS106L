# Container

## Common Container

- vector
- map
- set
- deque

They all are template and belong to Standard Template Library.

## STL

Using STL can make the operations eaiser.

Below we will introduce the std's operations.

## vector

We use *'std::vector <T>'* to record a linear list of item T.

Common use:

- std::vector<T> v// create a empty vector. STL: Vector<T> v;
- v.push_back(element) // append element to the end of v. STL: v.add(e);
- v.empty() // check if v is empty. STL: v.isEmpty();
- v.pop_back() // remove the last item and don't return it.
- T element = v.at(index) // read the item at index. STL:T e = v.get(index);
- v.at(index) = e. // write the item e into index. STL: v.get(i) = e;
- v.clear()

```c++
std::vector<int> v {1, 2, 3, 4 };
v.push_back(5);
v.push_back(6);
```

The vector will automatically double the capacity when size is not enough.

And it's a linear container.

- Tips: use *const auto&* when possible

```
std::vector<Person> vec {...};

for (const auto& elem: v) {
 ...;
}
```

Iteractor and *auto* sometimes may help.

### Behind the scenes

We have a object in  Stack and a list in Heap.
![image](cs106L\CS106L\images\1.png);
We don't have a *push_front* method,so when we need that we switch to deque.

## deque

We use *std::deque<T>* to represent a double-ended vector.

deque has all the feature vector has, plus a few more:

- d.push_front(e) // append e to the front of d.

- d.pop_front() // remove the item at front and don't return it.

### Behind the scenes2

Unlike vector use a linear list to record data,deque break the list into pieces.

```c++
std::deque<int> d { 4, 5, 6, 7, 8, 9 }; 
d.push_front(3); 
d.push_front(2); 
d.push_front(1);
d.push_front(0);
d.push_front(-1);
d.push_front(-2);
```

![deque](cs106l\CS106L\images\2.png)

As we can see,

Vector is quicker than deque because it don't need to track much.

But deque is more functional.
