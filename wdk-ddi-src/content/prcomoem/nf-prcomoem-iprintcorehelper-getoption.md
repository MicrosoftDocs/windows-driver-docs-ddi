---
UID: NF:prcomoem.IPrintCoreHelper.GetOption
title: IPrintCoreHelper::GetOption (prcomoem.h)
description: The IPrintCoreHelper::GetOption method gets a specified option for a given feature.
old-location: print\iprintcorehelper_getoption.htm
tech.root: print
ms.assetid: 515eed09-d386-4908-9d76-4e64930af5ab
ms.date: 04/20/2018
keywords: ["IPrintCoreHelper::GetOption"]
ms.keywords: GetOption, GetOption method [Print Devices], GetOption method [Print Devices],IPrintCoreHelper interface, IPrintCoreHelper interface [Print Devices],GetOption method, IPrintCoreHelper.GetOption, IPrintCoreHelper::GetOption, prcomoem/IPrintCoreHelper::GetOption, print.iprintcorehelper_getoption, print_unidrv-pscript_allplugins_38a01e42-9d70-47d1-9d3d-2b488af4c3f3.xml
f1_keywords:
 - "prcomoem/IPrintCoreHelper.GetOption"
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
- IPrintCoreHelper.GetOption
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintCoreHelper::GetOption


## -description


The <b>IPrintCoreHelper::GetOption</b> method gets a specified option for a given feature.


## -parameters




### -param pDevmode [in]

A pointer to a <a href="https://docs.microsoft.com/windows/win32/api/wingdi/ns-wingdi-devicemodew">DEVMODEW</a> structure. If this pointer is provided, <b>IPrintCoreHelper::GetOption</b> should use the DEVMODEW structure that is pointed to by <i>pDevmode</i> instead of the default or current DEVMODEW structure. If this method is called from the plug-in provider or from either <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemps-devmode">IPrintOemPS::DevMode</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemuni-devmode">IPrintOemUni::DevMode</a>, this parameter is required. In most other situations, the parameter should be <b>NULL</b>. When the core driver sets <i>pDevmode</i> to <b>NULL</b>, it modifies its internal state rather than that of the passed-in DEVMODEW structure. This is required during operations such as full UI replacement, where the DEVMODEW structure returned by a DDI, such as <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvdocumentpropertysheets">DrvDocumentPropertySheets</a>, is being serviced by the core driver's UI module.


### -param cbSize [in]

The size, in bytes, of the DEVMODEW structure that is pointed to by the <i>pDevmode</i> parameter.


### -param pszFeatureRequested [in]

A pointer to the ANSI string that contains the name of the feature as it appears in the GPD file.


### -param ppszOption [out]

A pointer to a variable that contains the address of an ANSI string. When <b>IPrintCoreHelper::GetOption</b> returns, the string should contain the keyword for the currently selected option as it appears in the configuration file. The caller should not modify this string and should not free the memory that is associated with this string.


## -returns



<b>IPrintCoreHelper::GetOption</b> should return one of the following values.

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
The method read the option for the specified feature.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_FAIL</b></dt>
</dl>
</td>
<td width="60%">
The caller provided information that resulted in an invalid request. For example, the feature that was requested does not exist.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
The arguments were invalid. This value might mean that the feature is not supported or that too many options were requested for the feature.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
The core driver was not able to service the request because there was insufficient memory.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_UNEXPECTED, or other return codes not listed here</b></dt>
</dl>
</td>
<td width="60%">
The core driver seems to be in an invalid state. The caller should return a failure code.

</td>
</tr>
</table>
 




## -remarks



<b>IPrintCoreHelper::GetOption</b> cannot be used for features that allow multiple options to be set simultaneously. 

Feature keywords are as defined in the GPD and PPD files. In addition, the Unidrv and Pscript5 drivers support several reserved keywords for options that are stored in their private <a href="https://docs.microsoft.com/windows/win32/api/wingdi/ns-wingdi-devicemodew">DEVMODEW</a> structures. 

The caller should not free the string that is pointed to by <i>ppszOption</i> and should not modify the string in any way.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nn-prcomoem-iprintcorehelper">IPrintCoreHelper</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintcorehelper-enumoptions">IPrintCoreHelper::EnumOptions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintcorehelper-setoptions">IPrintCoreHelper::SetOptions</a>
 

 

