---
UID: NC:dot11wdi.NDIS_WDI_OPEN_ADAPTER_COMPLETE
title: NDIS_WDI_OPEN_ADAPTER_COMPLETE
author: windows-driver-content
description: The NdisWdiOpenAdapterComplete callback function is called by the IHV when an Open Task operation from MiniportWdiOpenAdapter has been successfully started.
old-location: netvista\ndiswdiopenadaptercomplete.htm
old-project: netvista
ms.assetid: FD6FF134-A8D7-433E-9353-88965E67749E
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NDIS_WDI_OPEN_ADAPTER_COMPLETE, NdisWdiOpenAdapterComplete, NdisWdiOpenAdapterComplete callback function [Network Drivers Starting with Windows Vista], dot11wdi/NdisWdiOpenAdapterComplete, netvista.ndiswdiopenadaptercomplete
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
-	NdisWdiOpenAdapterComplete
product: Windows
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---

# NDIS_WDI_OPEN_ADAPTER_COMPLETE callback


## -description


The NdisWdiOpenAdapterComplete callback function is called by the IHV when an Open Task operation from <a href="https://msdn.microsoft.com/C4D09CAD-833A-43A0-AC03-EEDE8270EA12">MiniportWdiOpenAdapter</a> has been successfully started.

This is a control path callback inside <a href="https://msdn.microsoft.com/library/windows/hardware/mt297621">NDIS_WDI_INIT_PARAMETERS</a>.


## -parameters




### -param MiniportAdapterHandle [in]

The miniport handle.


### -param CompletionStatus [in]

The completion status.


## -returns



This callback function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/C4D09CAD-833A-43A0-AC03-EEDE8270EA12">MiniportWdiOpenAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297621">NDIS_WDI_INIT_PARAMETERS</a>
 

 

