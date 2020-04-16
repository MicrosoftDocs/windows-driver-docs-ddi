---
UID: NC:compstui.PFNCOMPROPSHEET
title: PFNCOMPROPSHEET (compstui.h)
description: The ComPropSheet function is supplied by CPSUI and can be called by CPSUI applications (including printer interface DLLs) to build property sheet pages.
old-location: print\compropsheet.htm
tech.root: print
ms.assetid: d9654346-1f28-4e02-8f6c-17e37ed09b92
ms.date: 04/20/2018
keywords: ["PFNCOMPROPSHEET callback function"]
ms.keywords: ComPropSheet, ComPropSheet routine [Print Devices], PFNCOMPROPSHEET, compstui/ComPropSheet, cpsuifnc_2586427b-a3ae-4c2e-b081-06d58ec310c3.xml, print.compropsheet
f1_keywords:
 - "compstui/ComPropSheet"
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
- ComPropSheet
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFNCOMPROPSHEET callback function


## -description


The <i>ComPropSheet</i> function is supplied by <a href="https://docs.microsoft.com/windows-hardware/drivers/print/common-property-sheet-user-interface">CPSUI</a> and can be called by CPSUI applications (including printer interface DLLs) to build property sheet pages.


## -parameters




### -param hComPropSheet [in]

Caller-supplied handle to a property sheet <a href="https://docs.microsoft.com/windows-hardware/drivers/print/group-parent">group parent</a>. For more information, see the following Remarks section.


### -param Function [in]

Caller-supplied, CPSFUNC_-prefixed ComPropSheet function codes specifying the operation to be performed by the <i>ComPropSheet</i> function.

<div class="alert"><b>Note</b>  See the <b>ComPropSheet</b> function codes table in the <b>Remarks</b> section below.</div>
<div> </div>

### -param lParam1 [in]

Caller-supplied value that depends on the <i>ComPropSheet</i> function code supplied for <i>Function</i>.


### -param lParam2 [in]

Caller-supplied value that depends on the <i>ComPropSheet</i> function code supplied for <i>Function</i>.


## -returns



The return value depends on the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_print/index">ComPropSheet function code</a> supplied for <i>Function</i>.




## -remarks



When CPSUI calls one of an application's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/nc-compstui-pfnpropsheetui">PFNPROPSHEETUI</a>-typed functions, it passes a pointer to the <i>ComPropSheet</i> function in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/ns-compstui-_propsheetui_info">PROPSHEETUI_INFO</a> structure. A <b>PFNPROPSHEETUI</b>-typed function can call the <i>ComPropSheet</i> function to describe property sheet pages to CPSUI.

A <a href="https://docs.microsoft.com/windows-hardware/drivers/print/printer-interface-dll">printer interface DLL</a> can call <i>ComPropSheet</i> from within its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvdocumentpropertysheets">DrvDocumentPropertySheets</a> function or its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvdevicepropertysheets">DrvDevicePropertySheets</a> function.


<a href="https://docs.microsoft.com/windows-hardware/drivers/print/user-interface-plug-ins">User interface plug-ins</a> for Microsoft's <a href="https://docs.microsoft.com/windows-hardware/drivers/">Unidrv</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/">Pscript</a> drivers can call <i>ComPropSheet</i> from within their <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemui-documentpropertysheets">IPrintOemUI::DocumentPropertySheets</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemui-devicepropertysheets">IPrintOemUI::DevicePropertySheets</a> methods.

The <a href="https://docs.microsoft.com/windows-hardware/drivers/print/group-parent">group parent</a> handle specified for the <i>hComPropSheet</i> parameter can be either of the following:

<ul>
<li>
The handle received in the <i>hComPropSheet</i> member of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/ns-compstui-_propsheetui_info">PROPSHEETUI_INFO</a> structure.

</li>
<li>
The handle received as a result of previously calling <i>ComPropSheet</i> with a <a href="https://docs.microsoft.com/previous-versions/ff546414(v=vs.85)">CPSFUNC_INSERT_PSUIPAGE</a> function code, and specifying PSUIPAGEINSERT_GROUP_PARENT as the <b>Type</b> member for an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/ns-compstui-_insertpsuipage_info">INSERTPSUIPAGE_INFO</a> structure.

</li>
</ul>
<h3><a id="ComPropSheet_function_codes"></a><a id="compropsheet_function_codes"></a><a id="COMPROPSHEET_FUNCTION_CODES"></a>ComPropSheet function codes</h3>
The following function codes can be passed to the CPSUI's <b>ComPropSheet</b> function:

<table>
<tr>
<th>Function code</th>
<th>Description</th>
<th>Parameters and Return Value</th>
</tr>
<tr>
<td><b>CPSFUNC_ADD_HPROPSHEETPAGE</b></td>
<td>
The <b>CPSFUNC_ADD_HPROPSHEETPAGE</b> function code causes the <b>ComPropSheet</b> function to add a property sheet page that has been created by calling the <b>CreatePropertySheetPage</b> function (described in the Microsoft Windows SDK documentation).

