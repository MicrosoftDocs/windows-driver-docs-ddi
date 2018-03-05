---
UID: NS:hbapiwmi._SM_GetLUNStatistics_OUT
title: "_SM_GetLUNStatistics_OUT"
author: windows-driver-content
description: The SM_GetLUNStatistics_OUT structure is used to receive output parameters from the SM_GetLUNStatistics_OUT method.
old-location: storage\sm_getlunstatistics_out.htm
old-project: storage
ms.assetid: 5b7e4eb2-d6e9-49c9-b84f-72dd4198c0ce
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PSM_GetLUNStatistics_OUT, PSM_GetLUNStatistics_OUT, PSM_GetLUNStatistics_OUT structure pointer [Storage Devices], SM_GetLUNStatistics_OUT, SM_GetLUNStatistics_OUT structure [Storage Devices], _SM_GetLUNStatistics_OUT, hbapiwmi/PSM_GetLUNStatistics_OUT, hbapiwmi/SM_GetLUNStatistics_OUT, storage.sm_getlunstatistics_out, structs-Fibre_3f322627-9c44-4675-9166-32860aa954a3.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	hbapiwmi.h
api_name:
-	SM_GetLUNStatistics_OUT
product: Windows
targetos: Windows
req.typenames: SM_GetLUNStatistics_OUT, *PSM_GetLUNStatistics_OUT
---

# _SM_GetLUNStatistics_OUT structure


## -description


The SM_GetLUNStatistics_OUT structure is used to receive output parameters from the SM_GetLUNStatistics_OUT method.


## -syntax


````
typedef struct _SM_GetLUNStatistics_OUT {
  ULONG                       HBAStatus;
  MS_SMHBA_PROTOCOLSTATISTICS ProtocolStatistics;
} SM_GetLUNStatistics_OUT, *PSM_GetLUNStatistics_OUT;
````


## -struct-fields




### -field HBAStatus

The status of the operation. For a list of allowed values and their descriptions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>.


### -field ProtocolStatistics

A structure of type <a href="..\hbapiwmi\ns-hbapiwmi-_ms_smhba_protocolstatistics.md">MS_SMHBA_PROTOCOLSTATISTICS</a> that is used to report protocol traffic statistics on a port.


## -remarks



The WMI tool suite generates a declaration of the SM_GetLUNStatistics_OUT structure in <i>Hbapiwmi.h</i> when it compiles the MS_SM_TargetInformationMethods WMI class.



