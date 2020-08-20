---
UID: NF:wdtfsimulatedbatterysystemaction.IWDTFSimulatedBatterySystemAction.SetSimulatedBatteryToDC
title: IWDTFSimulatedBatterySystemAction::SetSimulatedBatteryToDC (wdtfsimulatedbatterysystemaction.h)
description: Sets the simulated battery status to DC power.
old-location: dtf\iwdtfsimulatedbatterysystemaction_setsimulatedbatterytodc.htm
tech.root: dtf
ms.assetid: 7564c5f0-ea36-4009-bd34-3119ef23149e
ms.date: 04/04/2018
keywords: ["IWDTFSimulatedBatterySystemAction::SetSimulatedBatteryToDC"]
ms.keywords: IWDTFSimulatedBatterySystemAction interface [Windows Device Testing Framework],SetSimulatedBatteryToDC method, IWDTFSimulatedBatterySystemAction.SetSimulatedBatteryToDC, IWDTFSimulatedBatterySystemAction::SetSimulatedBatteryToDC, SetSimulatedBatteryToDC, SetSimulatedBatteryToDC method [Windows Device Testing Framework], SetSimulatedBatteryToDC method [Windows Device Testing Framework],IWDTFSimulatedBatterySystemAction interface, dtf.iwdtfsimulatedbatterysystemaction_setsimulatedbatterytodc, wdtfsimulatedbatterysystemaction/IWDTFSimulatedBatterySystemAction::SetSimulatedBatteryToDC
f1_keywords:
 - "wdtfsimulatedbatterysystemaction/IWDTFSimulatedBatterySystemAction.SetSimulatedBatteryToDC"
 - "IWDTFSimulatedBatterySystemAction.SetSimulatedBatteryToDC"
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
- IWDTFSimulatedBatterySystemAction.SetSimulatedBatteryToDC
targetos: Windows
req.typenames: 
---

# IWDTFSimulatedBatterySystemAction::SetSimulatedBatteryToDC


## -description



Sets the simulated battery status to DC power.



 Use this method to set the simulated battery status to DC power.  If
    real batteries in the system are disabled, this sets the OS status and 
    policy to DC power.  This is useful for testing software behavior that changes depending on the AC/DC state.


## -parameters




### -param pbSuccess 
[out, retval]

## -returns



If this method succeeds, it returns **S_OK**. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">IWDTFSimulatedBatterySystemAction</a>
 

 

