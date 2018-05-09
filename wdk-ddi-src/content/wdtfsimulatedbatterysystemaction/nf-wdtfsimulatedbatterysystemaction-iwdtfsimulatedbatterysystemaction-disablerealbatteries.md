---
UID: NF:wdtfsimulatedbatterysystemaction.IWDTFSimulatedBatterySystemAction.DisableRealBatteries
title: IWDTFSimulatedBatterySystemAction::DisableRealBatteries
author: windows-driver-content
description: Disables real batteries if they are present in the system.
old-location: dtf\iwdtfsimulatedbatterysystemaction_disablerealbatteries.htm
old-project: dtf
ms.assetid: 8118589c-00ef-4986-b523-b812160a547d
ms.author: windowsdriverdev
ms.date: 4/4/2018
ms.keywords: DisableRealBatteries, DisableRealBatteries method [Windows Device Testing Framework], DisableRealBatteries method [Windows Device Testing Framework],IWDTFSimulatedBatterySystemAction interface, IWDTFSimulatedBatterySystemAction interface [Windows Device Testing Framework],DisableRealBatteries method, IWDTFSimulatedBatterySystemAction.DisableRealBatteries, IWDTFSimulatedBatterySystemAction::DisableRealBatteries, dtf.iwdtfsimulatedbatterysystemaction_disablerealbatteries, wdtfsimulatedbatterysystemaction/IWDTFSimulatedBatterySystemAction::DisableRealBatteries
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
-	IWDTFSimulatedBatterySystemAction.DisableRealBatteries
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




<a href="https://msdn.microsoft.com/library/windows/hardware/dn265160">IWDTFSimulatedBatterySystemAction</a>
 

 

