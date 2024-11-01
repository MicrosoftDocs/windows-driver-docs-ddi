---
UID: NE:dbgmodel.UDTKind
tech.root: debugger
title: UDTKind enumeration (dbgmodel.h)
ms.date:  10/31/2024
targetos: Windows
description: The UDTKind enum defines the nature of the User-Defined Type (UDT) in question.  
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
 - UDTKind
f1_keywords:
 - UDTKind
 - dbgmodel/UDTKind
dev_langs:
 - c++
helpviewer_keywords:
 - UDTKind
---

## -description  
   
The **UDTKind** enum defines the nature of the User-Defined Type (UDT) in question.  
   
## -enum-fields  
   
### -field UDTStruct  
   
The UDT is a structure.  
   
### -field UDTClass  
   
The UDT is a class.  
   
### -field UDTUnion  
   
The UDT is a union.  
   
### -field UDTInterface  
   
The UDT is an interface.  
   
### -field UDTTaggedUnion  
   
The UDT is a tagged union.  
   
## -remarks  
   
These enums aid in identifying the kind of UDT, whether a UDT is a class, structure, interface, union, or tagged union. This can be valuable when dealing with complex data structures or when debugging. 

## -see-also

[Debugger Data Model C++ Overview](/windows-hardware/drivers/debugger/data-model-cpp-overview)

