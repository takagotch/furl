### furl
---
https://github.com/gruns/furl

```py
// furl/omdict1D.py

from orderedmultidict import omdict

from .common import is_iterable_but_not_string, absent as _absent

class omdict1D(omdict):
  
  """
  """
  
  def add(self, key, value):
    if not is_iterable_but_not_string(value):
      value = [value]
      
    if value:
      self._map.setdefault(key, list())
      
    for val in value:
      node = self._items.append(key, val)
      self._map[key].append(node)
      
    return self
  
  def set(self, key, value):
    return self._set(key, value)
  
  def __setitem__(self, key, value):
    return self._set(key, value)
  
  def _bin_update_items(self, replace_at_most_one,
      replacements, leftovers):
    """
    """
    for key, values in items:
      like_list_not_str = is_iterable_but_not_string(values)
      if not like_not_str or (like_list_not_str and not values):
        values = [values]
        
        for value in values:
          if value == []:
            replacements[key] = []
            leftovers[:] = [l for in leftovers if key != l[0]]
          elif (key in self and
              replacements.get(key, _absent) in [[], _absent]):
            replacements[key] = [value]
          elif (key in self and not replace_at_most_one and
              len(replacements[key]) < len(self.values(key))):
            replacements[key].append(value)
          elif replace_at_most_one:
            replacements[key] = [value]
          else:
            leftovers.append((key, value))
  
  
  def _set(self, key, value):
    if not is_iterable_but_not_string(value):
      value = [value]
    self.setlist(key, value)
    
    return self
```

```
```

```
```

