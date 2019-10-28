---
UID: NN:wdtfdriversetupsystemaction.IWDTFDriverSetupSystemAction2
title: IWDTFDriverSetupSystemAction2 (wdtfdriversetupsystemaction.h)
description: Defines operations that control the system during driver setup.
old-location: dtf\iwdtfdriversetupsystemaction2.htm
tech.root: dtf
ms.assetid: d825c8de-7565-494a-ae49-be404493945e
ms.date: 04/04/2018
ms.keywords: IWDTFDriverSetupSystemAction2, IWDTFDriverSetupSystemAction2 interface [Windows Device Testing Framework], IWDTFDriverSetupSystemAction2 interface [Windows Device Testing Framework],described, Microsoft.WDTF.IWDTFDriverSetupSystemAction2, dtf.iwdtfdriversetupsystemaction2, wdtfdriversetupsystemaction/IWDTFDriverSetupSystemAction2
ms.topic: interface
f1_keywords:
 - "wdtfdriversetupsystemaction/IWDTFDriverSetupSystemAction2"
req.header: wdtfdriversetupsystemaction.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTFDriverSetupSystemAction.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTFDriverSetupSystemAction.Interop.dll
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
- WDTFDriverSetupSystemAction.Interop.dll
api_name:
- IWDTFDriverSetupSystemAction2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFDriverSetupSystemAction2 interface


## -description


Defines operations that control the system during driver setup.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDTFDriverSetupSystemAction2</b> interface inherits from <b>IWDTFAction2</b>. <b>IWDTFDriverSetupSystemAction2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IWDTFDriverSetupSystemAction2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtfdriversetupsystemaction/nf-wdtfdriversetupsystemaction-iwdtfdriversetupsystemaction2-cleartriagelogs">ClearTriageLogs</a>
</td>
<td align="left" width="63%">
Clears the system device setup triage logs.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtfdriversetupsystemaction/nf-wdtfdriversetupsystemaction-iwdtfdriversetupsystemaction2-importdriverpackage">ImportDriverPackage</a>
</td>
<td align="left" width="63%">
Imports a driver packge to the system driver store.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtfdriverpackageaction/nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-get_isimported">IsImported</a>
</td>
<td align="left" width="63%">
Returns a value that indicates whether a package has already been imported.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtfdriversetupsystemaction/nf-wdtfdriversetupsystemaction-iwdtfdriversetupsystemaction2-removedriverpackage">RemoveDriverPackage</a>
</td>
<td align="left" width="63%">
Removes a driver package from the driver store.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtfdriversetupsystemaction/nf-wdtfdriversetupsystemaction-iwdtfdriversetupsystemaction2-rescanalldevices">RescanAllDevices</a>
</td>
<td align="left" width="63%">
Rescan all devices in the system.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtfdriversetupsystemaction/nf-wdtfdriversetupsystemaction-iwdtfdriversetupsystemaction2-snaptriagelogs">SnapTriageLogs</a>
</td>
<td align="left" width="63%">
Copies the driver setup triage logs.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtfdriversetupsystemaction/nf-wdtfdriversetupsystemaction-iwdtfdriversetupsystemaction2-waitnopendinginstallevents">WaitNoPendingInstallEvents</a>
</td>
<td align="left" width="63%">
Waits until all device installations have completed.

</td>
</tr>
</table> 

