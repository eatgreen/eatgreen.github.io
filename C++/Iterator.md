Iterator is a pointer and one can do arithmatic operation on it.

we can
auto Xt_iter=Xt_.begin();
Xobs_.push_back(*(Xt_iter+int(das_obj.t_offset()/dt_)+i*t_ratio_));

define a iterator and dereference it to access the data.

*iter read access to the element
iter-> member read access to a member of the element

++ iteratot step forward

== and != return whether two iterators represent the same position

= assign an iterator

###iterator end
the iterator end, or the last iterator is open.

.end() is the position behind the last element. **past-the-end iterator**

which means when having .begin(), begin()+2 where the int 2 is the size of range!!!

###iterator type
iterator, read/write mode
const_iterator, read only

###access map
pos->first, pos->second

###++pos vs pos++
pos++ returns the temporary old position. slightly slower.