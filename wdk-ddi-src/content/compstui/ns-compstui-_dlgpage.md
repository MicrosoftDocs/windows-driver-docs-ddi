---
UID: NS:compstui._DLGPAGE
title: DLGPAGE (compstui.h)
description: The DLGPAGE structure is used for specifying a property sheet page to CPSUI's ComPropSheet function. The structure's address is included in a COMPROPSHEETUI structure, and all member values are supplied by the ComPropSheet caller.
tech.root: print
ms.date: 11/15/2022
keywords: ["DLGPAGE structure"]
ms.keywords: "*PDLGPAGE, DLGPAGE, DLGPAGE structure [Print Devices], PDLGPAGE, PDLGPAGE structure pointer [Print Devices], _DLGPAGE, compstui/DLGPAGE, compstui/PDLGPAGE, cpsuifnc_5054b61d-a4fc-4017-a491-4d753ce3e137.xml, print.dlgpage"
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
req.typenames: DLGPAGE, *PDLGPAGE
f1_keywords:
 - _DLGPAGE
 - compstui/_DLGPAGE
 - PDLGPAGE
 - compstui/PDLGPAGE
 - DLGPAGE
 - compstui/DLGPAGE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - compstui.h
api_name:
 - _DLGPAGE
 - PDLGPAGE
 - DLGPAGE
---

## -description

The **DLGPAGE** structure is used for specifying a property sheet page to CPSUI's [ComPropSheet](/windows-hardware/drivers/ddi/compstui/nc-compstui-pfncompropsheet) function. The structure's address is included in a [**COMPROPSHEETUI**](/windows-hardware/drivers/ddi/compstui/ns-compstui-_compropsheetui) structure, and all member values are supplied by the **ComPropSheet** caller.

## -struct-fields

### -field cbSize

Caller-supplied size, in bytes, of the **DLGPAGE** structure.

### -field Flags

Caller-supplied bit flags, as described in the following table.

| Flag | Definition |
|---|---|
| DPF_ICONID_AS_HICON | If set, IconID contains an icon handle. If not set, IconID contains an icon resource identifier. |
| DPF_USE_HDLGTEMPLATE | If set, **hDlgTemplate** contains a template handle. If not set, **DlgTemplateID** contains a template resource identifier. |

Optional, caller-supplied [DLGPROC](/windows/win32/api/winuser/nc-winuser-dlgproc)-typed pointer to a dialog box procedure, used to process messages sent by the system when user events occur. If **NULL**, CPSUI supplies a dialog box procedure. For more information, see the Remarks section below.

### -field pTabName

Caller-supplied pointer to a NULL-terminated string to be displayed on the page tab.

### -field IconID

Caller-supplied, can be one of the following:

- An icon resource identifier. This can be application-defined, or it can be one of the CPSUI-supplied, IDI_CPSUI-prefixed icon resource identifiers.

- An icon handle. If a handle is specified, DPF_ICONID_AS_HICON must be set in the **Flags** member.

The specified icon is displayed on the page tab. If this value is zero, an icon is not displayed.

### -field DUMMYUNIONNAME

Defines the **DUMMYUNIONNAME** union.

### -field DUMMYUNIONNAME.DlgTemplateID

Caller-supplied resource identifier for a dialog box template. This can refer to an application-supplied DIALOG resource, or it can be one of the following CPSUI-supplied identifiers (defined in compstui.h):

| Identifier | Type of page |
|---|---|
| DP_STD_DOCPROPPAGE1 | Nontreeview page, used for a print document's **Layout** page. |
| DP_STD_DOCPROPPAGE2 | Nontreeview page, used for a print document's **Paper/Quality** page. |
| DP_STD_TREEVIEWPAGE | Generic treeview page. |

The CPSUI-supplied identifiers refer to templates that can display [CPSUI option types](/windows-hardware/drivers/print/cpsui-option-types). The page size for those templates is 252 by 216 dialog box units. For more information, see [CPSUI-Supplied Pages and Templates](/windows-hardware/drivers/print/cpsui-supplied-pages-and-templates).

This member is not used if DPF_USE_HDLGTEMPLATE is set in **Flags**.

### -field DUMMYUNIONNAME.hDlgTemplate

Caller-supplied handle to a [**DLGTEMPLATE**](/windows/win32/api/winuser/ns-winuser-dlgtemplate) structure.

Used only if DPF_USE_HDLGTEMPLATE is set in **Flags**.

## -remarks

CPSUI creates a property sheet page by allocating a [**PROPSHEETPAGE**](/windows/win32/controls/pss-propsheetpage) structure and passing it to [CreatePropertySheetPage](/windows/win32/api/prsht/nf-prsht-createpropertysheetpagew). If the caller has specified a DLGPROC-typed pointer to a dialog box procedure in [DlgProc](/windows/win32/api/winuser/nc-winuser-dlgproc), that procedure is used for handling the page's window messages. If DlgProc is **NULL**, CPSUI's own dialog box procedures are used.

When the dialog box procedure pointed to by DlgProc is called with a message value of [WM_INITDIALOG](/windows/win32/dlgbox/wm-initdialog), it receives the **PROPSHEETPAGE** structure as input, and it also receives a [**PSPINFO**](/windows-hardware/drivers/ddi/compstui/ns-compstui-_pspinfo) structure.

If a caller-supplied dialog box procedure handles a message, it should return a nonzero value. If the function does not handle the message it should return zero, which causes CPSUI to handle the message.
