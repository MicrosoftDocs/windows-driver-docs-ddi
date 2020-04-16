---
UID: NC:dot11wdi.MINIPORT_WDI_RX_RESUME
title: MINIPORT_WDI_RX_RESUME (dot11wdi.h)
description: The MiniportWdiRxResume handler function is issued by the RxMgr after it returns a pause status to a data indication.
old-location: netvista\miniportwdirxresume.htm
tech.root: netvista
ms.assetid: 483C59C3-8F9C-48A5-B5E4-34A60BAE1B1A
ms.date: 05/02/2018
keywords: ["MINIPORT_WDI_RX_RESUME callback function"]
ms.keywords: MINIPORT_WDI_RX_RESUME, MINIPORT_WDI_RX_RESUME callback, MiniportWdiRxResume, MiniportWdiRxResume callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiRxResume, netvista.miniportwdirxresume
f1_keywords:
 - "dot11wdi/MiniportWdiRxResume"
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
- MiniportWdiRxResume
product:
- Windows
targetos: Windows
req.typenames: 
---

# MINIPORT_WDI_RX_RESUME callback function


## -description


The 
  MiniportWdiRxResume handler function is issued by the RxMgr after it returns a pause status to a data indication. The RxEngine can  immediately resume creating data indications, either in the same context as the MiniportWdiRxResume or from a different thread.

This is a WDI miniport handler inside <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_wdi_data_handlers">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_RX_RESUME</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param MiniportTalTxRxContext

TAL device handle returned by the IHV miniport in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_tal_txrx_initialize">MiniportWdiTalTxRxInitialize</a>.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_wdi_data_handlers">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/tal-txrx-handle">TAL_TXRX_HANDLE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/network/wdi-rx-path">WDI RX path</a>
 

 

