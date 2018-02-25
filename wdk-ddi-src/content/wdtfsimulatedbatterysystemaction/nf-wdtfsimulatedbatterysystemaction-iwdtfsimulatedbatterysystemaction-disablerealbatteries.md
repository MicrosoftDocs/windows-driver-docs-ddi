---
UID: NF:wdtfsimulatedbatterysystemaction.IWDTFSimulatedBatterySystemAction.DisableRealBatteries
title: IWDTFSimulatedBatterySystemAction::DisableRealBatteries method
author: windows-driver-content
description: Disables real batteries if they are present in the system.
old-location: dtf\iwdtfsimulatedbatterysystemaction_disablerealbatteries.htm
old-project: dtf
ms.assetid: 8118589c-00ef-4986-b523-b812160a547d
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , ,, ., :, A, B, D, DisableRealBatteries method [Windows Device Testing Framework], DisableRealBatteries method [Windows Device Testing Framework], IWDTFSimulatedBatterySystemAction interface, DisableRealBatteries,IWDTFSimulatedBatterySystemAction.DisableRealBatteries, F, I, IWDTFSimulatedBatterySystemAction, IWDTFSimulatedBatterySystemAction interface [Windows Device Testing Framework], DisableRealBatteries method, IWDTFSimulatedBatterySystemAction::DisableRealBatteries, R, S, T, W, a, b, c, d, dtf.iwdtfsimulatedbatterysystemaction_disablerealbatteries, e, i, l, m, n, o, r, s, t, u, wdtfsimulatedbatterysystemaction/IWDTFSimulatedBatterySystemAction::DisableRealBatteries, y"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wdtfsimulatedbatterysystemaction.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTFSimulatedBatterySystemAction.idl
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: wdtfsimulatedbatterysystemaction.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	wdtfsimulatedbatterysystemaction.h
apiname:
-	IWDTFSimulatedBatterySystemAction.DisableRealBatteries
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFSimulatedBatterySystemAction::DisableRealBatteries method


## -description



Disables real batteries if they are present in the system.



Use this method to disable real batteries if they are present in the
    system.  If no real batteries are present, this method does nothing. This 
    method should be called before calling methods that change the simulated
    battery state, otherwise the state changes might not have the desired
    effect on OS or software behavior.


## -syntax


````
HRESULT DisableRealBatteries(
  [out, retval] VARIANT_BOOL *pbSuccess
);
````


## -parameters




### -param pbSuccess [out, retval]


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also

<a href="..\wdtfsimulatedbatterysystemaction\nn-wdtfsimulatedbatterysystemaction-iwdtfsimulatedbatterysystemaction.md">IWDTFSimulatedBatterySystemAction</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFSimulatedBatterySystemAction::DisableRealBatteries method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

