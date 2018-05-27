![image](https://i.redd.it/n0bxkzn1jpsz.jpg)

## [3 užduoties 'cookies'](https://github.com/brigitac/trecia_uzduotis)

```c++
int main (int argc, char *argv[]) //#1 argv and argc are command line arguments passed to main(). argc - number of strings pointed to by argv
{nuskaitymas(argv, studentai);}
```

```c++
template<typename T>
void nuskaitymas(char *argv[], T &studentai)
{
    ifstream failas1;
    failas1.open (argv[1]);
    studentas stud(failas1); //#2 studentas klases konstruktorius, kuriam paduodu failo stream'ą
}
```
```c++
studentas::studentas(std::istream& in)
{in>>pavarde>>vardas;}
```

## [4 užduoties 'cookies'](https://github.com/brigitac/Vector)

```c++
template <typename T> 
void Vector<T>::assign(T count, const T& value)
{
    for (size_t i = 0; i != size_; i++) {allocator.destroy(elem + i);} //#1 std::allocator
    allocator.deallocate(elem, capacity_);
    if (count > capacity_)
    {capacity_ = count;}
    elem = allocator.allocate(capacity_);
    std::fill_n(elem,count,value);  //#2 algoritmų naudojimas  
    size_ = count;
}
```

```c++
template <typename T> //#1
T* Vector<T>::insert(const T* pos, const T& value)
{
    T* pos2 = &elem[pos - elem];
    if (size_==capacity_)
    {
        capacity_=capacity_*2;
        reserve(capacity_);     
    }
    std::copy(pos2-1, pos2+(size_-(pos-elem)), pos2); //#2 algoritmų naudojimas
    (*pos2) = value;
    ++size_;
    return pos2;
}
```

## [5 užduoties 'cookies'](https://github.com/brigitac/penkta_uzduotis)

```c++
./a.out<text.txt //#1.Stream'as - text.txt failas.
```

```c++
#include <iostream>
#include <string>
#include <vector>
#include <sstream> 
#include <map>
#include <string>
#include <iomanip> 
int main()
{
    auto eile=0;
    std::map<std::string, size_t>  word_map;
    std::map<std::string, std::string>  line_map;
    std::string eilute;
    for(;std::getline(std::cin,eilute);). //#2.Paima eilutę iš stream'o, kuris yra .txt failas.
    {
        eile++;
        std::istringstream eilute2(eilute); //#3.Constructs new string stream.
        std:: string w;
        for (;eilute2>>w;)  
            {
                if (w.back()=='.' || w.back()==',' || w.back()==')' || w.back()=='"') w = w.substr(0, w.size()-1); //#4.Returns a substring 
                if (w.front()=='(' || w.front()=='"') w = w.substr(1, w.size());
                ++word_map[w];
                if (word_map[w]>1)
                    {
                        std::string eil=std::to_string(eile);    
                        char eilutuke=eil.front();
                        if (static_cast<char>(line_map[w].back())!=eilutuke)
                        {line_map[w]=line_map[w] +", " +std::to_string(eile);}
                    }
                else line_map[w]=std::to_string(eile);
            }
    }
    for(const auto &pair : word_map) 
    {
      if (pair.second>1) 
        {
         std::cout<<"'"+pair.first+"'"<<" žodis pasikartoja " << pair.second <<" kartus ir yra šiose eilutėse: "<<line_map[pair.first]<<std::endl;
        } 
    }
}
```

## [To sum up? I went from 0 to 1]()

![image](http://s1.funon.cc/img/orig/201702/23/58aeacc80ad90.png)

