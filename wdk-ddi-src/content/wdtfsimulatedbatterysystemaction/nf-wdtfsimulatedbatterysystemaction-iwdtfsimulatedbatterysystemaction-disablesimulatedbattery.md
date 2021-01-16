---
UID: NF:wdtfsimulatedbatterysystemaction.IWDTFSimulatedBatterySystemAction.DisableSimulatedBattery
title: IWDTFSimulatedBatterySystemAction::DisableSimulatedBattery (wdtfsimulatedbatterysystemaction.h)
description: Disables the simulated battery.
old-location: dtf\iwdtfsimulatedbatterysystemaction_disablesimulatedbattery.htm
tech.root: dtf
ms.date: 04/04/2018
keywords: ["IWDTFSimulatedBatterySystemAction::DisableSimulatedBattery"]
ms.keywords: DisableSimulatedBattery, DisableSimulatedBattery method [Windows Device Testing Framework], DisableSimulatedBattery method [Windows Device Testing Framework],IWDTFSimulatedBatterySystemAction interface, IWDTFSimulatedBatterySystemAction interface [Windows Device Testing Framework],DisableSimulatedBattery method, IWDTFSimulatedBatterySystemAction.DisableSimulatedBattery, IWDTFSimulatedBatterySystemAction::DisableSimulatedBattery, dtf.iwdtfsimulatedbatterysystemaction_disablesimulatedbattery, wdtfsimulatedbatterysystemaction/IWDTFSimulatedBatterySystemAction::DisableSimulatedBattery
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDTFSimulatedBatterySystemAction::DisableSimulatedBattery
 - wdtfsimulatedbatterysystemaction/IWDTFSimulatedBatterySystemAction::DisableSimulatedBattery
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - wdtfsimulatedbatterysystemaction.h
api_name:
 - IWDTFSimulatedBatterySystemAction::DisableSimulatedBattery
---

# IWDTFSimulatedBatterySystemAction::DisableSimulatedBattery


## -description

Disables the simulated battery.



Use this method is used to disable the simulated battery (uninstalls simulated
    battery device).  This does not restore the system to its original state, the <a href="/windows-hardware/drivers/ddi/index">WDTFSimulatedBatterySystemAction::EnableRealBatteries</a> method must also be called.

## -parameters

### -param pbSuccess 

[out, retval]

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.




<a href="/windows-hardware/drivers/ddi/index">WDTFSimulatedBatterySystemAction::EnableRealBatteries</a>

