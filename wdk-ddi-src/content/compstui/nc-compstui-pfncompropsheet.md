---
UID: NC:compstui.PFNCOMPROPSHEET
title: PFNCOMPROPSHEET (compstui.h)
description: The ComPropSheet function is supplied by CPSUI and can be called by CPSUI applications (including printer interface DLLs) to build property sheet pages.
tech.root: print
ms.date: 11/14/2022
keywords: ["PFNCOMPROPSHEET callback function"]
ms.keywords: ComPropSheet, ComPropSheet routine [Print Devices], PFNCOMPROPSHEET, compstui/ComPropSheet, cpsuifnc_2586427b-a3ae-4c2e-b081-06d58ec310c3.xml, print.compropsheet
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PFNCOMPROPSHEET
 - compstui/PFNCOMPROPSHEET
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - compstui.h
api_name:
 - PFNCOMPROPSHEET
---

## -description

The *ComPropSheet* function is supplied by [CPSUI](/windows-hardware/drivers/print/common-property-sheet-user-interface) and can be called by CPSUI applications (including printer interface DLLs) to build property sheet pages.

## -parameters

### -param hComPropSheet [in]

Caller-supplied handle to a property sheet [group parent](/windows-hardware/drivers/print/group-parent). For more information, see the following Remarks section.

### -param Function [in]

Caller-supplied, CPSFUNC_-prefixed ComPropSheet function codes specifying the operation to be performed by the *ComPropSheet* function.

> [!NOTE]
> See the *ComPropSheet* function codes table in the **Remarks** section below.

### -param lParam1 [in]

Caller-supplied value that depends on the *ComPropSheet* function code supplied for *Function*.

### -param lParam2 [in]

Caller-supplied value that depends on the *ComPropSheet* function code supplied for *Function*.

## -returns

The return value depends on the [ComPropSheet function code](/windows-hardware/drivers/ddi/_print/index) supplied for *Function*.

## -remarks

When CPSUI calls one of an application's [PFNPROPSHEETUI](/windows-hardware/drivers/ddi/compstui/nc-compstui-pfnpropsheetui)-typed functions, it passes a pointer to the *ComPropSheet* function in a [PROPSHEETUI_INFO](/windows-hardware/drivers/ddi/compstui/ns-compstui-_propsheetui_info) structure. A **PFNPROPSHEETUI**-typed function can call the *ComPropSheet* function to describe property sheet pages to CPSUI.

A [printer interface DLL](/windows-hardware/drivers/print/printer-interface-dll) can call *ComPropSheet* from within its [DrvDocumentPropertySheets](/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvdocumentpropertysheets) function or its [DrvDevicePropertySheets](/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvdevicepropertysheets) function.

[User interface plug-ins](/windows-hardware/drivers/print/user-interface-plug-ins) for Microsoft's [Unidrv](/windows-hardware/drivers/) and [Pscript](/windows-hardware/drivers/) drivers can call *ComPropSheet* from within their [IPrintOemUI::DocumentPropertySheets](/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemui-documentpropertysheets) and [IPrintOemUI::DevicePropertySheets](/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemui-devicepropertysheets) methods.

The [group parent](/windows-hardware/drivers/print/group-parent) handle specified for the *hComPropSheet* parameter can be either of the following:

- The handle received in the *hComPropSheet* member of a [PROPSHEETUI_INFO](/windows-hardware/drivers/ddi/compstui/ns-compstui-_propsheetui_info) structure.

- The handle received as a result of previously calling *ComPropSheet* with a [CPSFUNC_INSERT_PSUIPAGE](/previous-versions/ff546414(v=vs.85)) function code, and specifying PSUIPAGEINSERT_GROUP_PARENT as the **Type** member for an [INSERTPSUIPAGE_INFO](/windows-hardware/drivers/ddi/compstui/ns-compstui-_insertpsuipage_info) structure.

### ComPropSheet function codes

The following function codes can be passed to the CPSUI's **ComPropSheet** function:

#### CPSFUNC_ADD_HPROPSHEETPAGE

The **CPSFUNC_ADD_HPROPSHEETPAGE** function code causes the **ComPropSheet** function to add a property sheet page that has been created by calling the [**CreatePropertySheetPage**](/windows/win32/api/prsht/nf-prsht-createpropertysheetpagew) function.

##### Parameters (CPSFUNC_ADD_HPROPSHEETPAGE)

- *hComPropSheet*: Group parent handle

