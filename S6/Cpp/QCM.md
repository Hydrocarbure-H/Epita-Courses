# QCM

> Correct signature of `my_class` : 
>
> - Constructor : `my_class();`
> - Copy Constructor : `my_class(const my_class& other)`
> - Copy assignement operator : `my_class& operator=(const my_class& other)`

> For the next class declaration :
>
> - ```cpp
>    class X {
>        ...;
>    }
>   ```
>
> - `X x{};` –> Default Constructor
>
> - `auto x = b;` –> Copy constructor
>
> - `b = a` –> Copy assignement operator

> Link the following *iso C++* terms with conventional *Object* terms:
>
> - Member function → Instance Method
> - Static member function → Class Method
> - Member variable → Attribute

> A symbol that is declared but not defined produces an error during :
>
> - Linkage

> ODR stands for :
>
> - One definition rule

> `extern double t;` corresponds to :
>
> - The declaration of a variable `t`, possibly defined in another translation unit

> The keyword `auto` in
>
> ```cpp
> auto X = get_var();
> ```
>
> allows to :
>
> - Let the compiler deduce the type of X

> Which of the following call (some version of) the constructor of `my_class` :
>
> ```cpp
> my_class m;
> ```
>
> ```cpp
> auto m = my_class(1.1);
> ```
>
> ```cpp
> auto m = my_class();
> ```
>
> ```cpp
> my_class m(1.1);
> ```

> When is the destructor of `my_class` called on `m`:
>
> ```cpp
> void foo( my_class m){
>   // code block A
>   { // p1
>     // code block B
>     int m = 1i; // p2
>     // code block C
>   } // p3
>   // code block D
>  } // p4
> ```
>
> - p4

> If your class defines a custom copy-constructor you (at least) need to define :
>
> - The copy assignment operator 
> - The destructor

> Consider the definition of the constructor of `my_class` :
>
> ```cpp
>  my_class::my_class(int v1, float v2) //\@s
>    : v1_{v1}
>    , v2_{v2} //\@e
>  {
>    // function body
>  }
> ```
>
> - Member initializer list

> Which of the following lines uses constructor delegation :
>
> - `my_class::my_class(int v1): my_class(v1, 0.f){}`

> Which tools are C++ compilers ?
>
> - g++
> - clang++
> - msvc

> Which statement is (*are*) correct(s) ?
>
> - Translation unit (or complation unit) is a source file + all the header files it includes
> - Object file is *generally* the result of the compilation unit being compiled
> - An executable file is the result of linking the object file(s) (with the runtime library)

> `const` member functions can :
>
> - Call other const member functions
> - Can provide read-accessor to members
> - Can be called on const instances

> Which operator(s) is (are) called with `X x; x = X{}` :
>
> - The default constructor
> - The copy assignment operator

> Which operator is called with `auto x = X{}` :
>
> - The default constructor

> Exposing only member functions and not the members variables :
>
> - Allows you to enforce invariants

> `class ABC;`:
>
> -  Is a declaration

> What is held by `this` in a member function : 
>
> - The address of the instance

> ```cpp
>  // my_vector.h
>  class my_vector{
>    float x_, y_;
>  public:
>    void offset(float dx, float dy);
>  }
>  // my_vector.cpp
>  void my_vector::offset(float dx, float dy){
>    x_ += dx;
>    y_ += dy;
>  }
> ```
>
> What is the scop of `x_` : 
>
> - Class scope

> In order to be able to write : 
>
> ```cpp
> my_class m1;
> 
> my_class m2;
> 
> std::cin >> m1 >> m2;
> ```
>
> You need to define :
>
> - `std::istream& operator>>(std::istream& is, my_class& m);`

> `operator[](size_t idx)` is usually used when :
>
> - Your class represents some form of vector and you want to access an element

> In order to be able to write
>
> ```cpp
> my_poly p1;
> 
> my_poly p2;
> 
>  
> auto p3 = p1 + p2;
> ```
>
> You need to define (mark all possible signatures) :
>
> - `my_poly my_poly::operator+(const my_poly& other);`
> - `my_poly operator+(const my_poly& p1`
> - `const my_poly& p2);`

> What actions are performed by the preprocessor :
>
> - Replace `#include <...>` by the file content
> - Evaluate `#ifdef`, `#if`, `#elif` conditions
> - Evaluate macros
> - Concatenate string literals(`const char* x= "ab" "bc"` → `const char* x= "abbc"` )

