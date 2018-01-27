---
UID: NF:prcomoem.IPrintCoreHelper.GetOption
title: IPrintCoreHelper::GetOption method
author: windows-driver-content
description: The IPrintCoreHelper::GetOption method gets a specified option for a given feature.
old-location: print\iprintcorehelper_getoption.htm
old-project: print
ms.assetid: 515eed09-d386-4908-9d76-4e64930af5ab
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: GetOption method [Print Devices], IPrintCoreHelper interface, print_unidrv-pscript_allplugins_38a01e42-9d70-47d1-9d3d-2b488af4c3f3.xml, IPrintCoreHelper, IPrintCoreHelper::GetOption, GetOption, GetOption method [Print Devices], print.iprintcorehelper_getoption, IPrintCoreHelper interface [Print Devices], GetOption method, prcomoem/IPrintCoreHelper::GetOption
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
-	prcomoem.h
apiname: 
-	IPrintCoreHelper.GetOption
product: Windows
targetos: Windows
req.typenames: *POEMPTOPTS, OEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintCoreHelper::GetOption method


## -description


The <b>IPrintCoreHelper::GetOption</b> method gets a specified option for a given feature.


## -syntax


````
HRESULT GetOption(
  [in]  const DEVMODE *pDevmode,
  [in]        DWORD   cbSize,
  [in]        PCSTR   pszFeatureRequested,
  [out]       PCSTR   *ppszOption
);
````


## -parameters




### -param pDevmode [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure. If this pointer is provided, <b>IPrintCoreHelper::GetOption</b> should use the DEVMODEW structure that is pointed to by <i>pDevmode</i> instead of the default or current DEVMODEW structure. If this method is called from the plug-in provider or from either <a href="https://msdn.microsoft.com/library/windows/hardware/ff553205">IPrintOemPS::DevMode</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff554230">IPrintOemUni::DevMode</a>, this parameter is required. In most other situations, the parameter should be <b>NULL</b>. When the core driver sets <i>pDevmode</i> to <b>NULL</b>, it modifies its internal state rather than that of the passed-in DEVMODEW structure. This is required during operations such as full UI replacement, where the DEVMODEW structure returned by a DDI, such as <a href="..\winddiui\nf-winddiui-drvdocumentpropertysheets.md">DrvDocumentPropertySheets</a>, is being serviced by the core driver's UI module.


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

Feature keywords are as defined in the GPD and PPD files. In addition, the Unidrv and Pscript5 drivers support several reserved keywords for options that are stored in their private <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structures. 

The caller should not free the string that is pointed to by <i>ppszOption</i> and should not modify the string in any way.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552955">IPrintCoreHelper::EnumOptions</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552963">IPrintCoreHelper::SetOptions</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintCoreHelper::GetOption method%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

