---
UID: NN:prcomoem.IPrintCorePS2
title: IPrintCorePS2
author: windows-driver-content
description: This section describes the methods defined for the IPrintCorePS2 COM Interface. Method prototypes are defined in prcomoem.h.
old-location: print\iprintcoreps2_interface.htm
old-project: print
ms.assetid: bf7e15df-49ba-4850-acf6-dab5dc137f48
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IPrintCorePS2, IPrintCorePS2 interface [Print Devices], IPrintCorePS2 interface [Print Devices], described, prcomoem/IPrintCorePS2, print.iprintcoreps2_interface, print_unidrv-pscript_rendering_ee16e348-6dec-4820-ab6c-d41adecf8c74.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: prcomoem.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: prcomoem.h
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	prcomoem.h
api_name:
-	IPrintCorePS2
product: Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintCorePS2 interface


## -description


This section describes the methods defined for the <a href="https://msdn.microsoft.com/d5eb6962-2201-405f-9a22-2b11fb6d0360">IPrintCorePS2 COM Interface</a>. Method prototypes are defined in prcomoem.h.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintCorePS2</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IPrintCorePS2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPrintCorePS2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548662">DrvWriteSpoolBuf</a>
</td>
<td align="left" width="63%">
The <code>IPrintCorePS2::DrvWriteSpoolBuf</code> method is provided by the Pscript5 driver so that a <a href="https://msdn.microsoft.com/e55ca083-2790-4929-9e5b-6fce49eb0404">rendering plug-in</a> can send printer data to the spooler.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/0a8d1b25-da39-4bdc-a7d7-0d472e94e165">EnumFeatures</a>
</td>
<td align="left" width="63%">
The <code>IPrintCorePS2::EnumFeatures</code> method enumerates a printer's available features.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/2a861450-0bc5-432b-bf5d-9a9761c22ea1">EnumOptions</a>
</td>
<td align="left" width="63%">
The <code>IPrintCorePS2::EnumOptions</code> method enumerates the available options of a specific feature.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/1a87da8a-a495-4451-a6f3-1261efda09f3">GetFeatureAttribute</a>
</td>
<td align="left" width="63%">
The <code>IPrintCorePS2::GetFeatureAttribute</code> method retrieves the feature attribute list or the value of a specific feature attribute.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/a834cc10-eb59-4560-add3-e93f8292324b">GetGlobalAttribute</a>
</td>
<td align="left" width="63%">
The <code>IPrintCorePS2::GetGlobalAttribute</code> method retrieves the global attribute list or the value of a specific global attribute.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/b9ac4c2f-1eba-4425-a102-56fef6d0f5a7">GetOptionAttribute</a>
</td>
<td align="left" width="63%">
The <code>IPrintCorePS2::GetOptionAttribute</code> method retrieves the option attribute list or the value of a specific option attribute.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451244">GetOptions</a>
</td>
<td align="left" width="63%">
The <code>IPrintCorePS2::GetOptions</code> method retrieves the driver's current feature settings in the format of a list of feature/option keyword pairs.

</td>
</tr>
</table> 