- *Function*: Caller sets this function code parameter to **CPSFUNC_ADD_HPROPSHEETPAGE** when it calls **ComPropSheet** to add a property sheet page

- *lParam1*: Handle to a property sheet page, obtained by calling the [**CreatePropertySheetPage**](/windows/win32/api/prsht/nf-prsht-createpropertysheetpagew) function

- *lParam2*: Not used, must be zero

##### Return value (CPSFUNC_ADD_HPROPSHEETPAGE)

If the operation succeeds, **ComPropSheet** returns a CPSUI handle to the added page; otherwise, it returns NULL.

#### CPSFUNC_ADD_PCOMPROPSHEETUI

The **CPSFUNC_ADD_PCOMPROPSHEETUI** function code causes the **ComPropSheet** function to add a set of one or more property sheet pages that are described by a **COMPROPSHEETUI** structure.

##### Parameters

- *hComPropSheet*: Group parent handle

- *Function*: Caller sets this function code parameter to **CPSFUNC_ADD_PCOMPROPSHEETUI** when it calls **ComPropSheet** to add a set of one or more property sheet pages

- *lParam1*: Pointer to a **COMPROPSHEETUI** structure

- *lParam2*: Pointer to a 32-bit location to receive the number of pages added or, if a failure occurs, an ERR_CPSUI-prefixed error code

##### Return value

If the operation succeeds, **ComPropSheet** returns a handle to the set of added pages; otherwise, the function returns NULL.

#### CPSFUNC_ADD_PFNPROPSHEETUI

The **CPSFUNC_ADD_PFNPROPSHEETUI** function code causes the **ComPropSheet** function to call the specified PFNPROPSHEETUI-typed function, which must add a set of one or more property sheet pages.

##### Parameters (CPSFUNC_ADD_PFNPROPSHEETUI)

- *hComPropSheet*: Group parent handle  

- *Function*: Caller sets this function code parameter to **CPSFUNC_ADD_PFNPROPSHEETUI** when it calls **ComPropSheet**. **ComPropSheet** then calls the specified PFNPROPSHEETUI-typed function to add a set of one or more property sheet pages.

- *lParam1*: Pointer to a PFNPROPSHEETUI-typed function

- *lParam2*: A 32-bit value that is passed to the PFNPROPSHEETUI-typed function for its lParam parameter

##### Return value (CPSFUNC_ADD_PFNPROPSHEETUI)

If the operation succeeds, **ComPropSheet** returns a handle to the set of added pages; otherwise, the function returns NULL.

#### CPSFUNC_ADD_PROPSHEETPAGE

The **CPSFUNC_ADD_PROPSHEETPAGE** function code causes the **ComPropSheet** function to add the type of property sheet page that is described by a [**PROPSHEETPAGE**](/windows/win32/controls/pss-propsheetpage) structure.

##### Parameters (CPSFUNC_ADD_PROPSHEETPAGE)

- *hComPropSheet*: Group parent handle  

- *Function*: Caller sets this function code parameter to **CPSFUNC_ADD_PROPSHEETPAGE** when it calls **ComPropSheet** to add the type of property sheet page described by a **PROPSHEETPAGE** structure. The **ComPropSheet** function calls the [**CreatePropertySheetPage**](/windows/win32/api/prsht/nf-prsht-createpropertysheetpagew) function, and passes the **PROPSHEETPAGE** structure's address to create the page.

- *lParam1*: Pointer to a **PROPSHEETPAGE** structure

- *lParam2*: Not used, must be zero

##### Return value (CPSFUNC_ADD_PROPSHEETPAGE)

If the operation succeeds, **ComPropSheet** returns a CPSUI handle to the added page; otherwise, it returns NULL.

#### CPSFUNC_DELETE_HCOMPROPSHEET

The **CPSFUNC_DELETE_HCOMPROPSHEET** function code causes the **ComPropSheet** function to delete a set of property sheet pages that are specified by a CPSUI handle.

##### Parameters (CPSFUNC_DELETE_HCOMPROPSHEET)

- *hComPropSheet*: Group parent handle  

- *Function*: Caller sets this function code parameter to **CPSFUNC_DELETE_HCOMPROPSHEET** when it calls **ComPropSheet** to delete a set of property sheet pages