</td>
<td><b>Parameters</b><ul>
<li><i>hComPropSheet</i>: Group parent handle.  </li>
<li><i>Function</i>: Caller sets this function code parameter to <b>CPSFUNC_ADD_HPROPSHEETPAGE</b> when it calls <b>ComPropSheet</b> to add a property sheet page. </li>
<li><i>lParam1</i>: Handle to a property sheet page, obtained by calling the <b>CreatePropertySheetPage</b> function.</li>
<li><i>lParam2</i>: Not used, must be zero.</li>
</ul><b>Return Value</b>If the operation succeeds, <b>ComPropSheet</b> returns a CPSUI handle to the added page; otherwise, it returns NULL.



</td>
</tr>
<tr>
<td><b>CPSFUNC_ADD_PCOMPROPSHEETUI</b></td>
<td>
The <b>CPSFUNC_ADD_PCOMPROPSHEETUI</b> function code causes the <b>ComPropSheet</b> function to add a set of one or more property sheet pages that are described by a <b>COMPROPSHEETUI</b> structure.

</td>
<td><b>Parameters</b><ul>
<li><i>hComPropSheet</i>: Group parent handle.  </li>
<li><i>Function</i>: Caller sets this function code parameter to <b>CPSFUNC_ADD_PCOMPROPSHEETUI</b> when it calls <b>ComPropSheet</b> to add a set of one or more property sheet pages.</li>
<li><i>lParam1</i>: Pointer to a <b>COMPROPSHEETUI</b> structure.</li>
<li><i>lParam2</i>: Pointer to a 32-bit location to receive the number of pages added or, if a failure occurs, an ERR_CPSUI-prefixed error code.</li>
</ul><b>Return Value</b>If the operation succeeds, <b>ComPropSheet</b> returns a handle to the set of added pages; otherwise, the function returns NULL.

</td>
</tr>
<tr>
<td><b>CPSFUNC_ADD_PFNPROPSHEETUI</b></td>
<td>The <b>CPSFUNC_ADD_PFNPROPSHEETUI</b> function code causes the <b>ComPropSheet</b> function to call the specified PFNPROPSHEETUI-typed function, which must add a set of one or more property sheet pages. </td>
<td><b>Parameters</b><ul>
<li><i>hComPropSheet</i>: Group parent handle.  </li>
<li><i>Function</i>: Caller sets this function code parameter to <b>CPSFUNC_ADD_PFNPROPSHEETUI</b> when it calls <b>ComPropSheet</b>. <b>ComPropSheet</b> then calls the specified PFNPROPSHEETUI-typed function to add a set of one or more property sheet pages.</li>
<li><i>lParam1</i>: Pointer to a PFNPROPSHEETUI-typed function.</li>
<li><i>lParam2</i>: A 32-bit value that is passed to the PFNPROPSHEETUI-typed function for its lParam parameter.</li>
</ul><b>Return Value</b>If the operation succeeds, <b>ComPropSheet</b> returns a handle to the set of added pages; otherwise, the function returns NULL.

</td>
</tr>
<tr>
<td><b>CPSFUNC_ADD_PROPSHEETPAGE</b></td>
<td>The <b>CPSFUNC_ADD_PROPSHEETPAGE</b> function code causes the <b>ComPropSheet</b> function to add the type of property sheet page that is described by a <b>PROPSHEETPAGE</b> structure (described in the Microsoft Windows SDK documentation).</td>
<td><b>Parameters</b><ul>
<li><i>hComPropSheet</i>: Group parent handle.  </li>
<li><i>Function</i>: Caller sets this function code parameter to <b>CPSFUNC_ADD_PROPSHEETPAGE</b> when it calls <b>ComPropSheet</b> to add the type of property sheet page described by a <b>PROPSHEETPAGE</b> structure. The <b>ComPropSheet</b> function calls the <b>CreatePropertySheetPage</b> function (described in the Windows SDK documentation), and passes the <b>PROPSHEETPAGE</b> structure's address to create the page.</li>
<li><i>lParam1</i>: Pointer to a <b>PROPSHEETPAGE</b> structure.</li>
<li><i>lParam2</i>: Not used, must be zero.</li>
</ul><b>Return Value</b>If the operation succeeds, <b>ComPropSheet</b> returns a CPSUI handle to the added page; otherwise, it returns NULL.

</td>
</tr>
<tr>
<td><b>CPSFUNC_DELETE_HCOMPROPSHEET</b></td>
<td>The <b>CPSFUNC_DELETE_HCOMPROPSHEET</b> function code causes the <b>ComPropSheet</b> function to delete a set of property sheet pages that are specified by a CPSUI handle.</td>
<td><b>Parameters</b><ul>
<li><i>hComPropSheet</i>: Group parent handle.  </li>
<li><i>Function</i>: Caller sets this function code parameter to <b>CPSFUNC_DELETE_HCOMPROPSHEET</b> when it calls <b>ComPropSheet</b> to delete a set of property sheet pages. </li>
<li><i>lParam1</i>: CPSUI handle that refers to the set of pages to be deleted. This handle must previously have been obtained by a call to <b>ComPropSheet</b> with one of the following function codes:<dl>
<dd><b>CPSFUNC_ADD_HPROPSHEETPAGE</b></dd>
<dd><b>CPSFUNC_ADD_PCOMPROPSHEETUI</b></dd>
<dd><b>CPSFUNC_ADD_PFNPROPSHEETUI</b></dd>
<dd><b>CPSFUNC_ADD_PROPSHEETPAGE</b></dd>
<dd><b>CPSFUNC_INSERT_PSUIPAGE</b></dd>
</dl>
</li>
<li><i>lParam2</i>: Not used, must be zero.

</li>
</ul><b>Return Value</b>The <b>ComPropSheet</b> function returns the number of property sheet pages that were deleted.

</td>
</tr>
<tr>
<td><b>CPSFUNC_DO_APPLY_CPSUI</b></td>
<td>
The <b>CPSFUNC_DO_APPLY_CPSUI</b> function code causes the <b>ComPropSheet</b> function to simulate the delivery of a PSN_APPLY notification message.

CPSUI responds to the <b>CPSFUNC_DO_APPLY_CPSUI</b> function code by delivering the <b>CPSUICB_REASON_APPLYNOW</b> reason to an application's _CPSUICALLBACK-typed callback function.

</td>
<td><b>Parameters</b><ul>
<li><i>hComPropSheet</i>: Group parent handle.  </li>
<li><i>Function</i>: Caller sets this function code parameter to <b>CPSFUNC_DO_APPLY_CPSUI</b> when it calls <b>ComPropSheet</b> to simulate the delivery of a PSN_APPLY notification message. </li>
<li><i>lParam1</i>: CPSUI handle that points to a set of one or more property sheet pages. Typically, this handle has been previously specified as the lParam1 parameter to <b>ComPropSheet</b> using the <b>CPSFUNC_IGNORE_CPSUI_PSN_APPLY</b> function code.</li>
<li><i>lParam2</i>: This parameter is any combination of the following bit flags:<dl>
<dd>APPLYCPSUI_NO_NEWDEF - Set this flag if you do not want the current default values (used for the Undo operation) to be changed. Clear this flag if you want the current values for all options to become the defaults used for the Undo operation. </dd>
<dd>APPLYCPSUI_OK_CANCEL_BUTTON - Set this flag if the user selected the OK or Cancel button (or if you want to simulate this activity). Clear this flag if the user selected the Close or Apply Now button (or if you want to simulate this activity). If your code is set up to receive PSN_APPLY messages, the code should check the lParam member of the PSHNOTIFY structure. If the member is zero, this bit should be cleared. (The PSN_APPLY message and PSHNOTIFY structure are described in the Microsoft Windows SDK documentation.)</dd>
<dd></dd>
</dl>
</li>
</ul><b>Return Value</b>If the operation succeeds, the <b>ComPropSheet</b> function returns a nonzero value; otherwise it returns zero and the specified pages will become active.

If you use the <b>CPSFUNC_IGNORE_CPSUI_PSN_APPLY</b> function code to disable CPSUI's handling of the PSN_APPLY notification message, you must use the <b>CPSFUNC_DO_APPLY_CPSUI</b> function code to simulate delivery of the PSN_APPLY message. Otherwise, user changes to a property sheet page cannot be obtained.


</td>
</tr>
<tr>
<td><b>CPSFUNC_GET_HPSUIPAGES</b></td>
<td>
The <b>CPSFUNC_GET_HPSUIPAGES</b> function code causes the <b>ComPropSheet</b> function to return an array of CPSUI handles that point to property sheet pages. These handles identify the child pages associated with the specified group parent handle.

To use this function code, follow these steps:<ol>
<li>Call <b>ComPropSheet</b>, specifying the <b>CPSFUNC_GET_PAGECOUNT</b> function code, to obtain the number of child pages associated with the specified group parent. </li>
<li>Allocate enough local memory to contain a HANDLE structure for each page. </li>
<li>Call <b>ComPropSheet</b> again, specifying the <b>CPSFUNC_GET_HPSUIPAGES</b> function code and the address of the locally allocated memory, to obtain an array of HANDLE structures. </li>
</ol>


</td>
<td><b>Parameters</b><ul>
<li><i>hComPropSheet</i>: Group parent handle.  </li>
<li><i>Function</i>: Caller sets this function code parameter to <b>CPSFUNC_GET_HPSUIPAGES</b> when it calls <b>ComPropSheet</b> to retireve an array of CPSUI handles. </li>
<li><i>lParam1</i>: Pointer to an array of HANDLE structures.

</li>
<li><i>lParam2</i>: Size of the HANDLE array pointed to by lParam1.</li>
</ul><b>Return Value</b>The <b>ComPropSheet</b> function returns the number of handles that CPSUI places into the HANDLE array.

