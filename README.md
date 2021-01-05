# mtest
Totally simple header only test framework for C++.

## Usage:
```cpp
#include "mtest.h"

class Group : public mtest::test
{
public:
  void setup() {}
  void teardown() {}
};

MTEST(withoutGroup)
{
  //print outputs only if REQUIRE/EXPECT fails
  REQUIRE(true) << "would always fail";
  
  EXPECT(false) << "oha\n" << std::hex << "0x" << (700) << "test: " << (getName());
}

MTEST(Group,test1)
{
  REQUIRE(true);
}

// run all tests
int main(int argc, char **argv)
{
  mtest::runAllTests("*.*",mtest::enableColor|mtest::enableStdCout);
  
  return 0;
}
```
