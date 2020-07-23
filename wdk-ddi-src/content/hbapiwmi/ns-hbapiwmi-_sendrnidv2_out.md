---
UID: NS:hbapiwmi._SendRNIDV2_OUT
title: _SendRNIDV2_OUT (hbapiwmi.h)
description: The SendRNIDV2_OUT structure is used to report the output parameter data of the SendRNIDV2 WMI method to the WMI client.
old-location: storage\sendrnidv2_out.htm
tech.root: storage
ms.assetid: 2d8f1b49-5add-4dd9-998f-d0c1e79f3e7d
ms.date: 03/29/2018
keywords: ["_SendRNIDV2_OUT structure"]
ms.keywords: "*PSendRNIDV2_OUT, PSendRNIDV2_OUT, PSendRNIDV2_OUT structure pointer [Storage Devices], SendRNIDV2_OUT, SendRNIDV2_OUT structure [Storage Devices], _SendRNIDV2_OUT, hbapiwmi/PSendRNIDV2_OUT, hbapiwmi/SendRNIDV2_OUT, storage.sendrnidv2_out, structs-Fibre_78855dda-228d-432f-8189-8be83df6d2ea.xml"
f1_keywords:
 - "hbapiwmi/SendRNIDV2_OUT"
 - "SendRNIDV2_OUT"
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
- SendRNIDV2_OUT
targetos: Windows
req.typenames: SendRNIDV2_OUT, *PSendRNIDV2_OUT
---

# _SendRNIDV2_OUT structure


## -description


The SendRNIDV2_OUT structure is used to report the output parameter data of the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/sendrnidv2">SendRNIDV2</a> WMI method to the WMI client.


## -struct-fields




### -field HBAStatus

Contains the status of the operation. For a list of allowed values and their descriptions, see <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/hba-status">HBA_STATUS</a>. 


### -field TotalRspBufferSize

Contains the size in bytes of the results of the version 2 request node identification data (RNIDV2) command. 


### -field ActualRspBufferSize

Contains the size in bytes of the data that was actually retrieved. 


### -field RspBuffer

Contains the results of the RNIDV2 command. 


## -remarks



The WMI tool suite generates a declaration of the SendRNIDV2_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/msfc-hbaadaptermethods-wmi-class">MSFC_HBAAdapterMethods WMI Class</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/sendrnidv2">SendRNIDV2</a>
 

 

