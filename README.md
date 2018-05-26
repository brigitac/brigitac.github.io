![image](https://i.redd.it/n0bxkzn1jpsz.jpg)

## [5 užduoties cookies](https://github.com/brigitac/penkta_uzduotis)

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

## [4 užduoties cookies](https://github.com/brigitac/Vector)

To be soon. 

## [3 užduoties cookies](https://github.com/brigitac/trecia_uzduotis)

To be soon. 

## [To sum up? I went from zero 0 to 1]()

![image](http://s1.funon.cc/img/orig/201702/23/58aeacc80ad90.png)

