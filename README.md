# singleton

Просто обычная реализация паттерна Singleton.

Singleton гарантирует, что у класса есть только один экземпляр, и предоставляет к нему глобальную точку доступа.

## Использование

```cpp
template <typename TPar1, typename TPar2>
class MyApp : public Singleton<MyApp<TPar1,TPar2>> {
friend class Singleton<MyApp<TPar1,TPar2>>;
public:
	void DoStuffHere(void) {
        // do stuff here
    }
};

int main(int argc, char** argv) {
    static constexpr int par1 = 1;
    static constexpr double par2 = 2.0;

    MyApp<par1,par2>& app = MyApp<par1,par2>::GetInstance();
    app.DoStuffHere();
}
```