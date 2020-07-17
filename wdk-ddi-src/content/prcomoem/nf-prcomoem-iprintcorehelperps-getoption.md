---
UID: NF:prcomoem.IPrintCoreHelperPS.GetOption
title: IPrintCoreHelperPS::GetOption (prcomoem.h)
description: The IPrintCoreHelperPS::GetOption method gets a specified option for a given feature.
old-location: print\iprintcorehelperps_getoption.htm
tech.root: print
ms.assetid: fa212b86-89ae-4d22-a3ff-ebcc6100874b
ms.date: 04/20/2018
keywords: ["IPrintCoreHelperPS::GetOption"]
ms.keywords: GetOption, GetOption method [Print Devices], GetOption method [Print Devices],IPrintCoreHelperPS interface, IPrintCoreHelperPS interface [Print Devices],GetOption method, IPrintCoreHelperPS.GetOption, IPrintCoreHelperPS::GetOption, prcomoem/IPrintCoreHelperPS::GetOption, print.iprintcorehelperps_getoption, print_unidrv-pscript_allplugins_86ad53d5-280d-4aa5-9780-dd2b946f9880.xml
f1_keywords:
 - "prcomoem/IPrintCoreHelperPS.GetOption"
 - "IPrintCoreHelperPS.GetOption"
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
- IPrintCoreHelperPS.GetOption
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPrintCoreHelperPS::GetOption


## -description


The <b>IPrintCoreHelperPS::GetOption</b> method gets a specified option for a given feature.


## -parameters




### -param pDevmode [in, optional]

A pointer to a <a href="https://docs.microsoft.com/windows/win32/api/wingdi/ns-wingdi-devicemodew">DEVMODEW</a>structure. If this pointer is provided, <b>IPrintCoreHelperPS::GetOption</b> should use the DEVMODEW structure that is pointed to by <i>pDevmode</i> instead of the default or current DEVMODEW structure. If this method is called from the plug-in provider or from <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemps-devmode">IPrintOemPS::DevMode</a>, this parameter is required. In most other situations, the parameter should be <b>NULL</b>. When the core driver sets <i>pDevmode</i> to <b>NULL</b>, it modifies its internal state rather than that of the passed-in DEVMODEW structure. This is required during operations such as full UI replacement, where the DEVMODEW structure returned by a DDI, such as <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvdocumentpropertysheets">DrvDocumentPropertySheets</a>, is being serviced by the core driver's UI module.


### -param cbSize [in]

The size, in bytes, of the DEVMODEW structure that is pointed to by the <i>pDevmode</i> parameter.


### -param pszFeatureRequested [in]

A pointer to the ANSI string that contains the name of the feature as it appears in the PPD file.


### -param ppszOption [out]

A pointer to a variable that contains the address of an ANSI string. When <b>IPrintCoreHelperPS::GetOption</b> returns, the string should contain the keyword for the currently selected option as it appears in the configuration file. The caller should not modify this string and should not free the memory that is associated with this string.


## -returns



<b>IPrintCoreHelperPS::GetOption</b> should return one of the following values.

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



<b>IPrintCoreHelperPS::GetOption</b> cannot be used for features that allow multiple options to be set simultaneously. 

Feature keywords are as defined in the PPD file. In addition, the Pscript5 driver supports several reserved keywords for options that are stored in its private <a href="https://docs.microsoft.com/windows/win32/api/wingdi/ns-wingdi-devicemodew">DEVMODEW</a>structure. For the list of Pscript5 features, see <a href="https://docs.microsoft.com/windows-hardware/drivers/print/keyword-mapping">Keyword Mapping</a>. 

The caller should not free the string that is pointed to by <i>ppszOption</i> and should not modify the string in any way.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nn-prcomoem-iprintcorehelperps">IPrintCoreHelperPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintcorehelperps-enumoptions">IPrintCoreHelperPS::EnumOptions</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintcorehelperps-setoptions">IPrintCoreHelperPS::SetOptions</a>
 

 

