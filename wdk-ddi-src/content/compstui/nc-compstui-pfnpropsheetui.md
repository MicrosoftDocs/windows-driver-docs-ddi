---
UID: NC:compstui.PFNPROPSHEETUI
title: PFNPROPSHEETUI
author: windows-driver-content
description: The PFNPROPSHEETUI function type is used by CPSUI applications (including printer interface DLLs) for defining page creation callbacks, which specify property sheet pages for creation.
old-location: print\pfnpropsheetui.htm
old-project: print
ms.assetid: b78d0dd7-1fe9-4b7e-8f51-4b5dc5fa2571
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: _POWERSOURCEUPDATEEX, *PPOWERSOURCEUPDATEEX, POWERSOURCEUPDATEEX
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
req.alt-api: PFNPROPSHEETUI
req.alt-loc: compstui.h
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
req.typenames: *PPOWERSOURCEUPDATEEX, POWERSOURCEUPDATEEX
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




### -param PROPSHEETUI_REASON_BEFORE_INIT

This value is new to Windows 8 and it is provided only to the original PFNPROPSHEETUI parameter passed to <a href="https://msdn.microsoft.com/library/windows/hardware/ff546148">CommonPropertySheetUI</a>.


### -param PROPSHEETUI_REASON_DESTROY

The <i>lParam</i> value is nonzero if the user has selected the property sheet's <b>OK</b> or <b>Cancel</b> button. Otherwise the value is zero.

</dd>
</dl>



### -param PROPSHEETUI_REASON_GET_ICON

The <i>lParam</i> value is a pointer to a <a href="..\compstui\ns-compstui-_propsheetui_geticon_info.md">PROPSHEETUI_GETICON_INFO</a> structure.

</dd>
</dl>



### -param PROPSHEETUI_REASON_GET_INFO_HEADER

The <i>lParam</i> value is a pointer to a <a href="..\compstui\ns-compstui-_propsheetui_info_header.md">PROPSHEETUI_INFO_HEADER</a> structure.

</dd>
</dl>



### -param PROPSHEETUI_REASON_INIT

If the callback function is specified by the <i>pfnPropSheetUI</i> parameter to <a href="https://msdn.microsoft.com/library/windows/hardware/ff546148">CommonPropertySheetUI</a>, <i>lParam</i> is the <i>lParam</i> value passed to <b>CommonPropertySheetUI</b>.

If the callback function is specified using the CPSFUNC_ADD_PFNPROPSHEETUI function code with CPSUI's <a href="https://msdn.microsoft.com/library/windows/hardware/ff546207">ComPropSheet</a> function, <i>lParam</i> is the <i>lParam2</i> value passed to <b>ComPropSheet</b>.

CPSUI copies the <i>lParam</i> value into the <b>lParamInit</b> member of the function's <a href="..\compstui\ns-compstui-_propsheetui_info.md">PROPSHEETUI_INFO</a> structure.

The <i>lParam</i> value must not reside on the application's stack.

</dd>
</dl>



### -param PROPSHEETUI_REASON_SET_RESULT

The <i>lParam</i> value is a pointer to a <a href="..\compstui\ns-compstui-_setresult_info.md">SETRESULT_INFO</a> structure.

</dd>
</dl>

## -returns
If the operation succeeds, the function should return a value of one (or greater). Otherwise it should return a value less than one.
<dl>
<dt><b>One or greater.</b></dt>
</dl>The PFNPROPSHEETUI function associated with the parent of the current page will be called.
<dl>
<dt><b>Less than 1.</b></dt>
</dl>The PFNPROPSHEETUI function associated with the parent of the current page will not be called.

 


## -remarks
Callback functions specified using the PFNPROPSHEETUI function type are supplied by applications that use <a href="https://msdn.microsoft.com/7af3435a-19e0-40a1-9f94-319d9d323856">CPSUI</a> to manage customized property sheet pages. One such callback function must be specified when an application calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546148">CommonPropertySheetUI</a> function. For example, when the NT-based operating system print spooler calls CPSUI's <b>CommonPropertySheetUI</b> function to support its <b>DocumentProperties</b> or <b>PrinterProperties</b> API functions (described in the Microsoft Windows SDK documentation), the spooler specifies an internal PFNPROPSHEETUI-typed callback function. 

Applications can specify additional PFNPROPSHEETUI-typed callback functions by calling CPSUI's <a href="https://msdn.microsoft.com/library/windows/hardware/ff546207">ComPropSheet</a> function with a function code of <a href="https://msdn.microsoft.com/library/windows/hardware/ff546391">CPSFUNC_ADD_PFNPROPSHEETUI</a>. For example, the NT-based operating system print spooler does this to notify CPSUI of the existence of a printer interface DLL's <a href="..\winddiui\nf-winddiui-drvdocumentpropertysheets.md">DrvDocumentPropertySheets</a> and <a href="..\winddiui\nf-winddiui-drvdevicepropertysheets.md">DrvDevicePropertySheets</a> functions. Likewise, Microsoft's <a href="wdkgloss.u#wdkgloss.unidrv#wdkgloss.unidrv"><i>Unidrv</i></a> and <a href="wdkgloss.p#wdkgloss.pscript#wdkgloss.pscript"><i>Pscript</i></a> drivers use this technique to notify CPSUI of the existence of <a href="https://msdn.microsoft.com/library/windows/hardware/ff554173">IPrintOemUI::DocumentPropertySheets</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff554165">IPrintOemUI::DevicePropertySheets</a> methods in <a href="https://msdn.microsoft.com/22ac2af6-37d8-4913-95af-9c3dc8576d40">user interface plug-ins</a>.

Each PFNPROPSHEETUI-typed callback function is called by CPSUI several times. The <b>Reason</b> member of the <a href="..\compstui\ns-compstui-_propsheetui_info.md">PROPSHEETUI_INFO</a> structure stipulates the operation that the function should perform, as follows:



This <i>lParam</i> value is used between the common printer UI and the system-provided configuration
module for v4 printer drivers. This value should be ignored by v3 printer drivers, which should return -1 in this case.

The callback function should release resources that were allocated in response to PROPSHEETUI_REASON_INIT.

The callback function should call <b>LoadImage</b> (described in the Windows SDK documentation) to load an icon resource, using parameters specified by the <a href="..\compstui\ns-compstui-_propsheetui_geticon_info.md">PROPSHEETUI_GETICON_INFO</a> structure pointed to be <i>lParam</i>, and it should return the icon's handle in the structure.

The callback function should supply page header information in the <a href="..\compstui\ns-compstui-_propsheetui_info_header.md">PROPSHEETUI_INFO_HEADER</a> structure pointed to by <i>lParam</i>.

The callback function should call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546207">ComPropSheet</a> function to specify property sheet pages. (This is always the first reason received.)

The callback function receives result information in the <a href="..\compstui\ns-compstui-_setresult_info.md">SETRESULT_INFO</a> structure pointed to by <i>lParam</i>. This is application-supplied status information, specified by calling CPSUI's <a href="https://msdn.microsoft.com/library/windows/hardware/ff546207">ComPropSheet</a> function with a function code of CPSFUNC_SET_RESULT.

For more information about handling this reason value, see the description of <a href="..\compstui\ns-compstui-_setresult_info.md">SETRESULT_INFO</a>. </p>