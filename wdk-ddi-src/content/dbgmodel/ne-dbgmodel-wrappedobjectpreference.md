---
UID: NE:dbgmodel.WrappedObjectPreference
tech.root: debugger
title: WrappedObjectPreference enumeration (dbgmodel.h)
ms.date:  10/31/2024
targetos: Windows
description: The WrappedObjectPreference enum indicates a preference for how the wrapper and the wrapped object should be treated.  
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
 - WrappedObjectPreference
f1_keywords:
 - WrappedObjectPreference
 - dbgmodel/WrappedObjectPreference
dev_langs:
 - c++
helpviewer_keywords:
 - WrappedObjectPreference
---

## -description  
   
The **WrappedObjectPreference** enum indicates a preference for how the wrapper and the wrapped object should be treated.  
   
## -enum-fields  
   
### -field WrappedObjectNameResolution  
   
Indicates that the wrapped object should be used for name resolution and not interpreted to be a generalized proxy for the object. In essence, things like "." and "->" should work in an expression evaluator; however, other operations should not.  
   
### -field WrappedObjectGeneralProxy  
   
Indicates that the wrapper should be considered a general proxy for the wrapped object.  
   
## -remarks  
   
These enums serve to guide the handling of wrapper and wrapped objects, with two distinct modes available. These preferences can affect how functions and operations interact with these objects.

## -see-also

[Debugger Data Model C++ Overview](/windows-hardware/drivers/debugger/data-model-cpp-overview)