</td>
</tr>
<tr>
<td><b>CPSFUNC_GET_PAGECOUNT</b></td>
<td>The <b>CPSFUNC_GET_PAGECOUNT</b> function code causes the <b>ComPropSheet</b> function to return the number of property sheet pages that are child pages of the specified group parent handle.</td>
<td><b>Parameters</b><ul>
<li><i>hComPropSheet</i>: Group parent handle.  </li>
<li><i>Function</i>: Caller sets this function code parameter to <b>CPSFUNC_GET_PAGECOUNT</b> when it calls <b>ComPropSheet</b> to return the child page count. </li>
<li><i>lParam1</i>: Not used, must be zero.</li>
<li><i>lParam2</i>: Not used, must be zero.</li>
</ul><b>Return Value</b>The <b>ComPropSheet</b> function returns the number of pages counted.

</td>
</tr>
<tr>
<td><b>CPSFUNC_GET_PFNPROPSHEETUI_ICON</b></td>
<td>
The <b>CPSFUNC_GET_PFNPROPSHEETUI_ICON</b> function code causes the <b>ComPropSheet</b> function to return a handle to the icon that is associated with a set of property sheet pages. The set of pages must have been previously created by a PFNPROPSHEETUI-typed function.

The <b>ComPropSheet</b> function calls the PFNPROPSHEETUI-typed function associated with the specified page handle, and passes a reason value of <b>PROPSHEETUI_REASON_GET_ICON</b>. The PFNPROPSHEETUI-typed function then calls <b>LoadImage</b> (described in the Windows SDK documentation) and provides the icon size specified bylParam2 to load an icon resource.

</td>
<td><b>Parameters</b><ul>
<li><i>hComPropSheet</i>: Group parent handle.  </li>
<li><i>Function</i>: Caller sets this function code parameter to <b>CPSFUNC_GET_PFNPROPSHEETUI_ICON</b> when it calls <b>ComPropSheet</b> to retrieve a handle to the icon that is associated with a set of property sheet pages. </li>
<li><i>lParam1</i>: CPSUI handle that refers to a set of property sheet pages. This handle must previously have been obtained by a call to <b>ComPropSheet</b> with the <b>CPSFUNC_ADD_PFNPROPSHEETUI</b> function code.</li>
<li><i>lParam2</i>: Specifies two WORD-sized values representing the icon's size, in pixels. The LOWORD value is the width, and the HIWORD value is the height. If these values are zero, the system metrics SM_CXICON and SM_CYICON are used. (See <b>GetSystemMetrics</b> in the Microsoft Windows SDK documentation.)</li>
</ul><b>Return Value</b>If the operation succeeds, the <b>ComPropSheet</b> function returns an icon handle; otherwise it returns NULL.

</td>
</tr>
<tr>
<td><b>CPSFUNC_IGNORE_CPSUI_PSN_APPLY</b></td>
<td>
The <b>CPSFUNC_IGNORE_CPSUI_PSN_APPLY</b> function code causes the <b>ComPropSheet</b> function to disable or reenable CPSUI's handling of the PSN_APPLY notification message (described in the Microsoft Windows SDK documentation).

The system sends the PSN_APPLY notification message to CPSUI when a user selects a property sheet's OK or Cancel button. CPSUI responds to this message by delivering the <b>CPSUICB_REASON_APPLYNOW</b> reason to an application's _CPSUICALLBACK-typed callback function.

If you disable CPSUI's handling of the PSN_APPLY notification message, you must use the <b>CPSFUNC_DO_APPLY_CPSUI</b> function code to simulate delivery of the PSN_APPLY message. Otherwise, user changes to a property sheet page cannot be obtained.

If the <b>CPSFUNC_IGNORE_CPSUI_PSN_APPLY</b> function code is not used, CPSUI's handling of the PSN_APPLY notification message is enabled by default.


</td>
<td><b>Parameters</b><ul>
<li><i>hComPropSheet</i>: Group parent handle.  </li>
<li><i>Function</i>: Caller sets this function code parameter to <b>CPSFUNC_IGNORE_CPSUI_PSN_APPLY</b> when it calls <b>ComPropSheet</b> to disable or reenable CPSUI's handling of the PSN_APPLY notification message. </li>
<li><i>lParam1</i>: CPSUI handle that refers to a set of one or more property sheet pages. This handle must have been previously obtained by a call to <b>ComPropSheet</b> with a function code of <b>CPSFUNC_ADD_PCOMPROPSHEETUI</b>, or with a function code of <b>CPSFUNC_INSERT_PSUIPAGE</b> and an insertion type of <b>PSUIPAGEINSERT_PROPSHEETPAGE</b>.</li>
<li><i>lParam2</i>: Any nonzero value disables CPSUI's delivery of the <b>CPSUICB_REASON_APPLYNOW</b> reason. A zero value reenables delivery of the <b>CPSUICB_REASON_APPLYNOW</b> reason.</li>
</ul><b>Return Value</b>If the operation succeeds, the <b>ComPropSheet</b> function returns a nonzero value; otherwise it returns zero.

