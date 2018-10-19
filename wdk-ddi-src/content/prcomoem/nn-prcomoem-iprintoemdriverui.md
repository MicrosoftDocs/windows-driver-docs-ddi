---
UID: NN:prcomoem.IPrintOemDriverUI
title: IPrintOemDriverUI
author: windows-driver-content
description: This section describes the methods defined for the IPrintOemDriverUI COM Interface.
old-location: print\iprintoemdriverui_interface.htm
tech.root: print
ms.assetid: 2a885dd5-d328-4aae-8771-613ff93b35ac
ms.date: 04/20/2018
ms.keywords: IPrintOemDriverUI, IPrintOemDriverUI interface [Print Devices], IPrintOemDriverUI interface [Print Devices],described, prcomoem/IPrintOemDriverUI, print.iprintoemdriverui_interface, print_unidrv-pscript_ui_af445d30-9f51-4759-867d-d93e9ae0bc34.xml
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
-	IPrintOemDriverUI
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemDriverUI interface


## -description


This section describes the methods defined for the IPrintOemDriverUI COM Interface.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintOemDriverUI</b> interface inherits from the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface. <b>IPrintOemDriverUI</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IPrintOemDriverUI</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553114">IPrintOemDriverUI::DrvGetDriverSetting</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemDriverUI::DrvGetDriverSetting</code> method is provided by the Unidrv and Pscript5 minidrivers so that user interface plug-ins can obtain the current status of printer features and other internal information.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553115">IPrintOemDriverUI::DrvUpdateUISetting</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemDriverUI::DrvUpdateUISetting</code> method is provided by the Unidrv and Pscript5 minidrivers so that user interface plug-ins can notify the driver of a modified user interface option.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553118">IPrintOemDriverUI::DrvUpgradeRegistrySetting</a>
</td>
<td align="left" width="63%">
The <code>IPrintOemDriverUI::DrvUpdateRegistrySetting</code> method is provided by the Unidrv and Pscript5 minidrivers so that user interface plug-ins can update device settings stored in the registry.

</td>
</tr>
</table> 

