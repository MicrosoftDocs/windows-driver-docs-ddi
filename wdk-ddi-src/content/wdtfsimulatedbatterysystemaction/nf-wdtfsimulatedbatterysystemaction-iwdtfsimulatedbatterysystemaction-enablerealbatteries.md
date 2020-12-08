---
UID: NF:wdtfsimulatedbatterysystemaction.IWDTFSimulatedBatterySystemAction.EnableRealBatteries
title: IWDTFSimulatedBatterySystemAction::EnableRealBatteries (wdtfsimulatedbatterysystemaction.h)
description: Enables real batteries if they are present in the system.
old-location: dtf\iwdtfsimulatedbatterysystemaction_enablerealbatteries.htm
tech.root: dtf
ms.date: 04/04/2018
keywords: ["IWDTFSimulatedBatterySystemAction::EnableRealBatteries"]
ms.keywords: EnableRealBatteries, EnableRealBatteries method [Windows Device Testing Framework], EnableRealBatteries method [Windows Device Testing Framework],IWDTFSimulatedBatterySystemAction interface, IWDTFSimulatedBatterySystemAction interface [Windows Device Testing Framework],EnableRealBatteries method, IWDTFSimulatedBatterySystemAction.EnableRealBatteries, IWDTFSimulatedBatterySystemAction::EnableRealBatteries, dtf.iwdtfsimulatedbatterysystemaction_enablerealbatteries, wdtfsimulatedbatterysystemaction/IWDTFSimulatedBatterySystemAction::EnableRealBatteries
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
 - IWDTFSimulatedBatterySystemAction::EnableRealBatteries
 - wdtfsimulatedbatterysystemaction/IWDTFSimulatedBatterySystemAction::EnableRealBatteries
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - wdtfsimulatedbatterysystemaction.h
api_name:
 - IWDTFSimulatedBatterySystemAction.EnableRealBatteries
---

# IWDTFSimulatedBatterySystemAction::EnableRealBatteries


## -description

Enables real batteries if they are present in the system.



Use this method to enable real batteries if they are present in the
    system.  If no real batteries are present, this method does nothing. This
    method should be called when disabling the simulated battery in order to return the system to its original state.

## -parameters

### -param pbSuccess 

[out, retval]

## -returns

If this method succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -see-also

<a href="/windows-hardware/drivers/ddi/index">IWDTFSimulatedBatterySystemAction</a>
