---
UID: NC:dot11wdi.MINIPORT_WDI_STOP_ADAPTER_OPERATION
title: MINIPORT_WDI_STOP_ADAPTER_OPERATION (dot11wdi.h)
description: The MiniportWdiStopAdapterOperation handler function can be used by the IHV driver to undo the operations performed in MiniportWdiStartAdapterOperation.
old-location: netvista\miniportwdistopoperation.htm
tech.root: netvista
ms.assetid: 19BDA96D-DA25-4555-B836-78F4695257B0
ms.date: 05/02/2018
keywords: ["MINIPORT_WDI_STOP_ADAPTER_OPERATION callback function"]
ms.keywords: "(*MINIPORT_WDI_STOP_OPERATION_HANDLER), (*MINIPORT_WDI_STOP_OPERATION_HANDLER) callback function [Network Drivers Starting with Windows Vista], MINIPORT_WDI_STOP_ADAPTER_OPERATION, MINIPORT_WDI_STOP_ADAPTER_OPERATION callback, MiniportWdiStopAdapterOperation, MiniportWdiStopAdapterOperation callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiStopAdapterOperation, netvista.miniportwdistopoperation"
f1_keywords:
 - "dot11wdi/(*MINIPORT_WDI_STOP_OPERATION_HANDLER)"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- dot11wdi.h
api_name:
- (*MINIPORT_WDI_STOP_OPERATION_HANDLER)
product:
- Windows
targetos: Windows
req.typenames: 
---

# MINIPORT_WDI_STOP_ADAPTER_OPERATION callback function


## -description


The MiniportWdiStopAdapterOperation handler function can be used by the IHV driver to undo the operations performed in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_start_adapter_operation">MiniportWdiStartAdapterOperation</a>.

This is an optional WDI miniport handler inside <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_STOP_ADAPTER_OPERATION</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param MiniportAdapterContext [in]

The handle to the context area that the miniport driver allocated.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_start_adapter_operation">MiniportWdiStartOperation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>
 

 

