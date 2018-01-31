---
UID: NC:dot11wdi.MINIPORT_WDI_FREE_ADAPTER
title: MINIPORT_WDI_FREE_ADAPTER
author: windows-driver-content
description: The MiniportWdiFreeAdapter handler function requests that the IHV driver deletes its software state.
old-location: netvista\miniportwdifreeadapter.htm
old-project: netvista
ms.assetid: 7D88B513-5289-4347-BD25-BDFEB86CE62F
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.miniportwdifreeadapter, MiniportWdiFreeAdapter callback function [Network Drivers Starting with Windows Vista], MiniportWdiFreeAdapter, MINIPORT_WDI_FREE_ADAPTER, MINIPORT_WDI_FREE_ADAPTER, dot11wdi/MiniportWdiFreeAdapter
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	dot11wdi.h
apiname:
-	MiniportWdiFreeAdapter
product: Windows
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---

# MINIPORT_WDI_FREE_ADAPTER callback


## -description


The MiniportWdiFreeAdapter handler function requests that the IHV driver deletes its software state.

This is a WDI miniport handler inside <a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics.md">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_FREE_ADAPTER</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -prototype


````
MINIPORT_WDI_FREE_ADAPTER MiniportWdiFreeAdapter;

VOID MiniportWdiFreeAdapter(
  _In_ NDIS_HANDLE MiniportAdapterContext
)
{ ... }
````


## -parameters




#### - MiniportAdapterContext [in]

The handle to the context area that the miniport driver allocated.


## -returns


This callback function does not return a value.



## -see-also

<a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_driver_wdi_characteristics.md">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_WDI_FREE_ADAPTER callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

