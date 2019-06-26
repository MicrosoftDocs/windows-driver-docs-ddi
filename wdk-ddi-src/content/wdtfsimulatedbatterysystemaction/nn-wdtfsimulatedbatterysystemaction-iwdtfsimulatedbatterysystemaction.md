---
UID: NN:wdtfsimulatedbatterysystemaction.IWDTFSimulatedBatterySystemAction
title: IWDTFSimulatedBatterySystemAction (wdtfsimulatedbatterysystemaction.h)
description: IWDTFSimulatedBatterySystemAction Interface
old-location: dtf\iwdtfsimulatedbatterysystemaction.htm
tech.root: dtf
ms.assetid: 38df72bd-5206-4655-846c-ae925ed648eb
ms.date: 04/04/2018
ms.keywords: IWDTFSimulatedBatterySystemAction, IWDTFSimulatedBatterySystemAction interface [Windows Device Testing Framework], IWDTFSimulatedBatterySystemAction interface [Windows Device Testing Framework],described, dtf.iwdtfsimulatedbatterysystemaction, wdtfsimulatedbatterysystemaction/IWDTFSimulatedBatterySystemAction
ms.topic: interface
req.header: wdtfsimulatedbatterysystemaction.h
req.include-header: 
req.target-type: Windows
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
- IWDTFSimulatedBatterySystemAction
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFSimulatedBatterySystemAction interface


## -description


IWDTFSimulatedBatterySystemAction Interface


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDTFSimulatedBatterySystemAction</b> interface inherits from <b>IWDTFAction2</b>. <b>IWDTFSimulatedBatterySystemAction</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IWDTFSimulatedBatterySystemAction</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">DisableRealBatteries</a>
</td>
<td align="left" width="63%">
Disables real batteries if they are present in the system.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">DisableSimulatedBattery</a>
</td>
<td align="left" width="63%">
Disables the simulated battery.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">EnableRealBatteries</a>
</td>
<td align="left" width="63%">
Enables real batteries if they are present in the system.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">EnableSimulatedBattery</a>
</td>
<td align="left" width="63%">
Enables the simulated battery.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">SetSimulatedBatteryChargePercentage</a>
</td>
<td align="left" width="63%">
Sets the charge percentage reported to the OS by the simulated battery.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">SetSimulatedBatteryToAC</a>
</td>
<td align="left" width="63%">
Sets the simulated battery status to AC power.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/index">SetSimulatedBatteryToDC</a>
</td>
<td align="left" width="63%">
Sets the simulated battery status to DC power.

</td>
</tr>
</table> 

