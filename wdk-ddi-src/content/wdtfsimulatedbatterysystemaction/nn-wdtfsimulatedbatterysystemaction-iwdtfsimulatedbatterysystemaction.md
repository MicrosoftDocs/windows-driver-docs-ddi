---
UID: NN:wdtfsimulatedbatterysystemaction.IWDTFSimulatedBatterySystemAction
title: IWDTFSimulatedBatterySystemAction
author: windows-driver-content
description: IWDTFSimulatedBatterySystemAction Interface
old-location: dtf\iwdtfsimulatedbatterysystemaction.htm
old-project: dtf
ms.assetid: 38df72bd-5206-4655-846c-ae925ed648eb
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: dtf.iwdtfsimulatedbatterysystemaction, IWDTFSimulatedBatterySystemAction interface [Windows Device Testing Framework], IWDTFSimulatedBatterySystemAction interface [Windows Device Testing Framework], described, IWDTFSimulatedBatterySystemAction, wdtfsimulatedbatterysystemaction/IWDTFSimulatedBatterySystemAction
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	IWDTFSimulatedBatterySystemAction
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFSimulatedBatterySystemAction interface


## -description


IWDTFSimulatedBatterySystemAction Interface


## -members

The <b>IWDTFSimulatedBatterySystemAction</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/8118589c-00ef-4986-b523-b812160a547d">DisableRealBatteries</a>
</td>
<td align="left" width="63%">
Disables real batteries if they are present in the system.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/52ddeb83-8ac3-4e9d-84d8-dddfcc404b6e">DisableSimulatedBattery</a>
</td>
<td align="left" width="63%">
Disables the simulated battery.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/32748776-fe07-4f7e-bceb-5b554fa8f9f1">EnableRealBatteries</a>
</td>
<td align="left" width="63%">
Enables real batteries if they are present in the system.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/c9ca8bb4-2a05-4934-b589-41fba8092b1b">EnableSimulatedBattery</a>
</td>
<td align="left" width="63%">
Enables the simulated battery.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/b330c423-b295-4b5b-b6bf-1f48549e8bfa">SetSimulatedBatteryChargePercentage</a>
</td>
<td align="left" width="63%">
Sets the charge percentage reported to the OS by the simulated battery.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/ddfd38d9-a78e-4573-9bf3-24f2f69b5949">SetSimulatedBatteryToAC</a>
</td>
<td align="left" width="63%">
Sets the simulated battery status to AC power.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/7564c5f0-ea36-4009-bd34-3119ef23149e">SetSimulatedBatteryToDC</a>
</td>
<td align="left" width="63%">
Sets the simulated battery status to DC power.

</td>
</tr>
</table>Disables real batteries if they are present in the system.

Disables the simulated battery.

Enables real batteries if they are present in the system.

Enables the simulated battery.

Sets the charge percentage reported to the OS by the simulated battery.

Sets the simulated battery status to AC power.

Sets the simulated battery status to DC power.

 

