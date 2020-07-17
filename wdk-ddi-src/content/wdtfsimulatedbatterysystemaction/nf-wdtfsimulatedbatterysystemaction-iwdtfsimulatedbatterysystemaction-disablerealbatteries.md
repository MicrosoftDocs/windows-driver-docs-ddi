---
UID: NF:wdtfsimulatedbatterysystemaction.IWDTFSimulatedBatterySystemAction.DisableRealBatteries
title: IWDTFSimulatedBatterySystemAction::DisableRealBatteries (wdtfsimulatedbatterysystemaction.h)
description: Disables real batteries if they are present in the system.
old-location: dtf\iwdtfsimulatedbatterysystemaction_disablerealbatteries.htm
tech.root: dtf
ms.assetid: 8118589c-00ef-4986-b523-b812160a547d
ms.date: 04/04/2018
keywords: ["IWDTFSimulatedBatterySystemAction::DisableRealBatteries"]
ms.keywords: DisableRealBatteries, DisableRealBatteries method [Windows Device Testing Framework], DisableRealBatteries method [Windows Device Testing Framework],IWDTFSimulatedBatterySystemAction interface, IWDTFSimulatedBatterySystemAction interface [Windows Device Testing Framework],DisableRealBatteries method, IWDTFSimulatedBatterySystemAction.DisableRealBatteries, IWDTFSimulatedBatterySystemAction::DisableRealBatteries, dtf.iwdtfsimulatedbatterysystemaction_disablerealbatteries, wdtfsimulatedbatterysystemaction/IWDTFSimulatedBatterySystemAction::DisableRealBatteries
f1_keywords:
 - "wdtfsimulatedbatterysystemaction/IWDTFSimulatedBatterySystemAction.DisableRealBatteries"
 - "IWDTFSimulatedBatterySystemAction.DisableRealBatteries"
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
- IWDTFSimulatedBatterySystemAction.DisableRealBatteries
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFSimulatedBatterySystemAction::DisableRealBatteries


## -description



Disables real batteries if they are present in the system.



Use this method to disable real batteries if they are present in the
    system.  If no real batteries are present, this method does nothing. This 
    method should be called before calling methods that change the simulated
    battery state, otherwise the state changes might not have the desired
    effect on OS or software behavior.


## -parameters




### -param pbSuccess [out, retval]


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">IWDTFSimulatedBatterySystemAction</a>
 

 

