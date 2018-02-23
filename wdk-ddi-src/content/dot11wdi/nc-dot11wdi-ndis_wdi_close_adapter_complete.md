---
UID: NC:dot11wdi.NDIS_WDI_CLOSE_ADAPTER_COMPLETE
title: NDIS_WDI_CLOSE_ADAPTER_COMPLETE
author: windows-driver-content
description: The NdisWdiCloseAdapterComplete callback function is called by the IHV when a Close Task operation from MiniportWdiCloseAdapter has been successfully started.
old-location: netvista\ndiswdicloseadaptercomplete.htm
old-project: netvista
ms.assetid: 42500F6F-8E97-454F-819F-8EA3785C0D04
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: netvista.ndiswdicloseadaptercomplete, NdisWdiCloseAdapterComplete callback function [Network Drivers Starting with Windows Vista], NdisWdiCloseAdapterComplete, NDIS_WDI_CLOSE_ADAPTER_COMPLETE, NDIS_WDI_CLOSE_ADAPTER_COMPLETE, dot11wdi/NdisWdiCloseAdapterComplete
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
-	NdisWdiCloseAdapterComplete
product: Windows
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---

# NDIS_WDI_CLOSE_ADAPTER_COMPLETE callback


## -description


The NdisWdiCloseAdapterComplete callback function is called by the IHV when a Close Task operation from <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_close_adapter.md">MiniportWdiCloseAdapter</a> has been successfully started.

This is a control path callback inside <a href="..\dot11wdi\ns-dot11wdi-_ndis_wdi_init_parameters.md">NDIS_WDI_INIT_PARAMETERS</a>.


## -prototype


````
NDIS_WDI_CLOSE_ADAPTER_COMPLETE NdisWdiCloseAdapterComplete;

VOID NdisWdiCloseAdapterComplete(
  _In_ NDIS_HANDLE MiniportAdapterHandle,
  _In_ NDIS_STATUS CompletionStatus
)
{ ... }
````


## -parameters




### -param MiniportAdapterHandle [in]

The miniport handle.


### -param CompletionStatus [in]

The completion status.


## -returns



This callback function does not return a value.




## -see-also

<a href="..\dot11wdi\ns-dot11wdi-_ndis_wdi_init_parameters.md">NDIS_WDI_INIT_PARAMETERS</a>



<a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_close_adapter.md">MiniportWdiCloseAdapter</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WDI_CLOSE_ADAPTER_COMPLETE callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

