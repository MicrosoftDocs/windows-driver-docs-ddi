---
UID: NS:hbapiwmi._SM_SendRPS_OUT
title: _SM_SendRPS_OUT (hbapiwmi.h)
description: The SM_SendRPS_OUT structure is used to receive output parameters from the SM_SendRPS method.
old-location: storage\sm_sendrps_out.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["SM_SendRPS_OUT structure"]
ms.keywords: "*PSM_SendRPS_OUT, PSM_SendRPS_OUT, PSM_SendRPS_OUT structure pointer [Storage Devices], SM_SendRPS_OUT, SM_SendRPS_OUT structure [Storage Devices], _SM_SendRPS_OUT, hbapiwmi/PSM_SendRPS_OUT, hbapiwmi/SM_SendRPS_OUT, storage.sm_sendrps_out, structs-Fibre_6aad3070-5819-4742-87c6-f5c3b50b4f9b.xml"
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
req.typenames: SM_SendRPS_OUT, *PSM_SendRPS_OUT
f1_keywords:
 - _SM_SendRPS_OUT
 - hbapiwmi/_SM_SendRPS_OUT
 - PSM_SendRPS_OUT
 - hbapiwmi/PSM_SendRPS_OUT
 - SM_SendRPS_OUT
 - hbapiwmi/SM_SendRPS_OUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hbapiwmi.h
api_name:
 - SM_SendRPS_OUT
---

# _SM_SendRPS_OUT structure


## -description

The SM_SendRPS_OUT structure is used to receive output parameters from the SM_SendRPS method.

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

The WMI tool suite generates a declaration of the SM_SendRPS_OUT structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_FabricAndDomainManagementMethod WMI class.
