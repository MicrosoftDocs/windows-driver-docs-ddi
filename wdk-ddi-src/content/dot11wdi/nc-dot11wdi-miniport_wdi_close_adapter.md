---
UID: NC:dot11wdi.MINIPORT_WDI_CLOSE_ADAPTER
title: MINIPORT_WDI_CLOSE_ADAPTER
author: windows-driver-content
description: The MiniportWdiCloseAdapter handler function is used by the Microsoft component to initiate the Close Task operation on the IHV driver.
old-location: netvista\miniportwdicloseadapter.htm
old-project: netvista
ms.assetid: E6A96765-3D95-431B-B29A-5BD7641325A8
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: MINIPORT_WDI_CLOSE_ADAPTER, MiniportWdiCloseAdapter, MiniportWdiCloseAdapter callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiCloseAdapter, netvista.miniportwdicloseadapter
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
-	MiniportWdiCloseAdapter
product: Windows
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---

# MINIPORT_WDI_CLOSE_ADAPTER callback


## -description


The MiniportWdiCloseAdapter handler function is used by the Microsoft component to initiate the Close Task operation on the IHV driver.

This is a WDI miniport handler inside <a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics.md">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>.

This call must complete quickly. If the close operation is successfully started, the IHV must return NDIS_STATUS_SUCCESS and call the WDI <a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_close_adapter_complete.md">CloseAdapterComplete</a> handler that was passed into <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_allocate_adapter.md">MiniportWdiAllocateAdapter</a> with the <a href="..\dot11wdi\ns-dot11wdi-_ndis_wdi_init_parameters.md">NDIS_WDI_INIT_PARAMETERS</a> structure.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_CLOSE_ADAPTER</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -prototype


````
MINIPORT_WDI_CLOSE_ADAPTER MiniportWdiCloseAdapter;

NDIS_STATUS MiniportWdiCloseAdapter(
  _In_ NDIS_HANDLE MiniportAdapterContext
)
{ ... }
````


## -parameters




### -param MiniportAdapterContext [in]

The handle to the context area that the miniport driver allocated.


## -returns




            MiniportWdiCloseAdapter can return any of the following return values.

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
MiniportWdiCloseAdapter successfully completed.

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

<a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_allocate_adapter.md">MiniportWdiAllocateAdapter</a>



<a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_close_adapter_complete.md">CloseAdapterComplete</a>



<a href="..\dot11wdi\ns-dot11wdi-_ndis_wdi_init_parameters.md">NDIS_WDI_INIT_PARAMETERS</a>



<a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics.md">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>



 

 


