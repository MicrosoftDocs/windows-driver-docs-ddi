---
UID: NS:hbapiwmi._SM_RemoveTarget_OUT
title: _SM_RemoveTarget_OUT (hbapiwmi.h)
description: The SM_RemoveTarget_OUT structure is used to receive output parameters from the SM_RemoveTarget WMI method.
old-location: storage\sm_removetarget_out.htm
tech.root: storage
ms.assetid: b93f999e-471a-4f02-a6f2-e21386b9e289
ms.date: 03/29/2018
keywords: ["_SM_RemoveTarget_OUT structure"]
ms.keywords: "*PSM_RemoveTarget_OUT, PSM_RemoveTarget_OUT, PSM_RemoveTarget_OUT structure pointer [Storage Devices], SM_RemoveTarget_OUT, SM_RemoveTarget_OUT structure [Storage Devices], _SM_RemoveTarget_OUT, hbapiwmi/PSM_RemoveTarget_OUT, hbapiwmi/SM_RemoveTarget_OUT, storage.sm_removetarget_out, structs-Fibre_3535f161-920f-4483-80d0-3d2d9863c935.xml"
f1_keywords:
 - "hbapiwmi/SM_RemoveTarget_OUT"
 - "SM_RemoveTarget_OUT"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- hbapiwmi.h
api_name:
- SM_RemoveTarget_OUT
targetos: Windows
req.typenames: SM_RemoveTarget_OUT, *PSM_RemoveTarget_OUT
---

# _SM_RemoveTarget_OUT structure


## -description


The SM_RemoveTarget_OUT structure is used to receive output parameters from the SM_RemoveTarget WMI method.


## -struct-fields




### -field HBAStatus

The status of the operation. For a list of allowed values and their descriptions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/hba-status">HBA_STATUS</a>.


## -remarks



The WMI tool suite generates a declaration of the SM_RemoveTarget_OUT structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_EventControl WMI class.



