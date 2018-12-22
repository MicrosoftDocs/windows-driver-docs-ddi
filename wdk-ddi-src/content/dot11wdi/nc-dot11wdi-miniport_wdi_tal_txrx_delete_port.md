---
UID: NC:dot11wdi.MINIPORT_WDI_TAL_TXRX_DELETE_PORT
title: MINIPORT_WDI_TAL_TXRX_DELETE_PORT
description: The MiniportWdiTalTxRxDeletePort handler function notifies the datapath components of the deletion of a virtual port.
old-location: netvista\miniportwditaltxrxdeleteport.htm
tech.root: netvista
ms.assetid: 3DB6AC6F-2A6F-43E1-B98D-B4E5C8A87845
ms.date: 05/02/2018
ms.keywords: MINIPORT_WDI_TAL_TXRX_DELETE_PORT, MINIPORT_WDI_TAL_TXRX_DELETE_PORT callback, MiniportWdiTalTxRxDeletePort, MiniportWdiTalTxRxDeletePort callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiTalTxRxDeletePort, netvista.miniportwditaltxrxdeleteport
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
-	MiniportWdiTalTxRxDeletePort
product:
- Windows
targetos: Windows
req.typenames: 
---

# MINIPORT_WDI_TAL_TXRX_DELETE_PORT callback function


## -description


The 
  MiniportWdiTalTxRxDeletePort handler  function notifies the datapath components of the deletion of a virtual port. It is invoked after the completion of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn925950">OID_WDI_TASK_DELETE_PORT</a> command. The functional components RXEngine and TxEngine have already stopped operations associated  with this port and any pending data frames completed/returned.

This is a WDI miniport handler inside <a href="https://msdn.microsoft.com/library/windows/hardware/mt297618">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_TAL_TXRX_DELETE_PORT</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param MiniportTalTxRxContext [in]

TAL device handle returned by the IHV miniport in <a href="https://msdn.microsoft.com/C297D681-D43F-4105-9E08-7FF42807E9A0">MiniportWdiTalTxRxInitialize</a>.


### -param PortId [in]

Port ID that specifies the deleted port.


## -returns



This callback function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt297618">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn925950">OID_WDI_TASK_DELETE_PORT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297625">TAL_TXRX_HANDLE</a>



<a href="https://msdn.microsoft.com/5B40171C-4E5F-4C35-A6E7-1EA5181C02E8">WDI general datapath interfaces</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt269099">WDI_PORT_ID</a>
 

 

