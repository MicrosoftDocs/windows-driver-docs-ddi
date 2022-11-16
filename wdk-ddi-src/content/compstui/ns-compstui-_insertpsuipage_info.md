---
UID: NS:compstui._INSERTPSUIPAGE_INFO
title: INSERTPSUIPAGE_INFO (compstui.h)
description: The INSERTPSUIPAGE_INFO structure is used as an input parameter to CPSUI's ComPropSheet function, if the function code is CPSFUNC_INSERT_PSUIPAGE. All member values must be supplied by the ComPropSheet caller.
tech.root: print
ms.date: 11/15/2022
keywords: ["INSERTPSUIPAGE_INFO structure"]
ms.keywords: "*PINSERTPSUIPAGE_INFO, INSERTPSUIPAGE_INFO, INSERTPSUIPAGE_INFO structure [Print Devices], PINSERTPSUIPAGE_INFO, PINSERTPSUIPAGE_INFO structure pointer [Print Devices], _INSERTPSUIPAGE_INFO, compstui/INSERTPSUIPAGE_INFO, compstui/PINSERTPSUIPAGE_INFO, cpsuifnc_0d805815-c7ca-4fd4-8a77-269d6b79588e.xml, print.insertpsuipage_info"
req.header: compstui.h
req.include-header: Compstui.h
req.target-type: Windows
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
req.typenames: INSERTPSUIPAGE_INFO, *PINSERTPSUIPAGE_INFO
f1_keywords:
 - _INSERTPSUIPAGE_INFO
 - compstui/_INSERTPSUIPAGE_INFO
 - PINSERTPSUIPAGE_INFO
 - compstui/PINSERTPSUIPAGE_INFO
 - INSERTPSUIPAGE_INFO
 - compstui/INSERTPSUIPAGE_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - compstui.h
api_name:
 - _INSERTPSUIPAGE_INFO
 - PINSERTPSUIPAGE_INFO
 - INSERTPSUIPAGE_INFO
---

## -description

The **INSERTPSUIPAGE_INFO** structure is used as an input parameter to CPSUI's [ComPropSheet](/windows-hardware/drivers/ddi/compstui/nc-compstui-pfncompropsheet) function, if the function code is [CPSFUNC_INSERT_PSUIPAGE](/previous-versions/ff546414(v=vs.85)). All member values must be supplied by the **ComPropSheet** caller.

## -struct-fields

### -field cbSize

Caller-supplied size, in bytes, of the INSERTPSUIPAGE_INFO structure.

### -field Type

Caller-supplied integer value indicating the type of insertion being requested. The member can contain one of the following constants:

#### PSUIPAGEINSERT_DLL

CPSUI calls the specified [PFNPROPSHEETUI](/windows-hardware/drivers/ddi/compstui/nc-compstui-pfnpropsheetui) typed function, with a reason value of PROPSHEETUI_REASON_INIT. The function is contained in a separate DLL.

#### PSUIPAGEINSERT_GROUP_PARENT

CPSUI creates a new [group parent](/windows-hardware/drivers/print/group-parent).

#### PSUIPAGEINSERT_HPROPSHEETPAGE

CPSUI inserts a page that has been created by calling [CreatePropertySheetPage](/windows/win32/api/prsht/nf-prsht-createpropertysheetpagew).

(This is equivalent to calling [ComPropSheet](/windows-hardware/drivers/ddi/compstui/nc-compstui-pfncompropsheet) with a function code of [CPSFUNC_ADD_HPROPSHEETPAGE](/previous-versions/ff546385(v=vs.85)).)

#### PSUIPAGEINSERT_PCOMPROPSHEETUI

CPSUI inserts pages described by a [COMPROPSHEETUI](/windows-hardware/drivers/ddi/compstui/ns-compstui-_compropsheetui) structure.

(This is equivalent to calling [ComPropSheet](/windows-hardware/drivers/ddi/compstui/nc-compstui-pfncompropsheet) with a function code of [CPSFUNC_ADD_PCOMPROPSHEETUI](/previous-versions/ff546388(v=vs.85)).)

#### PSUIPAGEINSERT_PFNPROPSHEETUI

CPSUI calls the specified [PFNPROPSHEETUI](/windows-hardware/drivers/ddi/compstui/nc-compstui-pfnpropsheetui) typed function, with a reason value of PROPSHEETUI_REASON_INIT.

(This is equivalent to calling [ComPropSheet](/windows-hardware/drivers/ddi/compstui/nc-compstui-pfncompropsheet) with a function code of [CPSFUNC_ADD_PFNPROPSHEETUI](/previous-versions/ff546391(v=vs.85)).)

#### PSUIPAGEINSERT_PROPSHEETPAGE

CPSUI inserts the page described by the specified PROPSHEETPAGE structure.

