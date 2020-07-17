---
UID: NF:prcomoem.IPrintCoreUI2.DrvGetDriverSetting
title: IPrintCoreUI2::DrvGetDriverSetting (prcomoem.h)
description: The IPrintCoreUI2::DrvGetDriverSetting method is provided by the Windows XP Pscript5 driver so that Pscript5 user interface plug-ins can obtain the current status of printer features and other internal information.
old-location: print\iprintcoreui2_drvgetdriversetting.htm
tech.root: print
ms.assetid: 501ff6f1-c5f1-4ad7-be96-a95ba3e34622
ms.date: 04/20/2018
keywords: ["IPrintCoreUI2::DrvGetDriverSetting"]
ms.keywords: DrvGetDriverSetting, DrvGetDriverSetting method [Print Devices], DrvGetDriverSetting method [Print Devices],IPrintCoreUI2 interface, IPrintCoreUI2 interface [Print Devices],DrvGetDriverSetting method, IPrintCoreUI2.DrvGetDriverSetting, IPrintCoreUI2::DrvGetDriverSetting, prcomoem/IPrintCoreUI2::DrvGetDriverSetting, print.iprintcoreui2_drvgetdriversetting, print_unidrv-pscript_ui_cb699f2f-d919-4aec-8787-d466a5e8461c.xml
f1_keywords:
 - "prcomoem/IPrintCoreUI2.DrvGetDriverSetting"
 - "IPrintCoreUI2.DrvGetDriverSetting"
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
- IPrintCoreUI2.DrvGetDriverSetting
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintCoreUI2::DrvGetDriverSetting


## -description


The <code>IPrintCoreUI2::DrvGetDriverSetting</code> method is provided by the Windows XP Pscript5 driver so that Pscript5 user interface plug-ins can obtain the current status of printer features and other internal information.


## -parameters




### -param pci

Caller-supplied pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/printoem/ns-printoem-_oemuiobj">OEMUIOBJ</a> structure. 


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



This method is inherited from the <a href="https://docs.microsoft.com/windows-hardware/drivers/print/iprintoemdriverui-com-interface">IPrintOemDriverUI COM Interface</a>, and can be called only by Windows XP and later Pscript5 UI plug-ins that do not fully replace the core driver's standard UI pages, and is supported during the UI plug-in's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemui-documentpropertysheets">IPrintOemUI::DocumentPropertySheets</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemui-devicepropertysheets">IPrintOemUI::DevicePropertySheets</a> functions, and their property sheet callback routines. When this method is supported, it has the same behavior as <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemdriverui-drvgetdriversetting">IPrintOemDriverUI::DrvGetDriverSetting</a>. When it is not supported, this method should return E_NOTIMPL.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nn-prcomoem-iprintcoreui2">IPrintCoreUI2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemdriverui-drvgetdriversetting">IPrintOemDriverUI::DrvGetDriverSetting</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemui-devicepropertysheets">IPrintOemUI::DevicePropertySheets</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemui-documentpropertysheets">IPrintOemUI::DocumentPropertySheets</a>
 

 

