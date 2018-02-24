---
UID: NF:wdtfsimulatedbatterysystemaction.IWDTFSimulatedBatterySystemAction.SetSimulatedBatteryChargePercentage
title: IWDTFSimulatedBatterySystemAction::SetSimulatedBatteryChargePercentage method
author: windows-driver-content
description: Sets the charge percentage reported to the OS by the simulated battery.
old-location: dtf\iwdtfsimulatedbatterysystemaction_setsimulatedbatterychargepercentage.htm
old-project: dtf
ms.assetid: b330c423-b295-4b5b-b6bf-1f48549e8bfa
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: wdtfsimulatedbatterysystemaction/IWDTFSimulatedBatterySystemAction::SetSimulatedBatteryChargePercentage, IWDTFSimulatedBatterySystemAction::SetSimulatedBatteryChargePercentage, dtf.iwdtfsimulatedbatterysystemaction_setsimulatedbatterychargepercentage, IWDTFSimulatedBatterySystemAction, IWDTFSimulatedBatterySystemAction interface [Windows Device Testing Framework], SetSimulatedBatteryChargePercentage method, SetSimulatedBatteryChargePercentage, SetSimulatedBatteryChargePercentage method [Windows Device Testing Framework], SetSimulatedBatteryChargePercentage method [Windows Device Testing Framework], IWDTFSimulatedBatterySystemAction interface
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
-	IWDTFSimulatedBatterySystemAction.SetSimulatedBatteryChargePercentage
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFSimulatedBatterySystemAction::SetSimulatedBatteryChargePercentage method


## -description



Sets the charge percentage reported to the OS by the simulated battery.



Use this method to change the charge level reported to the OS by the
    simulated battery.  This is useful for testing software behavior that changes based on the battery charge level.


## -syntax


````
HRESULT SetSimulatedBatteryChargePercentage(
  [in]          ULONG        Percent,
  [out, retval] VARIANT_BOOL *pbSuccess
);
````


## -parameters




### -param Percent [in]

Specifies charge level percentage, 0-100.


### -param pbSuccess [out, retval]


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also

<a href="..\wdtfsimulatedbatterysystemaction\nn-wdtfsimulatedbatterysystemaction-iwdtfsimulatedbatterysystemaction.md">IWDTFSimulatedBatterySystemAction</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [dtf\dtf]:%20IWDTFSimulatedBatterySystemAction::SetSimulatedBatteryChargePercentage method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

