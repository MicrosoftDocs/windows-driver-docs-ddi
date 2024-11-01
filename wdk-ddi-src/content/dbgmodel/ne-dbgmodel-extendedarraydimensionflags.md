---
UID: NE:dbgmodel.ExtendedArrayDimensionFlags
tech.root: debugger
title: ExtendedArrayDimensionFlags
ms.date: 10/31/2024
targetos: Windows
description: This enum defines the memory layout of one dimension of an extended array.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: dbgmodel.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: false
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - dbgmodel.h
api_name:
 - ExtendedArrayDimensionFlags
f1_keywords:
 - ExtendedArrayDimensionFlags
 - dbgmodel/ExtendedArrayDimensionFlags
dev_langs:
 - c++
helpviewer_keywords:
 - ExtendedArrayDimensionFlags
---

## -description

This enum defines the memory layout of one dimension of an extended array. It is designed to fully describe the array layout of a CLI (ECMA-335) array.  

## -enum-fields

### -field ExtendedArrayLengthIsOffset32

Indicates that the "Length" field of the array dimension is an offset from the base address of the array where to find a dynamic size.  
  
### -field ExtendedArrayLengthIsOffset64

Similar to `ExtendedArrayLengthIsOffset32` but for 64 bit offsets.  
  
### -field ExtendedArrayLengthIsOffset

This flag can be used in place of `ExtendedArrayLengthIsOffset32` or `ExtendedArrayLengthIsOffset64` to denote the offset of the dynamic size.  

### -field ExtendedArrayLowerBoundIsOffset32
  
Indicates that the "LowerBound" field of the array dimension is an offset from the base address of the array where to find a dynamic bound.  
  
### -field ExtendedArrayLowerBoundIsOffset64

Similar to `ExtendedArrayLowerBoundIsOffset32` but for 64 bit offsets.  
  
### -field ExtendedArrayLowerBoundIsOffset

This flag can be used in place of `ExtendedArrayLowerBoundIsOffset32` or `ExtendedArrayLowerBoundIsOffset64` to denote the offset of the dynamic bound.  
  
### -field ExtendedArrayStrideIsOffset32

Indicates that the "Stride" field of the array dimension is an offset from the base address of the array where to find a dynamic stride.  
  
### -field ExtendedArrayStrideIsOffset64

Similar to `ExtendedArrayStrideIsOffset32` but for 64 bit offsets.  
  
### -field ExtendedArrayStrideIsOffset

This flag can be used in place of `ExtendedArrayStrideIsOffset32` or `ExtendedArrayStrideIsOffset64` to denote the offset of the dynamic stride.  
  
### -field ExtendedArrayStrideIsComputedByNextRank

Indicates that the "Stride" field is computed from the element size and the computed sizes of each dimension as indicated by other fields. The stride of this dimension is based on the stride of the next (e.g.: dim[0] is the largest).  
  
### -field ExtendedArrayStrideIsComputedByPreviousRank

Similar to `ExtendedArrayStrideIsComputedByNextRank`, but the stride of this dimension is based on the stride of the previous (e.g.: dim[0] is the smallest).  
  
### -field ExtendedArrayStrideIsComputed

This flag can be used in place of `ExtendedArrayStrideIsComputedByNextRank` or `ExtendedArrayStrideIsComputedByPreviousRank` to denote that the stride is computed based on other dimensions.  

## -remarks

## -see-also

[Debugger Data Model C++ Overview](/windows-hardware/drivers/debugger/data-model-cpp-overview)
