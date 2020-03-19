---
UID: NC:dot11wdi.MINIPORT_WDI_FREE_ADAPTER
title: MINIPORT_WDI_FREE_ADAPTER (dot11wdi.h)
description: The MiniportWdiFreeAdapter handler function requests that the IHV driver deletes its software state.
old-location: netvista\miniportwdifreeadapter.htm
tech.root: netvista
ms.assetid: 7D88B513-5289-4347-BD25-BDFEB86CE62F
ms.date: 05/02/2018
keywords: ["MINIPORT_WDI_FREE_ADAPTER callback function"]
ms.keywords: MINIPORT_WDI_FREE_ADAPTER, MINIPORT_WDI_FREE_ADAPTER callback, MiniportWdiFreeAdapter, MiniportWdiFreeAdapter callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiFreeAdapter, netvista.miniportwdifreeadapter
f1_keywords:
 - "dot11wdi/MiniportWdiFreeAdapter"
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
- MiniportWdiFreeAdapter
product:
- Windows
targetos: Windows
req.typenames: 
---

# MINIPORT_WDI_FREE_ADAPTER callback function


## -description


The MiniportWdiFreeAdapter handler function requests that the IHV driver deletes its software state.

This is a WDI miniport handler inside <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_FREE_ADAPTER</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param MiniportAdapterContext [in]

The handle to the context area that the miniport driver allocated.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>
 

 

