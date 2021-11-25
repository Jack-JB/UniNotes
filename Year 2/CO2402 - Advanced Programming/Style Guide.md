# Advanced Programming Style Guide

> This file is a copy of the Style Guide for the module provided by Nick [Here](https://learn-eu-central-1-prod-fleet01-xythos.content.blackboardcdn.com/5d19e1c95e7e7/10911695?X-Blackboard-Expiration=1637863200000&X-Blackboard-Signature=XeH0kcdSG1cBXAkN4SzNoIjzdx9RoRCdOy%2Bl%2F6Igrxc%3D&X-Blackboard-Client-Id=100100&response-cache-control=private%2C%20max-age%3D21600&response-content-disposition=inline%3B%20filename%2A%3DUTF-8%27%27CO2402%2520Style%2520Guide.pdf&response-content-type=application%2Fpdf&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEK3%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FwEaDGV1LWNlbnRyYWwtMSJIMEYCIQDNucTcQsIgHfCxzHS7XN6LBDaDGhPCx1V9D%2FrbQ9yxyAIhAOUTg9Kx1jj2SIL%2FTgtI5dbXvYAjEVMPP8RxHsZhtXalKoAECHYQAhoMNjM1NTY3OTI0MTgzIgzhY5kgxOsFIMxPXewq3QNnojbzz0DKCZ3F2DNZPPn%2Fi8plS%2FKwSC3vGg9IkiFfMz62VAhXZrMGpWptorcLF%2FOZ6KtdoHUuubXCFLIbWMKmhTLoLLC6kZ8x5VrB8IdeePI1kRjfAgNEbxTON0Nsfjn7sQepbyFObSaUPjmhQq%2BZj21Gxu2etmndA4gDmTUX4poi%2B35lKJGE5wYRYHalIhDsvSEslTNyupziNJPmWyw9qxhnMeYem3kiCdZMF%2B5q%2F17l5DcDlE4q51EJlWGNXnVmud4xOXrVIaePLOK%2BMmfzHYrxr3W%2Fg%2F3OqojeWfSCkBZMKfsyU%2Byn3EL7yXLyZ2T6gHVpILKbJrUeDzQY5y9%2Fhi5rt2yzL0i6DZtY2AIuJfdJxF3zvPU6VzvxO6u4VWvFtYuobMkd5SUPsSAaei3pzAT3kgP4i5vka44Ozows3OJxb%2FmPGNkV%2FKysmSmht2ayEDvfrERpAJ7ISJuL241ZCZeqfma0%2FNYKKsBDDhyOyOJkXX9qNTUQTONDKRA7GQbTnh%2FRERVtu8o0YL9tgy73xBVVOk%2FHqI4IgfUVlN4JTVrUFaUmqvQWhkyWbOtPw3LnQ7EHlPZudYYxKWijVtCe1bbZgB2LANS9cvdOzIOekoBLhlw3Fx7eUcnq8z8wi5v%2BjAY6pAEtX34WwkSVox0%2B8sZyDXcQfLR69SwCCjUL8nA9A9rBr32hiKyq66ubSxxJs%2BIDJPi1TDv6hwbVugq8oaYWHBIRfd7H3ie4rYHAf7m%2FHvk6DLDFs5ixe%2FY0lbrNi9Ps2eF3OuCLX9jXgVXkbAVSetgYfcmuLxKomztpiAjZN0uNTvZA9W0iX0wyvialAZJy%2F1tRhbQVgW8IyJDVJFuOqB%2F56eXcng%3D%3D&X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Date=20211125T120000Z&X-Amz-SignedHeaders=host&X-Amz-Expires=21600&X-Amz-Credential=ASIAZH6WM4PLRQYTNCMI%2F20211125%2Feu-central-1%2Fs3%2Faws4_request&X-Amz-Signature=7834841fce9cb8e3d5cfc3237ac35d53c83fc6f77416d015542d6f75cd6441e9)

## Introduction

The following style guide is intended for CO2402: Advanced Programming with C++. 

You are required to use this style guide for code submissions for this module. You may be required to use it  for other modules as well. 

Do note that this style guide is much smaller than a real guide would be!

## How should you name things?

- Absolutely no meaningless names. All names must be meaningful.

- A function must have a strong verb (a “doing word”). The form should be verb followed by an object.  

  - The object is often a noun (a “name”), e.g.

    ```c++
    DisplayRecord();
    ```

  - Avoid meaningless or wishy-washy verbs.

  - If a function returns a value then use a description of the return value in the name, e.g.

    ```C++
    GetName(); // returns the name
    ```

- A variable name is likely to be a noun, e.g.

  ``` cp
  CRecord studentRecords;
  ```

- A name should be neither too short nor too long.

- Short variable names can only be used if the context is completely unambiguous, e.g. `x` and `y` are  acceptable in the case of coordinates.

- Single character variable names are OK for loop counters and maths.

- If you do use a single character for a loop counter then it must follow the convention: `i`, `j`, `k`, unless  there is an explicit reason otherwise, e.g.

  ```cpp 
  for( int i = 0; i < total; i++ )
  ```

## Names

-  Underscores should **not** be used. The only exception to this is in the naming of constants (see below). If  a name is made up of more than one word then each succeeding word should begin with a capital  letter, e.g.

  ```c++
  largestValue();
  ```

- **Variable names** begin with a lower-case character. If a variable is made up of more than one word then  each word must begin with an upper-case character (apart from the one beginning the variable name).  All other characters must be lower-case. For example:

  ```C++
  float wriggle;
  
  int noOfRecords;
  
  CEmployee fullTimeEmployees;
  ```

- **Function names** begin with an upper-case character. Each word must begin with an upper-case  character. All other characters must be lower-case. For example:

  ```c++
  DisplayRecord();
  ```

- **Constants** are written all upper-case. Underscores can be used to separate words in the name of a  constant. This is the only exception to the rule that underscores should not be used., e.g.

  ```C++
  MAX
    
  ARRAY_SIZE
  ```

- **Member variables** begin a lower case m. Each word must begin with an upper-case character. All other  characters must be lower-case. For example:

  ```C++
  mProductCode
  ```

- **Global variables** begin a lower case g. Each word must begin with an upper-case character. All other  characters must be lower-case. For example:

  ```C++
  gDatabaseSize
  ```

- **Pointers** begin a lower case p. Each word must begin with an upper-case character. All other characters  must be lower-case. The m or g prefix is placed before the p prefix, e.g.

  ```c++
  pDatabaseRecords
    
  mpDatabaseSize
    
  gpDataFormat
  ```

- **Class types** begin with an upper-case C. Each word must begin with an upper-case character. All other  characters must be lower-case. For example:

  ```C++
  CTimer
    
  Cemployee
  ```

- **Enumerated types** begin with an upper-case E. Each word must begin with an upper-case character. All  other characters must be lower-case. For example:

  ```C++	
  EKeyCode
  ```

- **Structure types** begin with an upper-case S. Each word must begin with an upper-case character. All  other characters must be lower-case. For example:

  ```c++
  SAddress
  ```

### Here are the prefixes in table format. The first character of a name indicates its type.

| **Type**         | **Prefix** | **Example**             |
| ---------------- | ---------- | ----------------------- |
| class            | C          | `CtableOfValues`        |
| structure        | S          | `SProductSpecification` |
| enumeration      | E          | `ECategoryCode`         |
| pointer variable | p          | `pElement`              |
| member variable  | m          | `m`                     |
| global variable  | g          | `g`                     |

## Variables

- All variables should be given a default (and sensible) value when they are declared if this is at all possible.

- A pointer should be assigned a value of `0` if is not currently pointing at a known memory address.

- Each variable should be declared on its own line, with its own type preceding it.

  ```C++
  int age;
  
  std::string name;
  ```

- Pointers are declared with asterisk next to the type.

  ```c++
  CQueue* pProductList = new CQueue;
  ```

## Tabs, Whitespace and Layout

- Use a tab character rather than spaces.

- Tab distance should be 4 (i.e. the equivalent of 4 spaces).

- Generally speaking put spaces around all mathematical operators and most other operators, e.g.

  ```c++
  result = myMoney + yourMoney;
  
  bill && ben
  ```

- It is difficult to be more precise than “most other operators” without a long list, but unary operators  such as increment and decrement don’t get spaces whilst a logical operator would, e.g.

  ```c++
  daysGoneBy++;
  
  christopher || alice
  ```

- The curly braces of a control block are aligned with the left hand side of the block. Each brace is placed  line of its own.

  ```C++
  while( currentSpeed < maxTolerance )
  {
   IncreaseThrust( );
  }
  ```

## Global Variables

- In general you should avoid the use of global variables. It is better to use access routines in the place of  global data.
- There are reasons to use global variables. Reasons to use them include:
  - Declaring constants.
  - Eliminating tramp data – a variable that is used in many functions and needs to be passed on  and on via a function chain. It will be obvious when you see this happening! The reason for this  is that the data is used throughout a program. This genuinely would appear to be global data.

## Comments

- Write comments at the level of the code’s intent.
- Focus on **why** rather than **how**.
- Place a comment before each block of statements.
- Document the source of algorithms.
- Every method needs a comment section which briefly but clearly describes what the method does. The comment section can be placed in the header file or in the source file.

## General Points

- Don’t abbreviate by just removing one character from a word – what’s the point?
- Abbreviations must be consistent.
- A variable should only be used for one purpose only.