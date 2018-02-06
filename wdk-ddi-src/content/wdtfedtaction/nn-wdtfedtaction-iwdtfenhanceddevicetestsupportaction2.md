---
UID: NN:wdtfedtaction.IWDTFEnhancedDeviceTestSupportAction2
title: IWDTFEnhancedDeviceTestSupportAction2
author: windows-driver-content
description: Defines operations and properties that support the Enhanced Device Test (EDT) filter driver.
old-location: dtf\iwdtfenhanceddevicetestsupportaction2.htm
old-project: dtf
ms.assetid: 273eb6e9-10cb-4ed3-86a4-103dea801b77
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: dtf.iwdtfenhanceddevicetestsupportaction2, IWDTFEnhancedDeviceTestSupportAction2 interface [Windows Device Testing Framework], IWDTFEnhancedDeviceTestSupportAction2 interface [Windows Device Testing Framework], described, IWDTFEnhancedDeviceTestSupportAction2, wdtfedtaction/IWDTFEnhancedDeviceTestSupportAction2, Microsoft.WDTF.IWDTFEnhancedDeviceTestSupportAction2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: wdtfedtaction.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTFEDTAction.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTFDriverEDTAction.Interop.dll
req.type-library: 
req.lib: wdtfedtaction.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WDTFDriverEDTAction.Interop.dll
apiname:
-	IWDTFEnhancedDeviceTestSupportAction2
product: Windows
targetos: Windows
req.typenames: "*PWORK_QUEUE_ITEM, WORK_QUEUE_ITEM"
req.product: Windows 10 or later.
---

# IWDTFEnhancedDeviceTestSupportAction2 interface


## -description


Defines operations and properties that support the Enhanced Device Test (EDT) filter driver.


## -members

The <b>IWDTFEnhancedDeviceTestSupportAction2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh450971">Disable</a>
</td>
<td align="left" width="63%">
Disables the Enhanced Device Test (EDT) filter driver on the target device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451004">Enable</a>
</td>
<td align="left" width="63%">
Enables the Enhanced Device Test (EDT) filter driver on the target device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh450992">IsEnabled</a>
</td>
<td align="left" width="63%">
Gets a value that indicates whether the Enhanced Device Test (EDT) filter driver is enabled 
on the target device.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451008">IsRebootRequired</a>
</td>
<td align="left" width="63%">
Gets a value that indicates whether the Enhanced Device Test (EDT) filter driver requires a reboot.

</td>
</tr>
</table>Disables the Enhanced Device Test (EDT) filter driver on the target device.

Enables the Enhanced Device Test (EDT) filter driver on the target device.

Gets a value that indicates whether the Enhanced Device Test (EDT) filter driver is enabled 
on the target device.

Gets a value that indicates whether the Enhanced Device Test (EDT) filter driver requires a reboot.

 

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDTFEnhancedDeviceTestSupportAction2</b> interface has these properties.
<table class="members" id="memberListProperties">
<tr>
<th align="left" width="27%">Property</th>
<th align="left" width="10%">Access type</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451010">SkipRestart</a>


</td>
<td align="left" width="10%">
Write-only

</td>
<td align="left" width="63%">
Sets a value that indicates whether the target device should be restarted by default.

</td>
</tr>
</table>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451010">SkipRestart</a>


Write-only

Sets a value that indicates whether the target device should be restarted by default.

 


## -remarks


The EDT filter driver provides support for the 
<a href="..\wdtfpnpaction\nn-wdtfpnpaction-iwdtfpnpaction2.md">IWDTFPNPAction2</a> interface methods 
that are prefixed with <b>EDT</b>.


