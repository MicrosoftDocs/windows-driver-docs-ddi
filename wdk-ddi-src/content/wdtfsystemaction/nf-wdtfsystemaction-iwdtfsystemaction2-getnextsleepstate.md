---
UID: NF:wdtfsystemaction.IWDTFSystemAction2.GetNextSleepState
title: IWDTFSystemAction2::GetNextSleepState method
author: windows-driver-content
description: Returns the next supported sleep state.
old-location: dtf\iwdtfsystemaction2_getnextsleepstate.htm
old-project: dtf
ms.assetid: B90D7C3D-0370-48A1-90DC-FC14477DA835
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: GetNextSleepState method [Windows Device Testing Framework], GetNextSleepState method [Windows Device Testing Framework], IWDTFSystemAction2 interface, GetNextSleepState,IWDTFSystemAction2.GetNextSleepState, IWDTFSystemAction2, IWDTFSystemAction2 interface [Windows Device Testing Framework], GetNextSleepState method, IWDTFSystemAction2::GetNextSleepState, Microsoft.WDTF.IWDTFSystemAction2.GetNextSleepState, Microsoft::WDTF::IWDTFSystemAction2::GetNextSleepState, dtf.iwdtfsystemaction2_getnextsleepstate, wdtfsystemaction/IWDTFSystemAction2::GetNextSleepState
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wdtfsystemaction.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTFSystemAction.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTFSystemAction.Interop.dll
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WDTFSystemAction.Interop.dll
api_name:
-	IWDTFSystemAction2.GetNextSleepState
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFSystemAction2::GetNextSleepState method


## -description


Returns the next supported sleep state.


## -parameters




### -param pnSleepState [out, retval]

The sleep state.


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439302">IWDTFSystemAction2</a>
 

 

