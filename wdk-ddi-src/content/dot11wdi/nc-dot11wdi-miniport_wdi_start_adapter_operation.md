---
UID: NC:dot11wdi.MINIPORT_WDI_START_ADAPTER_OPERATION
title: MINIPORT_WDI_START_ADAPTER_OPERATION
author: windows-driver-content
description: The MiniportWdiStartAdapterOperation handler function can be used by the IHV driver to perform any additional MiniportInitializeEx tasks.
old-location: netvista\miniportwdistartoperation.htm
old-project: netvista
ms.assetid: B74F44E4-AD7A-46EE-81B0-E2BD2FB79A5B
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: netvista.miniportwdistartoperation, MiniportWdiStartAdapterOperation callback function [Network Drivers Starting with Windows Vista], MiniportWdiStartAdapterOperation, MINIPORT_WDI_START_ADAPTER_OPERATION, MINIPORT_WDI_START_ADAPTER_OPERATION, dot11wdi/MiniportWdiStartAdapterOperation, (*MINIPORT_WDI_START_OPERATION_HANDLER) callback function [Network Drivers Starting with Windows Vista], (*MINIPORT_WDI_START_OPERATION_HANDLER)
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
-	(*MINIPORT_WDI_START_OPERATION_HANDLER)
product: Windows
targetos: Windows
req.typenames: "*PSYNTH_STATS, SYNTH_STATS"
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



<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_WDI_START_ADAPTER_OPERATION callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

