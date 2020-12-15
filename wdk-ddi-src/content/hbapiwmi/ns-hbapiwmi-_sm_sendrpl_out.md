---
UID: NS:hbapiwmi._SM_SendRPL_OUT
title: _SM_SendRPL_OUT (hbapiwmi.h)
description: The SM_SendRPL_OUT structure is used to receive output parameters from the SM_SendRPL method.
old-location: storage\sm_sendrpl_out.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["SM_SendRPL_OUT structure"]
ms.keywords: "*PSM_SendRPL_OUT, PSM_SendRPL_OUT, PSM_SendRPL_OUT structure pointer [Storage Devices], SM_SendRPL_OUT, SM_SendRPL_OUT structure [Storage Devices], _SM_SendRPL_OUT, hbapiwmi/PSM_SendRPL_OUT, hbapiwmi/SM_SendRPL_OUT, storage.sm_sendrpl_out, structs-Fibre_831fc75d-cdee-4fba-9dd1-22204e814d50.xml"
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
req.typenames: SM_SendRPL_OUT, *PSM_SendRPL_OUT
f1_keywords:
 - _SM_SendRPL_OUT
 - hbapiwmi/_SM_SendRPL_OUT
 - PSM_SendRPL_OUT
 - hbapiwmi/PSM_SendRPL_OUT
 - SM_SendRPL_OUT
 - hbapiwmi/SM_SendRPL_OUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hbapiwmi.h
api_name:
 - SM_SendRPL_OUT
---

# _SM_SendRPL_OUT structure


## -description

The SM_SendRPL_OUT structure is used to receive output parameters from the SM_SendRPL method.

## -struct-fields

### -field HBAStatus

The status of the operation. For a list of allowed values and their descriptions, see <a href="/windows-hardware/drivers/storage/hba-status">HBA_STATUS</a>.

### -field TotalRespBufferSize

The size, in bytes, of the results common transport (CT) command.

### -field OutRespBufferSize

The size, in bytes, of the data that was actually retrieved.

### -field RespBuffer

The results of the common transport command.

## -remarks

The WMI tool suite generates a declaration of the SM_SendRPL_OUT structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_FabricAndDomainManagementMethod WMI class.
