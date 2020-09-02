---
UID: NC:dot11wdi.MINIPORT_WDI_OPEN_ADAPTER
title: MINIPORT_WDI_OPEN_ADAPTER (dot11wdi.h)
description: The MiniportWdiOpenAdapter handler function is used by the Microsoft component to initiate the Open Task operation on the IHV driver.
old-location: netvista\miniportwdiopenadapter.htm
tech.root: netvista
ms.assetid: C4D09CAD-833A-43A0-AC03-EEDE8270EA12
ms.date: 05/02/2018
keywords: ["MINIPORT_WDI_OPEN_ADAPTER callback function"]
ms.keywords: MINIPORT_WDI_OPEN_ADAPTER, MINIPORT_WDI_OPEN_ADAPTER callback, MiniportWdiOpenAdapter, MiniportWdiOpenAdapter callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiOpenAdapter, netvista.miniportwdiopenadapter
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
targetos: Windows
req.typenames: 
f1_keywords:
 - MINIPORT_WDI_OPEN_ADAPTER
 - dot11wdi/MINIPORT_WDI_OPEN_ADAPTER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dot11wdi.h
api_name:
 - MiniportWdiOpenAdapter
---

# MINIPORT_WDI_OPEN_ADAPTER callback function


## -description

The MiniportWdiOpenAdapter handler function is used by the Microsoft component to initiate the Open Task operation on the IHV driver.

This is a WDI miniport handler inside <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>.

This call must complete quickly. If the open operation is successfully started, the IHV must return <b>NDIS_STATUS_SUCCESS</b> and call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_open_adapter_complete">OpenAdapterComplete</a> handler that was passed into <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_allocate_adapter">MiniportWdiAllocateAdapter</a> with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_wdi_init_parameters">NDIS_WDI_INIT_PARAMETERS</a> structure.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_OPEN_ADAPTER</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters

### -param MiniportAdapterContext 

[in]
The handle to the context area that the miniport driver allocated.

### -param MiniportInitParameters 

[in]
A pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_init_parameters">NDIS_MINIPORT_INIT_PARAMETERS</a> structure that defines the initialization parameters for the miniport adapter.

## -returns

MiniportWdiOpenAdapter can return any of the following return values.

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
MiniportWdiOpenAdapter successfully completed.

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

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_allocate_adapter">MiniportWdiAllocateAdapter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_miniport_init_parameters">NDIS_MINIPORT_INIT_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_wdi_init_parameters">NDIS_WDI_INIT_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_open_adapter_complete">OpenAdapterComplete</a>

