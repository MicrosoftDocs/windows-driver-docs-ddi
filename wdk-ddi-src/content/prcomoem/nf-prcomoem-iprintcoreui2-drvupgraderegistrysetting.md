---
UID: NF:prcomoem.IPrintCoreUI2.DrvUpgradeRegistrySetting
title: IPrintCoreUI2::DrvUpgradeRegistrySetting (prcomoem.h)
description: The IPrintCoreUI2::DrvUpgradeRegistrySetting method is provided by the Windows XP Pscript5 driver so that Pscript5 user interface plug-ins can update device settings stored in the registry.
old-location: print\iprintcoreui2_drvupgraderegistrysetting.htm
tech.root: print
ms.assetid: c9fa1506-ffef-44a8-9b25-9033280e0c33
ms.date: 04/20/2018
ms.keywords: DrvUpgradeRegistrySetting, DrvUpgradeRegistrySetting method [Print Devices], DrvUpgradeRegistrySetting method [Print Devices],IPrintCoreUI2 interface, IPrintCoreUI2 interface [Print Devices],DrvUpgradeRegistrySetting method, IPrintCoreUI2.DrvUpgradeRegistrySetting, IPrintCoreUI2::DrvUpgradeRegistrySetting, prcomoem/IPrintCoreUI2::DrvUpgradeRegistrySetting, print.iprintcoreui2_drvupgraderegistrysetting, print_unidrv-pscript_ui_e7337077-8ed0-4c41-a182-99764e17b55c.xml
f1_keywords:
 - "prcomoem/IPrintCoreUI2.DrvUpgradeRegistrySetting"
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
- Prcomoem.h
api_name:
- IPrintCoreUI2.DrvUpgradeRegistrySetting
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintCoreUI2::DrvUpgradeRegistrySetting


## -description


The <code>IPrintCoreUI2::DrvUpgradeRegistrySetting</code> method is provided by the Windows XP Pscript5 driver so that Pscript5 user interface plug-ins can update device settings stored in the registry.


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



This method is inherited from the <a href="https://docs.microsoft.com/windows-hardware/drivers/print/iprintoemdriverui-com-interface">IPrintOemDriverUI COM Interface</a>, which includes a <code>DrvUpgradeRegistrySetting</code> method. The behavior of this method is exactly the same as that of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemdriverui-drvupgraderegistrysetting">IPrintOemDriverUI::DrvUpgradeRegistrySetting</a>. 

This method should be called only by the OEM's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemui-upgradeprinter">IPrintOemUI::UpgradePrinter</a> method.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nn-prcomoem-iprintcoreui2">IPrintCoreUI2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemdriverui-drvupgraderegistrysetting">IPrintOemDriverUI::DrvUpgradeRegistrySetting</a>
 

 

