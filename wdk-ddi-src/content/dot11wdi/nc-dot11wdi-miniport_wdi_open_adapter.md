---
UID: NC:dot11wdi.MINIPORT_WDI_OPEN_ADAPTER
title: MINIPORT_WDI_OPEN_ADAPTER
author: windows-driver-content
description: The MiniportWdiOpenAdapter handler function is used by the Microsoft component to initiate the Open Task operation on the IHV driver.
old-location: netvista\miniportwdiopenadapter.htm
old-project: netvista
ms.assetid: C4D09CAD-833A-43A0-AC03-EEDE8270EA12
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: MINIPORT_WDI_OPEN_ADAPTER, MINIPORT_WDI_OPEN_ADAPTER callback, MiniportWdiOpenAdapter, MiniportWdiOpenAdapter callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiOpenAdapter, netvista.miniportwdiopenadapter
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
-	MiniportWdiOpenAdapter
product: Windows
targetos: Windows
req.typenames: 
---

# MINIPORT_WDI_OPEN_ADAPTER callback function


## -description


The MiniportWdiOpenAdapter handler function is used by the Microsoft component to initiate the Open Task operation on the IHV driver.

This is a WDI miniport handler inside <a href="https://msdn.microsoft.com/library/windows/hardware/mt297617">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>.

This call must complete quickly. If the open operation is successfully started, the IHV must return <b>NDIS_STATUS_SUCCESS</b> and call the <a href="https://msdn.microsoft.com/FD6FF134-A8D7-433E-9353-88965E67749E">OpenAdapterComplete</a> handler that was passed into <a href="https://msdn.microsoft.com/4CBC7230-6480-40C9-90B7-A286FCEB1FA8">MiniportWdiAllocateAdapter</a> with the <a href="https://msdn.microsoft.com/library/windows/hardware/mt297621">NDIS_WDI_INIT_PARAMETERS</a> structure.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_OPEN_ADAPTER</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param MiniportAdapterContext [in]

The handle to the context area that the miniport driver allocated.


### -param MiniportInitParameters [in]

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff565972">NDIS_MINIPORT_INIT_PARAMETERS</a> structure that defines the initialization parameters for the miniport adapter.


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




<a href="https://msdn.microsoft.com/4CBC7230-6480-40C9-90B7-A286FCEB1FA8">MiniportWdiAllocateAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297617">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565972">NDIS_MINIPORT_INIT_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297621">NDIS_WDI_INIT_PARAMETERS</a>



<a href="https://msdn.microsoft.com/FD6FF134-A8D7-433E-9353-88965E67749E">OpenAdapterComplete</a>
 

 

