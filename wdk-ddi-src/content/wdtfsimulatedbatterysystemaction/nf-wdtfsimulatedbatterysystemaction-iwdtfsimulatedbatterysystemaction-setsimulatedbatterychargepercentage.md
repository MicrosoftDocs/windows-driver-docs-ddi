---
UID: NF:wdtfsimulatedbatterysystemaction.IWDTFSimulatedBatterySystemAction.SetSimulatedBatteryChargePercentage
title: IWDTFSimulatedBatterySystemAction::SetSimulatedBatteryChargePercentage (wdtfsimulatedbatterysystemaction.h)
description: Sets the charge percentage reported to the OS by the simulated battery.
old-location: dtf\iwdtfsimulatedbatterysystemaction_setsimulatedbatterychargepercentage.htm
tech.root: dtf
ms.assetid: b330c423-b295-4b5b-b6bf-1f48549e8bfa
ms.date: 04/04/2018
keywords: ["IWDTFSimulatedBatterySystemAction::SetSimulatedBatteryChargePercentage"]
ms.keywords: IWDTFSimulatedBatterySystemAction interface [Windows Device Testing Framework],SetSimulatedBatteryChargePercentage method, IWDTFSimulatedBatterySystemAction.SetSimulatedBatteryChargePercentage, IWDTFSimulatedBatterySystemAction::SetSimulatedBatteryChargePercentage, SetSimulatedBatteryChargePercentage, SetSimulatedBatteryChargePercentage method [Windows Device Testing Framework], SetSimulatedBatteryChargePercentage method [Windows Device Testing Framework],IWDTFSimulatedBatterySystemAction interface, dtf.iwdtfsimulatedbatterysystemaction_setsimulatedbatterychargepercentage, wdtfsimulatedbatterysystemaction/IWDTFSimulatedBatterySystemAction::SetSimulatedBatteryChargePercentage
f1_keywords:
 - "wdtfsimulatedbatterysystemaction/IWDTFSimulatedBatterySystemAction.SetSimulatedBatteryChargePercentage"
 - "IWDTFSimulatedBatterySystemAction.SetSimulatedBatteryChargePercentage"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- wdtfsimulatedbatterysystemaction.h
api_name:
- IWDTFSimulatedBatterySystemAction.SetSimulatedBatteryChargePercentage
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFSimulatedBatterySystemAction::SetSimulatedBatteryChargePercentage


## -description



Sets the charge percentage reported to the OS by the simulated battery.



Use this method to change the charge level reported to the OS by the
    simulated battery.  This is useful for testing software behavior that changes based on the battery charge level.


## -parameters




### -param Percent [in]

Specifies charge level percentage, 0-100.


### -param pbSuccess [out, retval]


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">IWDTFSimulatedBatterySystemAction</a>
 

 

