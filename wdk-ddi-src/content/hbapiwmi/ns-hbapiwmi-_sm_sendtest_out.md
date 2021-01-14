---
UID: NS:hbapiwmi._SM_SendTEST_OUT
title: _SM_SendTEST_OUT (hbapiwmi.h)
description: The SM_SendTEST_OUT structure is used to receive output parameters from the SM_SendTEST method.
old-location: storage\sm_sendtest_out.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["SM_SendTEST_OUT structure"]
ms.keywords: "*PSM_SendTEST_OUT, PSM_SendTEST_OUT, PSM_SendTEST_OUT structure pointer [Storage Devices], SM_SendTEST_OUT, SM_SendTEST_OUT structure [Storage Devices], _SM_SendTEST_OUT, hbapiwmi/PSM_SendTEST_OUT, hbapiwmi/SM_SendTEST_OUT, storage.sm_sendtest_out, structs-Fibre_901c8256-fe8d-4194-aaec-8a0557287687.xml"
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
req.typenames: SM_SendTEST_OUT, *PSM_SendTEST_OUT
f1_keywords:
 - _SM_SendTEST_OUT
 - hbapiwmi/_SM_SendTEST_OUT
 - PSM_SendTEST_OUT
 - hbapiwmi/PSM_SendTEST_OUT
 - SM_SendTEST_OUT
 - hbapiwmi/SM_SendTEST_OUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hbapiwmi.h
api_name:
 - _SM_SendTEST_OUT
 - PSM_SendTEST_OUT
 - SM_SendTEST_OUT
---

# _SM_SendTEST_OUT structure


## -description

The SM_SendTEST_OUT structure is used to receive output parameters from the SM_SendTEST method.

## -struct-fields

### -field HBAStatus

The status of the operation. For a list of allowed values and their descriptions, see <a href="/windows-hardware/drivers/storage/hba-status">HBA_STATUS</a>.

## -remarks

The WMI tool suite generates a declaration of the SM_SendTEST_OUT structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_FabricAndDomainManagementMethod WMI class.

