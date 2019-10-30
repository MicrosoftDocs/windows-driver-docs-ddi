---
UID: NN:wdtfdriverpackageaction.IWDTFDriverPackageAction2
title: IWDTFDriverPackageAction2 (wdtfdriverpackageaction.h)
description: Defines operations and properties that represent a driver package for imported and pre-imported driver packages.
old-location: dtf\iwdtfdriverpackageaction2.htm
tech.root: dtf
ms.assetid: aa66280d-c32e-4d1c-bcc8-aa2719b61010
ms.date: 04/04/2018
ms.keywords: IWDTFDriverPackageAction2, IWDTFDriverPackageAction2 interface [Windows Device Testing Framework], IWDTFDriverPackageAction2 interface [Windows Device Testing Framework],described, Microsoft.WDTF.IWDTFDriverPackageAction2, dtf.iwdtfdriverpackageaction2, wdtfdriverpackageaction/IWDTFDriverPackageAction2
ms.topic: interface
f1_keywords:
 - "wdtfdriverpackageaction/IWDTFDriverPackageAction2"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WDTFDriverPackageAction.Interop.dll
api_name:
- IWDTFDriverPackageAction2
product:
- Windows
targetos: Windows
req.typenames: 
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
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtfdriverpackageaction/nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-compare">Compare</a>
</td>
<td align="left" width="63%">
Compares two driver packages.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtfdriverpackageaction/nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-getqueryfordevicethatcanusepackage">GetQueryForDevicesThatCanUsePackage</a>
</td>
<td align="left" width="63%">
Returns an SDEL statement that queries for all devices that can use the driver package.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtfdriverpackageaction/nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-getqueryfordeviceusingpackage">GetQueryForDevicesUsingPackage</a>
</td>
<td align="left" width="63%">
Returns an SDEL statement that queries for all devices that use the driver package.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtfdriverpackageaction/nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-setpackageinffilename">SetPackageInfFileName</a>
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

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtfdriverpackageaction/nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-get_catalogfile">CatalogFile</a>


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

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtfdriverpackageaction/nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-get_classguid">ClassGuid</a>


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

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtfdriverpackageaction/nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-get_classname">ClassName</a>


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

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtfdriverpackageaction/nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-get_date">Date</a>


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

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtfdriverpackageaction/nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-get_digitalsigner">DigitalSigner</a>


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

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtfdriverpackageaction/nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-get_hascatalog">HasCatalog</a>


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

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtfdriverpackageaction/nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-get_inffilename">InfFileName</a>


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

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtfdriverpackageaction/nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-get_isdigitalsigned">IsDigitalSigned</a>


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

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtfdriverpackageaction/nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-get_isimported">IsImported</a>


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

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdtfdriverpackageaction/nf-wdtfdriverpackageaction-iwdtfdriverpackageaction2-get_provider">Provider</a>


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

<a href="https://docs.microsoft.com/windows-hardware/drivers/mobilebroadband/version">Version</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets the driver package version.

</td>
</tr>
</table> 

