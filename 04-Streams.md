# Streams

Streams are used to transform data.

- iostream
- istream
  - stringstream
- ostream
- ...

std::stream example:

```c++
void foo() {
  std::stringstream ss;
  ss << "My test at C++";

  std::string first, last, language;

  s >> first >> last >> language;
  // first -> My
  // last -> test
  // language -> at
}
```

The *>>* operator stops at whitespace.

## Getline()

getline(istream& is, string& str, char delim);

*getline()* read from is until delim and write into str.

The getline() will consume the delim.

The delim char is by default '\n';

```c++
void foo() {
  std::stringstream ss;
  ss << "My test at C++";

  std::string first, last, language, remain;

  ss >> first >> last >> language;
  // first -> My
  // last -> test
  // language -> at
  std::getline(ss, remain);
  // remain -> C++
  // ss ends with a '\n' we can't see.
}
```

- std::cout
  std::flush, std::endl, '\n' are all pushing the buffer to the destination.

  And without them, the output will not change lines.

## Output File Streams

- std::ofstream

- Methods
- is_open()
- close()
- open()

```c++
int main() {
std::ofstream ofs("hello.txt");

if (ofs.isopen()) {
  ofs << "hello cs106l" << '\n';
}

ofs.close();

ofs.open("hello.txt", std::ios::app);
ofs << "this is opened again" << endl;

return 0;
}
```

### Input File System

std::cin

cin buffer read the input until the next whitespace.

- whitespace
- '\n'
- '\t'
- ' '

*Attention* cin won't consume the whitespace.

```c++
int main() {
double d1, d2;
std::string name;

//3.14\nFabio Ibanez\n6.18\n
//Above is what we typed in.

std::cin >> d1;
std::getline(std::cin, name); // to consume the '\n'.
std::getline(std::cin, name);
std:cin >> d2;

std::cout << d1 << name << d2 << endl;
return 0;
}
```

You shouldn't use *getline()* and *std::cin* together.
