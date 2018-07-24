---
UID: NC:dot11wdi.MINIPORT_WDI_RX_RESUME
title: MINIPORT_WDI_RX_RESUME
author: windows-driver-content
description: The MiniportWdiRxResume handler function is issued by the RxMgr after it returns a pause status to a data indication.
old-location: netvista\miniportwdirxresume.htm
tech.root: netvista
ms.assetid: 483C59C3-8F9C-48A5-B5E4-34A60BAE1B1A
ms.author: windowsdriverdev
ms.date: 5/2/2018
ms.keywords: MINIPORT_WDI_RX_RESUME, MINIPORT_WDI_RX_RESUME callback, MiniportWdiRxResume, MiniportWdiRxResume callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiRxResume, netvista.miniportwdirxresume
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
-	MiniportWdiRxResume
product:
- Windows
targetos: Windows
req.typenames: 
---

# MINIPORT_WDI_RX_RESUME callback function


## -description


The 
  MiniportWdiRxResume handler function is issued by the RxMgr after it returns a pause status to a data indication. The RxEngine can  immediately resume creating data indications, either in the same context as the MiniportWdiRxResume or from a different thread.

This is a WDI miniport handler inside <a href="https://msdn.microsoft.com/library/windows/hardware/mt297618">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_RX_RESUME</b> type. For more
   information, see the following Examples section.</div><div> </div>

## -parameters




### -param MiniportTalTxRxContext

TAL device handle returned by the IHV miniport in <a href="https://msdn.microsoft.com/C297D681-D43F-4105-9E08-7FF42807E9A0">MiniportWdiTalTxRxInitialize</a>.


## -returns



This callback function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt297618">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297625">TAL_TXRX_HANDLE</a>



<a href="https://msdn.microsoft.com/EEEA7181-4A24-4F40-8A44-65EC38D1A867">WDI RX path</a>
 

 

