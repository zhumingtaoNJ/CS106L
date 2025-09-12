# Type

C++ is a ```static type```language.
Every item should be check what type it is before complier go.

Otherwise, Runtime error happens!-

## Struct

struct is used to define user's type.

```c++
struct {
  int number;

  std::tring name;
}
```

## Type aliases with using

' using ' in C++ is like ' typedef ' in C;

```c++
using Studect = std::pair<int number, std::string name>
```

``` c
//Solution for ax**2+bx+c=0
using QuadraticSolution = std::pair<bool, std::pair<double, double>>;

QuadraticSolution solveQuadratic(double a, double b, double c);

int main() {
  QuadraticSolution soln = solveQuadratic(1, 2, 3);
  return 0;
}
```

## auto

auto can be used to infer some normal type, or even a list，typically，it's used in ```loops```

But it can't be used for user-defined type

```c
std::vector vec {1, 2, 3, 4 }
for (auto v : vex) {
  std::cout << v << std::endl;
}
```
