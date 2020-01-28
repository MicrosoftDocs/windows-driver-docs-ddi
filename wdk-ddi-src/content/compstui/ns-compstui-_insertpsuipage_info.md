---
UID: NS:compstui._INSERTPSUIPAGE_INFO
title: _INSERTPSUIPAGE_INFO (compstui.h)
description: The INSERTPSUIPAGE_INFO structure is used as an input parameter to CPSUI's ComPropSheet function, if the function code is CPSFUNC_INSERT_PSUIPAGE. All member values must be supplied by the ComPropSheet caller.
old-location: print\insertpsuipage_info.htm
tech.root: print
ms.assetid: 99ec8cfa-3ec7-4080-b22a-dba0a86b7e4a
ms.date: 04/20/2018
ms.keywords: "*PINSERTPSUIPAGE_INFO, INSERTPSUIPAGE_INFO, INSERTPSUIPAGE_INFO structure [Print Devices], PINSERTPSUIPAGE_INFO, PINSERTPSUIPAGE_INFO structure pointer [Print Devices], _INSERTPSUIPAGE_INFO, compstui/INSERTPSUIPAGE_INFO, compstui/PINSERTPSUIPAGE_INFO, cpsuifnc_0d805815-c7ca-4fd4-8a77-269d6b79588e.xml, print.insertpsuipage_info"
f1_keywords:
 - "compstui/INSERTPSUIPAGE_INFO"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- compstui.h
api_name:
- INSERTPSUIPAGE_INFO
product:
- Windows
targetos: Windows
req.typenames: INSERTPSUIPAGE_INFO, *PINSERTPSUIPAGE_INFO
---

# _INSERTPSUIPAGE_INFO structure


## -description


The INSERTPSUIPAGE_INFO structure is used as an input parameter to CPSUI's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/nc-compstui-pfncompropsheet">ComPropSheet</a> function, if the function code is <a href="https://docs.microsoft.com/previous-versions/ff546414(v=vs.85)">CPSFUNC_INSERT_PSUIPAGE</a>. All member values must be supplied by the <b>ComPropSheet</b> caller.


## -struct-fields




### -field cbSize

Caller-supplied size, in bytes, of the INSERTPSUIPAGE_INFO structure.


### -field Type

Caller-supplied integer value indicating the type of insertion being requested. The member can contain one of the following constants:





#### PSUIPAGEINSERT_DLL

CPSUI calls the specified <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/nc-compstui-pfnpropsheetui">PFNPROPSHEETUI</a> typed function, with a reason value of PROPSHEETUI_REASON_INIT. The function is contained in a separate DLL.





#### PSUIPAGEINSERT_GROUP_PARENT

CPSUI creates a new <a href="https://docs.microsoft.com/windows-hardware/drivers/print/group-parent">group parent</a>.





#### PSUIPAGEINSERT_HPROPSHEETPAGE

CPSUI inserts a page that has been created by calling <b>CreatePropertySheetPage</b> (see the Microsoft Windows SDK documentation).