- *lParam1*: CPSUI handle that refers to the set of pages to be deleted. This handle must previously have been obtained by a call to **ComPropSheet** with one of the following function codes:

  - **CPSFUNC_ADD_HPROPSHEETPAGE**
  
  - **CPSFUNC_ADD_PCOMPROPSHEETUI**
  
  - **CPSFUNC_ADD_PFNPROPSHEETUI**
  
  - **CPSFUNC_ADD_PROPSHEETPAGE**
  
  - **CPSFUNC_INSERT_PSUIPAGE**

- *lParam2*: Not used, must be zero

##### Return value (CPSFUNC_DELETE_HCOMPROPSHEET)

The **ComPropSheet** function returns the number of property sheet pages that were deleted.

#### CPSFUNC_DO_APPLY_CPSUI

The **CPSFUNC_DO_APPLY_CPSUI** function code causes the **ComPropSheet** function to simulate the delivery of a PSN_APPLY notification message.

CPSUI responds to the **CPSFUNC_DO_APPLY_CPSUI** function code by delivering the **CPSUICB_REASON_APPLYNOW** reason to an application's _CPSUICALLBACK-typed callback function.

##### Parameters (CPSFUNC_DO_APPLY_CPSUI)

- *hComPropSheet*: Group parent handle  

- *Function*: Caller sets this function code parameter to **CPSFUNC_DO_APPLY_CPSUI** when it calls **ComPropSheet** to simulate the delivery of a PSN_APPLY notification message

- *lParam1*: CPSUI handle that points to a set of one or more property sheet pages. Typically, this handle has been previously specified as the lParam1 parameter to **ComPropSheet** using the **CPSFUNC_IGNORE_CPSUI_PSN_APPLY** function code.

- *lParam2*: This parameter is any combination of the following bit flags:

  - APPLYCPSUI_NO_NEWDEF - Set this flag if you do not want the current default values (used for the Undo operation) to be changed. Clear this flag if you want the current values for all options to become the defaults used for the Undo operation.

  - APPLYCPSUI_OK_CANCEL_BUTTON - Set this flag if the user selected the OK or Cancel button (or if you want to simulate this activity). Clear this flag if the user selected the Close or Apply Now button (or if you want to simulate this activity). If your code is set up to receive [PSN_APPLY](/windows/win32/controls/psn-apply) messages, the code should check the lParam member of the [**PSHNOTIFY**](/windows/win32/api/prsht/ns-prsht-pshnotify) structure. If the member is zero, this bit should be cleared.

##### Return value (CPSFUNC_DO_APPLY_CPSUI)

If the operation succeeds, the **ComPropSheet** function returns a nonzero value; otherwise it returns zero and the specified pages will become active.

If you use the **CPSFUNC_IGNORE_CPSUI_PSN_APPLY** function code to disable CPSUI's handling of the PSN_APPLY notification message, you must use the **CPSFUNC_DO_APPLY_CPSUI** function code to simulate delivery of the PSN_APPLY message. Otherwise, user changes to a property sheet page cannot be obtained.

#### CPSFUNC_GET_HPSUIPAGES

The **CPSFUNC_GET_HPSUIPAGES** function code causes the **ComPropSheet** function to return an array of CPSUI handles that point to property sheet pages. These handles identify the child pages associated with the specified group parent handle.

To use this function code, follow these steps:

- Call **ComPropSheet**, specifying the **CPSFUNC_GET_PAGECOUNT** function code, to obtain the number of child pages associated with the specified group parent.

- Allocate enough local memory to contain a HANDLE structure for each page.

- Call **ComPropSheet** again, specifying the **CPSFUNC_GET_HPSUIPAGES** function code and the address of the locally allocated memory, to obtain an array of HANDLE structures.

##### Parameters (CPSFUNC_GET_HPSUIPAGES)

- *hComPropSheet*: Group parent handle  

- *Function*: Caller sets this function code parameter to **CPSFUNC_GET_HPSUIPAGES** when it calls **ComPropSheet** to retrieve an array of CPSUI handles

- *lParam1*: Pointer to an array of HANDLE structures

- *lParam2*: Size of the HANDLE array pointed to by lParam1

##### Return value (CPSFUNC_GET_HPSUIPAGES)

The **ComPropSheet** function returns the number of handles that CPSUI places into the HANDLE array.

#### CPSFUNC_GET_PAGECOUNT

The **CPSFUNC_GET_PAGECOUNT** function code causes the **ComPropSheet** function to return the number of property sheet pages that are child pages of the specified group parent handle.

##### Parameters (CPSFUNC_GET_PAGECOUNT)

- *hComPropSheet*: Group parent handle  

