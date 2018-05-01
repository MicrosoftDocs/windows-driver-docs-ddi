---
UID: NF:prcomoem.IPrintOemDriverUI.DrvGetDriverSetting
title: IPrintOemDriverUI::DrvGetDriverSetting
author: windows-driver-content
description: The IPrintOemDriverUI::DrvGetDriverSetting method is provided by the Unidrv and Pscript5 minidrivers so that user interface plug-ins can obtain the current status of printer features and other internal information.
old-location: print\iprintoemdriverui_drvgetdriversetting.htm
old-project: print
ms.assetid: 25e8aec7-86af-4753-83d7-e7df5435f602
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: DrvGetDriverSetting, DrvGetDriverSetting method [Print Devices], DrvGetDriverSetting method [Print Devices],IPrintOemDriverUI interface, IPrintOemDriverUI interface [Print Devices],DrvGetDriverSetting method, IPrintOemDriverUI.DrvGetDriverSetting, IPrintOemDriverUI::DrvGetDriverSetting, prcomoem/IPrintOemDriverUI::DrvGetDriverSetting, print.iprintoemdriverui_drvgetdriversetting, print_unidrv-pscript_ui_3685add0-a9b4-43c3-9a5e-665e1f6f2034.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: prcomoem.h
req.include-header: Prcomoem.h
req.target-type: Desktop
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
-	IPrintOemDriverUI.DrvGetDriverSetting
product: Windows
targetos: Windows
req.typenames: 
---

# IPrintOemDriverUI::DrvGetDriverSetting


## -description


The <code>IPrintOemDriverUI::DrvGetDriverSetting</code> method is provided by the Unidrv and Pscript5 minidrivers so that user interface plug-ins can obtain the current status of printer features and other internal information.


## -parameters




### -param pci

Caller-supplied pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff559571">OEMUIOBJ</a> structure.


### -param Feature

Caller-supplied value identifying the printer feature for which option settings are returned. This can be either a string pointer or a constant, as described in the following Remarks section.


### -param pOutput

Caller-supplied pointer to a buffer to receive the specified information.


### -param cbSize

Caller-supplied size, in bytes, of the buffer pointed to by <i>pOutput</i>.


### -param pcbNeeded

Caller-supplied pointer to a location to receive the minimum buffer size required to contain the requested information.


### -param pdwOptionsReturned

Caller-supplied pointer to a location to receive the number of option strings placed in <i>pOutput</i>.


## -returns



The method must return one of the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The operation succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_FAIL</b></dt>
</dl>
</td>
<td width="60%">
The operation failed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>
</td>
<td width="60%">
The method is not implemented.

</td>
</tr>
</table>
 




## -remarks



When calling the <code>IPrintOemDriverUI::DrvGetDriverSetting</code> method, a user interface plug-in can specify either a string pointer or a constant value for <i>pFeatureKeyword</i>.

<ul>
<li>
If <i>pFeatureKeyword</i> is a string, it must represent one of the following:<ul>
<li>A feature name specified in a <a href="https://msdn.microsoft.com/ebf12f61-6194-4033-92a2-2bbccc40a6fd">Unidrv minidriver</a> GPD file, or,</li>
<li>A keyword argument to an *<b>OpenUI</b> entry in a Pscript5 minidriver's PPD file.</li>
</ul>


The method returns one or more NULL-terminated strings in the buffer pointed to by <i>pOutput</i>. Each string represents the name of a currently selected option.The number of strings is returned in <i>pdwOptionsReturned</i>.

</li>
<li>
If <i>pFeatureKeyword</i> is a constant, it must be one of the <b>OEMGDS_</b>-prefixed constants defined in printoem.h. The method returns the value indicated by the specified constant by placing it in the buffer pointed to by <i>pOutput</i>. The value returned in <i>pdwOptionsReturned</i> is always 1.

</li>
</ul>


