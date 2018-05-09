---
UID: NF:wdtfsimulatedbatterysystemaction.IWDTFSimulatedBatterySystemAction.EnableRealBatteries
title: IWDTFSimulatedBatterySystemAction::EnableRealBatteries
author: windows-driver-content
description: Enables real batteries if they are present in the system.
old-location: dtf\iwdtfsimulatedbatterysystemaction_enablerealbatteries.htm
old-project: dtf
ms.assetid: 32748776-fe07-4f7e-bceb-5b554fa8f9f1
ms.author: windowsdriverdev
ms.date: 4/4/2018
ms.keywords: EnableRealBatteries, EnableRealBatteries method [Windows Device Testing Framework], EnableRealBatteries method [Windows Device Testing Framework],IWDTFSimulatedBatterySystemAction interface, IWDTFSimulatedBatterySystemAction interface [Windows Device Testing Framework],EnableRealBatteries method, IWDTFSimulatedBatterySystemAction.EnableRealBatteries, IWDTFSimulatedBatterySystemAction::EnableRealBatteries, dtf.iwdtfsimulatedbatterysystemaction_enablerealbatteries, wdtfsimulatedbatterysystemaction/IWDTFSimulatedBatterySystemAction::EnableRealBatteries
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
-	IWDTFSimulatedBatterySystemAction.EnableRealBatteries
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFSimulatedBatterySystemAction::EnableRealBatteries


## -description



Enables real batteries if they are present in the system.



Use this method to enable real batteries if they are present in the
    system.  If no real batteries are present, this method does nothing. This
    method should be called when disabling the simulated battery in order to return the system to its original state.


## -parameters




### -param pbSuccess [out, retval]


## -returns



If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn265160">IWDTFSimulatedBatterySystemAction</a>
 

 