</td>
</tr>
<tr>
<td><b>CPSFUNC_INSERT_PSUIPAGE</b></td>
<td>The <b>CPSFUNC_INSERT_PSUIPAGE</b> function code causes the <b>ComPropSheet</b> function to insert a set of property sheet pages at a specific position.</td>
<td><b>Parameters</b><ul>
<li><i>hComPropSheet</i>: Group parent handle.  </li>
<li><i>Function</i>: Caller sets this function code parameter to <b>CPSFUNC_INSERT_PSUIPAGE</b> when it calls <b>ComPropSheet</b> to insert a set of property sheet pages at a specific position. </li>
<li><i>lParam1</i>: Specifies a handle to a set of one or more property sheet pages. The new pages will be inserted before or after these pages, depending on the Mode member of the <b>INSERTPSUIPAGE_INFO</b> structure pointed to by lParam2. This handle must previously have been obtained by a call to <b>ComPropSheet</b> with one of the following function codes:<dl>
<dd><b>CPSFUNC_ADD_HPROPSHEETPAGE</b></dd>
<dd><b>CPSFUNC_ADD_PCOMPROPSHEETUI </b></dd>
<dd><b>CPSFUNC_ADD_PFNPROPSHEETUI</b></dd>
<dd><b>CPSFUNC_ADD_PROPSHEETPAGE</b></dd>
<dd><b>CPSFUNC_INSERT_PSUIPAGE</b></dd>
</dl>
</li>
<li><i>lParam2</i>: Pointer to an <b>INSERTPSUIPAGE_INFO</b> structure, describing where and how the new pages should be inserted.</li>
</ul><b>Return Value</b>If the operation succeeds, the <b>ComPropSheet</b> function returns a handle to the set of pages that were inserted; otherwise, the function returns NULL.

</td>
</tr>
<tr>
<td><b>CPSFUNC_LOAD_CPSUI_ICON</b></td>
<td>
The <b>CPSFUNC_LOAD_CPSUI_ICON</b> function code causes the <b>ComPropSheet</b> function to load a CPSUI-supplied icon resource.

CPSUI calls <b>LoadImage</b> (described in the Windows SDK documentation) to load the specified icon resource.

</td>
<td><b>Parameters</b><ul>
<li><i>hComPropSheet</i>: Group parent handle.  </li>
<li><i>Function</i>: Caller sets this function code parameter to <b>CPSFUNC_LOAD_CPSUI_ICON</b> when it calls <b>ComPropSheet</b> to load a CPSUI-supplied icon resource. </li>
<li><i>lParam1</i>: Resource identifier of the CPSUI-supplied icon to be loaded. This must be an IDI_CPSUI-prefixed identifier as defined in Compstui.h.</li>
<li><i>lParam2</i>: Specifies two WORD-sized values representing the icon's size, in pixels. The LOWORD value is the width, and the HIWORD value is the height. If these values are zero, the system metrics SM_CXICON and SM_CYICON are used. (See <b>GetSystemMetrics</b> in the Microsoft Windows SDK documentation.)</li>
</ul><b>Return Value</b>If the operation succeeds, the <b>ComPropSheet</b> function returns an icon handle; otherwise it returns NULL.

</td>
</tr>
<tr>
<td><b>CPSFUNC_LOAD_CPSUI_STRING</b></td>
<td>
The <b>CPSFUNC_LOAD_CPSUI_STRING</b> function code causes the <b>ComPropSheet</b> function to load a CPSUI-supplied string resource.

The <b>ComPropSheet</b> function calls <b>LoadString</b> (described in the Microsoft Windows SDK documentation) to load the specified string.

</td>
<td><b>Parameters</b><ul>
<li><i>hComPropSheet</i>: Group parent handle.  </li>
<li><i>Function</i>: Caller sets this function code parameter to <b>CPSFUNC_LOAD_CPSUI_STRING</b> when it calls ComPropSheet to load a CPSUI-supplied string resource.</li>
<li><i>lParam1</i>: An LPSTR-typed pointer to a caller-allocated buffer, into which the CPSUI-supplied string specified by HIWORD(<i>lParam2</i>) will be placed.</li>
<li><i>lParam2</i>: Contains the following two caller-supplied values:<dl>
<dd>LOWORD(<i>lParam2</i>). Size, in bytes, of the buffer pointed to by lParam1. </dd>
<dd>HIWORD(<i>lParam2</i>). Resource identifier of the CPSUI-supplied string to be loaded. This must be an IDS_CPSUI-prefixed identifier as defined in Compstui.h. </dd>
</dl>
</li>
</ul><b>Return Value</b>If the operation succeeds, the <b>ComPropSheet</b> function returns the length of the string. If an invalid resource identifier is specified, the function returns zero. If <i>lParam1</i> is NULL or LOWORD(<i>lParam2</i>) is zero, the function returns -1.

</td>
</tr>
<tr>
<td><b>CPSFUNC_QUERY_DATABLOCK</b></td>
<td>
The <b>CPSFUNC_QUERY_DATABLOCK</b> function code causes the <b>ComPropSheet</b> function to retrieve a caller-supplied data block that was previously stored using the <b>CPSFUNC_SET_DATABLOCK</b> function code.

