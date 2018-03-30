---
UID: NC:dot11wdi.MINIPORT_WDI_STOP_ADAPTER_OPERATION
title: MINIPORT_WDI_STOP_ADAPTER_OPERATION
author: windows-driver-content
description: The MiniportWdiStopAdapterOperation handler function can be used by the IHV driver to undo the operations performed in MiniportWdiStartAdapterOperation.
old-location: netvista\miniportwdistopoperation.htm
old-project: netvista
ms.assetid: 19BDA96D-DA25-4555-B836-78F4695257B0
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "(*MINIPORT_WDI_STOP_OPERATION_HANDLER), (*MINIPORT_WDI_STOP_OPERATION_HANDLER) callback function [Network Drivers Starting with Windows Vista], MINIPORT_WDI_STOP_ADAPTER_OPERATION, MiniportWdiStopAdapterOperation, MiniportWdiStopAdapterOperation callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiStopAdapterOperation, netvista.miniportwdistopoperation"
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
-	(*MINIPORT_WDI_STOP_OPERATION_HANDLER)
product: Windows
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---

# MINIPORT_WDI_STOP_ADAPTER_OPERATION callback


## -description


The MiniportWdiStopAdapterOperation handler function can be used by the IHV driver to undo the operations performed in <a href="https://msdn.microsoft.com/B74F44E4-AD7A-46EE-81B0-E2BD2FB79A5B">MiniportWdiStartAdapterOperation</a>.

This is an optional WDI miniport handler inside <a href="https://msdn.microsoft.com/library/windows/hardware/mt297617">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_STOP_ADAPTER_OPERATION</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param MiniportAdapterContext [in]

The handle to the context area that the miniport driver allocated.


## -returns



This callback function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/B74F44E4-AD7A-46EE-81B0-E2BD2FB79A5B">MiniportWdiStartOperation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297617">NDIS_MINIPORT_DRIVER_WDI_CHARACTERISTICS</a>
 

 

<<<<<<< HEAD
=======
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_WDI_STOP_ADAPTER_OPERATION callback function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

>>>>>>> parent of 2d896a8e266... Added changes
