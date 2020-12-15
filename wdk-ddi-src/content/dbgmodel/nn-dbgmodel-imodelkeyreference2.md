---
UID: NN:dbgmodel.IModelKeyReference2
title: IModelKeyReference2 (dbgmodel.h)
description: A reference to a key on a data model object.
ms.date: 06/11/2019
keywords: ["IModelKeyReference2 interface"]
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
targetos: Windows
tech.root: debugger
ms.custom: RS5
f1_keywords:
 - IModelKeyReference2
 - dbgmodel/IModelKeyReference2
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IModelKeyReference2
---

# IModelKeyReference2 interface


## -description

A reference to a key on a data model object.

This version 2 of the interface supports all of the previous methods with identical signatures and includes additional new methods that provide added functionality. The new methods are listed in the header at the end of the section for that interface.

## -inheritance

IModelKeyReference2 interits from [IModelKeyReference](nn-dbgmodel-imodelkeyreference.md).

## -remarks

**Key References** 

A key reference is, in essence, a handle to a key on a particular object. A client can retrieve such handle via methods such as GetKeyReference and use the handle later to get or set the value of the key without necessarily holding onto the original object. This type of object is an implementation of the [IModelKeyReference](nn-dbgmodel-imodelkeyreference.md) or IModelKeyReference2 interface which is boxed into an [IModelObject](nn-dbgmodel-imodelobject.md). The model object will return a kind of ObjectKeyReference when queried and then intrinsic value is a VT_UNKNOWN which is guaranteed to be queryable for [IModelKeyReference](nn-dbgmodel-imodelkeyreference.md). In process, it is guaranteed to be statically castable to [IModelKeyReference](nn-dbgmodel-imodelkeyreference.md).

## -see-also

[Debugger Data Model C++ Overview](/windows-hardware/drivers/debugger/data-model-cpp-overview)
