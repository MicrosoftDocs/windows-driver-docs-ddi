---
UID: NC:dot11wdi.MINIPORT_WDI_TAL_TXRX_INITIALIZE
title: MINIPORT_WDI_TAL_TXRX_INITIALIZE
description: The MiniportWdiTalTxRxInitialize handler function initializes data structures in the TAL and exchanges datapath component handles between the UE and TAL.
old-location: netvista\miniportwditaltxrxinitialize.htm
tech.root: netvista
ms.assetid: C297D681-D43F-4105-9E08-7FF42807E9A0
ms.date: 05/02/2018
ms.keywords: MINIPORT_WDI_TAL_TXRX_INITIALIZE, MINIPORT_WDI_TAL_TXRX_INITIALIZE callback, MiniportWdiTalTxRxInitialize, MiniportWdiTalTxRxInitialize callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiTalTxRxInitialize, netvista.miniportwditaltxrxinitialize
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
-	MiniportWdiTalTxRxInitialize
product:
- Windows
targetos: Windows
req.typenames: 
---

# MINIPORT_WDI_TAL_TXRX_INITIALIZE callback function


## -description


The 
  MiniportWdiTalTxRxInitialize handler function initializes data structures in the TAL and exchanges datapath component handles between the UE and TAL. This is issued in the context of the driver initialization, and is issued prior to querying the firmware for the device capabilities.

This is a WDI miniport handler inside <a href="https://msdn.microsoft.com/library/windows/hardware/mt297617">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_TAL_TXRX_INITIALIZE</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param MiniportAdapterContext [in]

Handle for the IHV miniport context.


### -param NdisMiniportDataPathHandle [in]

Handle for the IHV miniport to use in datapath indications.


### -param NdisWdiDataPathApi [in]

Pointer to the WDI data API function table.


### -param pMiniportTalTxRxContext [out]

The TAL device handle is a control path handle for the device (for example, MiniportContext). It is associated with the MiniportHandle, which used as context for NDIS API calls.


### -param pMiniportDataHandlers [in, out]

The UE initializes the NDIS Header field so the LE can determine the revision and size that is safe to initialize according to traditional NDIS versioning rules.  The LE is responsible for updating the Header with the revision and size that the LE actually implements and supports before returning.


### -param *pMiniportWdiFrameMetadataExtraSpace [out]

The LE sets the value pointed to by this parameter to the amount of space that WDI should reserve after the <a href="https://msdn.microsoft.com/library/windows/hardware/dn897827">WDI_FRAME_METADATA</a> for the LE to use.


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
Indicates that the miniport driver successfully exchanged datapath component handles.

</td>
</tr>
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt297617">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297625">TAL_TXRX_HANDLE</a>



<a href="https://msdn.microsoft.com/5B40171C-4E5F-4C35-A6E7-1EA5181C02E8">WDI general datapath interfaces</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn897827">WDI_FRAME_METADATA</a>
 

 

