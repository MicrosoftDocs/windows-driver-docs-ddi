---
UID: NS:hbapiwmi._SM_SendSRL_OUT
title: _SM_SendSRL_OUT (hbapiwmi.h)
description: The SM_SendSRL_OUT structure is used to receive output parameters from the SM_SendSRL method.
old-location: storage\sm_sendsrl_out.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["SM_SendSRL_OUT structure"]
ms.keywords: "*PSM_SendSRL_OUT, PSM_SendSRL_OUT, PSM_SendSRL_OUT structure pointer [Storage Devices], SM_SendSRL_OUT, SM_SendSRL_OUT structure [Storage Devices], _SM_SendSRL_OUT, hbapiwmi/PSM_SendSRL_OUT, hbapiwmi/SM_SendSRL_OUT, storage.sm_sendsrl_out, structs-Fibre_35335fb8-61e9-47bd-9b55-48f28a53483b.xml"
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
req.typenames: SM_SendSRL_OUT, *PSM_SendSRL_OUT
f1_keywords:
 - _SM_SendSRL_OUT
 - hbapiwmi/_SM_SendSRL_OUT
 - PSM_SendSRL_OUT
 - hbapiwmi/PSM_SendSRL_OUT
 - SM_SendSRL_OUT
 - hbapiwmi/SM_SendSRL_OUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - hbapiwmi.h
api_name:
 - SM_SendSRL_OUT
---

# _SM_SendSRL_OUT structure


## -description

The SM_SendSRL_OUT structure is used to receive output parameters from the SM_SendSRL method.

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

The WMI tool suite generates a declaration of the SM_SendSRL_OUT structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_FabricAndDomainManagementMethod WMI class.