> Which statements are correct about RAII classes :
>
> - Have a non-default constructor
> - Manage some resources
> - Have non-default destructor

> C++ is a domain specific language like Fortran :
>
> - Faux

> C++ strives to be high-level while maintaining zero abstraction cost :
>
> - Vrai

> Header files (.h) usually provide the definition of functions:
>
> - Faux

> C++ is C plus object oriented programming :
>
> - Faux

> `const`-qualifier is part of the type :
>
> - Vrai

> We can have two member functions `const` and `non-const`, with the same name and the same signature :
>
> ```cpp
> void foo(int) const;
> void foo(int);
> ```
>
> - Vrai

> The Public Interface of your **class** should not expose member variables :
>
> - Vrai

> Encapsulation means grouping together data and algorithms :
>
> - Vrai

> C++ forbids mutually dependent types :
>
> - Faux

> A class may have multiple constructors :
>
> - Vrai

> If you want to ship a program `X` that depends and links **statically** against your personnal libraries `A` and `B`. Then :
>
> - You just need to provide `X` binary

> ```cpp
>  struct Node {
>      int                     value;
>      std::unique_ptr<Node> next;
>  };
>  class List {
>      std::unique_ptr<Node> m_head;
>      public:
>          List = default();
>          void push_front(int v);
>  };
> 
> // Answer
> 
> void Node::push_front(int v) 
> {
> 		m_head = std::make_unique<Node>(v, std::move(m_head));
> }
> ```

> ```cpp
>  class A {
>    public:
>      virtual void foo() {}
>      virtual void bar() = 0;
>      virtual ~A() = default;
>  };
>  class B : public A {
>      void bar() override {}
>  };
>  class C : public B {
>      void foo() override {}
>  };
>  class D : public A {
>      void bar() override {}
>  };
> 
> ```
>
> - D is concrete
> - A is abstract
> - B is concrete
> - C is concrete

> If `A` is a public base class of `B` then :
>
> -  `B` is-a `A` is implicitely convertible to `A*`
> - `B&` is implicilety convertible to `A&`
> - `shared_ptr<B>` is implicitely convertible to `shared_ptr<A>`
> - `unique_ptr<B>&&` is implicilety convertible to `unique_ptr<A>&&`

> ``` cpp
>  int* foo() {
>      auto x = new int[10];
>      return x;
>  }
> ```
>
> This code :
>
> - Is valid
> - Requires the client-side to free the array with something else than `delete`

> Let `B` inherit (public) from an abstract class `A`. Let `a` ot type `const A*`, what is the safe and proper way to check the concrete type of `a`.
>
> ```cpp
>  if (int x = foo(); x == 2) {
>  }
> ```
>
> - ```cpp
>   if (auto x = dynamic_cast<const B*>(a); x != nullptr)
>   ```

> What is the difference between `dynamic_cast<B*>` and `static_cast<B*>` when downcasting from `A*` to `B*` (where `A` is a base class of `B`) :
>
> - `dynamic_cast` will return null if the type is incorrect
> - Dynamic-cast can only be used on polymorphic classes (classes having at least one virtual function)

> ```cpp
>  struct A {
>     int x;
>  };
>  class B {
>     std::unique_ptr<A> x = std::make_unique<A>{};
>   public:
>     B() = default;
>  };
> ```
>
> Which of these lines lead to an (direct or indirect) allocation on the heap :
>
> - `auto foo = B{}`, `auto foo = std::make_shared<A>{}`
> - `auto foo = std::make_shared<B>{}`

> ```cpp
>  struct Node {
>      int                     value;
>      std::unique_ptr<Node> next;
>  };
>  class List {
>      std::unique_ptr<Node> m_head;
>      public:
>          List = default();
>          void push_front(int v);
>  };
> ```
>
> - Has no memory leaks at destruction
> - May cause stack corruption at destruction

> ```cpp
>  class A {
>      public:
>      ~A() = default;
>      virtual void foo() {}
>  };
>  class B : public A {
>     public:
>      ~B() = default;
>      void foo() override {}
>  };
> ```
>
> `std::unique_ptr<A> x = std::make_unique<B>();` When `x` goes out-of-scope, which destructor is called :
>
> -  A's

> ```cpp
>  class A {
>      public:
>         virtual ~A() = default;
>         virtual void foo() = 0;
>  };
>  class B : public A {
>     public:
>      void foo() override {}
>  };
> 
> ```
>
> `std::unique_ptr<A> x = std::make_unique<B>();` When `x` goes out-of-scope, which destructor(s) is(are) called :
>
> - A's
> - B's