- *Function*: Caller sets this function code parameter to **CPSFUNC_GET_PAGECOUNT** when it calls **ComPropSheet** to return the child page count

- *lParam1*: Not used, must be zero

- *lParam2*: Not used, must be zero

##### Return value (CPSFUNC_GET_PAGECOUNT)

The **ComPropSheet** function returns the number of pages counted.

#### CPSFUNC_GET_PFNPROPSHEETUI_ICON

The **CPSFUNC_GET_PFNPROPSHEETUI_ICON** function code causes the **ComPropSheet** function to return a handle to the icon that is associated with a set of property sheet pages. The set of pages must have been previously created by a PFNPROPSHEETUI-typed function.

The **ComPropSheet** function calls the PFNPROPSHEETUI-typed function associated with the specified page handle, and passes a reason value of **PROPSHEETUI_REASON_GET_ICON**. The PFNPROPSHEETUI-typed function then calls [**LoadImage**](/windows/win32/api/winuser/nf-winuser-loadimagew) and provides the icon size specified bylParam2 to load an icon resource.

##### Parameters (CPSFUNC_GET_PFNPROPSHEETUI_ICON)

- *hComPropSheet*: Group parent handle  

- *Function*: Caller sets this function code parameter to **CPSFUNC_GET_PFNPROPSHEETUI_ICON** when it calls **ComPropSheet** to retrieve a handle to the icon that is associated with a set of property sheet pages

- *lParam1*: CPSUI handle that refers to a set of property sheet pages. This handle must previously have been obtained by a call to **ComPropSheet** with the **CPSFUNC_ADD_PFNPROPSHEETUI** function code.

- *lParam2*: Specifies two WORD-sized values representing the icon's size, in pixels. The LOWORD value is the width, and the HIWORD value is the height. If these values are zero, the system metrics SM_CXICON and SM_CYICON are used. For more information, see [**GetSystemMetrics**](/windows/win32/api/winuser/nf-winuser-getsystemmetrics).

##### Return value (CPSFUNC_GET_PFNPROPSHEETUI_ICON)

If the operation succeeds, the **ComPropSheet** function returns an icon handle; otherwise it returns NULL.

#### CPSFUNC_IGNORE_CPSUI_PSN_APPLY

The **CPSFUNC_IGNORE_CPSUI_PSN_APPLY** function code causes the **ComPropSheet** function to disable or reenable CPSUI's handling of the [PSN_APPLY](/windows/win32/controls/psn-apply) notification message.

The system sends the PSN_APPLY notification message to CPSUI when a user selects a property sheet's OK or Cancel button. CPSUI responds to this message by delivering the **CPSUICB_REASON_APPLYNOW** reason to an application's _CPSUICALLBACK-typed callback function.

If you disable CPSUI's handling of the PSN_APPLY notification message, you must use the **CPSFUNC_DO_APPLY_CPSUI** function code to simulate delivery of the PSN_APPLY message. Otherwise, user changes to a property sheet page cannot be obtained.

If the **CPSFUNC_IGNORE_CPSUI_PSN_APPLY** function code is not used, CPSUI's handling of the PSN_APPLY notification message is enabled by default.

##### Parameters (CPSFUNC_IGNORE_CPSUI_PSN_APPLY)

- *hComPropSheet*: Group parent handle  

- *Function*: Caller sets this function code parameter to **CPSFUNC_IGNORE_CPSUI_PSN_APPLY** when it calls **ComPropSheet** to disable or reenable CPSUI's handling of the PSN_APPLY notification message

- *lParam1*: CPSUI handle that refers to a set of one or more property sheet pages. This handle must have been previously obtained by a call to **ComPropSheet** with a function code of **CPSFUNC_ADD_PCOMPROPSHEETUI**, or with a function code of **CPSFUNC_INSERT_PSUIPAGE** and an insertion type of **PSUIPAGEINSERT_PROPSHEETPAGE**.

- *lParam2*: Any nonzero value disables CPSUI's delivery of the **CPSUICB_REASON_APPLYNOW** reason. A zero value reenables delivery of the **CPSUICB_REASON_APPLYNOW** reason.

##### Return value (CPSFUNC_IGNORE_CPSUI_PSN_APPLY)

If the operation succeeds, the **ComPropSheet** function returns a nonzero value; otherwise it returns zero.

#### CPSFUNC_INSERT_PSUIPAGE

