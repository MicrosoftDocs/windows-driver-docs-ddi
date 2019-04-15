---
UID: NS:hbapiwmi._SendRLS_OUT
title: _SendRLS_OUT (hbapiwmi.h)
description: The SendRLS_OUT structure is used to report the output parameter data of the SendRLS WMI method to the WMI client.
old-location: storage\sendrls_out.htm
tech.root: storage
ms.assetid: 6eccc5e8-7bf6-40bd-abb9-94b6fe4418a0
ms.date: 03/29/2018
ms.keywords: "*PSendRLS_OUT, PSendRLS_OUT, PSendRLS_OUT structure pointer [Storage Devices], SendRLS_OUT, SendRLS_OUT structure [Storage Devices], _SendRLS_OUT, hbapiwmi/PSendRLS_OUT, hbapiwmi/SendRLS_OUT, storage.sendrls_out, structs-Fibre_0d3c1fb1-9827-4962-8aec-97fa6bd84d76.xml"
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
- SendRLS_OUT
product:
- Windows
targetos: Windows
req.typenames: SendRLS_OUT, *PSendRLS_OUT
---

# _SendRLS_OUT structure


## -description


The SendRLS_OUT structure is used to report the output parameter data of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff565442">SendRLS</a> WMI method to the WMI client.


## -struct-fields




### -field HBAStatus

Contains the status of the operation. For a list of allowed values and their descriptions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>. 


### -field TotalRspBufferSize

Contains the size in bytes of the results of the RLS command. 


### -field ActualRspBufferSize

Contains the size in bytes of the data that was actually retrieved. 


### -field RspBuffer

Contains the results of the RLS command. 


## -remarks



The WMI tool suite generates a declaration of the SendRLS_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562506">MSFC_HBAAdapterMethods WMI Class</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff565442">SendRLS</a>
 

 

