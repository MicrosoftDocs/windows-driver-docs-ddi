---
UID: NC:dot11wdi.MINIPORT_WDI_ALLOCATE_ADAPTER
title: MINIPORT_WDI_ALLOCATE_ADAPTER
author: windows-driver-content
description: The MiniportWdiAllocateAdapter handler function allocates a WDI miniport adapter.
old-location: netvista\miniportwdiallocateadapter.htm
tech.root: netvista
ms.assetid: 4CBC7230-6480-40C9-90B7-A286FCEB1FA8
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: MINIPORT_WDI_ALLOCATE_ADAPTER, MINIPORT_WDI_ALLOCATE_ADAPTER callback, MiniportWdiAllocateAdapter, MiniportWdiAllocateAdapter callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiAllocateAdapter, netvista.miniportwdiallocateadapter
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
-	MiniportWdiAllocateAdapter
product:
- Windows
targetos: Windows
req.typenames: 
---

# MINIPORT_WDI_ALLOCATE_ADAPTER callback function


## -description


The MiniportWdiAllocateAdapter handler function allocates a WDI miniport adapter.

This is a WDI miniport handler inside <a href="https://msdn.microsoft.com/library/windows/hardware/mt297617">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_ALLOCATE_ADAPTER</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param NdisMiniportHandle [in]

The NDIS-supplied handle that identifies the miniport adapter.


### -param MiniportDriverContext [in]

The handle to a driver-allocated context area where the driver maintains state and configuration information. The miniport driver passed this context area to the <a href="https://msdn.microsoft.com/library/windows/hardware/mt297596">NdisMRegisterWdiMiniportDriver</a> function.




### -param MiniportInitParameters [in]

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff565972">NDIS_MINIPORT_INIT_PARAMETERS</a> structure that defines the initialization parameters for the miniport adapter.


### -param NdisWdiInitParameters [in]

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/mt297621">NDIS_WDI_INIT_PARAMETERS</a> structure that defines the WDI initialization parameters for the miniport adapter.


### -param RegistrationAttributes [in, out]

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff565934">NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES</a> structure that defines registration attributes that are associated with the miniport adapter.


## -returns




            MiniportWdiAllocateAdapter can return any of the following return values.

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
MiniportWdiAllocateAdapter successfully completed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
MiniportWdiAllocateAdapter could not allocate the necessary resources.

</td>
</tr>
</table>
 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff565934">NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297617">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565972">NDIS_MINIPORT_INIT_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297621">NDIS_WDI_INIT_PARAMETERS</a>
 

 

