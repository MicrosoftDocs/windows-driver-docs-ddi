---
UID: NC:dot11wdi.MINIPORT_WDI_START_ADAPTER_OPERATION
title: MINIPORT_WDI_START_ADAPTER_OPERATION (dot11wdi.h)
description: The MiniportWdiStartAdapterOperation handler function can be used by the IHV driver to perform any additional MiniportInitializeEx tasks.
old-location: netvista\miniportwdistartoperation.htm
tech.root: netvista
ms.assetid: B74F44E4-AD7A-46EE-81B0-E2BD2FB79A5B
ms.date: 05/02/2018
ms.keywords: "(*MINIPORT_WDI_START_OPERATION_HANDLER), (*MINIPORT_WDI_START_OPERATION_HANDLER) callback function [Network Drivers Starting with Windows Vista], MINIPORT_WDI_START_ADAPTER_OPERATION, MINIPORT_WDI_START_ADAPTER_OPERATION callback, MiniportWdiStartAdapterOperation, MiniportWdiStartAdapterOperation callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiStartAdapterOperation, netvista.miniportwdistartoperation"
ms.topic: callback
req.header: dot11wdi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	UserDefined
api_location:
-	dot11wdi.h
api_name:
-	(*MINIPORT_WDI_START_OPERATION_HANDLER)
product:
- Windows
targetos: Windows
req.typenames: 
---

# MINIPORT_WDI_START_ADAPTER_OPERATION callback function


## -description


The MiniportWdiStartAdapterOperation handler function can be used by the IHV driver to perform any additional <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a> tasks. The IHV miniport can also use it as a hint that the Microsoft component has finished initializing the miniport and the miniport can start any needed background activities.

This is an optional WDI miniport handler inside <a href="https://msdn.microsoft.com/library/windows/hardware/mt297617">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_START_ADAPTER_OPERATION</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param MiniportAdapterContext [in]

The handle to the context area that the miniport driver allocated.


## -returns



MiniportWdiStartAdapterOperation can return any of the following return values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
MiniportWdiStartAdapterOperation successfully completed. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other NDIS_STATUS codes</b></dt>
</dl>
</td>
<td width="60%">
An appropriate NDIS_STATUS code in the case of a failure.

</td>
</tr>
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297617">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>
 

 

