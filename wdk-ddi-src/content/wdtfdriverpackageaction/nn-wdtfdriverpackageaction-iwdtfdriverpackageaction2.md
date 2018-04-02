---
UID: NN:wdtfdriverpackageaction.IWDTFDriverPackageAction2
title: IWDTFDriverPackageAction2
author: windows-driver-content
description: Defines operations and properties that represent a driver package for imported and pre-imported driver packages.
old-location: dtf\iwdtfdriverpackageaction2.htm
old-project: dtf
ms.assetid: aa66280d-c32e-4d1c-bcc8-aa2719b61010
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IWDTFDriverPackageAction2, IWDTFDriverPackageAction2 interface [Windows Device Testing Framework], IWDTFDriverPackageAction2 interface [Windows Device Testing Framework], described, Microsoft.WDTF.IWDTFDriverPackageAction2, dtf.iwdtfdriverpackageaction2, wdtfdriverpackageaction/IWDTFDriverPackageAction2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: wdtfdriverpackageaction.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTFDriverPackageAction.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTFDriverPackageAction.Interop.dll
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
-	WDTFDriverPackageAction.Interop.dll
api_name:
-	IWDTFDriverPackageAction2
product:
- Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---

# IWDTFDriverPackageAction2 interface


## -description


Defines operations and properties that represent a driver package for imported and pre-imported
driver packages.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDTFDriverPackageAction2</b> interface inherits from <b>IWDTFAction2</b>. <b>IWDTFDriverPackageAction2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
<li><a href="https://docs.microsoft.com/">Properties</a></li>
</ul>

## -members

The <b>IWDTFDriverPackageAction2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406436">Compare</a>
</td>
<td align="left" width="63%">
Compares two driver packages.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/218146e6-c94a-455a-ab87-1e77da3152f2">GetQueryForDevicesThatCanUsePackage</a>
</td>
<td align="left" width="63%">
Returns an SDEL statement that queries for all devices that can use the driver package.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/c7d73c86-0ac4-4e87-8f82-39be2329dafd">GetQueryForDevicesUsingPackage</a>
</td>
<td align="left" width="63%">
Returns an SDEL statement that queries for all devices that use the driver package.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh450929">SetPackageInfFileName</a>
</td>
<td align="left" width="63%">
Sets the pre-imported driver package path.

</td>
</tr>
</table> 
<h3><a id="properties"></a>Properties</h3>The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDTFDriverPackageAction2</b> interface has these properties.
<table class="members" id="memberListProperties">
<tr>
<th align="left" width="27%">Property</th>
<th align="left" width="10%">Access type</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406430">CatalogFile</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets the catalog file name.

</td>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406432">ClassGuid</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets the class GUID.

</td>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406434">ClassName</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets the class name.

</td>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406437">Date</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets the driver package date.

</td>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406440">DigitalSigner</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets the digital signer.

</td>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406447">HasCatalog</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets a value that indicates whether the driver package has a catalog.

</td>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406449">InfFileName</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets the INF file name.

</td>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406451">IsDigitalSigned</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets a value that indicates whether the driver package is signed.

</td>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406453">IsImported</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets a value that indicates whether the driver package is imported.

</td>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406455">Provider</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets the driver package provider.

</td>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://msdn.microsoft.com/library/windows/hardware/dn973197">Version</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets the driver package version.

</td>
</tr>
</table> 

