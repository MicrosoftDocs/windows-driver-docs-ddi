---
UID: NF:wdtfsimulatedbatterysystemaction.IWDTFSimulatedBatterySystemAction.SetSimulatedBatteryChargePercentage
title: IWDTFSimulatedBatterySystemAction::SetSimulatedBatteryChargePercentage method
author: windows-driver-content
description: Sets the charge percentage reported to the OS by the simulated battery.
old-location: dtf\iwdtfsimulatedbatterysystemaction_setsimulatedbatterychargepercentage.htm
old-project: dtf
ms.assetid: b330c423-b295-4b5b-b6bf-1f48549e8bfa
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IWDTFSimulatedBatterySystemAction, IWDTFSimulatedBatterySystemAction interface [Windows Device Testing Framework], SetSimulatedBatteryChargePercentage method, IWDTFSimulatedBatterySystemAction::SetSimulatedBatteryChargePercentage, SetSimulatedBatteryChargePercentage method [Windows Device Testing Framework], SetSimulatedBatteryChargePercentage method [Windows Device Testing Framework], IWDTFSimulatedBatterySystemAction interface, SetSimulatedBatteryChargePercentage,IWDTFSimulatedBatterySystemAction.SetSimulatedBatteryChargePercentage, dtf.iwdtfsimulatedbatterysystemaction_setsimulatedbatterychargepercentage, wdtfsimulatedbatterysystemaction/IWDTFSimulatedBatterySystemAction::SetSimulatedBatteryChargePercentage
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
req.lib: 
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



 

 


