# Groovy中使用Gpath

Gpath用到对类的属性的操作上，是用于对对象属性的访问，形如：“对象.属性”的访问方式。“person.name”访问的是对象“person”的属性“name”，而“person.addr.city”则是 先访问“person”的属性“addr”，然后再访问“addr”的属性“city”。通过这样的一种访问方式， 使得这种类的组合方式不论嵌套多少层，都可以使用Gpath访问得到。

对于空指针的访问，我们只需要使用“?.”操作符即可，它的结果是如果Gpath访问 的对象存在，则返回结果；否则返回null。

使用Gpath访问GroovyBean对象的属性并不是直接访问该属性，而是通过“set” 和“get”方法进行的。当然，我们也有办法访问属性的真实值，这就是使用“.@”操作符。


但是，在通过Gpath访问XML的时候，“.@”操作符以访问一个节点的属性。

