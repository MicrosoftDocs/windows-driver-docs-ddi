---
UID: NE:dbgmodel.StorageKind
tech.root: debugger
title: StorageKind enumeration (dbgmodel.h)
ms.date:  10/31/2024
targetos: Windows
description: The StorageKind enum defines where a local is stored.  
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
 - StorageKind
f1_keywords:
 - StorageKind
 - dbgmodel/StorageKind
dev_langs:
 - c++
helpviewer_keywords:
 - StorageKind
---

## -description  
   
The **StorageKind** enum defines where a local is stored.  
   
## -enum-fields  
   
### -field StorageUnknown  
   
The storage location of the local is unknown.  
   
### -field StorageRegister  
   
The local is stored in a register.  
   
### -field StorageRegisterRelative  
   
The local is stored at an address relative to a register.  
   
### -field StorageRegisterRelativeIndirect  
   
The local is stored indirectly through a register-relative address.  
   
## -remarks  
   
This enums help to clarify the storage location of the local, providing information about how and where it is stored within the system. 

## -see-also

[Debugger Data Model C++ Overview](/windows-hardware/drivers/debugger/data-model-cpp-overview)

