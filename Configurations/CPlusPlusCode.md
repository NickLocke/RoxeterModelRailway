# C++ Code

## Anonymous Namespaces


## Public vs Private


## Lists of Objects


## Instance vs Static

Where it is necessary to access the specific instance of an object, rather than just some static properties, it is necessary to gain access to that instance. Using RoxEventHandler as an example, a pointer to the instance is defined in the header:

```
static RoxEventHandler *instance;
```

An initial value of `nullptr` needs to be set. A sensible place to do this is in the CPP file which contains the constructor:

```
RoxEventHandler* RoxEventHandler::instance = nullptr;
```

Then, in the constructor, the value of instance is actually set:

```
RoxEventHandler::RoxEventHandler()
{
   instance = this;
}
```

From then on, `instance` can be used whenever it is necessary to refer to something non-static in the specific instance of the class. Typically, that is a requirement when access to member variables is needed. For example:

```
instance->processTrackOccupancyEvent(actionType, eventVariableType, eventVariableNumber);
```