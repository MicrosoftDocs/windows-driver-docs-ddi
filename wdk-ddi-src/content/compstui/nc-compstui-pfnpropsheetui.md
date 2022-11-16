---
UID: NC:compstui.PFNPROPSHEETUI
title: PFNPROPSHEETUI (compstui.h)
description: The PFNPROPSHEETUI function type is used by CPSUI applications (including printer interface DLLs) for defining page creation callbacks, which specify property sheet pages for creation.
tech.root: print
ms.date: 11/14/2022
keywords: ["PFNPROPSHEETUI callback function"]
ms.keywords: PFNPROPSHEETUI, PFNPROPSHEETUI callback, PFNPROPSHEETUI callback function [Print Devices], compstui/PFNPROPSHEETUI, cpsuifnc_a30dfbce-634a-4eb9-b86c-fdd14d8333fd.xml, print.pfnpropsheetui
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
 - PFNPROPSHEETUI
 - compstui/PFNPROPSHEETUI
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - compstui.h
api_name:
 - PFNPROPSHEETUI
---

## -description

The PFNPROPSHEETUI function type is used by CPSUI applications (including printer interface DLLs) for defining [page creation callbacks](/windows-hardware/drivers/print/page-creation-callbacks), which specify property sheet pages for creation.

## -parameters

### -param pPSUIInfo

CPSUI-supplied pointer to a [**PROPSHEETUI_INFO**](/windows-hardware/drivers/ddi/compstui/ns-compstui-_propsheetui_info) structure.

### -param lParam

CPSUI-supplied integer value that is dependent on the contents of the **Reason** member of the [**PROPSHEETUI_INFO**](/windows-hardware/drivers/ddi/compstui/ns-compstui-_propsheetui_info) structure. Valid values are as follows:

#### PROPSHEETUI_REASON_BEFORE_INIT

This value is new to Windows 8 and it is provided only to the original PFNPROPSHEETUI parameter passed to [CommonPropertySheetUI](/windows-hardware/drivers/ddi/compstui/nf-compstui-commonpropertysheetuia).

#### PROPSHEETUI_REASON_DESTROY

The *lParam* value is nonzero if the user has selected the property sheet's **OK** or **Cancel** button. Otherwise the value is zero.

#### PROPSHEETUI_REASON_GET_ICON

The *lParam* value is a pointer to a [**PROPSHEETUI_GETICON_INFO**](/windows-hardware/drivers/ddi/compstui/ns-compstui-_propsheetui_geticon_info) structure.

#### PROPSHEETUI_REASON_GET_INFO_HEADER

The *lParam* value is a pointer to a [**PROPSHEETUI_INFO_HEADER**](/windows-hardware/drivers/ddi/compstui/ns-compstui-_propsheetui_info_header) structure.

#### PROPSHEETUI_REASON_INIT

If the callback function is specified by the *pfnPropSheetUI* parameter to [CommonPropertySheetUI](/windows-hardware/drivers/ddi/compstui/nf-compstui-commonpropertysheetuia), *lParam* is the *lParam* value passed to **CommonPropertySheetUI**.

If the callback function is specified using the CPSFUNC_ADD_PFNPROPSHEETUI function code with CPSUI's [ComPropSheet](/windows-hardware/drivers/ddi/compstui/nc-compstui-pfncompropsheet) function, *lParam* is the *lParam2* value passed to **ComPropSheet**.

CPSUI copies the *lParam* value into the **lParamInit** member of the function's [**PROPSHEETUI_INFO**](/windows-hardware/drivers/ddi/compstui/ns-compstui-_propsheetui_info) structure.

The *lParam* value must not reside on the application's stack.

#### PROPSHEETUI_REASON_SET_RESULT

The *lParam* value is a pointer to a [SETRESULT_INFO](/windows-hardware/drivers/ddi/compstui/ns-compstui-_setresult_info) structure.

## -returns

If the operation succeeds, the function should return a value of one (or greater). Otherwise it should return a value less than one.

| Return code | Description |
|---|---|
| **One or greater.** | The PFNPROPSHEETUI function associated with the parent of the current page will be called. |
| **Less than 1.** | The PFNPROPSHEETUI function associated with the parent of the current page will not be called. |

## -remarks

Callback functions specified using the PFNPROPSHEETUI function type are supplied by applications that use [CPSUI](/windows-hardware/drivers/print/common-property-sheet-user-interface) to manage customized property sheet pages. One such callback function must be specified when an application calls the [CommonPropertySheetUI](/windows-hardware/drivers/ddi/compstui/nf-compstui-commonpropertysheetuia) function. For example, when the NT-based operating system print spooler calls CPSUI's **CommonPropertySheetUI** function to support its [DocumentProperties](/windows/win32/printdocs/documentproperties) or [PrinterProperties](/windows/win32/printdocs/printerproperties) functions, the spooler specifies an internal PFNPROPSHEETUI-typed callback function.

Applications can specify additional PFNPROPSHEETUI-typed callback functions by calling CPSUI's [ComPropSheet](/windows-hardware/drivers/ddi/compstui/nc-compstui-pfncompropsheet) function with a function code of [CPSFUNC_ADD_PFNPROPSHEETUI](/previous-versions/ff546391(v=vs.85)). For example, the NT-based operating system print spooler does this to notify CPSUI of the existence of a printer interface DLL's [DrvDocumentPropertySheets](/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvdocumentpropertysheets) and [DrvDevicePropertySheets](/windows-hardware/drivers/ddi/winddiui/nf-winddiui-drvdevicepropertysheets) functions. Likewise, Microsoft's [Unidrv](/windows-hardware/drivers/) and [Pscript](/windows-hardware/drivers/) drivers use this technique to notify CPSUI of the existence of [IPrintOemUI::DocumentPropertySheets](/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemui-documentpropertysheets) and [IPrintOemUI::DevicePropertySheets](/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemui-devicepropertysheets) methods in [user interface plug-ins](/windows-hardware/drivers/print/user-interface-plug-ins).

Each PFNPROPSHEETUI-typed callback function is called by CPSUI several times. The **Reason** member of the [**PROPSHEETUI_INFO**](/windows-hardware/drivers/ddi/compstui/ns-compstui-_propsheetui_info) structure stipulates the operation that the function should perform, as follows:
