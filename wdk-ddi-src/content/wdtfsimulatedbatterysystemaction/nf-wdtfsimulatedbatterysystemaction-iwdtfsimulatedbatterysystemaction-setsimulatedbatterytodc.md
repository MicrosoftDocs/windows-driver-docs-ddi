---
UID: NF:wdtfsimulatedbatterysystemaction.IWDTFSimulatedBatterySystemAction.SetSimulatedBatteryToDC
title: IWDTFSimulatedBatterySystemAction::SetSimulatedBatteryToDC method
author: windows-driver-content
description: Sets the simulated battery status to DC power.
old-location: dtf\iwdtfsimulatedbatterysystemaction_setsimulatedbatterytodc.htm
old-project: dtf
ms.assetid: 7564c5f0-ea36-4009-bd34-3119ef23149e
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IWDTFSimulatedBatterySystemAction, IWDTFSimulatedBatterySystemAction interface [Windows Device Testing Framework], SetSimulatedBatteryToDC method, IWDTFSimulatedBatterySystemAction::SetSimulatedBatteryToDC, SetSimulatedBatteryToDC method [Windows Device Testing Framework], SetSimulatedBatteryToDC method [Windows Device Testing Framework], IWDTFSimulatedBatterySystemAction interface, SetSimulatedBatteryToDC,IWDTFSimulatedBatterySystemAction.SetSimulatedBatteryToDC, dtf.iwdtfsimulatedbatterysystemaction_setsimulatedbatterytodc, wdtfsimulatedbatterysystemaction/IWDTFSimulatedBatterySystemAction::SetSimulatedBatteryToDC
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	wdtfsimulatedbatterysystemaction.h
api_name:
-	IWDTFSimulatedBatterySystemAction.SetSimulatedBatteryToDC
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFSimulatedBatterySystemAction::SetSimulatedBatteryToDC method


## -description



Sets the simulated battery status to DC power.



 Use this method to set the simulated battery status to DC power.  If
    real batteries in the system are disabled, this sets the OS status and 
    policy to DC power.  This is useful for testing software behavior that changes depending on the AC/DC state.


## -syntax


````
HRESULT SetSimulatedBatteryToDC(
  [out, retval] VARIANT_BOOL *pbSuccess
);
````


## -parameters




### -param pbSuccess [out, retval]


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also

<a href="..\wdtfsimulatedbatterysystemaction\nn-wdtfsimulatedbatterysystemaction-iwdtfsimulatedbatterysystemaction.md">IWDTFSimulatedBatterySystemAction</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFSimulatedBatterySystemAction::SetSimulatedBatteryToDC method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