The **CPSFUNC_INSERT_PSUIPAGE** function code causes the **ComPropSheet** function to insert a set of property sheet pages at a specific position.

##### Parameters (CPSFUNC_INSERT_PSUIPAGE)

- *hComPropSheet*: Group parent handle  

- *Function*: Caller sets this function code parameter to **CPSFUNC_INSERT_PSUIPAGE** when it calls **ComPropSheet** to insert a set of property sheet pages at a specific position

- *lParam1*: Specifies a handle to a set of one or more property sheet pages. The new pages will be inserted before or after these pages, depending on the Mode member of the **INSERTPSUIPAGE_INFO** structure pointed to by *lParam2*. This handle must previously have been obtained by a call to **ComPropSheet** with one of the following function codes:

  - **CPSFUNC_ADD_HPROPSHEETPAGE**

  - **CPSFUNC_ADD_PCOMPROPSHEETUI**

  - **CPSFUNC_ADD_PFNPROPSHEETUI**

  - **CPSFUNC_ADD_PROPSHEETPAGE**

  - **CPSFUNC_INSERT_PSUIPAGE**

- *lParam2*: Pointer to an **INSERTPSUIPAGE_INFO** structure, describing where and how the new pages should be inserted

##### Return value (CPSFUNC_INSERT_PSUIPAGE)

If the operation succeeds, the **ComPropSheet** function returns a handle to the set of pages that were inserted; otherwise, the function returns NULL.

#### CPSFUNC_LOAD_CPSUI_ICON

The **CPSFUNC_LOAD_CPSUI_ICON** function code causes the **ComPropSheet** function to load a CPSUI-supplied icon resource.

CPSUI calls [**LoadImage**](/windows/win32/api/winuser/nf-winuser-loadimagew) to load the specified icon resource.

##### Parameters (CPSFUNC_LOAD_CPSUI_ICON)

- *hComPropSheet*: Group parent handle  

- *Function*: Caller sets this function code parameter to **CPSFUNC_LOAD_CPSUI_ICON** when it calls **ComPropSheet** to load a CPSUI-supplied icon resource

- *lParam1*: Resource identifier of the CPSUI-supplied icon to be loaded. This must be an IDI_CPSUI-prefixed identifier as defined in Compstui.h.

- *lParam2*: Specifies two WORD-sized values representing the icon's size, in pixels. The LOWORD value is the width, and the HIWORD value is the height. If these values are zero, the system metrics SM_CXICON and SM_CYICON are used. For more information, see [**GetSystemMetrics**](/windows/win32/api/winuser/nf-winuser-getsystemmetrics)

##### Return value (CPSFUNC_LOAD_CPSUI_ICON)

If the operation succeeds, the **ComPropSheet** function returns an icon handle; otherwise it returns NULL.

#### CPSFUNC_LOAD_CPSUI_STRING

The **CPSFUNC_LOAD_CPSUI_STRING** function code causes the **ComPropSheet** function to load a CPSUI-supplied string resource.

The **ComPropSheet** function calls the **LoadString**](/windows/win32/api/winuser/nf-winuser-loadstringw) function to load the specified string.

##### Parameters (CPSFUNC_LOAD_CPSUI_STRING)

- *hComPropSheet*: Group parent handle  

- *Function*: Caller sets this function code parameter to **CPSFUNC_LOAD_CPSUI_STRING** when it calls ComPropSheet to load a CPSUI-supplied string resource

- *lParam1*: An LPSTR-typed pointer to a caller-allocated buffer, into which the CPSUI-supplied string specified by HIWORD(*lParam2*) will be placed

- *lParam2*: Contains the following two caller-supplied values:

  - LOWORD(*lParam2*). Size, in bytes, of the buffer pointed to by lParam1.

  - HIWORD(*lParam2*). Resource identifier of the CPSUI-supplied string to be loaded. This must be an IDS_CPSUI-prefixed identifier as defined in Compstui.h.

##### Return value (CPSFUNC_LOAD_CPSUI_STRING)

If the operation succeeds, the **ComPropSheet** function returns the length of the string. If an invalid resource identifier is specified, the function returns zero. If *lParam1* is NULL or LOWORD(*lParam2*) is zero, the function returns -1.

#### CPSFUNC_QUERY_DATABLOCK

The **CPSFUNC_QUERY_DATABLOCK** function code causes the **ComPropSheet** function to retrieve a caller-supplied data block that was previously stored using the **CPSFUNC_SET_DATABLOCK** function code.

