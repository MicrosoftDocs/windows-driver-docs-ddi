---
UID: NS:hbapiwmi._SM_SendRLS_OUT
title: _SM_SendRLS_OUT (hbapiwmi.h)
description: The SM_SendRLS_OUT structure is used to receive output parameters from the SM_SendRLS method.
old-location: storage\sm_sendrls_out.htm
tech.root: storage
ms.assetid: 28c08a30-b6c6-4f1b-a3a9-0581da0159b9
ms.date: 03/29/2018
ms.keywords: "*PSM_SendRLS_OUT, PSM_SendRLS_OUT, PSM_SendRLS_OUT structure pointer [Storage Devices], SM_SendRLS_OUT, SM_SendRLS_OUT structure [Storage Devices], _SM_SendRLS_OUT, hbapiwmi/PSM_SendRLS_OUT, hbapiwmi/SM_SendRLS_OUT, storage.sm_sendrls_out, structs-Fibre_8244cf34-aaf9-4c88-aeb7-4adf77d40269.xml"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- hbapiwmi.h
api_name:
- SM_SendRLS_OUT
product:
- Windows
targetos: Windows
req.typenames: SM_SendRLS_OUT, *PSM_SendRLS_OUT
---

# _SM_SendRLS_OUT structure


## -description


The SM_SendRLS_OUT structure is used to receive output parameters from the SM_SendRLS method.


## -struct-fields




### -field HBAStatus

The status of the operation. For a list of allowed values and their descriptions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>.


### -field TotalRespBufferSize

The size, in bytes, of the results common transport (CT) command.


### -field OutRespBufferSize

The size, in bytes, of the data that was actually retrieved.


### -field RespBuffer

The results of the common transport command.


## -remarks



The WMI tool suite generates a declaration of the SM_SendRNID_OUT structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_FabricAndDomainManagementMethod WMI class.



