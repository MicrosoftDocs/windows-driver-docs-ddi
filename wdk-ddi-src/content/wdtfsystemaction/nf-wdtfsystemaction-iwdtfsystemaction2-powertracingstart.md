---
UID: NF:wdtfsystemaction.IWDTFSystemAction2.PowerTracingStart
title: IWDTFSystemAction2::PowerTracingStart method
author: windows-driver-content
description: Starts a trace session for power state transitions and saves the trace message file (Wdtfpwr.etl) in the current working directory. This method is available starting with Windows 8.
old-location: dtf\iwdtfsystemaction2_powertracingstart.htm
old-project: dtf
ms.assetid: b82ebd99-289e-4761-9717-ce09cf5c40f0
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , ,, ., 2, :, A, D, F, I, IWDTFSystemAction2, IWDTFSystemAction2 interface [Windows Device Testing Framework], PowerTracingStart method, IWDTFSystemAction2::PowerTracingStart, Microsoft.WDTF.IWDTFSystemAction2.PowerTracingStart, Microsoft::WDTF::IWDTFSystemAction2::PowerTracingStart, P, PowerTracingStart method [Windows Device Testing Framework], PowerTracingStart method [Windows Device Testing Framework], IWDTFSystemAction2 interface, PowerTracingStart,IWDTFSystemAction2.PowerTracingStart, S, T, W, a, c, dtf.iwdtfsystemaction2_powertracingstart, e, g, i, m, n, o, r, s, t, w, wdtfsystemaction/IWDTFSystemAction2::PowerTracingStart, y"
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
req.lib: wdtfsystemaction.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WDTFSystemAction.Interop.dll
apiname:
-	IWDTFSystemAction2.PowerTracingStart
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFSystemAction2::PowerTracingStart method


## -description


Starts a trace session for power state transitions and saves the trace message file (Wdtfpwr.etl) in the current working directory. This method
    is available starting with Windows 8.


Starts a trace for power state transitions and saves an .etl file in the current working directory


## -syntax


````
HRESULT PowerTracingStart();
````


## -parameters






## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also

<a href="..\wdtfsystemaction\nn-wdtfsystemaction-iwdtfsystemaction2.md">IWDTFSystemAction2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFSystemAction2::PowerTracingStart method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

