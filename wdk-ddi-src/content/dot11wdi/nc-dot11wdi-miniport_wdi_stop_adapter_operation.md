---
UID: NC:dot11wdi.MINIPORT_WDI_STOP_ADAPTER_OPERATION
title: MINIPORT_WDI_STOP_ADAPTER_OPERATION
author: windows-driver-content
description: The MiniportWdiStopAdapterOperation handler function can be used by the IHV driver to undo the operations performed in MiniportWdiStartAdapterOperation.
old-location: netvista\miniportwdistopoperation.htm
old-project: netvista
ms.assetid: 19BDA96D-DA25-4555-B836-78F4695257B0
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "(*MINIPORT_WDI_STOP_OPERATION_HANDLER), (*MINIPORT_WDI_STOP_OPERATION_HANDLER) callback function [Network Drivers Starting with Windows Vista], MINIPORT_WDI_STOP_ADAPTER_OPERATION, MiniportWdiStopAdapterOperation, MiniportWdiStopAdapterOperation callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiStopAdapterOperation, netvista.miniportwdistopoperation"
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
-	(*MINIPORT_WDI_STOP_OPERATION_HANDLER)
product: Windows
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---

# MINIPORT_WDI_STOP_ADAPTER_OPERATION callback


## -description


The MiniportWdiStopAdapterOperation handler function can be used by the IHV driver to undo the operations performed in <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_start_adapter_operation.md">MiniportWdiStartAdapterOperation</a>.

This is an optional WDI miniport handler inside <a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics.md">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_STOP_ADAPTER_OPERATION</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -prototype


````
MINIPORT_WDI_STOP_ADAPTER_OPERATION MiniportWdiStopAdapterOperation;

VOID MiniportWdiStopAdapterOperation(
  _In_ NDIS_HANDLE MiniportAdapterContext
)
{ ... }

typedef MINIPORT_WDI_STOP_ADAPTER_OPERATION (*MINIPORT_WDI_STOP_OPERATION_HANDLER);
````


## -parameters




### -param MiniportAdapterContext [in]

The handle to the context area that the miniport driver allocated.


## -returns



This callback function does not return a value.




## -see-also

<a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_start_adapter_operation.md">MiniportWdiStartOperation</a>



<a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics.md">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>



 

 


