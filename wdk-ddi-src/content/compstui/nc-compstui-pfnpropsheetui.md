---
UID: NC:compstui.PFNPROPSHEETUI
title: PFNPROPSHEETUI (compstui.h)
description: The PFNPROPSHEETUI function type is used by CPSUI applications (including printer interface DLLs) for defining page creation callbacks, which specify property sheet pages for creation.
old-location: print\pfnpropsheetui.htm
tech.root: print
ms.assetid: b78d0dd7-1fe9-4b7e-8f51-4b5dc5fa2571
ms.date: 04/20/2018
keywords: ["PFNPROPSHEETUI callback function"]
ms.keywords: PFNPROPSHEETUI, PFNPROPSHEETUI callback, PFNPROPSHEETUI callback function [Print Devices], compstui/PFNPROPSHEETUI, cpsuifnc_a30dfbce-634a-4eb9-b86c-fdd14d8333fd.xml, print.pfnpropsheetui
f1_keywords:
 - "compstui/PFNPROPSHEETUI"
req.header: compstui.h
req.include-header: Compstui.h
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
- UserDefined
api_location:
- compstui.h
api_name:
- PFNPROPSHEETUI
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFNPROPSHEETUI callback function


## -description


The PFNPROPSHEETUI function type is used by CPSUI applications (including printer interface DLLs) for defining <a href="https://docs.microsoft.com/windows-hardware/drivers/print/page-creation-callbacks">page creation callbacks</a>, which specify property sheet pages for creation.


## -parameters




### -param pPSUIInfo

CPSUI-supplied pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/ns-compstui-_propsheetui_info">PROPSHEETUI_INFO</a> structure.


### -param lParam

CPSUI-supplied integer value that is dependent on the contents of the <b>Reason</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/ns-compstui-_propsheetui_info">PROPSHEETUI_INFO</a> structure. Valid values are as follows:





#### PROPSHEETUI_REASON_BEFORE_INIT

This value is new to Windows 8 and it is provided only to the original PFNPROPSHEETUI parameter passed to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/nf-compstui-commonpropertysheetuia">CommonPropertySheetUI</a>.



#### PROPSHEETUI_REASON_DESTROY

The <i>lParam</i> value is nonzero if the user has selected the property sheet's <b>OK</b> or <b>Cancel</b> button. Otherwise the value is zero.





#### PROPSHEETUI_REASON_GET_ICON

The <i>lParam</i> value is a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/ns-compstui-_propsheetui_geticon_info">PROPSHEETUI_GETICON_INFO</a> structure.





#### PROPSHEETUI_REASON_GET_INFO_HEADER

The <i>lParam</i> value is a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/ns-compstui-_propsheetui_info_header">PROPSHEETUI_INFO_HEADER</a> structure.





#### PROPSHEETUI_REASON_INIT

If the callback function is specified by the <i>pfnPropSheetUI</i> parameter to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/nf-compstui-commonpropertysheetuia">CommonPropertySheetUI</a>, <i>lParam</i> is the <i>lParam</i> value passed to <b>CommonPropertySheetUI</b>.

If the callback function is specified using the CPSFUNC_ADD_PFNPROPSHEETUI function code with CPSUI's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/nc-compstui-pfncompropsheet">ComPropSheet</a> function, <i>lParam</i> is the <i>lParam2</i> value passed to <b>ComPropSheet</b>.

CPSUI copies the <i>lParam</i> value into the <b>lParamInit</b> member of the function's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/ns-compstui-_propsheetui_info">PROPSHEETUI_INFO</a> structure.

The <i>lParam</i> value must not reside on the application's stack.





#### PROPSHEETUI_REASON_SET_RESULT

The <i>lParam</i> value is a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/ns-compstui-_setresult_info">SETRESULT_INFO</a> structure.


## -returns



If the operation succeeds, the function should return a value of one (or greater). Otherwise it should return a value less than one.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>One or greater.</b></dt>
</dl>
</td>
<td width="60%">
The PFNPROPSHEETUI function associated with the parent of the current page will be called.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Less than 1.</b></dt>
</dl>
</td>
<td width="60%">
The PFNPROPSHEETUI function associated with the parent of the current page will not be called.

</td>
</tr>
</table>
 




## -remarks



Callback functions specified using the PFNPROPSHEETUI function type are supplied by applications that use <a href="https://docs.microsoft.com/windows-hardware/drivers/print/common-property-sheet-user-interface">CPSUI</a> to manage customized property sheet pages. One such callback function must be specified when an application calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/nf-compstui-commonpropertysheetuia">CommonPropertySheetUI</a> function. For example, when the NT-based operating system print spooler calls CPSUI's <b>CommonPropertySheetUI</b> function to support its <b>DocumentProperties</b> or <b>PrinterProperties</b> API functions (described in the Microsoft Windows SDK documentation), the spooler specifies an internal PFNPROPSHEETUI-typed callback function. 

Applications can specify additional PFNPROPSHEETUI-typed callback functions by calling CPSUI's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/nc-compstui-pfncompropsheet">ComPropSheet</a> function with a function code of <a href="https://docs.microsoft.com/previous-versions/ff546391(v=vs.85)">CPSFUNC_ADD_PFNPROPSHEETUI</a>. For example, the NT-based operating system print spooler does this to notify CPSUI of the existence of a printer interface DLL's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvdocumentpropertysheets">DrvDocumentPropertySheets</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvdevicepropertysheets">DrvDevicePropertySheets</a> functions. Likewise, Microsoft's <a href="https://docs.microsoft.com/windows-hardware/drivers/">Unidrv</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/">Pscript</a> drivers use this technique to notify CPSUI of the existence of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemui-documentpropertysheets">IPrintOemUI::DocumentPropertySheets</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemui-devicepropertysheets">IPrintOemUI::DevicePropertySheets</a> methods in <a href="https://docs.microsoft.com/windows-hardware/drivers/print/user-interface-plug-ins">user interface plug-ins</a>.

Each PFNPROPSHEETUI-typed callback function is called by CPSUI several times. The <b>Reason</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/ns-compstui-_propsheetui_info">PROPSHEETUI_INFO</a> structure stipulates the operation that the function should perform, as follows:













