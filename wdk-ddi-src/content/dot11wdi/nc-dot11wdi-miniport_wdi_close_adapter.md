---
UID: NC:dot11wdi.MINIPORT_WDI_CLOSE_ADAPTER
title: MINIPORT_WDI_CLOSE_ADAPTER
author: windows-driver-content
description: The MiniportWdiCloseAdapter handler function is used by the Microsoft component to initiate the Close Task operation on the IHV driver.
old-location: netvista\miniportwdicloseadapter.htm
old-project: netvista
ms.assetid: E6A96765-3D95-431B-B29A-5BD7641325A8
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.miniportwdicloseadapter, MiniportWdiCloseAdapter callback function [Network Drivers Starting with Windows Vista], MiniportWdiCloseAdapter, MINIPORT_WDI_CLOSE_ADAPTER, MINIPORT_WDI_CLOSE_ADAPTER, dot11wdi/MiniportWdiCloseAdapter
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	dot11wdi.h
apiname:
-	MiniportWdiCloseAdapter
product: Windows
targetos: Windows
req.typenames: "*PSYNTH_STATS, SYNTH_STATS"
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

<a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_close_adapter_complete.md">CloseAdapterComplete</a>



<a href="..\dot11wdi\ns-dot11wdi-_ndis_wdi_init_parameters.md">NDIS_WDI_INIT_PARAMETERS</a>



<a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_allocate_adapter.md">MiniportWdiAllocateAdapter</a>



<a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics.md">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_WDI_CLOSE_ADAPTER callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