(This is equivalent to calling [ComPropSheet](/windows-hardware/drivers/ddi/compstui/nc-compstui-pfncompropsheet) with a function code of [CPSFUNC_ADD_PROPSHEETPAGE](/previous-versions/ff546394(v=vs.85)).)

### -field Mode

Caller-supplied value indicating where CPSUI should insert the new pages. It must be one of the following values:

#### INSPSUIPAGE_MODE_AFTER

CPSUI inserts pages after the page identified by the CPSUI page handle that is specified by the *lParam1* parameter to [ComPropSheet](/windows-hardware/drivers/ddi/compstui/nc-compstui-pfncompropsheet).

#### INSPSUIPAGE_MODE_BEFORE

CPSUI inserts pages before the page identified by the CPSUI page handle that is specified by the *lParam1* parameter to [ComPropSheet](/windows-hardware/drivers/ddi/compstui/nc-compstui-pfncompropsheet).

#### INSPSUIPAGE_MODE_FIRST_CHILD

CPSUI inserts pages as the first children of the parent group identified by the *hComPropSheet* parameter to [ComPropSheet](/windows-hardware/drivers/ddi/compstui/nc-compstui-pfncompropsheet).

The *lParam1* parameter to [ComPropSheet](/windows-hardware/drivers/ddi/compstui/nc-compstui-pfncompropsheet) is ignored.

#### INSPUIPAGE_MODE_INDEX

CPSUI inserts pages as children of the parent group identified by the *hComPropSheet* parameter to [ComPropSheet](/windows-hardware/drivers/ddi/compstui/nc-compstui-pfncompropsheet).

The *lParam1* parameter to [ComPropSheet](/windows-hardware/drivers/ddi/compstui/nc-compstui-pfncompropsheet) specifies a zero-based index identifying where, within the set of children, the specified pages should be inserted. If *lParam1* is 0, the pages are inserted starting at page 1; if *lParam1* is 1, the pages are inserted starting at page 2; and so on. If the index is greater than the number of existing children, the new pages are added as the last children. The *lParam1* value must be specified as HINSPSUIPAGE_INDEX(index).

#### INSPSUIPAGE_MODE_LAST_CHILD

CPSUI inserts pages as the last children of the parent group identified by the *hComPropSheet* parameter to [ComPropSheet](/windows-hardware/drivers/ddi/compstui/nc-compstui-pfncompropsheet).

The *lParam1* parameter to [ComPropSheet](/windows-hardware/drivers/ddi/compstui/nc-compstui-pfncompropsheet) is ignored.

### -field dwData1

See the **Remarks** section below.

### -field dwData2

See the **Remarks** section below.

### -field dwData3

See the **Remarks** section below.

## -remarks

dwData1, dwData2, and dwData3 members contain caller-supplied values that depend on the contents of the **Type** member, as follows:

### Type member contains PSUIPAGEINSERT_DLL

dwData1 - Caller-supplied pointer to a NULL-terminated string representing the DLL path name.

dwData2 - Caller-supplied pointer to a NULL-terminated string representing the name of a [PFNPROPSHEETUI](/windows-hardware/drivers/ddi/compstui/nc-compstui-pfnpropsheetui) typed function, contained in the specified DLL.

dwData3 - Caller-supplied 32-bit value, passed to the PFNPROPSHEETUI-typed function for its *lParam* parameter.

### Type member contains PSUIPAGEINSERT_GROUP_PARENT

dwData1 - Not used, must be zero.

dwData2 - Not used, must be zero.

dwData3 - Not used, must be zero.

### Type member contains PSUIPAGEINSERT_HPROPSHEETPAGE

dwData1 - Caller-supplied handle to a property sheet, returned by **CreatePropertySheetPage**.

dwData2 - Not used, must be zero.

dwData3 - Not used, must be zero.

### Type member contains PSUIPAGEINSERT_PCOMPROPSHEETUI

dwData1 - Caller-supplied pointer to a COMPROPSHEETUI structure.

dwData2 - On success, receives the number of pages inserted. On failure, receives an ERR_CPSUI-prefixed error code.

dwData3 - Not used, must be zero.

### Type member contains PSUIPAGEINSERT_PFNPROPSHEETUI

dwData1 - Caller-supplied pointer to a PFNPROPSHEETUI-typed function.

dwData2 - Caller-supplied 32-bit value, passed to the PFNPROPSHEETUI-typed function for its *lParam* parameter.

dwData3 - Not used, must be zero.

### Type member contains PSUIPAGEINSERT_PROPSHEETPAGE

dwData1 - Caller-supplied pointer to a PROPSHEETPAGE structure.

dwData2 - Not used, must be zero.

dwData3 - Not used, must be zero.