> Let 
>
> ```cpp
>  void f1(std::unique_ptr<X>);
>  void f2(std::share_ptr<const X>);
>  void f3(const X*);
>  
>  std::unique_ptr<X> a;
>  std::shared_ptr<X> b;
> ```
>
> Choose the correct(s) expression(s) :
>
> - `f1(std::move(a))`
> - `f2(b)`
> - `f2(std::move(b))`
> - `f3(b.get())`
> - `b = std::move(a)`;

> ```cpp
>  class A {
>     protected:
>         int m_x;
>     private:
>         int m_y;
>     public:
>      virtual ~A() = default;
>      virtual void foo() = 0;
>      int m_z;
>  };
>  class B : public A {
>      A() = default;
>      void foo() override {}
>  };
> ```
>
> Which member variables can be accessed from a `B`'s instance :
>
> - m_x
> - m_z

> What is the purpose of a `weak_ptr<X>` :
>
> - Break cycles of *shared pointer* chains

> Code that handles an exception thrown by "subprograms" must :
>
> - call the code in a **try** clause
> - always have a **catch** clause (that can be empty)
> - must set the program in stable state

> ```cpp
> class A { public: virtual const char* what() const = 0; };
>  class B : public A { public: const char* what() const override { return "B"; }};
>  class C : public B { public: const char* what() const override { return "C"; }};
>  
> 
>  void foo() {
>      try {
>          throw C{};
>      }
>      catch (const A& ex) { std::cout << ex.what(); }
>      catch (const B& ex) { std::cout << ex.what(); }
>      catch (const C& ex) { std::cout << ex.what(); }
>  }
> ```
>
> - Will be print: C

> What are the **possible** ways in C++ to handle runtime errors in production :
>
> - Returning error codes
> - Using exceptions

> ```cpp
>  #include <stdexcept>
>  #include <memory>
>  
>  void foo() {
>      try {
>          std::unique_ptr<int> a;
>          throw std::runtime_error{"oups"};
>  
>          std::unique_ptr<int> b;
>      }
>      catch (...) {
>          // FIXME
>          throw;
>      }
>  }
> ```
>
> What should be written instead of FIXME to correcly release the resources (**write the c++ instruction and end with ';'**)
>
> - ;

> `dynamic_cast` can be used to downcast from a `shared_ptr<A>` to `shared_ptr<B>` (where `A` is a base class of `B`) :
>
> - Faux

> In a proper Object Oriented hierarchy, it is a good practice to inherit from concrete classes :
>
> - Faux

> An abstract class has at least one pure virtual method ?
>
> - Vrai

> A concrete class has no virtual method ?
>
> - Faux

> In a hierarchy, the destructor of a base class shall always be **defined** (possibly defaulted) :
>
> - Vrai

> In a hierarchy, the destructor of the base class is either :
>
> - public and virtual
>
> - non-virtual, and thus, protected
>
>   
>
> - Vrai

> `assert` can be used to have compile-time checks (eg `assert(sizeof(int) == 4`) :
>
> - Faux

> Exception shoud be caught by `const &` :
>
> - Vrai

> ```cpp
>  class Node {
>          std::vector<Node> m_children;
>      public:
>          Node() = default;
>          size_t get_children_count() const;
> };
> ```
>
> 
>
> - ```
>   const Node* get_child() const;
>   Node* get_child();
>   ```

> ```cpp
>  struct Node {
>      char     label;
>      Node*    next = nullptr;
>  
>      ~Node() { std::cout << label;}
>  };
>  
>  int main() {
>      Node a = {'a'};
>      Node b = {'b', &a};
>      Node c = {'c', &b};
>  }
> ```
>
> - c b a

> ```cpp
>  struct Node {
>      char     label;
>      Node*    next = nullptr;
>  
>      ~Node() { std::cout << label; delete next;}
>  };
>  
>  int main() {
>      Node a = {'a'};
>      Node b = {'b', &a};
>      Node c = {'c', &b};
>  }
> ```
>
> - Nothing, elements are freed multiple times and there is a heap corruption.

