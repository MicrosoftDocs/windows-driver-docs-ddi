---
UID: NN:dbgmodel.IModelObject
title: IModelObject (dbgmodel.h)
description: The IModelObject interface encapsulates the notion of an object -- whether that object is an integer, a string, some complex type in the target address space of the debugger. 
ms.assetid: d4ac8601-7610-40af-8fe5-0ce0d96fe124
ms.date: 07/20/2018
keywords: ["IModelObject interface"]
f1_keywords:
 - "dbgmodel/IModelObject"
req.header: dbgmodel.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.umdf-ver:
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- COM
api_location: 
- dbgmodel.h
api_name: 
- IModelObject
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IModelObject interface

## -description

One of the most basic yet powerful things about the data model is that it standardizes the definition of what an object is and how one interacts with an object. The IModelObject interface encapsulates the notion of an object -- whether that object is an integer, a floating point value, a string, some complex type in the target address space of the debugger, or some debugger concept like the notion of a process or a module. 

There are several different things that can be held in (or boxed into) an IModelObject: 

• Intrinsic Values - An IModelObject can be a container for a number of basic types: 8, 16, 32, or 64 bit signed or unsigned integers, booleans, strings, errors, or the notion of empty.

• Native Objects - An IModelObject can represent a complex type (as defined by the debugger's type system) within the address space of whatever the debugger is targeting

• Synthetic Objects - An IModelObject can be a dynamic object -- a dictionary if you will: a collection of key / value / metadata tuples and a set of concepts which define behaviors that aren't simply represented by key / value pairs.

• Properties - An IModelObject can represent a property: something whose value can be retrieved or altered with a method call. A property within an IModelObject is effectively an [IModelPropertyAccessor](nn-dbgmodel-imodelpropertyaccessor.md) interface boxed into an IModelObject

• Methods - An IModelObject can represent a method: something you can call with a set of arguments and get a return value. A method within an IModelObject is effectively an [IModelMethod](nn-dbgmodel-imodelmethod.md) interface boxed into an IModelObject

An IModelObject is not an object in isolation. In addition to representing one of the types of objects shown above, each object has the notion of a chain of parent data models. This chain behaves much like a | JavaScript prototype chain. Instead of a linear chain of prototypes like JavaScript has, each data model object defines a linear chain of parent models. Each of those parent models in turn has another linear chain of its own set of parents. In essence, each object is an aggregation of the capabilities (properties, etc...) of both itself and every object in this tree. When a specific property is queried, if the object it is queried on does not support that property, the query is passed in linear order to each parent in turn. This creates a behavior where the search for a property is resolved by a depth-first search of the aggregate tree. 

Extensibility within this object model is very simple given this notion that every object is an aggregate of itself and the tree of parent models. An extension can come in and add itself into the list of parent models for another object. Doing this extends the object. In this manner, it is possible to add capabilities onto anything: a particular instance of an object or value, a native type, the debugger's concept of what a process or thread is, or even the notion of "all iterable objects". 


## -inheritance
IModelObject interits from IUnknown. 
## -remarks

## -see-also
