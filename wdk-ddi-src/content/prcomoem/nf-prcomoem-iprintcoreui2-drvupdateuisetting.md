---
UID: NF:prcomoem.IPrintCoreUI2.DrvUpdateUISetting
title: IPrintCoreUI2::DrvUpdateUISetting method
author: windows-driver-content
description: The IPrintCoreUI2::DrvUpdateUISetting method is provided by the Windows XP Pscript5 driver so that Pscript5 user interface plug-ins can notify the driver of a modified user interface option.
old-location: print\iprintcoreui2_drvupdateuisetting.htm
old-project: print
ms.assetid: 64cbb304-51f6-4db4-93cb-a64ea5e03599
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: DrvUpdateUISetting method [Print Devices], DrvUpdateUISetting method [Print Devices], IPrintCoreUI2 interface, DrvUpdateUISetting,IPrintCoreUI2.DrvUpdateUISetting, IPrintCoreUI2, IPrintCoreUI2 interface [Print Devices], DrvUpdateUISetting method, IPrintCoreUI2::DrvUpdateUISetting, prcomoem/IPrintCoreUI2::DrvUpdateUISetting, print.iprintcoreui2_drvupdateuisetting, print_unidrv-pscript_ui_47ba2d93-a51d-4140-8932-9c4caee1ca21.xml
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
req.lib: prcomoem.h
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Prcomoem.h
api_name:
-	IPrintCoreUI2.DrvUpdateUISetting
product: Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintCoreUI2::DrvUpdateUISetting method


## -description


The <code>IPrintCoreUI2::DrvUpdateUISetting</code> method is provided by the Windows XP Pscript5 driver so that Pscript5 user interface plug-ins can notify the driver of a modified user interface option.


## -syntax


````
STDMETHOD DrvUpdateUISetting(
   PVOID pci,
   PVOID pOptItem,
   DWORD dwPreviousSelection,
   DWORD dwMode
);
````


## -parameters




### -param pci

Caller-supplied pointer to an <a href="..\printoem\ns-printoem-_oemuiobj.md">OEMUIOBJ</a> structure. 


### -param pOptItem

Caller-supplied pointer to an <a href="..\compstui\ns-compstui-_optitem.md">OPTITEM</a> structure describing a user interface option item.


### -param dwPreviousSelection

Not used. 


### -param dwMode

Caller-supplied integer constant indicating to which property sheet page the supplied option item belongs. The following constants are valid. 

<table>
<tr>
<th>Value</th>
<th>Definition</th>
</tr>
<tr>
<td>
OEMCUIP_DOCPROP 

</td>
<td>
The supplied option item belongs to the Advanced page of the document property sheet. 

</td>
</tr>
<tr>
<td>
OEMCUIP_PRNPROP 

</td>
<td>
The supplied option item belongs to the Device Settings page of the printer property sheet. 

</td>
</tr>
<tr>
<td>
OEMCUIP_PRNPROP 

</td>
<td>
The supplied option item belongs to the Device Settings page of the printer property sheet. 

</td>
</tr>
</table>
 


## -returns



This method must return one of the following values.

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



This method is inherited from the <a href="https://msdn.microsoft.com/ed11789f-750d-4f29-b5e0-ab299a1388db">IPrintOemDriverUI COM Interface</a>, and can be called only by Windows XP Pscript5 UI plug-ins that do not fully replace the core driver's standard UI pages, and is supported during the UI plug-in's <a href="https://msdn.microsoft.com/library/windows/hardware/ff554173">IPrintOemUI::DocumentPropertySheets</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff554165">IPrintOemUI::DevicePropertySheets</a> functions, and their property sheet callback routines. When this method is supported, it has the same behavior as <a href="https://msdn.microsoft.com/library/windows/hardware/ff553115">IPrintOemDriverUI::DrvUpdateUISetting</a>. When it is not supported, this method should return E_NOTIMPL.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553115">IPrintOemDriverUI::DrvUpdateUISetting</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554165">IPrintOemUI::DevicePropertySheets</a>



<a href="..\prcomoem\nn-prcomoem-iprintcoreui2.md">IPrintCoreUI2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554173">IPrintOemUI::DocumentPropertySheets</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintCoreUI2::DrvUpdateUISetting method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