(This is equivalent to calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/nc-compstui-pfncompropsheet">ComPropSheet</a> with a function code of <a href="https://docs.microsoft.com/previous-versions/ff546385(v=vs.85)">CPSFUNC_ADD_HPROPSHEETPAGE</a>.)





#### PSUIPAGEINSERT_PCOMPROPSHEETUI

CPSUI inserts pages described by a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/ns-compstui-_compropsheetui">COMPROPSHEETUI</a> structure.

(This is equivalent to calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/nc-compstui-pfncompropsheet">ComPropSheet</a> with a function code of <a href="https://docs.microsoft.com/previous-versions/ff546388(v=vs.85)">CPSFUNC_ADD_PCOMPROPSHEETUI</a>.)





#### PSUIPAGEINSERT_PFNPROPSHEETUI

CPSUI calls the specified <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/nc-compstui-pfnpropsheetui">PFNPROPSHEETUI</a> typed function, with a reason value of PROPSHEETUI_REASON_INIT.

(This is equivalent to calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/nc-compstui-pfncompropsheet">ComPropSheet</a> with a function code of <a href="https://docs.microsoft.com/previous-versions/ff546391(v=vs.85)">CPSFUNC_ADD_PFNPROPSHEETUI</a>.)





#### PSUIPAGEINSERT_PROPSHEETPAGE

CPSUI inserts the page described by the specified PROPSHEETPAGE structure.

(This is equivalent to calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/nc-compstui-pfncompropsheet">ComPropSheet</a> with a function code of <a href="https://docs.microsoft.com/previous-versions/ff546394(v=vs.85)">CPSFUNC_ADD_PROPSHEETPAGE</a>.)


### -field Mode

Caller-supplied value indicating where CPSUI should insert the new pages. It must be one of the following values:





#### INSPSUIPAGE_MODE_AFTER

CPSUI inserts pages after the page identified by the CPSUI page handle that is specified by the <i>lParam1</i> parameter to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/nc-compstui-pfncompropsheet">ComPropSheet</a>.





#### INSPSUIPAGE_MODE_BEFORE

CPSUI inserts pages before the page identified by the CPSUI page handle that is specified by the <i>lParam1</i> parameter to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/nc-compstui-pfncompropsheet">ComPropSheet</a>.





#### INSPSUIPAGE_MODE_FIRST_CHILD

CPSUI inserts pages as the first children of the parent group identified by the <i>hComPropSheet</i> parameter to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/nc-compstui-pfncompropsheet">ComPropSheet</a>.

The <i>lParam1</i> parameter to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/nc-compstui-pfncompropsheet">ComPropSheet</a> is ignored.





#### INSPUIPAGE_MODE_INDEX

CPSUI inserts pages as children of the parent group identified by the <i>hComPropSheet</i> parameter to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/nc-compstui-pfncompropsheet">ComPropSheet</a>.

The <i>lParam1</i> parameter to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/nc-compstui-pfncompropsheet">ComPropSheet</a> specifies a zero-based index identifying where, within the set of children, the specified pages should be inserted. If <i>lParam1</i> is 0, the pages are inserted starting at page 1; if <i>lParam1</i> is 1, the pages are inserted starting at page 2; and so on. If the index is greater than the number of existing children, the new pages are added as the last children. The <i>lParam1</i> value must be specified as HINSPSUIPAGE_INDEX(index).





#### INSPSUIPAGE_MODE_LAST_CHILD

CPSUI inserts pages as the last children of the parent group identified by the <i>hComPropSheet</i> parameter to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/nc-compstui-pfncompropsheet">ComPropSheet</a>.

The <i>lParam1</i> parameter to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/nc-compstui-pfncompropsheet">ComPropSheet</a> is ignored.


### -field dwData1


### -field dwData2


### -field dwData3

Caller-supplied values that depend on the contents of the <b>Type</b> member, as follows:





#### PSUIPAGEINSERT_DLL

dwData1 - Caller-supplied pointer to a NULL-terminated string representing the DLL path name.

dwData2 - Caller-supplied pointer to a NULL-terminated string representing the name of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/nc-compstui-pfnpropsheetui">PFNPROPSHEETUI</a> typed function, contained in the specified DLL.

dwData3 - Caller-supplied 32-bit value, passed to the PFNPROPSHEETUI-typed function for its <i>lParam</i> parameter.





#### PSUIPAGEINSERT_GROUP_PARENT

dwData1 - Not used, must be zero.

dwData2 - Not used, must be zero.

dwData3 - Not used, must be zero.





#### PSUIPAGEINSERT_HPROPSHEETPAGE

dwData1 - Caller-supplied handle to a property sheet, returned by <b>CreatePropertySheetPage</b>.

dwData2 - Not used, must be zero.

dwData3 - Not used, must be zero.





#### PSUIPAGEINSERT_PCOMPROPSHEETUI

dwData1 - Caller-supplied pointer to a COMPROPSHEETUI structure.

dwData2 - On success, receives the number of pages inserted. On failure, receives an ERR_CPSUI-prefixed error code.

dwData3 - Not used, must be zero.





#### PSUIPAGEINSERT_PFNPROPSHEETUI

dwData1 - Caller-supplied pointer to a PFNPROPSHEETUI-typed function.

dwData2 - Caller-supplied 32-bit value, passed to the PFNPROPSHEETUI-typed function for its <i>lParam</i> parameter.

dwData3 - Not used, must be zero.





#### PSUIPAGEINSERT_PROPSHEETPAGE

dwData1 - Caller-supplied pointer to a PROPSHEETPAGE structure.

dwData2 - Not used, must be zero.

dwData3 - Not used, must be zero.

