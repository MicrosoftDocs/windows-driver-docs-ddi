---
UID: NF:prcomoem.IPrintOemUI2.HideStandardUI
title: IPrintOemUI2::HideStandardUI (prcomoem.h)
description: The IPrintOemUI2::HideStandardUI method allows a user interface plug-in to specify whether the standard property sheets should be displayed or hidden.
old-location: print\iprintoemui2_hidestandardui.htm
tech.root: print
ms.assetid: 144618d0-0d77-487c-a074-8bd9f6030de2
ms.date: 04/20/2018
ms.keywords: HideStandardUI, HideStandardUI method [Print Devices], HideStandardUI method [Print Devices],IPrintOemUI2 interface, IPrintOemUI2 interface [Print Devices],HideStandardUI method, IPrintOemUI2.HideStandardUI, IPrintOemUI2::HideStandardUI, prcomoem/IPrintOemUI2::HideStandardUI, print.iprintoemui2_hidestandardui, print_unidrv-pscript_ui_27b169d4-4e08-496c-b9d1-1b73dc27995b.xml
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- prcomoem.h
api_name:
- IPrintOemUI2.HideStandardUI
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintOemUI2::HideStandardUI


## -description


The <code>IPrintOemUI2::HideStandardUI</code> method allows a user interface plug-in to specify whether the standard property sheets should be displayed or hidden. Beginning with Microsoft Windows XP, this method can be implemented by a Pscript5 user interface plug-in. Beginning with Windows Vista, this method can be implemented by a Unidrv user interface plug-in.


## -parameters




### -param dwMode

Specifies which type of property sheet UI -- document property sheet or device property sheet -- to hide. This parameter should be set to one of the following constants, which are defined in printoem.h:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
OEMCUIP_DOCPROP

</td>
<td>
Hide standard document property sheet UI.

</td>
</tr>
<tr>
<td>
OEMCUIP_PRNPROP

</td>
<td>
Hide standard device property sheet UI.

</td>
</tr>
</table>
 


## -returns



On success, this method should return S_OK. Otherwise, it should return E_NOTIMPL. See Remarks for additional information.




## -remarks



This method is supported in Windows Vista for Pscript 5 and Unidrv plug-ins, and in Windows XP only for Pscript5 plug-ins.

Within the <a href="https://msdn.microsoft.com/library/windows/hardware/ff548548">DrvDocumentPropertySheets</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff548542">DrvDevicePropertySheets</a> DDIs when pPSUIInfo-->Reason is set to PROPSHEETUI_REASON_INIT, the driver calls the <code>IPrintOemUI2::HideStandardUI</code> method to ask the UI plug-in about user interface requests. This method can respond in any of four ways: 

<ol>
<li>
Hide standard document property sheet UI.

</li>
<li>
Hide standard device property sheet UI.

</li>
<li>
Hide all standard property sheet UI.

</li>
<li>
Do not hide any standard property sheet UI.

</li>
</ol>
The following table summarizes how the <code>IPrintOemUI2::HideStandardUI</code> method would respond in each of these situations.

<table>
<tr>
<th>To indicate this response...</th>
<th>IPrintOemUI2::HideStandardUI returns...</th>
</tr>
<tr>
<td>
Hide standard document property sheet UI. The plug-in implements its own document property sheet UI.

</td>
<td>
If <i>dwMode</i> == OEMCUIP_DOCPROP, return S_OK; otherwise return E_NOTIMPL.

</td>
</tr>
<tr>
<td>
Hide standard device property sheet UI. The plug-in implements its own device property sheet UI.

</td>
<td>
If <i>dwMode</i> == OEMCUIP_PRNPROP, return S_OK; otherwise return E_NOTIMPL.

</td>
</tr>
<tr>
<td>
Hide all standard property sheet UI. The plug-in implements its own document property sheet and device property sheet UI.

</td>
<td>
Return S_OK, regardless of the value of <i>dwMode</i>.

</td>
</tr>
<tr>
<td>
Display all standard property sheet UI.

</td>
<td>
Return E_NOTIMPL, regardless of the value of <i>dwMode</i>.

</td>
</tr>
</table>
 

If the <code>IPrintOemUI2::HideStandardUI</code> method indicates to the driver that all standard property sheets should be hidden, the driver omits calls to compstui.dll (see <a href="https://msdn.microsoft.com/9f3bd004-e62c-42b6-99da-045c12e088a3">Pscript Components</a>) to add the standard property sheets. A UI plug-in must implement at least one custom property sheet UI if <code>IPrintOemUI2::HideStandardUI</code> returns S_OK.

When the printer has multiple UI plug-ins installed, the driver calls UI plug-ins in the order they were installed, until one of them returns S_OK, or until all of the UI plug-ins have been called and none of them returned S_OK. The former case indicates to the driver that the standard property sheet UI should be hidden. The latter case indicates to the driver that the standard property sheet UI should be displayed.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff548542">DrvDevicePropertySheets</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548548">DrvDocumentPropertySheets</a>



<a href="https://msdn.microsoft.com/9b7afb56-7abb-4f20-b69d-12a28d7e3617">IPrintOemUI2</a>
 

 

