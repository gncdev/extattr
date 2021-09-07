# ExtAttr for Python 3.x

----
### Notes;
- This program should not work on Python 2.x versions.


----
> ## Final Class
>
> ### Variables
> - can_throws: (Recommended)
>   - type: Boolean
>   - description: If make this variable true; Program throws on any "BIG" fail but if false; program returns None
>   - default value: False
 ---
 
### Functions 
>
> #### final(key_, value_):
>   - ##### Variables:
>       - key_: 
>           - type: String
>           - description: Variable key
>       - value_:
>           - type: String
>           - description: Variable Value. If not none, (and if string). Adds new variable to final variables.
>           - default value: None
>   - ##### Returns:
>       - String
>       - Throw

> #### final(key_):
>   - ##### Variables:
>       - key_: 
>           - type: String
>           - description: Variable key
>   - ##### Returns:
>       - String (Registered variable string)
>       - Throw
>       - None
--- 

### Examples:

#### Pure Codes

```python
from extattr import final

n_final = final()

n_final("test", "test1")
n_final("test", "test2")
print(n_final("test")) # Result: test1
```

```python
from extattr import final

n_final = final()

n_final("test1", "test1")
n_final("test1", "test1_2")

n_final("test2", "test2_1")
n_final("test2", "test2_2")

print(n_final("test1")) # Result: test1
print(n_final("test2")) # Result: test2_1
```

```python
from extattr import final

n_final = final()

n_final("test1", "test1")
n_final("test1", "test1_2")

n_final("test2", "test2_1")
n_final("test2", "test2_2")

print(n_final("test1")) # Result: test1
print(n_final("test2")) # Result: test2_1
```

##### Codes With Exceptions

```python
from extattr import final

n_final = final(can_throws=True)

n_final("testkey", "testvalue")
print(n_final("testkey1")) # Throws: "Not found key!"
```

```python
from extattr import final

n_final = final(can_throws=True)

n_final("testkey", "testvalue")
n_final("testkey", "testvalue1") # Throws: Your can not replace final value/values!
print(n_final("testkey1")) # Throws: "Not found key!"
```


