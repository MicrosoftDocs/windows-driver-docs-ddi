---
UID: NS:hbapiwmi._SM_SendLIRR_OUT
title: _SM_SendLIRR_OUT (hbapiwmi.h)
description: The SM_SendLIRR_OUT structure is used to receive output parameters from the SM_SendLIRR method.
old-location: storage\sm_sendlirr_out.htm
tech.root: storage
ms.assetid: 68e6ab20-b8a2-4a72-bb38-28fe4345e638
ms.date: 03/29/2018
keywords: ["_SM_SendLIRR_OUT structure"]
ms.keywords: "*PSM_SendLIRR_OUT, PSM_SendLIRR_OUT, PSM_SendLIRR_OUT structure pointer [Storage Devices], SM_SendLIRR_OUT, SM_SendLIRR_OUT structure [Storage Devices], _SM_SendLIRR_OUT, hbapiwmi/PSM_SendLIRR_OUT, hbapiwmi/SM_SendLIRR_OUT, storage.sm_sendlirr_out, structs-Fibre_42d6f555-895e-4cb7-a2fb-8bc61025a940.xml"
f1_keywords:
 - "hbapiwmi/SM_SendLIRR_OUT"
 - "SM_SendLIRR_OUT"
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
- SM_SendLIRR_OUT
targetos: Windows
req.typenames: SM_SendLIRR_OUT, *PSM_SendLIRR_OUT
---

# _SM_SendLIRR_OUT structure


## -description


The SM_SendLIRR_OUT structure is used to receive output parameters from the SM_SendLIRR method.


## -struct-fields




### -field HBAStatus

The status of the operation. For a list of allowed values and their descriptions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/hba-status">HBA_STATUS</a>.


### -field TotalRespBufferSize

The size, in bytes, of the results common transport (CT) command.


### -field OutRespBufferSize

The size, in bytes, of the data that was actually retrieved.


### -field RespBuffer

The results of the common transport command.


## -remarks



The WMI tool suite generates a declaration of the SM_SendRNID_OUT structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_FabricAndDomainManagementMethod WMI class.



