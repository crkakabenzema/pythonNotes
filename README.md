| 属性     | 类公有属性                   | 类私有属性                     | 实例方法公有属性                  | 实例方法私有属性       |
| -------- | ---------------------------- | ------------------------------ | --------------------------------- | ---------------------- |
| 存在域   | 类中单独定义或在构造函数定义 | 类中单独定义或在构造函数定义   | __init__方法内，优先访问          | 实例对象单独定义       |
| 标识符   | 无                           | __属性                         | 一般用self.属性标识（__标识除外） | 无                     |
| 外部调用 | 实例对象或类对象             | 通过实例对象.__str__()方法访问 | 通过实例对象的方法或类对象的方法  | 实例方法return         |
| 修改     | 使用类方法@classmethod       | 不能修改                       | 实例对象属性覆盖(del属性后复原)   | 实例对象覆盖，不能修改 |

| 类中定义方法                                                 | 实例方法                                 | 类方法                                                       | 静态方法                                                     |
| ------------------------------------------------------------ | ---------------------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 标识符                                                       | 无（__init__可定义类公有属性）           | 类方法上添加@classmethod，类方法内使用cls.属性调用，类中其他方法内使用ClassName.属性调用 | @staticmethod，无self参数                                    |
| 参数                                                         | 第一个是self                             | 第一个是类对象cls                                            | 可以无参数                                                   |
| 外部调用                                                     | 可以是类属性或实例属性，实例属性优先级高 | 通过实例对象或类对象                                         | 实例对象或类对象调用                                         |
| 作用对象                                                     | 实例方法                                 | 类                                                           |                                                              |
| 特殊用途                                                     | 必须实例化对象调用                       | 修改类属性，可不使用实例化对象调用                           | 和类本身无关，不会涉及类属性和方法的操作。可不使用实例化对象调用 |
| 注1：构造函数__init__内定义，会覆盖类属性，是一种特殊的实例方法，只和实例对象有关 | 注2：self参数的本质是实例化类的对象形参  |                                                              |                                                              |

| 变量     | 不同类传递变量                                   | 同一类中不同方法传递变量             |
| -------- | ------------------------------------------------ | ------------------------------------ |
| 调用方式 | 方法中定义return, 通过实例化类中的方法调用返回值 | 通过设置self的属性传递，无需return值 |

| 参数         | 必选参数   | 默认参数                                                     | 可变参数                       | 关键字参数                    |
| ------------ | ---------- | ------------------------------------------------------------ | ------------------------------ | ----------------------------- |
| 定义形式     | f(x)       | f(x=defaultValue)                                            | f(*X)                          | f(**kw)                       |
| 赋值形式     | f(value)   | f(value)                                                     | f(*listX/tupleX)               | f(valueName=’value’)          |
| 函数引用要求 | 必须赋值   | 可不赋值，x将使用value                                       | 可赋任意数量的值，也可不赋值。 | 参数需含参数名，数量任意包括0 |
| 缺点         | 不可不赋值 | 调用该函数时，如参数变化，则默认参数内容改变。所以必须指向不变对象。 |                                |                               |

