---
UID: NN:prcomoem.IPrintOemUI2
title: IPrintOemUI2
author: windows-driver-content
description: This section describes the methods defined for the IPrintOemUI2 COM interface.
old-location: print\iprintoemui2_interface.htm
old-project: print
ms.assetid: 9b7afb56-7abb-4f20-b69d-12a28d7e3617
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrintOemUI2, IPrintOemUI2 interface [Print Devices], IPrintOemUI2 interface [Print Devices], described, prcomoem/IPrintOemUI2, print.iprintoemui2_interface, print_unidrv-pscript_ui_838f6394-df99-4045-9059-6ff480212733.xml
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
req.lib: 
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
-	IPrintOemUI2
product:
- Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintOemUI2 interface


## -description


This section describes the methods defined for the <b>IPrintOemUI2</b> COM interface.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintOemUI2</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IPrintOemUI2</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPrintOemUI2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/c98d1510-7db8-4fd6-a95f-1906f553d1c5">DocumentEvent</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUI2::DocumentEvent</code> method allows a UI plug-in to replace the core driver UI module's default implementation of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548544">DrvDocumentEvent</a> DDI.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/144618d0-0d77-487c-a074-8bd9f6030de2">HideStandardUI</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUI2::HideStandardUI</code> method allows a user interface plug-in to specify whether the standard property sheets should be displayed or hidden. Beginning with Microsoft Windows XP, this method can be implemented by a Pscript5 user interface plug-in. Beginning with Windows Vista, this method can be implemented by a Unidrv user interface plug-in.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/cb510aa6-7156-4b02-bab1-6951becbc1a0">QueryJobAttributes</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemUI2::QueryJobAttributes</code> method allows a UI plug-in to postprocess the core driver's results after a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548581">DrvQueryJobAttributes</a> DDI. The plug-in can choose to overwrite the values that the core driver placed in the <i>lpAttributeInfo</i> output buffer.

</td>
</tr>
</table> 

