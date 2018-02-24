---
UID: NF:prcomoem.IPrintCoreUI2.DrvUpgradeRegistrySetting
title: IPrintCoreUI2::DrvUpgradeRegistrySetting method
author: windows-driver-content
description: The IPrintCoreUI2::DrvUpgradeRegistrySetting method is provided by the Windows XP Pscript5 driver so that Pscript5 user interface plug-ins can update device settings stored in the registry.
old-location: print\iprintcoreui2_drvupgraderegistrysetting.htm
old-project: print
ms.assetid: c9fa1506-ffef-44a8-9b25-9033280e0c33
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: IPrintCoreUI2, print_unidrv-pscript_ui_e7337077-8ed0-4c41-a182-99764e17b55c.xml, prcomoem/IPrintCoreUI2::DrvUpgradeRegistrySetting, DrvUpgradeRegistrySetting method [Print Devices], IPrintCoreUI2 interface, DrvUpgradeRegistrySetting method [Print Devices], DrvUpgradeRegistrySetting, IPrintCoreUI2::DrvUpgradeRegistrySetting, print.iprintcoreui2_drvupgraderegistrysetting, IPrintCoreUI2 interface [Print Devices], DrvUpgradeRegistrySetting method
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Prcomoem.h
apiname:
-	IPrintCoreUI2.DrvUpgradeRegistrySetting
product: Windows
targetos: Windows
req.typenames: "*POEMPTOPTS, OEMPTOPTS"
req.product: Windows 10 or later.
---

# IPrintCoreUI2::DrvUpgradeRegistrySetting method


## -description


The <code>IPrintCoreUI2::DrvUpgradeRegistrySetting</code> method is provided by the Windows XP Pscript5 driver so that Pscript5 user interface plug-ins can update device settings stored in the registry.


## -syntax


````
STDMETHOD DrvUpgradeRegistrySetting(
   HANDLE hPrinter ,
   PCSTR  pFeature,
   PCSTR  pOption
);
````


## -parameters




### -param hPrinter

Caller-supplied printer handle.


### -param pFeature

Caller-supplied pointer to a string identifying a printer feature name contained in the printer's GPD or PPD file.


### -param pOption

Caller-supplied pointer to a string identifying an option name, associated with the specified feature, contained in the printer's GPD or PPD file.


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



This method is inherited from the <a href="https://msdn.microsoft.com/ed11789f-750d-4f29-b5e0-ab299a1388db">IPrintOemDriverUI COM Interface</a>, which includes a <code>DrvUpgradeRegistrySetting</code> method. The behavior of this method is exactly the same as that of <a href="https://msdn.microsoft.com/library/windows/hardware/ff553118">IPrintOemDriverUI::DrvUpgradeRegistrySetting</a>. 

This method should be called only by the OEM's <a href="https://msdn.microsoft.com/library/windows/hardware/ff554189">IPrintOemUI::UpgradePrinter</a> method.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553118">IPrintOemDriverUI::DrvUpgradeRegistrySetting</a>



<a href="https://msdn.microsoft.com/e2d2e486-d69d-4a6d-aaab-a7b8806665b4">IPrintCoreUI2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintCoreUI2::DrvUpgradeRegistrySetting method%20 RELEASE:%20(2/21/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

