---
UID: NC:dot11wdi.NDIS_WDI_CLOSE_ADAPTER_COMPLETE
title: NDIS_WDI_CLOSE_ADAPTER_COMPLETE
author: windows-driver-content
description: The NdisWdiCloseAdapterComplete callback function is called by the IHV when a Close Task operation from MiniportWdiCloseAdapter has been successfully started.
old-location: netvista\ndiswdicloseadaptercomplete.htm
tech.root: netvista
ms.assetid: 42500F6F-8E97-454F-819F-8EA3785C0D04
ms.date: 05/02/2018
ms.keywords: NDIS_WDI_CLOSE_ADAPTER_COMPLETE, NDIS_WDI_CLOSE_ADAPTER_COMPLETE callback, NdisWdiCloseAdapterComplete, NdisWdiCloseAdapterComplete callback function [Network Drivers Starting with Windows Vista], dot11wdi/NdisWdiCloseAdapterComplete, netvista.ndiswdicloseadaptercomplete
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
-	NdisWdiCloseAdapterComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# NDIS_WDI_CLOSE_ADAPTER_COMPLETE callback function


## -description


The NdisWdiCloseAdapterComplete callback function is called by the IHV when a Close Task operation from <a href="https://msdn.microsoft.com/E6A96765-3D95-431B-B29A-5BD7641325A8">MiniportWdiCloseAdapter</a> has been successfully started.

This is a control path callback inside <a href="https://msdn.microsoft.com/library/windows/hardware/mt297621">NDIS_WDI_INIT_PARAMETERS</a>.


## -parameters




### -param MiniportAdapterHandle [in]

The miniport handle.


### -param CompletionStatus [in]

The completion status.


## -returns



This callback function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/E6A96765-3D95-431B-B29A-5BD7641325A8">MiniportWdiCloseAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297621">NDIS_WDI_INIT_PARAMETERS</a>
 

 

