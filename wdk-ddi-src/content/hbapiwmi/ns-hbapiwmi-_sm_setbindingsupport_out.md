---
UID: NS:hbapiwmi._SM_SetBindingSupport_OUT
title: "_SM_SetBindingSupport_OUT"
author: windows-driver-content
description: The SM_SetBindingSupport_OUT structure is used to receive output parameters from the SM_SetBindingSupport method.
old-location: storage\sm_setbindingsupport_out.htm
old-project: storage
ms.assetid: b0902b79-25ee-45e6-944e-de9e69ce43ec
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PSM_SetBindingSupport_OUT, ,, B, M, O, P, PSM_SetBindingSupport_OUT, PSM_SetBindingSupport_OUT structure pointer [Storage Devices], S, SM_SetBindingSupport_OUT, SM_SetBindingSupport_OUT structure [Storage Devices], T, U, _, _SM_SetBindingSupport_OUT, d, e, g, hbapiwmi/PSM_SetBindingSupport_OUT, hbapiwmi/SM_SetBindingSupport_OUT, i, n, o, p, r, storage.sm_setbindingsupport_out, structs-Fibre_b14ee92a-9c2c-4f8a-be35-b189b0d5e97f.xml, t, u"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	hbapiwmi.h
apiname:
-	SM_SetBindingSupport_OUT
product: Windows
targetos: Windows
req.typenames: SM_SetBindingSupport_OUT, *PSM_SetBindingSupport_OUT
---

# _SM_SetBindingSupport_OUT structure


## -description


The SM_SetBindingSupport_OUT structure is used to receive output parameters from the SM_SetBindingSupport method.


## -syntax


````
typedef struct _SM_SetBindingSupport_OUT {
  ULONG HBAStatus;
} SM_SetBindingSupport_OUT, *PSM_SetBindingSupport_OUT;
````


## -struct-fields




### -field HBAStatus

The status of the operation. For a list of allowed values and their descriptions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>.


## -remarks



The WMI tool suite generates a declaration of the SM_SetBindingSupport_OUT structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_TargetInformationMethods WMI class.



