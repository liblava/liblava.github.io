---
title: lava::file
summary: File. 

---

# lava::file



File. 


`#include <file.hpp>`

Inherits from [lava::no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md)

## Public Types

|                | Name           |
| -------------- | -------------- |
| using [file](/_doxybook/Classes/structlava_1_1file.md) const  & | **[ref](/_doxybook/Classes/structlava_1_1file.md#using-ref)** <br>Reference to file.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[file](/_doxybook/Classes/structlava_1_1file.md#function-file)**([string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) path ="", [file_mode](/_doxybook/Namespaces/namespacelava.md#enum-file-mode) mode =file_mode::read)<br>Construct a new file.  |
| | **[~file](/_doxybook/Classes/structlava_1_1file.md#function-~file)**()<br>Destroy the file.  |
| bool | **[open](/_doxybook/Classes/structlava_1_1file.md#function-open)**([string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) path, [file_mode](/_doxybook/Namespaces/namespacelava.md#enum-file-mode) mode =file_mode::read)<br>Open the file.  |
| void | **[close](/_doxybook/Classes/structlava_1_1file.md#function-close)**()<br>Close the file.  |
| bool | **[opened](/_doxybook/Classes/structlava_1_1file.md#function-opened)**() const<br>Check if the file is opened.  |
| [i64](/_doxybook/Namespaces/namespacelava.md#using-i64) | **[get_size](/_doxybook/Classes/structlava_1_1file.md#function-get-size)**() const<br>Get the size of the file.  |
| [i64](/_doxybook/Namespaces/namespacelava.md#using-i64) | **[read](/_doxybook/Classes/structlava_1_1file.md#function-read)**([data::ptr](/_doxybook/Classes/structlava_1_1data.md#using-ptr) data)<br>Read data from file.  |
| [i64](/_doxybook/Namespaces/namespacelava.md#using-i64) | **[read](/_doxybook/Classes/structlava_1_1file.md#function-read)**([data::ptr](/_doxybook/Classes/structlava_1_1data.md#using-ptr) data, [ui64](/_doxybook/Namespaces/namespacelava.md#using-ui64) size)<br>Read data from file (limited size)  |
| [i64](/_doxybook/Namespaces/namespacelava.md#using-i64) | **[write](/_doxybook/Classes/structlava_1_1file.md#function-write)**([data::c_ptr](/_doxybook/Classes/structlava_1_1data.md#using-c-ptr) data, [ui64](/_doxybook/Namespaces/namespacelava.md#using-ui64) size)<br>Write data to file.  |
| [i64](/_doxybook/Namespaces/namespacelava.md#using-i64) | **[seek](/_doxybook/Classes/structlava_1_1file.md#function-seek)**([ui64](/_doxybook/Namespaces/namespacelava.md#using-ui64) position)<br>Seek to position in the file.  |
| [i64](/_doxybook/Namespaces/namespacelava.md#using-i64) | **[tell](/_doxybook/Classes/structlava_1_1file.md#function-tell)**() const<br>Get the current position in the file.  |
| bool | **[writable](/_doxybook/Classes/structlava_1_1file.md#function-writable)**() const<br>Check if the file is in write mode.  |
| [file_type](/_doxybook/Namespaces/namespacelava.md#enum-file-type) | **[get_type](/_doxybook/Classes/structlava_1_1file.md#function-get-type)**() const<br>Get the file type.  |
| [string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) | **[get_path](/_doxybook/Classes/structlava_1_1file.md#function-get-path)**() const<br>Get the path of the file.  |

## Additional inherited members

**Public Functions inherited from [lava::no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md)**

|                | Name           |
| -------------- | -------------- |
| | **[no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md#function-no-copy-no-move)**() =default<br>Construct a new object.  |
| | **[no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md#function-no-copy-no-move)**([no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md) const & ) =delete<br>No copy.  |
| void | **[operator=](/_doxybook/Classes/structlava_1_1no__copy__no__move.md#function-operator=)**([no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md) const & ) =delete<br>No move.  |


## Public Types Documentation

### using ref

```cpp
using lava::file::ref =  file const&;
```

Reference to file. 

## Public Functions Documentation

### function file

```cpp
explicit file(
    string_ref path ="",
    file_mode mode =file_mode::read
)
```

Construct a new file. 

**Parameters**: 

  * **path** Name of file 
  * **mode** File mode 


### function ~file

```cpp
~file()
```

Destroy the file. 

### function open

```cpp
bool open(
    string_ref path,
    file_mode mode =file_mode::read
)
```

Open the file. 

**Parameters**: 

  * **path** Name of file 
  * **mode** File mode 


**Return**: Open was successful or failed 

### function close

```cpp
void close()
```

Close the file. 

### function opened

```cpp
bool opened() const
```

Check if the file is opened. 

**Return**: File is opened or not 

### function get_size

```cpp
i64 get_size() const
```

Get the size of the file. 

**Return**: [i64](/_doxybook/Namespaces/namespacelava.md#using-i64) File size 

### function read

```cpp
inline i64 read(
    data::ptr data
)
```

Read data from file. 

**Parameters**: 

  * **data** Data to read 


**Return**: [i64](/_doxybook/Namespaces/namespacelava.md#using-i64) File size 

### function read

```cpp
i64 read(
    data::ptr data,
    ui64 size
)
```

Read data from file (limited size) 

**Parameters**: 

  * **data** Data to read 
  * **size** File size 


**Return**: [i64](/_doxybook/Namespaces/namespacelava.md#using-i64) File size 

### function write

```cpp
i64 write(
    data::c_ptr data,
    ui64 size
)
```

Write data to file. 

**Parameters**: 

  * **data** Data to write 
  * **size** File size 


**Return**: [i64](/_doxybook/Namespaces/namespacelava.md#using-i64) File size 

### function seek

```cpp
i64 seek(
    ui64 position
)
```

Seek to position in the file. 

**Parameters**: 

  * **position** Position to seek to 


**Return**: [i64](/_doxybook/Namespaces/namespacelava.md#using-i64) Current position 

### function tell

```cpp
i64 tell() const
```

Get the current position in the file. 

**Return**: [i64](/_doxybook/Namespaces/namespacelava.md#using-i64) Current position 

### function writable

```cpp
inline bool writable() const
```

Check if the file is in write mode. 

**Return**: File is writable or only readable 

### function get_type

```cpp
inline file_type get_type() const
```

Get the file type. 

**Return**: [file_type](/_doxybook/Namespaces/namespacelava.md#enum-file-type) Type of file 

### function get_path

```cpp
inline string_ref get_path() const
```

Get the path of the file. 

**Return**: name File path 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000