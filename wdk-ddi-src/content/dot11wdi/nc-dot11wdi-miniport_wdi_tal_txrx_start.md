---
UID: NC:dot11wdi.MINIPORT_WDI_TAL_TXRX_START
title: MINIPORT_WDI_TAL_TXRX_START
author: windows-driver-content
description: The MiniportWdiTalTxRxStart handler function provides TXRX configuration parameters to the TAL.
old-location: netvista\miniportwditaltxrxstart.htm
tech.root: netvista
ms.assetid: 6F88F4B1-8D2A-41CC-8D60-C1CF91ED072A
ms.date: 05/02/2018
ms.keywords: MINIPORT_WDI_TAL_TXRX_START, MINIPORT_WDI_TAL_TXRX_START callback, MiniportWdiTalTxRxStart, MiniportWdiTalTxRxStart callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiTalTxRxStart, netvista.miniportwditaltxrxstart
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
-	MiniportWdiTalTxRxStart
product:
- Windows
targetos: Windows
req.typenames: 
---

# MINIPORT_WDI_TAL_TXRX_START callback function


## -description


The 
  MiniportWdiTalTxRxStart handler function provides TXRX configuration parameters to the TAL.   The configuration parameters include the TX/RX capabilities specified by the target device as part of its initialization. It is issued in the context of driver initialization after obtaining device capabilities.

This is a WDI miniport handler inside <a href="https://msdn.microsoft.com/library/windows/hardware/mt297618">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_TAL_TXRX_START</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param MiniportTalTxRxContext [in]

TAL device handle returned by the IHV miniport in <a href="https://msdn.microsoft.com/C297D681-D43F-4105-9E08-7FF42807E9A0">MiniportWdiTalTxRxInitialize</a>.


### -param pWifiTxRxConfiguration [in]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/dn898192">WDI_TXRX_TARGET_CONFIGURATION</a> structure specified by the target device as part of initialization.


### -param pTalTxRxParameters [out]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn897669">TAL_TXRX_PARAMETERS</a> structure that specifies the TAL parameters used by the TxMgr or RxMgr.


## -returns



<div class="alert"><b>Note</b>  Non-<b>NDIS_STATUS_SUCCESS</b> return values indicate a generic failure.</div>
<div> </div>
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
Indicates that the miniport driver successfully started the datapath components.

</td>
</tr>
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt297618">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297625">TAL_TXRX_HANDLE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn897669">TAL_TXRX_PARAMETERS</a>



<a href="https://msdn.microsoft.com/5B40171C-4E5F-4C35-A6E7-1EA5181C02E8">WDI general datapath interfaces</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn898192">WDI_TXRX_TARGET_CONFIGURATION</a>
 

 

