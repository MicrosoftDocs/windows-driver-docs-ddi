---
UID: NS:dbgmodel.ExtendedArrayDimension
tech.root: debugger
title: ExtendedArrayDimension structure (dbgmodel.h)
ms.date: 10/31/2024
targetos: Windows
description: The ExtendedArrayDimension struct provides details about an array dimension, including how to interpret the remainder of the information in the array dimension, lower bounds, length, and stride.  
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: dbgmodel.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dbgmodel.h
api_name:
 - ExtendedArrayDimension
f1_keywords:
 - ExtendedArrayDimension
 - dbgmodel/ExtendedArrayDimension
dev_langs:
 - c++
helpviewer_keywords:
 - ExtendedArrayDimension
---


## -description  
   
The **ExtendedArrayDimension** struct provides details about an array dimension, including how to interpret the remainder of the information in the array dimension, lower bounds, length, and stride.  
   
## -struct-fields  
   
### -field DimensionFlags  
   
The **DimensionFlags** member is a ULONG64 type that specifies information about how to interpret the remainder of the information in the array dimension.  
   
### -field LowerBound  
   
The **LowerBound** member is a LONG64 type that defines the lower bounds of the array. For C style zero based arrays, this will always be zero. Note that there is no uniform restriction that all arrays represented by these interfaces are zero based.  
   
### -field Length  
   
The **Length** member is a ULONG64 type that specifies the length of the dimension. The dimension is considered to be of the form (LowerBound, LowerBound + Length).  
   
### -field Stride  
   
The **Stride** member is a ULONG64 type that defines how many bytes to move forward in memory to walk from index N of the dimension to index N + 1.  
   
## -remarks  
   
The **ExtendedArrayDimension** struct is typically used for handling multi-dimensional arrays. With this struct, each dimension of the array can have its own properties such as lower bound, length, and stride. This makes it especially useful when dealing with non-zero based or non-uniform arrays.

## -see-also

[Debugger Data Model C++ Overview](/windows-hardware/drivers/debugger/data-model-cpp-overview)

