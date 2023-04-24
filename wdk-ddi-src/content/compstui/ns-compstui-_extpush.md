---
UID: NS:compstui._EXTPUSH
title: EXTPUSH (compstui.h)
description: The EXTPUSH structure is used by CPSUI applications (including printer interface DLLs) for specifying an extended push button, which can be added to a property sheet page option. When the button is pushed, a new dialog can be displayed.
tech.root: print
ms.date: 11/15/2022
keywords: ["EXTPUSH structure"]
ms.keywords: "*PEXTPUSH, EXTPUSH, EXTPUSH structure [Print Devices], PEXTPUSH, PEXTPUSH structure pointer [Print Devices], _EXTPUSH, compstui/EXTPUSH, compstui/PEXTPUSH, cpsuifnc_d8f5e9ba-ef61-4adb-959f-1d0ebf456dad.xml, print.extpush"
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
req.typenames: EXTPUSH, *PEXTPUSH
f1_keywords:
 - _EXTPUSH
 - compstui/_EXTPUSH
 - PEXTPUSH
 - compstui/PEXTPUSH
 - EXTPUSH
 - compstui/EXTPUSH
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - compstui.h
api_name:
 - _EXTPUSH
 - PEXTPUSH
 - EXTPUSH
---

## -description

The **EXTPUSH** structure is used by CPSUI applications (including printer interface DLLs) for specifying an extended push button, which can be added to a property sheet page option. When the button is pushed, a new dialog can be displayed.

## -struct-fields

### -field cbSize

Size, in bytes, of the **EXTPUSH** structure.

### -field Flags

Bit flags, which can be one of the following:

| Flag | Description |
|---|---|
| EPF_ICONID_AS_HICON | If set, the **IconID** member contains an icon handle. If not set, the **IconID** member contains an icon resource identifier. |
| EPF_INCLUDE_SETUP_TITLE | If set, CPSUI appends "Setup" to the string pointed to by **pTitle**. |
| EPF_NO_DOT_DOT_DOT | If set, CPSUI does not append "..." to the string pointed to by **pTitle**. |
| EPF_OVERLAY_NO_ICON | If set, CPSUI overlays its IDI_CPSUI_NO icon onto the icon identified by the **IconID** member. |
| EPF_OVERLAY_STOP_ICON | If set, CPSUI overlays the IDI_CPSUI_STOP icon onto the icon identified by the **IconID** member. |
| EPF_OVERLAY_WARNING_ICON | If set, CPSUI overlays its IDI_CPSUI_WARNING icon onto the icon identified by the **IconID** member. |
| EPF_PUSH_TYPE_DLGPROC | If set, the **DlgProc** and **DlgTemplateID/hDlgTemplate** members are valid. If not set, the **pfnCallBack** member is valid. |
| EPF_USE_HDLGTEMPLATE | If set, **hDlgTemplate** contains a template handle. If not set, **DlgTemplateID** contains a template resource identifier. |

### -field pTitle

String identifier, representing the push button title. This can be a 32-bit pointer to a NULL-terminated string, or it can be a 16-bit string resource identifier with HIWORD set to zero.

### -field DUMMYUNIONNAME

Defines the **DUMMYUNIONNAME** union.

### -field DUMMYUNIONNAME.DlgProc

DLGPROC-typed pointer to a dialog box procedure to process messages for the push button's dialog box. For more information on using [*DialogProc*](/windows/win32/api/winuser/nc-winuser-dlgproc), see the **Remarks** section below.

If this pointer is supplied, EPF_PUSH_TYPE_DLGPROC must be set in **Flags**.

### -field DUMMYUNIONNAME.pfnCallBack

Pointer to a [_CPSUICALLBACK](./nc-compstui-_cpsuicallback.md)-typed callback function to handle the CPSUICB_REASON_PUSHBUTTON reason. For more information, see the following Remarks section.

If this pointer is supplied, EPF_PUSH_TYPE_DLGPROC must be cleared in **Flags**.

### -field IconID

One of the following icon identifiers:

- An icon resource identifier. This can be application-defined, or it can be one of the CPSUI-supplied, IDI_CPSUI-prefixed icon resource identifiers.

- An icon handle. If a handle is specified, EPF_ICONID_AS_HICON must be set in the **Flags** member.

- CPSUI displays the icon next to the push button. If this value is zero, an icon is not displayed.

### -field DUMMYUNIONNAME2

Defines the **DUMMYUNIONNAME2** union.

### -field DUMMYUNIONNAME2.DlgTemplateID

Specifies the resource ID for the dialog box.

If **DlgTemplateID** = 0 then common UI will call *DlgProc* with following parameter:

```cpp
DlgProc(hDlg, WM_USER, NULL, (LPARAM)pCPSUICBParam);
```

### -field DUMMYUNIONNAME2.hDlgTemplate

Handle to the **DLGTEMPLATE** which will be used for a pop up dialog box.

### -field dwReserved

Reserved, must be initialized to zero.

## -remarks

An extended push button is a CPSUI-defined type of push button that can be associated with an [**OPTITEM**](./ns-compstui-_optitem.md) structure. An **OPTITEM** structure can have one extended push button or one extended check box associated with it.

When you use the **EXTPUSH** structure to create a push button, you can optionally create an additional dialog box that opens when the user clicks on the button. To create this dialog box, you should specify a pointer to a dialog box procedure in the **DlgProc** member, and include a dialog template specification in either the **DlgTemplateID** or the **hDlgTemplate** member.

If EPF_USE_HDLGTEMPLATE is set in **Flags**, CPSUI creates the dialog box by calling [*DialogBoxIndirectParam*](/windows/win32/api/winuser/nf-winuser-dialogboxindirectparama), passing the contents of the **DlgProc** and **hDlgTemplate** members.

If EPF_USE_HDLGTEMPLATE is not set in **Flags**, CPSUI creates the dialog box by calling [*DialogBoxParam*](/windows/win32/api/winuser/nf-winuser-dialogboxparama), passing the contents of the **DlgProc** and **DlgTemplateID** members.

When the dialog box procedure is called with a *uMsg* value of WM_INITDIALOG, the *lParam* value is the address of a [**CPSUICBPARAM**](./ns-compstui-_cpsuicbparam.md) structure, with the **Reason** member set to CPSUICB_REASON_EXTPUSH. For more information about the *uMsg* and *lParam* parameters, see [*DialogProc*](/windows/win32/api/winuser/nc-winuser-dlgproc).

If you do not need CPSUI to display a dialog box when the user clicks on the button, you can specify the address of a [_CPSUICALLBACK](./nc-compstui-_cpsuicallback.md)-typed callback function in the **pfnCallBack** member. When a user clicks on the button, CPSUI calls the callback function. The accompanying CPSUICBPARAM structure's **Reason** member will be set to CPSUICB_REASON_EXTPUSH.

## -see-also

[**EXTCHKBOX**](./ns-compstui-_extchkbox.md)
