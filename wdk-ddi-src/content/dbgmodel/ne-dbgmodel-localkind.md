---
UID: NE:dbgmodel.LocalKind
tech.root: debugger
title: LocalKind enumeration (dbgmodel.h)
ms.date:  10/31/2024
targetos: Windows
description: Defines the kind of local that a particular name is (whether an argument to the function or a local variable).  
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
 - LocalKind
f1_keywords:
 - LocalKind
 - dbgmodel/LocalKind
dev_langs:
 - c++
helpviewer_keywords:
 - LocalKind
---

## -description
   
The **LocalKind** enum defines the kind of local that a particular name is (whether an argument to the function or a local variable).  
   
## -enum-fields  
   
### -field LocalArgument  
   
The name is a local argument to the function.  
   
### -field LocalVariable  
   
The  name is a local variable of the function.  
   
## -remarks  
   
These enums values provide a way to understand the scope and nature of the local within the function. 


## -see-also

[Debugger Data Model C++ Overview](/windows-hardware/drivers/debugger/data-model-cpp-overview)