> Which of these containers are implemented with hash-maps ?
>
> - `std::unordered_map`
> - `std::unordered_set

> Which of these containers provide a key → value store ?
>
> - `std::map`
> - `std::unordered_map`

> ```cpp
>  class Vector {
>      public:
>      FIXME Vector(int size);
>  };
>  
>  void foo(Vector);
> ```
>
> What should be written instead of FIXME to prevent the error-prone call `foo(10)` ?
>
> - explicit

> ```cpp
>  class Animal {
>      public:
>      virtual bool has_sex_with() (const Animal&) = 0;
>  };
>  class Monkey : public Animal {
>      public:
>      bool has_sex_with(const Animal&) override;
>      bool has_sex_with(const Monkey&);
>  }
>  class Cow : public Animal{
>      public:
>      bool has_sex_with(const Animal&) override;
>      bool has_sex_with(const Cow&);
>  }
>  bool has_sex_with(Animal& a, Animal& b) {
>      return a.has_sex_with(b);
>  }
> ```
>
> With this polymorphism, can a cow have sex with a monkey ? If yes, which polymorphism enables this ?
>
> - Inclusion

> What are the kind polymorphism available in C++ :
>
> -  coercion
> - inclusion
> - ad-hoc
> - parametric

> ```cpp
>  class Monkey  {
>      public:
>      bool has_sex_with(const Monkey&);
>  }
>  class Cow {
>      public:
>      bool has_sex_with(const Cow&);
>  }
>  template <class Animal>
>  void has_sex_with(Animal& a, Animal& b) {
>      return a.has_sex_with(b);
>  }
> ```
>
> With this polymorphism, can a cow have sex with a monkey ? If yes, which polymorphism enables this ?
>
> - No it cannot

> ```cpp
>   template <class T>
>   FIXME max(T x, T y) {
>       return x < y ? x : y;
>   }
> ```
>
> What can be written instead of FIXME ?
>
> - auto
> - T
> - inline T

> Template parameter are evaluated :
>
> - At compile time

> ```cpp
> template <class T>
> void foo(T x) {}
> ```
>
> With the expression `foo(2)`, what is `T` ?
>
> - int

> Which entities can be templated :
>
> - class, function, member function, variables

> ```cpp
> template <FIME T>
> class A;
> ```
>
> FIXME can be :
>
> - class, typename, int, int*

> What is `std::vector<int>` ?
>
> - A contiguous buffer of *ints* that supports insertion/deletion at the end

> If I have a vector of unique pointers (e.g. `std::vector<std::unique_ptr<int>> v`), what should we do to ensure a proper memory reclamation ?
>
> - Nothing special

> ```cpp
>  class Vector {
>      public:
>      Vector(int size);
>  };
>  
>  void foo(Vector);
> ```
>
> What type of polymorphism is implemented with `foo(10)` ?
>
> - Coercion

> Given two vectors of ints (`vector<int>`) *a* and *b* of **the same size**. Wich expressions allow to make *b* a copy of *a*'s content ?
>
> - ```
>   copy(begin(a), end(a), begin(b))`, `b = a`, `ranges::copy(a, b)
>   ```

> The C++ class `Object` is an implicit base class for all C++ classes :
>
> - Faux

> In C++, it is possible to overload on the return type :
>
> - Faux

> What is the usage of a class specialization :
>
> - To customize the implementation for some template parameters

> ```cpp
> std::vector<int> vec = {2, 3, 4};
> for  (auto& v : vec)
> v += 1;
> ```
>
> What's the value of `vec[0]` at the end ?
>
> - 3

> `std::function` can wrap :
>
> - a regular function
> - a static member function
> - a lambda function
> - a functor

> Lambda function are often created "locally" to parametrize other, more complicated algorithms :
>
> - Vrai

> Lambda functions are condensed functors :
>
> - Vrai

> A lambda function can capture another lambda :
>
> Vrai

> Rvalue-reference are real references ?
>
> - Vrai

> ```cpp
> class X {};
> X foo();
> X a{};
> ```
>
> - `auto x = X{};` –> Default Constructor
> - `auto x = foo();` –> Move Constructor
> - `x = a` –> Copy Assignement
> - `auto x = a;` → Copy constructor
> - `x = std::move(a);` → Move assignment
> - `x = foo();` → Move assignment

> Which C++ tool allows to constrain a C++ template parameter ?
>
> - Concepts

> Functions marked as `constexpr` :
>
> - Can be evaluated at compile time, Can be evaluated at runtime time

> ```cpp
>   // ...
>   if constexpr (cond1){
>     // C1
>   } else {
>     // C2
>   }
>   // ...
> ```
>
> For a `constexpr if` :
>
> - If cond1 holds, only C1 needs to compile.
> - The value of cond1 needs to be known at compile time
