guard and bees system 

overview
- there should be only one reader of a queue to prevent race situations that would cause double execution. this reader is the guard. the work orders produced from the [in-protocol] reading of the element are given to independently spawned processes the "bees" 

- processes
-- guard
--- upon wake
----- per element on queue
------ read an element off the queue
-------- move element to a hold area
-------- produce a work order
-------- spawn a worker bee process with a specific work order
----- once the queue is empty die.

-- bees
--- upon wake
----- process according to work order (parameter attached)
----- upon successful completion 
------- delete element in hold (non recycled) OR
------- reenter element to queue with new ID (recycled) and delete element in hold
------- then
------- die
