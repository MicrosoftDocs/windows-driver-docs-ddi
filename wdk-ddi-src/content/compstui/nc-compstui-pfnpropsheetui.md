---
UID: NC:compstui.PFNPROPSHEETUI
title: PFNPROPSHEETUI
author: windows-driver-content
description: The PFNPROPSHEETUI function type is used by CPSUI applications (including printer interface DLLs) for defining page creation callbacks, which specify property sheet pages for creation.
old-location: print\pfnpropsheetui.htm
old-project: print
ms.assetid: b78d0dd7-1fe9-4b7e-8f51-4b5dc5fa2571
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFNPROPSHEETUI, PFNPROPSHEETUI callback function [Print Devices], compstui/PFNPROPSHEETUI, cpsuifnc_a30dfbce-634a-4eb9-b86c-fdd14d8333fd.xml, print.pfnpropsheetui
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	compstui.h
api_name:
-	PFNPROPSHEETUI
product: Windows
targetos: Windows
req.typenames: POWERSOURCEUPDATEEX, *PPOWERSOURCEUPDATEEX
---

# PFNPROPSHEETUI callback


## -description


The PFNPROPSHEETUI function type is used by CPSUI applications (including printer interface DLLs) for defining <a href="https://msdn.microsoft.com/ec514d17-415e-417b-bb29-b37be43c3cf6">page creation callbacks</a>, which specify property sheet pages for creation.


## -prototype


````
LONG PFNPROPSHEETUI(
   PPROPSHEETUI_INFO pPSUIInfo,
   LPARAM            lParam
);
````


## -parameters




### -param pPSUIInfo

CPSUI-supplied pointer to a <a href="..\compstui\ns-compstui-_propsheetui_info.md">PROPSHEETUI_INFO</a> structure.


### -param lParam

CPSUI-supplied integer value that is dependent on the contents of the <b>Reason</b> member of the <a href="..\compstui\ns-compstui-_propsheetui_info.md">PROPSHEETUI_INFO</a> structure. Valid values are as follows:





#### PROPSHEETUI_REASON_BEFORE_INIT

This value is new to Windows 8 and it is provided only to the original PFNPROPSHEETUI parameter passed to <a href="https://msdn.microsoft.com/library/windows/hardware/ff546148">CommonPropertySheetUI</a>.



#### PROPSHEETUI_REASON_DESTROY

The <i>lParam</i> value is nonzero if the user has selected the property sheet's <b>OK</b> or <b>Cancel</b> button. Otherwise the value is zero.





#### PROPSHEETUI_REASON_GET_ICON

The <i>lParam</i> value is a pointer to a <a href="..\compstui\ns-compstui-_propsheetui_geticon_info.md">PROPSHEETUI_GETICON_INFO</a> structure.





#### PROPSHEETUI_REASON_GET_INFO_HEADER

The <i>lParam</i> value is a pointer to a <a href="..\compstui\ns-compstui-_propsheetui_info_header.md">PROPSHEETUI_INFO_HEADER</a> structure.





#### PROPSHEETUI_REASON_INIT

If the callback function is specified by the <i>pfnPropSheetUI</i> parameter to <a href="https://msdn.microsoft.com/library/windows/hardware/ff546148">CommonPropertySheetUI</a>, <i>lParam</i> is the <i>lParam</i> value passed to <b>CommonPropertySheetUI</b>.

If the callback function is specified using the CPSFUNC_ADD_PFNPROPSHEETUI function code with CPSUI's <a href="https://msdn.microsoft.com/library/windows/hardware/ff546207">ComPropSheet</a> function, <i>lParam</i> is the <i>lParam2</i> value passed to <b>ComPropSheet</b>.

CPSUI copies the <i>lParam</i> value into the <b>lParamInit</b> member of the function's <a href="..\compstui\ns-compstui-_propsheetui_info.md">PROPSHEETUI_INFO</a> structure.

The <i>lParam</i> value must not reside on the application's stack.





#### PROPSHEETUI_REASON_SET_RESULT

The <i>lParam</i> value is a pointer to a <a href="..\compstui\ns-compstui-_setresult_info.md">SETRESULT_INFO</a> structure.


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



Callback functions specified using the PFNPROPSHEETUI function type are supplied by applications that use <a href="https://msdn.microsoft.com/7af3435a-19e0-40a1-9f94-319d9d323856">CPSUI</a> to manage customized property sheet pages. One such callback function must be specified when an application calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546148">CommonPropertySheetUI</a> function. For example, when the NT-based operating system print spooler calls CPSUI's <b>CommonPropertySheetUI</b> function to support its <b>DocumentProperties</b> or <b>PrinterProperties</b> API functions (described in the Microsoft Windows SDK documentation), the spooler specifies an internal PFNPROPSHEETUI-typed callback function. 

Applications can specify additional PFNPROPSHEETUI-typed callback functions by calling CPSUI's <a href="https://msdn.microsoft.com/library/windows/hardware/ff546207">ComPropSheet</a> function with a function code of <a href="https://msdn.microsoft.com/library/windows/hardware/ff546391">CPSFUNC_ADD_PFNPROPSHEETUI</a>. For example, the NT-based operating system print spooler does this to notify CPSUI of the existence of a printer interface DLL's <a href="..\winddiui\nf-winddiui-drvdocumentpropertysheets.md">DrvDocumentPropertySheets</a> and <a href="..\winddiui\nf-winddiui-drvdevicepropertysheets.md">DrvDevicePropertySheets</a> functions. Likewise, Microsoft's <a href="https://msdn.microsoft.com/0a51fa2b-3d09-4a5f-9fff-40604877a414">Unidrv</a> and <a href="https://msdn.microsoft.com/139a10e9-203b-499b-9291-8537eae9189c">Pscript</a> drivers use this technique to notify CPSUI of the existence of <a href="https://msdn.microsoft.com/library/windows/hardware/ff554173">IPrintOemUI::DocumentPropertySheets</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff554165">IPrintOemUI::DevicePropertySheets</a> methods in <a href="https://msdn.microsoft.com/22ac2af6-37d8-4913-95af-9c3dc8576d40">user interface plug-ins</a>.

Each PFNPROPSHEETUI-typed callback function is called by CPSUI several times. The <b>Reason</b> member of the <a href="..\compstui\ns-compstui-_propsheetui_info.md">PROPSHEETUI_INFO</a> structure stipulates the operation that the function should perform, as follows:













