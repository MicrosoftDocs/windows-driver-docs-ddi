---
UID: NC:dot11wdi.MINIPORT_WDI_START_ADAPTER_OPERATION
title: MINIPORT_WDI_START_ADAPTER_OPERATION
author: windows-driver-content
description: The MiniportWdiStartAdapterOperation handler function can be used by the IHV driver to perform any additional MiniportInitializeEx tasks.
old-location: netvista\miniportwdistartoperation.htm
old-project: netvista
ms.assetid: B74F44E4-AD7A-46EE-81B0-E2BD2FB79A5B
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "(*MINIPORT_WDI_START_OPERATION_HANDLER), (*MINIPORT_WDI_START_OPERATION_HANDLER) callback function [Network Drivers Starting with Windows Vista], MINIPORT_WDI_START_ADAPTER_OPERATION, MiniportWdiStartAdapterOperation, MiniportWdiStartAdapterOperation callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiStartAdapterOperation, netvista.miniportwdistartoperation"
ms.prod: windows-hardware
ms.technology: windows-devices
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
product: Windows
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---

# MINIPORT_WDI_START_ADAPTER_OPERATION callback


## -description


The MiniportWdiStartAdapterOperation handler function can be used by the IHV driver to perform any additional <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> tasks. The IHV miniport can also use it as a hint that the Microsoft component has finished initializing the miniport and the miniport can start any needed background activities.

This is an optional WDI miniport handler inside <a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics.md">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_START_ADAPTER_OPERATION</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -prototype


````
MINIPORT_WDI_START_ADAPTER_OPERATION MiniportWdiStartAdapterOperation;

NDIS_STATUS MiniportWdiStartAdapterOperation(
  _In_ NDIS_HANDLE MiniportAdapterContext
)
{ ... }

typedef MINIPORT_WDI_START_ADAPTER_OPERATION (*MINIPORT_WDI_START_OPERATION_HANDLER);
````


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

<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



<a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics.md">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>



 

 


