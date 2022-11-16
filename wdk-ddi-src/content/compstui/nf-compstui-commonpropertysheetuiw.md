---
UID: NF:compstui.CommonPropertySheetUIW
title: CommonPropertySheetUIW function (compstui.h)
description: The CommonPropertySheetUIW function displays property sheet pages and provides a way for users to modify displayed values.
tech.root: print
ms.date: 11/14/2022
keywords: ["CommonPropertySheetUIW function"]
ms.keywords: CommonPropertySheetUI, CommonPropertySheetUI function [Print Devices], CommonPropertySheetUIA, CommonPropertySheetUIW, compstui/CommonPropertySheetUI, cpsuifnc_547a4235-9e08-43fc-acae-b30091032ab3.xml, print.commonpropertysheetui
req.header: compstui.h
req.include-header: Compstui.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: F
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
 - CommonPropertySheetUIW
 - compstui/CommonPropertySheetUIW
 - CommonPropertySheetUI
 - compstui/CommonPropertySheetUI
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - compstui.h
api_name:
 - CommonPropertySheetUIW
 - CommonPropertySheetUI
---

## -description

CPSUI's **CommonPropertySheetUI** function displays property sheet pages and allows user modifications to displayed values.

## -parameters

### -param hWndOwner

Caller-supplied window handle identifying the window into which new property sheet pages are to be placed.

### -param pfnPropSheetUI

Caller-supplied pointer to a [PFNPROPSHEETUI](/windows-hardware/drivers/ddi/compstui/nc-compstui-pfnpropsheetui)-typed callback function.

### -param lParam

Caller-supplied value that is used as an input argument to the *pfnPropSheetUI* function. This value can be a pointer.

### -param pResult

Caller-supplied pointer to a DWORD that receives the *pfnPropSheetUI* function's final return status. If **NULL**, the final return status is not returned. For more information, see the **Remarks** section below.

## -returns

The **CommonPropertySheetUI** function returns one of the following values:

| Return code | Description |
|---|---|
| **CPSUI_CANCEL** | The *pfnPropSheetUI* function returned a negative value. |
| **CPSUI_OK** | The operation succeeded. |
| **CPSUI_REBOOTSYSTEM** | The operation succeeded, and a dialog box procedure sent the [PSM_REBOOTSYSTEM](/windows/win32/controls/psm-rebootsystem) message. |
| **CPSUI_RESTARTWINDOWS** | The operation succeeded, and a dialog box procedure sent the [PSM_RESTARTWINDOWS](/windows/win32/controls/psm-restartwindows) message. |
| **ERR_CPSUI-prefixed error code** | A failure occurred. The ERR_CPSUI-prefixed error codes are defined in compstui.h. |

## -remarks

The **CommonPropertySheetUI** function is CPSUI's entry point for applications. A CPSUI application (such as the Microsoft NT-based operating system print spooler) can call the function to add one or more property sheet pages to a predefined parent window. CPSUI displays the pages, allows the user to modify them, and notifies the application of user activity through callback functions.

The NT-based operating system print spooler calls the **CommonPropertySheetUI** function when a Win32 application calls the spooler's [DocumentProperties](/windows/win32/printdocs/documentproperties) or [PrinterProperties](/windows/win32/printdocs/printerproperties) functions.

The callback function specified by the *pfnPropSheetUI* parameter is responsible for describing the property sheet pages to be added. For more information, see the description of the [PFNPROPSHEETUI](/windows-hardware/drivers/ddi/compstui/nc-compstui-pfnpropsheetui) function type.

The sequence of operation is as follows:

1. The **CommonPropertySheetUI** function calls the *pfnPropSheetUI* callback so the callback can describe the pages to be added by calling CPSUI's [ComPropSheet](/windows-hardware/drivers/ddi/compstui/nc-compstui-pfncompropsheet) function.

1. If the *pfnPropSheetUI* callback succeeds, the **CommonPropertySheetUI** function displays the new property sheet pages and allows the user to modify page values.

1. If the user modifies page values, a [page event callback](/windows-hardware/drivers/print/page-event-callbacks) notifies the application of the changes.

1. When the user chooses the **OK** or **Cancel** button, the **CommonPropertySheetUI** function destroys the displayed pages and returns.

For more information about the sequence of operation, see [Using CPSUI with Printer Drivers](/windows-hardware/drivers/print/using-cpsui-with-printer-drivers), in the section entitled [CPSUI](/windows-hardware/drivers/print/common-property-sheet-user-interface).

The **CommonPropertySheetUI** function actually calls the *pfnPropSheetUI* callback several times, specifying different **Reason** member values in the callback's [PROPSHEETUI_INFO](/windows-hardware/drivers/ddi/compstui/ns-compstui-_propsheetui_info) structure. Each time the callback returns, it places a result status in the PROPSHEETUI_INFO structure's **Result** member. When the **CommonPropertySheetUI** function returns, it copies the final contents of **Result** into the location pointed to by *pResult*.