Typically, this function code is used by a _CPSUICALLBACK-typed callback function (when the function's <b>CPSUICBPARAM</b> structure contains a Reason value of <b>CPSUICB_REASON_SETACTIVE</b>) to retrieve values associated with another page before the current page becomes inactive.

</td>
<td><b>Parameters</b><ul>
<li><i>hComPropSheet</i>: Group parent handle.  </li>
<li><i>Function</i>: Caller sets this function code parameter to <b>CPSFUNC_QUERY_DATABLOCK</b> when it calls ComPropSheet to retrieve a caller-supplied data block. </li>
<li><i>lParam1</i>: Pointer to a <b>CPSUIDATABLOCK</b> structure that identifies the size and location of a buffer to receive the requested data block.</li>
<li><i>lParam2</i>: DWORD-sized identifier value, used to identify the requested <b>CPSUIDATABLOCK</b> structure. This value must have been specified in a previous call to <b>ComPropSheet</b> using the <b>CPSFUNC_SET_DATABLOCK</b> function code.</li>
</ul><b>Return Value</b>If the operation succeeds, the <b>ComPropSheet</b> function returns a value that represents the size of the retrieved data block. If <i>lParam1</i> is NULL, or if the value of any member of the supplied <b>CPSUIDATABLOCK</b> structure is zero, <b>ComPropSheet</b> returns the size required to store the data block. If an error occurs, the function returns a value less than or equal to zero.

</td>
</tr>
<tr>
<td><b>CPSFUNC_SET_DATABLOCK</b></td>
<td>
The <b>CPSFUNC_SET_DATABLOCK</b> function code causes the <b>ComPropSheet</b> function to store a caller-supplied data block. You can use this function code to make the information about a property sheet page available to other pages.

Typically, this function code is used by a _CPSUICALLBACK-typed callback function (when the function's <b>CPSUICBPARAM</b> structure contains a Reason value of <b>CPSUICB_REASON_KILLACTIVE</b>) to save values associated with a page before it becomes inactive.

</td>
<td><b>Parameters</b><ul>
<li><i>hComPropSheet</i>: Group parent handle.  </li>
<li><i>Function</i>: Caller sets this function code parameter to <b>CPSFUNC_SET_DATABLOCK</b> when it calls <b>ComPropSheet</b> to store a caller-supplied data block. </li>
<li><i>lParam1</i>: Pointer to a <b>CPSUIDATABLOCK</b> structure that describes the data block to be stored.</li>
<li><i>lParam2</i>: Caller-defined DWORD-sized identifier value. It is used to identify the supplied <b>CPSUIDATABLOCK</b> structure in subsequent calls to <b>ComPropSheet</b> using the <b>CPSFUNC_QUERY_DATABLOCK</b> function code.</li>
</ul><b>Return Value</b>If the operation is successful, the <b>ComPropSheet</b> function returns a value representing the number of bytes that were stored; otherwise it returns a value less than or equal to zero.

</td>
</tr>
<tr>
<td><b>CPSFUNC_SET_DMPUB_HIDEBITS</b></td>
<td>
The <b>CPSFUNC_SET_DMPUB_HIDEBITS</b> function code causes the <b>ComPropSheet</b> function to "hide" a specified set of document property options, so that they are not displayed.

You can use the <b>CPSFUNC_SET_DMPUB_HIDEBITS</b> function code if you want to define OPTITEM structures for one or more document property sheet options, but you do not want the options to be user-modifiable. The property sheet page must be defined using the <b>COMPROPSHEETUI</b> structure, and the structure's pDlgPage member must be <b>CPSUI_PDLGPAGE_DOCPROP</b> or <b>CPSUI_PDLGPAGE_ADVDOCPROP</b>.

If you use the <b>CPSFUNC_SET_DMPUB_HIDEBITS</b> function code, it must be specified to <b>ComPropSheet</b> before the <b>CPSFUNC_ADD_PCOMPROPSHEETUI</b> or <b>CPSFUNC_INSERT_PSUIPAGE</b> function code is used to create the page.


</td>
<td><b>Parameters</b><ul>
<li><i>hComPropSheet</i>: Group parent handle.  </li>
<li><i>Function</i>: Caller sets this function code parameter to <b>CPSFUNC_SET_DMPUB_HIDEBITS</b> when it calls <b>ComPropSheet</b> to "hide" a specified set of document property options. </li>
<li><i>lParam1</i>: Pointer to a bit array that indicates the options to be hidden. This array must be created using the <b>MAKE_DMPUB_HIDEBIT</b>(DMPub) macro, where DMPub is the OR-combination of one or more DMPUB_-prefixed constants. The DMPUB_-prefixed constants are listed in the description of the <b>OPTITEM</b> structure. The macro and constants are defined in Compstui.h.

</li>
<li><i>lParam2</i>: Not used, must be zero.</li>
</ul><b>Return Value</b>If the operation is successful, the <b>ComPropSheet</b> function returns the value specified for <i>lParam1</i>; otherwise it returns zero.

</td>
</tr>
<tr>
<td><b>CPSFUNC_SET_FUSION_CONTEXT</b></td>
<td>
The <b>CPSFUNC_SET_FUSION_CONTEXT</b> sets a Fusion activation context for the specified page.

When a page is about to be created or inserted and it does not specify an activation context in its <b>PROPSHEETPAGE</b> structure (described in the Windows SDK documentation), it will be created in the parent's page activation context. If the parent's activation context is not set, then Compstui.dll looks up the parent's parent, continuing until the top level parent is reached or until it finds a parent with an activation context properly set. If none of the parents has an activation context set, then Compstui.dll will not specify an activation context in the <b>PROPSHEETPAGE</b> structure. This means that the page will be created in the activation context of the caller of the <b>PropertySheet</b> API (described in the Windows SDK documentation).

</td>
<td><b>Parameters</b><ul>
<li><i>hComPropSheet</i>: Group parent handle.  </li>
<li><i>Function</i>: Caller sets this function code parameter to <b>CPSFUNC_SET_FUSION_CONTEXT</b> when it calls <b>ComPropSheet</b> to set a Fusion activation context for the specified page. 

</li>
<li><i>lParam1</i>: Specifies the handle to the Fusion context. Compstui.dll duplicates the handle, attaching it to its internal structures, so that the caller is not obligated to retain the handle. Compstui.dll releases the passed-in context handle when the Compstui.dll handle is deleted.</li>
<li><i>lParam2</i>: Not used, must be zero.</li>
</ul><b>Return Value</b>If the operation is successful, the <b>ComPropSheet</b> function returns a value greater than zero. Otherwise, <b>ComPropSheet</b> returns a value that is less than or equal to zero. For information about the error, use <b>GetLastError</b>, which is described in the Microsoft Windows SDK documentation.

</td>
</tr>
<tr>
<td><b>CPSFUNC_SET_HSTARTPAGE</b></td>
<td>The <b>CPSFUNC_SET_HSTARTPAGE</b> function code causes the <b>ComPropSheet</b> function to mark a specified property sheet page to be the top page of the associated property sheet. If the property sheet is currently being displayed, the specified page becomes the active page.</td>
<td><b>Parameters</b><ul>
<li><i>hComPropSheet</i>: Group parent handle.  </li>
<li><i>Function</i>: Caller sets this function code parameter to <b>CPSFUNC_SET_HSTARTPAGE</b> when it calls <b>ComPropSheet</b> to mark a specified property sheet page to be the top page of the associated property sheet.</li>
<li><i>lParam1</i>: Caller-supplied CPSUI page handle, previously obtained by a call to <b>ComPropSheet</b> with one of the following function codes:

<dl>
<dd><b>CPSFUNC_ADD_HPROPSHEETPAGE</b></dd>
<dd><b>CPSFUNC_ADD_PCOMPROPSHEETUI </b></dd>
<dd><b>CPSFUNC_ADD_PFNPROPSHEETUI</b></dd>
<dd><b>CPSFUNC_ADD_PROPSHEETPAGE</b></dd>
<dd><b>CPSFUNC_INSERT_PSUIPAGE</b></dd>
</dl>If the handle represents a single page belonging to the group specified by <i>hComPropSheet</i>, CPSUI makes this page the top page.

If the handle represents a group parent handle (see <b>CPSFUNC_INSERT_PSUIPAGE</b>), then <i>lParam2</i> represents a zero-based index into the group's pages and the page represented by the index becomes the top page.
</li>
<li><i>lParam2</i>: If lParam1 represents a group parent handle, this caller-supplied value is a zero-based index into the group's pages.

If <i>lParam1</i> represents a single page belonging to the group specified by <i>hComPropSheet</i>, this parameter is not used.

If the handle specified by <i>lParam1</i> was obtained using the <b>CPSFUNC_ADD_PCOMPROPSHEETUI</b> function code, and if the <b>pDlgPage</b> member of the associated <b>COMPROPSHEETUI</b> structure was set to <b>CPSUI_PDLGPAGE_DOCPROP</b>, then one of the following values can be specified for <i>lParam2.</i><ul>
<li>SSP_STDPAGE1 - Make the Layout page the top page.</li>
<li>SSP_STDPAGE2 - Make the Paper/Quality page the top page. </li>
<li>SSP_TVPAGE - Make the Advanced page the top page. </li>
</ul>
</li>
</ul><b>Return Value</b>If the operation is successful, the <b>ComPropSheet</b> function returns the value specified for <i>lParam1</i>; otherwise it returns zero.

</td>
</tr>
<tr>
<td><b>CPSFUNC_SET_PSUIPAGE_ICON</b></td>
<td>
The <b>CPSFUNC_SET_PSUIPAGE_ICON</b> function code causes the <b>ComPropSheet</b> function to add, replace, or remove the icon assigned to the tab of a property sheet page.

If lParam2 contains an icon handle, and if the page specified by lParam1 is currently being displayed, CPSUI adds the icon to the specified page's tab. If an icon is already assigned to the page, the old icon is replaced with the new one. If lParam2 is zero, the current icon (if one exists) is removed.

For all icons specified with the <b>CPSFUNC_SET_PSUIPAGE_ICON</b> function code, CPSUI sets the image size to 16 by 16 pixels.

Icon handles should be obtained by calling <b>LoadImage</b>, which is described in the Microsoft Windows SDK documentation.


</td>
<td><b>Parameters</b><ul>
<li><i>hComPropSheet</i>: Group parent handle.  </li>
<li><i>Function</i>: Caller sets this function code parameter to <b>CPSFUNC_SET_PSUIPAGE_ICON</b> when it calls <b>ComPropSheet</b> to add, replace, or remove the icon assigned to the tab of a property sheet page.</li>
<li><i>lParam1</i>: Caller-supplied CPSUI page handle, previously obtained by a call to <b>ComPropSheet</b> with one of the following function codes:<dl>
<dd><b>CPSFUNC_ADD_HPROPSHEETPAGE</b></dd>
<dd><b>CPSFUNC_ADD_PROPSHEETPAGE</b></dd>
<dd><b>CPSFUNC_INSERT_PSUIPAGE</b> (with the Type member of the <b>INSERTPSUIPAGE_INFO</b> structure set to <b>PSUIPAGEINSERT_HPROPSHEETPAGE</b> or <b>PSUIPAGEINSERT_PROPSHEETPAGE</b>). </dd>
</dl>
</li>
<li><i>lParam2</i>: Caller-supplied icon handle. You can set this parameter to zero to remove the current icon.</li>
</ul><b>Return Value</b>If the operation is successful, the <b>ComPropSheet</b> function returns 1. If an error is encountered, or if the specified page is not currently being displayed, the function returns zero.

</td>
</tr>
<tr>
<td><b>CPSFUNC_SET_PSUIPAGE_TITLE</b></td>
<td>The <b>CPSFUNC_SET_PSUIPAGE_TITLE</b> function code causes the <b>ComPropSheet</b> function to set the tab title for a property sheet page.</td>
<td><b>Parameters</b><ul>
<li><i>hComPropSheet</i>: Group parent handle.  </li>
<li><i>Function</i>: Caller sets this function code parameter to <b>CPSFUNC_SET_PSUIPAGE_TITLE</b> when it calls <b>ComPropSheet</b> to set the tab title for a property sheet page.</li>
<li><i>lParam1</i>: Caller-supplied CPSUI page handle, previously obtained by a call to <b>ComPropSheet</b> with one of the following function codes:<dl>
<dd><b>CPSFUNC_ADD_HPROPSHEETPAGE</b></dd>
<dd><b>CPSFUNC_ADD_PROPSHEETPAGE</b></dd>
<dd><b>CPSFUNC_INSERT_PSUIPAGE</b> (with the Type member of the <b>INSERTPSUIPAGE_INFO</b> structure set to <b>PSUIPAGEINSERT_HPROPSHEETPAGE</b> or <b>PSUIPAGEINSERT_PROPSHEETPAGE</b>). </dd>
</dl>
</li>
<li><i>lParam2</i>: Caller-supplied pointer to a NULL-terminated string that specifies the new title.</li>
</ul><b>Return Value</b>If the operation is successful, the <b>ComPropSheet</b> function returns 1. If an error is encountered, or if the specified page is not currently being displayed, the function returns zero.

</td>
</tr>
<tr>
<td><b>CPSFUNC_SET_RESULT</b></td>
<td>
The <b>CPSFUNC_SET_RESULT</b> function code causes the <b>ComPropSheet</b> function to pass a specified result value to all PFNPROPSHEETUI-typed functions associated with a specified page and its parents.

For more information about how to set result values, see the description of the <b>SETRESULT_INFO</b> structure.

The following caution applies to Unidrv- or Pscript5-based IHV UI plug-in with custom UI property sheets, and for which user settings made in the property sheets should be persistent. When the plug-in calls the <b>ComPropSheet</b> function with the Function parameter set to <b>CPSFUNC_SET_RESULT</b>, the plug-in must set the lParam2 parameter to <b>CPSUI_OK</b>.

</td>
<td><b>Parameters</b><ul>
<li><i>hComPropSheet</i>: Group parent handle.  </li>
<li><i>Function</i>: Caller sets this function code parameter to <b>CPSFUNC_SET_RESULT</b> when it calls <b>ComPropSheet</b> to pass a specified result value to all PFNPROPSHEETUI-typed functions associated with a specified page and its parents. </li>
<li><i>lParam1</i>: Caller-supplied CPSUI handle to the page for which a result value is being passed. If lParam1 is NULL, the CPSUI uses the value specified by <i>hComPropSheet</i>.</li>
<li><i>lParam2</i>: Caller-supplied 32-bit DWORD result value.</li>
</ul><b>Return Value</b>If the operation is successful, the <b>ComPropSheet</b> function returns the number of PFNPROPSHEETUI-typed functions that were called. If the handle specified for <i>lParam1</i> is invalid, the function returns -1.

</td>
</tr>
</table>
 



