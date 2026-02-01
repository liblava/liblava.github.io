---
title: lava::file_system
summary: File system. 

---

# lava::file_system



File system. 


`#include <file_system.hpp>`

Inherits from [lava::no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md)

## Public Functions

|                | Name           |
| -------------- | -------------- |
| [sem_version](/_doxybook/Namespaces/namespacelava.md#using-sem-version) | **[get_version](/_doxybook/Classes/structlava_1_1file__system.md#function-get-version)**()<br>Get the version.  |
| [string](/_doxybook/Namespaces/namespacelava.md#using-string) | **[get_base_dir](/_doxybook/Classes/structlava_1_1file__system.md#function-get-base-dir)**()<br>Get the base directory.  |
| [string](/_doxybook/Namespaces/namespacelava.md#using-string) | **[get_full_base_dir](/_doxybook/Classes/structlava_1_1file__system.md#function-get-full-base-dir)**([string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) path)<br>Get the path relative to base directory.  |
| [string](/_doxybook/Namespaces/namespacelava.md#using-string) | **[get_pref_dir](/_doxybook/Classes/structlava_1_1file__system.md#function-get-pref-dir)**()<br>Get the preferences directory.  |
| [string](/_doxybook/Namespaces/namespacelava.md#using-string) | **[get_res_dir](/_doxybook/Classes/structlava_1_1file__system.md#function-get-res-dir)**()<br>Get the resource directory.  |
| bool | **[mount](/_doxybook/Classes/structlava_1_1file__system.md#function-mount)**([string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) path)<br>Mount path.  |
| bool | **[mount_base](/_doxybook/Classes/structlava_1_1file__system.md#function-mount-base)**([string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) base_dir_path)<br>Mount base directory path.  |
| bool | **[exists](/_doxybook/Classes/structlava_1_1file__system.md#function-exists)**([string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) file)<br>Check if file exists.  |
| [string](/_doxybook/Namespaces/namespacelava.md#using-string) | **[get_real_dir](/_doxybook/Classes/structlava_1_1file__system.md#function-get-real-dir)**([string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) file)<br>Get the real directory of file.  |
| [string_list](/_doxybook/Namespaces/namespacelava.md#using-string-list) | **[enumerate_files](/_doxybook/Classes/structlava_1_1file__system.md#function-enumerate-files)**([string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) path)<br>Enumerate files in directory.  |
| bool | **[initialize](/_doxybook/Classes/structlava_1_1file__system.md#function-initialize)**([string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) argv_0, [string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) org, [string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) app, [string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) ext)<br>Initialize the file system.  |
| void | **[terminate](/_doxybook/Classes/structlava_1_1file__system.md#function-terminate)**()<br>Terminate the file system.  |
| [string_list](/_doxybook/Namespaces/namespacelava.md#using-string-list) | **[mount_res](/_doxybook/Classes/structlava_1_1file__system.md#function-mount-res)**()<br>Mount resource directories and files.  |
| bool | **[create_folder](/_doxybook/Classes/structlava_1_1file__system.md#function-create-folder)**([string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) name ="data")<br>Create a folder in the preferences directory.  |
| void | **[clean_pref_dir](/_doxybook/Classes/structlava_1_1file__system.md#function-clean-pref-dir)**()<br>Clean preferences directory.  |
| [string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) | **[get_org](/_doxybook/Classes/structlava_1_1file__system.md#function-get-org)**() const<br>Get the organization name.  |
| [string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) | **[get_app](/_doxybook/Classes/structlava_1_1file__system.md#function-get-app)**() const<br>Get the application name.  |
| [string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) | **[get_ext](/_doxybook/Classes/structlava_1_1file__system.md#function-get-ext)**() const<br>Get the extension name.  |
| bool | **[ready](/_doxybook/Classes/structlava_1_1file__system.md#function-ready)**() const<br>Check if file system is ready.  |

## Additional inherited members

**Public Functions inherited from [lava::no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md)**

|                | Name           |
| -------------- | -------------- |
| | **[no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md#function-no-copy-no-move)**() =default<br>Construct a new object.  |
| | **[no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md#function-no-copy-no-move)**([no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md) const & ) =delete<br>No copy.  |
| void | **[operator=](/_doxybook/Classes/structlava_1_1no__copy__no__move.md#function-operator=)**([no_copy_no_move](/_doxybook/Classes/structlava_1_1no__copy__no__move.md) const & ) =delete<br>No move.  |


## Public Functions Documentation

### function get_version

```cpp
sem_version get_version()
```

Get the version. 

**Return**: [sem_version](/_doxybook/Namespaces/namespacelava.md#using-sem-version) Semantic version 

### function get_base_dir

```cpp
string get_base_dir()
```

Get the base directory. 

**Return**: string Base directory 

### function get_full_base_dir

```cpp
string get_full_base_dir(
    string_ref path
)
```

Get the path relative to base directory. 

**Parameters**: 

  * **path** Path to add to base directory 


**Return**: string Relative base directory path 

### function get_pref_dir

```cpp
string get_pref_dir()
```

Get the preferences directory. 

**Return**: string Preferences directory 

### function get_res_dir

```cpp
string get_res_dir()
```

Get the resource directory. 

**Return**: string Resource directory 

### function mount

```cpp
bool mount(
    string_ref path
)
```

Mount path. 

**Parameters**: 

  * **path** Path to mount 


**Return**: Mount was successful or failed 

### function mount_base

```cpp
bool mount_base(
    string_ref base_dir_path
)
```

Mount base directory path. 

**Parameters**: 

  * **base_dir_path** Base directory path 


**Return**: Mount was successful or failed 

### function exists

```cpp
bool exists(
    string_ref file
)
```

Check if file exists. 

**Parameters**: 

  * **file** File to check 


**Return**: File exists or not found 

### function get_real_dir

```cpp
string get_real_dir(
    string_ref file
)
```

Get the real directory of file. 

**Parameters**: 

  * **file** Target file 


**Return**: string Real directory of file 

### function enumerate_files

```cpp
string_list enumerate_files(
    string_ref path
)
```

Enumerate files in directory. 

**Parameters**: 

  * **path** Target directory 


**Return**: [string_list](/_doxybook/Namespaces/namespacelava.md#using-string-list) List of files 

### function initialize

```cpp
bool initialize(
    string_ref argv_0,
    string_ref org,
    string_ref app,
    string_ref ext
)
```

Initialize the file system. 

**Parameters**: 

  * **argv_0** First command line argument 
  * **org** Organization name 
  * **app** Application name 
  * **ext** Extension name 


**Return**: Initialize was successful or failed 

### function terminate

```cpp
void terminate()
```

Terminate the file system. 

### function mount_res

```cpp
string_list mount_res()
```

Mount resource directories and files. 

**Return**: [string_list](/_doxybook/Namespaces/namespacelava.md#using-string-list) List of mounted resources 

### function create_folder

```cpp
bool create_folder(
    string_ref name ="data"
)
```

Create a folder in the preferences directory. 

**Parameters**: 

  * **name** Name of folder (default: data) 


**Return**: Folder created or not 

### function clean_pref_dir

```cpp
void clean_pref_dir()
```

Clean preferences directory. 

### function get_org

```cpp
inline string_ref get_org() const
```

Get the organization name. 

**Return**: [string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) Name of organization 

### function get_app

```cpp
inline string_ref get_app() const
```

Get the application name. 

**Return**: [string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) Name of application 

### function get_ext

```cpp
inline string_ref get_ext() const
```

Get the extension name. 

**Return**: [string_ref](/_doxybook/Namespaces/namespacelava.md#using-string-ref) Name of extension 

### function ready

```cpp
inline bool ready() const
```

Check if file system is ready. 

**Return**: File system is ready or not 

-------------------------------

Updated on 2026-02-01 at 18:13:39 +0000