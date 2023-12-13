### Node, Elemnts,Interface

### للتوضيح فقط

Node = N = interface (properties + methods) = blueprint model

node = n = real interface = the real model

-So the Node Interface is a blueprint for all of [the properties (data) and methods (functionality)] that every real node has after it's been created.

--------------

*Element points to its parent, Node*

![A diagram showing an Element with an arrow pointing to Node, and Node with an arrow pointing to EventTarget](https://video.udacity-data.com/topher/2017/December/5a22d197_ud117-l1-interface-chain/ud117-l1-interface-chain.jpg)

-Since Element is pointing at Node, this indicates that the Element Interface inherits all of the Node Interface's properties and methods. This means that any element (lowercase "e"!) that was created from the Element Interface is *also* a descendent from the Node Interface...which means the element (lowercase "e"!) is also a node (lowercase "n"!).
