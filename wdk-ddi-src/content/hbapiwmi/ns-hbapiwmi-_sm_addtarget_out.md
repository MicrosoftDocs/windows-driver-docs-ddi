---
UID: NS:hbapiwmi._SM_AddTarget_OUT
title: _SM_AddTarget_OUT
author: windows-driver-content
description: The SM_AddTarget_OUT structure is used to receive output parameters from the SM_AddTarget WMI method.
old-location: storage\sm_addtarget_out.htm
old-project: storage
ms.assetid: ed4e58cb-6b32-454b-9538-f9f8aa68df4c
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _SM_AddTarget_OUT, SM_AddTarget_OUT, *PSM_AddTarget_OUT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SM_AddTarget_OUT
req.alt-loc: hbapiwmi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.typenames: SM_AddTarget_OUT, *PSM_AddTarget_OUT
---

# _SM_AddTarget_OUT structure



## -description
The SM_AddTarget_OUT structure is used to receive output parameters from the SM_AddTarget WMI method.



## -syntax

````
typedef struct _SM_AddTarget_OUT {
  ULONG HBAStatus;
} SM_AddTarget_OUT, *PSM_AddTarget_OUT;
````


## -struct-fields

### -field HBAStatus

The status of the operation. For a list of allowed values and their descriptions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>.


## -remarks
