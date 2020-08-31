---
UID: NS:hbapiwmi._SM_RemovePort_OUT
title: _SM_RemovePort_OUT (hbapiwmi.h)
description: The SM_RemovePort_OUT structure is used to receive output parameters from the SM_RemovePort WMI method.
old-location: storage\sm_removeport_out.htm
tech.root: storage
ms.assetid: 7ca1bd9f-8fd4-4d9d-8571-4d6e4b721f3b
ms.date: 03/29/2018
keywords: ["SM_RemovePort_OUT structure"]
ms.keywords: "*PSM_RemovePort_OUT, PSM_RemovePort_OUT, PSM_RemovePort_OUT structure pointer [Storage Devices], SM_RemovePort_OUT, SM_RemovePort_OUT structure [Storage Devices], _SM_RemovePort_OUT, hbapiwmi/PSM_RemovePort_OUT, hbapiwmi/SM_RemovePort_OUT, storage.sm_removeport_out, structs-Fibre_00eb7ab2-9a70-4e22-8b57-1468f52bfe02.xml"
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
targetos: Windows
req.typenames: SM_RemovePort_OUT, *PSM_RemovePort_OUT
f1_keywords:
 - _SM_RemovePort_OUT
 - hbapiwmi/_SM_RemovePort_OUT
 - PSM_RemovePort_OUT
 - hbapiwmi/PSM_RemovePort_OUT
 - SM_RemovePort_OUT
 - hbapiwmi/SM_RemovePort_OUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hbapiwmi.h
api_name:
 - SM_RemovePort_OUT
---

# _SM_RemovePort_OUT structure


## -description

The SM_RemovePort_OUT structure is used to receive output parameters from the SM_RemovePort WMI method.

## -struct-fields

### -field HBAStatus

The status of the operation. For a list of allowed values and their descriptions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/hba-status">HBA_STATUS</a>.

## -remarks

The WMI tool suite generates a declaration of the SM_RemovePort_OUT structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_EventControl WMI class.

