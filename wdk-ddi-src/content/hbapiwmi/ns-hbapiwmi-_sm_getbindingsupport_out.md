---
UID: NS:hbapiwmi._SM_GetBindingSupport_OUT
title: _SM_GetBindingSupport_OUT
author: windows-driver-content
description: The SM_GetBindingSupport_OUT structure is used to receive output parameters from the SM_GetBindingSupport method.
old-location: storage\sm_getbindingsupport_out.htm
old-project: storage
ms.assetid: 4f45e2ad-19f9-4308-8d63-edf066545e07
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: SM_GetBindingSupport_OUT, hbapiwmi/SM_GetBindingSupport_OUT, PSM_GetBindingSupport_OUT structure pointer [Storage Devices], PSM_GetBindingSupport_OUT, *PSM_GetBindingSupport_OUT, structs-Fibre_687416b3-60d9-494f-895b-a23fcb666994.xml, storage.sm_getbindingsupport_out, _SM_GetBindingSupport_OUT, SM_GetBindingSupport_OUT structure [Storage Devices], hbapiwmi/PSM_GetBindingSupport_OUT
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
-	SM_GetBindingSupport_OUT
product: Windows
targetos: Windows
req.typenames: SM_GetBindingSupport_OUT, *PSM_GetBindingSupport_OUT
---

# _SM_GetBindingSupport_OUT structure


## -description


The SM_GetBindingSupport_OUT structure is used to receive output parameters from the SM_GetBindingSupport method.


## -syntax


````
typedef struct _SM_GetBindingSupport_OUT {
  ULONG HBAStatus;
  ULONG Flags;
} SM_GetBindingSupport_OUT, *PSM_GetBindingSupport_OUT;
````


## -struct-fields




### -field HBAStatus

The status of the operation. For a list of allowed values and their descriptions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>.


### -field Flags

The HBA_BIND_CAPABILITY binding capabilities.


## -remarks


The WMI tool suite generates a declaration of the SM_GetBindingSupport_OUT structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_TargetInformationMethods WMI class.