Typically, this function code is used by a _CPSUICALLBACK-typed callback function (when the function's **CPSUICBPARAM** structure contains a Reason value of **CPSUICB_REASON_SETACTIVE**) to retrieve values associated with another page before the current page becomes inactive.

##### Parameters (CPSFUNC_QUERY_DATABLOCK)

- *hComPropSheet*: Group parent handle  

- *Function*: Caller sets this function code parameter to **CPSFUNC_QUERY_DATABLOCK** when it calls ComPropSheet to retrieve a caller-supplied data block

- *lParam1*: Pointer to a **CPSUIDATABLOCK** structure that identifies the size and location of a buffer to receive the requested data block

- *lParam2*: DWORD-sized identifier value, used to identify the requested **CPSUIDATABLOCK** structure. This value must have been specified in a previous call to **ComPropSheet** using the **CPSFUNC_SET_DATABLOCK** function code.

##### Return value (CPSFUNC_QUERY_DATABLOCK)

If the operation succeeds, the **ComPropSheet** function returns a value that represents the size of the retrieved data block. If *lParam1* is NULL, or if the value of any member of the supplied **CPSUIDATABLOCK** structure is zero, **ComPropSheet** returns the size required to store the data block. If an error occurs, the function returns a value less than or equal to zero.

#### CPSFUNC_SET_DATABLOCK

The **CPSFUNC_SET_DATABLOCK** function code causes the **ComPropSheet** function to store a caller-supplied data block. You can use this function code to make the information about a property sheet page available to other pages.

Typically, this function code is used by a _CPSUICALLBACK-typed callback function (when the function's **CPSUICBPARAM** structure contains a Reason value of **CPSUICB_REASON_KILLACTIVE**) to save values associated with a page before it becomes inactive.

##### Parameters (CPSFUNC_SET_DATABLOCK)

- *hComPropSheet*: Group parent handle  

- *Function*: Caller sets this function code parameter to **CPSFUNC_SET_DATABLOCK** when it calls **ComPropSheet** to store a caller-supplied data block

- *lParam1*: Pointer to a **CPSUIDATABLOCK** structure that describes the data block to be stored

- *lParam2*: Caller-defined DWORD-sized identifier value. It is used to identify the supplied **CPSUIDATABLOCK** structure in subsequent calls to **ComPropSheet** using the **CPSFUNC_QUERY_DATABLOCK** function code.

##### Return value (CPSFUNC_SET_DATABLOCK)

If the operation is successful, the **ComPropSheet** function returns a value representing the number of bytes that were stored; otherwise it returns a value less than or equal to zero.

#### CPSFUNC_SET_DMPUB_HIDEBITS

The **CPSFUNC_SET_DMPUB_HIDEBITS** function code causes the **ComPropSheet** function to "hide" a specified set of document property options, so that they are not displayed.

You can use the **CPSFUNC_SET_DMPUB_HIDEBITS** function code if you want to define OPTITEM structures for one or more document property sheet options, but you do not want the options to be user-modifiable. The property sheet page must be defined using the **COMPROPSHEETUI** structure, and the structure's pDlgPage member must be **CPSUI_PDLGPAGE_DOCPROP** or **CPSUI_PDLGPAGE_ADVDOCPROP**.

If you use the **CPSFUNC_SET_DMPUB_HIDEBITS** function code, it must be specified to **ComPropSheet** before the **CPSFUNC_ADD_PCOMPROPSHEETUI** or **CPSFUNC_INSERT_PSUIPAGE** function code is used to create the page.

##### Parameters (CPSFUNC_SET_DMPUB_HIDEBITS)

- *hComPropSheet*: Group parent handle  

- *Function*: Caller sets this function code parameter to **CPSFUNC_SET_DMPUB_HIDEBITS** when it calls **ComPropSheet** to "hide" a specified set of document property options

- *lParam1*: Pointer to a bit array that indicates the options to be hidden. This array must be created using the **MAKE_DMPUB_HIDEBIT**(DMPub) macro, where DMPub is the OR-combination of one or more DMPUB_-prefixed constants. The DMPUB_-prefixed constants are listed in the description of the **OPTITEM** structure. The macro and constants are defined in Compstui.h.

- *lParam2*: Not used, must be zero

##### Return value (CPSFUNC_SET_DMPUB_HIDEBITS)

If the operation is successful, the **ComPropSheet** function returns the value specified for *lParam1*; otherwise it returns zero.

#### CPSFUNC_SET_FUSION_CONTEXT

The **CPSFUNC_SET_FUSION_CONTEXT** sets a Fusion activation context for the specified page.

When a page is about to be created or inserted and it does not specify an activation context in its [**PROPSHEETPAGE**](/windows/win32/controls/pss-propsheetpage) structure, it will be created in the parent's page activation context.

If the parent's activation context is not set, then Compstui.dll looks up the parent's parent, continuing until the top level parent is reached or until it finds a parent with an activation context properly set.

If none of the parents has an activation context set, then Compstui.dll will not specify an activation context in the **PROPSHEETPAGE** structure. This means that the page will be created in the activation context of the caller of the [**PropertySheet**](/windows/win32/api/prsht/nf-prsht-propertysheetw) function.

##### Parameters (CPSFUNC_SET_FUSION_CONTEXT)

- *hComPropSheet*: Group parent handle  

- *Function*: Caller sets this function code parameter to **CPSFUNC_SET_FUSION_CONTEXT** when it calls **ComPropSheet** to set a Fusion activation context for the specified page

- *lParam1*: Specifies the handle to the Fusion context. Compstui.dll duplicates the handle, attaching it to its internal structures, so that the caller is not obligated to retain the handle. Compstui.dll releases the passed-in context handle when the Compstui.dll handle is deleted.

- *lParam2*: Not used, must be zero

##### Return value (CPSFUNC_SET_FUSION_CONTEXT)

If the operation is successful, the **ComPropSheet** function returns a value greater than zero. Otherwise, **ComPropSheet** returns a value that is less than or equal to zero. For information about the error, use the [**GetLastError**](/windows/win32/api/errhandlingapi/nf-errhandlingapi-getlasterror) function.

#### CPSFUNC_SET_HSTARTPAGE

The **CPSFUNC_SET_HSTARTPAGE** function code causes the **ComPropSheet** function to mark a specified property sheet page to be the top page of the associated property sheet. If the property sheet is currently being displayed, the specified page becomes the active page.

##### Parameters (CPSFUNC_SET_HSTARTPAGE)

- *hComPropSheet*: Group parent handle  

- *Function*: Caller sets this function code parameter to **CPSFUNC_SET_HSTARTPAGE** when it calls **ComPropSheet** to mark a specified property sheet page to be the top page of the associated property sheet

- *lParam1*: Caller-supplied CPSUI page handle, previously obtained by a call to **ComPropSheet** with one of the following function codes:

  - **CPSFUNC_ADD_HPROPSHEETPAGE**

  - **CPSFUNC_ADD_PCOMPROPSHEETUI**

  - **CPSFUNC_ADD_PFNPROPSHEETUI**

  - **CPSFUNC_ADD_PROPSHEETPAGE**

  - **CPSFUNC_INSERT_PSUIPAGE**

  If the handle represents a single page belonging to the group specified by *hComPropSheet*, CPSUI makes this page the top page.

  If the handle represents a group parent handle (see **CPSFUNC_INSERT_PSUIPAGE**), then *lParam2* represents a zero-based index into the group's pages and the page represented by the index becomes the top page.

- *lParam2*: If lParam1 represents a group parent handle, this caller-supplied value is a zero-based index into the group's pages. If *lParam1* represents a single page belonging to the group specified by *hComPropSheet*, this parameter is not used. If the handle specified by *lParam1* was obtained using the **CPSFUNC_ADD_PCOMPROPSHEETUI** function code, and if the **pDlgPage** member of the associated **COMPROPSHEETUI** structure was set to **CPSUI_PDLGPAGE_DOCPROP**, then one of the following values can be specified for *lParam2*:

  - SSP_STDPAGE1 - Make the Layout page the top page.

  - SSP_STDPAGE2 - Make the Paper/Quality page the top page.

  - SSP_TVPAGE - Make the Advanced page the top page.

##### Return value (CPSFUNC_SET_HSTARTPAGE)

If the operation is successful, the **ComPropSheet** function returns the value specified for *lParam1*; otherwise it returns zero.

#### CPSFUNC_SET_PSUIPAGE_ICON

The **CPSFUNC_SET_PSUIPAGE_ICON** function code causes the **ComPropSheet** function to add, replace, or remove the icon assigned to the tab of a property sheet page.

If lParam2 contains an icon handle, and if the page specified by lParam1 is currently being displayed, CPSUI adds the icon to the specified page's tab. If an icon is already assigned to the page, the old icon is replaced with the new one. If lParam2 is zero, the current icon (if one exists) is removed.

For all icons specified with the **CPSFUNC_SET_PSUIPAGE_ICON** function code, CPSUI sets the image size to 16 by 16 pixels.

Icon handles should be obtained by calling [**LoadImage**](/windows/win32/api/winuser/nf-winuser-loadimagew).

##### Parameters (CPSFUNC_SET_PSUIPAGE_ICON)

- *hComPropSheet*: Group parent handle  

- *Function*: Caller sets this function code parameter to **CPSFUNC_SET_PSUIPAGE_ICON** when it calls **ComPropSheet** to add, replace, or remove the icon assigned to the tab of a property sheet page

- *lParam1*: Caller-supplied CPSUI page handle, previously obtained by a call to **ComPropSheet** with one of the following function codes:

  - **CPSFUNC_ADD_HPROPSHEETPAGE**

  - **CPSFUNC_ADD_PROPSHEETPAGE**

  - **CPSFUNC_INSERT_PSUIPAGE** (with the Type member of the **INSERTPSUIPAGE_INFO** structure set to **PSUIPAGEINSERT_HPROPSHEETPAGE** or **PSUIPAGEINSERT_PROPSHEETPAGE**)

- *lParam2*: Caller-supplied icon handle. You can set this parameter to zero to remove the current icon

##### Return value (CPSFUNC_SET_PSUIPAGE_ICON)

If the operation is successful, the **ComPropSheet** function returns 1. If an error is encountered, or if the specified page is not currently being displayed, the function returns zero.

#### CPSFUNC_SET_PSUIPAGE_TITLE

The **CPSFUNC_SET_PSUIPAGE_TITLE** function code causes the **ComPropSheet** function to set the tab title for a property sheet page.

##### Parameters (CPSFUNC_SET_PSUIPAGE_TITLE)

- *hComPropSheet*: Group parent handle  

- *Function*: Caller sets this function code parameter to **CPSFUNC_SET_PSUIPAGE_TITLE** when it calls **ComPropSheet** to set the tab title for a property sheet page

- *lParam1*: Caller-supplied CPSUI page handle, previously obtained by a call to **ComPropSheet** with one of the following function codes:

  - **CPSFUNC_ADD_HPROPSHEETPAGE**

  - **CPSFUNC_ADD_PROPSHEETPAGE**

  - **CPSFUNC_INSERT_PSUIPAGE** (with the Type member of the **INSERTPSUIPAGE_INFO** structure set to **PSUIPAGEINSERT_HPROPSHEETPAGE** or **PSUIPAGEINSERT_PROPSHEETPAGE**).

- *lParam2*: Caller-supplied pointer to a NULL-terminated string that specifies the new title

##### Return value (CPSFUNC_SET_PSUIPAGE_TITLE)

If the operation is successful, the **ComPropSheet** function returns 1. If an error is encountered, or if the specified page is not currently being displayed, the function returns zero.

#### CPSFUNC_SET_RESULT

The **CPSFUNC_SET_RESULT** function code causes the **ComPropSheet** function to pass a specified result value to all PFNPROPSHEETUI-typed functions associated with a specified page and its parents.

For more information about how to set result values, see the description of the **SETRESULT_INFO** structure.

The following caution applies to Unidrv- or Pscript5-based IHV UI plug-in with custom UI property sheets, and for which user settings made in the property sheets should be persistent. When the plug-in calls the **ComPropSheet** function with the Function parameter set to **CPSFUNC_SET_RESULT**, the plug-in must set the lParam2 parameter to **CPSUI_OK**.

##### Parameters (CPSFUNC_SET_RESULT)

- *hComPropSheet*: Group parent handle  

- *Function*: Caller sets this function code parameter to **CPSFUNC_SET_RESULT** when it calls **ComPropSheet** to pass a specified result value to all PFNPROPSHEETUI-typed functions associated with a specified page and its parents.

- *lParam1*: Caller-supplied CPSUI handle to the page for which a result value is being passed. If lParam1 is NULL, the CPSUI uses the value specified by *hComPropSheet*.

- *lParam2*: Caller-supplied 32-bit DWORD result value.

##### Return value (CPSFUNC_SET_RESULT)

If the operation is successful, the **ComPropSheet** function returns the number of PFNPROPSHEETUI-typed functions that were called. If the handle specified for *lParam1* is invalid, the function returns -1.
