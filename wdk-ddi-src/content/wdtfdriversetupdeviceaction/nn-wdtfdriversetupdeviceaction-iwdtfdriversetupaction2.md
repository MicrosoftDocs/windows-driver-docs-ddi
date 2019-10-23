---
UID: NN:wdtfdriversetupdeviceaction.IWDTFDriverSetupAction2
title: IWDTFDriverSetupAction2 (wdtfdriversetupdeviceaction.h)
description: Defines operations that control the target device during driver setup.
old-location: dtf\iwdtfdriversetupaction2.htm
tech.root: dtf
ms.assetid: 474590f9-f737-4b9a-9a63-8cce8a35c538
ms.date: 04/04/2018
ms.keywords: IWDTFDriverSetupAction2, IWDTFDriverSetupAction2 interface [Windows Device Testing Framework], IWDTFDriverSetupAction2 interface [Windows Device Testing Framework],described, Microsoft.WDTF.IWDTFDriverSetupAction2, dtf.iwdtfdriversetupaction2, wdtfdriversetupdeviceaction/IWDTFDriverSetupAction2
ms.topic: interface
f1_keywords:
 - "wdtfdriversetupdeviceaction/IWDTFDriverSetupAction2"
req.header: wdtfdriversetupdeviceaction.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTFDriverSetupDeviceAction.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTFDriverSetupDeviceAction.Interop.dll
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
- WDTFDriverSetupDeviceAction.Interop.dll
api_name:
- IWDTFDriverSetupAction2
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDTFDriverSetupAction2 interface


## -description


Defines operations that control the target device during driver setup.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDTFDriverSetupAction2</b> interface inherits from <b>IWDTFAction2</b>. <b>IWDTFDriverSetupAction2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IWDTFDriverSetupAction2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtfdriversetupdeviceaction/nf-wdtfdriversetupdeviceaction-iwdtfdriversetupaction2-uninstalldriverpermanently">UnInstallDriverPermanently</a>
</td>
<td align="left" width="63%">
Uninstalls the current driver for the target device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtfdriversetupdeviceaction/nf-wdtfdriversetupdeviceaction-iwdtfdriversetupaction2-updatedriver">UpdateDriver</a>
</td>
<td align="left" width="63%">
Updates the target device with a driver from the driver package.

</td>
</tr>
</table> 

