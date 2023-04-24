---
UID: NS:compstui._OPTPARAM
title: OPTPARAM (compstui.h)
description: An array of OPTPARAM structures is used by CPSUI applications (including printer interface DLLs) for describing all the parameter values associated with a property sheet option. The array's address is included in an OPTTYPE structure.
tech.root: print
ms.date: 11/16/2022
keywords: ["OPTPARAM structure"]
ms.keywords: "*POPTPARAM, OPTPARAM, OPTPARAM structure [Print Devices], POPTPARAM, POPTPARAM structure pointer [Print Devices], _OPTPARAM, compstui/OPTPARAM, compstui/POPTPARAM, cpsuifnc_1c22c283-993e-45d7-b0c7-1148eafeb13c.xml, print.optparam"
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
req.typenames: OPTPARAM, *POPTPARAM
f1_keywords:
 - _OPTPARAM
 - compstui/_OPTPARAM
 - POPTPARAM
 - compstui/POPTPARAM
 - OPTPARAM
 - compstui/OPTPARAM
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - compstui.h
api_name:
 - _OPTPARAM
 - POPTPARAM
 - OPTPARAM
---

## -description

An array of **OPTPARAM** structures is used by CPSUI applications (including printer interface DLLs) for describing all the parameter values associated with a [property sheet option](/windows-hardware/drivers/print/property-sheet-options). The array's address is included in an [**OPTTYPE**](./ns-compstui-_opttype.md) structure.

## -struct-fields

### -field cbSize

Size, in bytes, of the **OPTPARAM** structure.

### -field Flags

Optional bit flags that modify the parameter's characteristics. The following flags can be set in any combination:

#### OPTPF_DISABLED

If set, the parameter is not user-selectable. Can be used with the following option types:

[TVOT_2STATES](/windows-hardware/drivers/print/tvot-2states)

[TVOT_3STATES](/windows-hardware/drivers/print/tvot-3states)

[TVOT_COMBOBOX](/windows-hardware/drivers/print/tvot-combobox)

[TVOT_LISTBOX](/windows-hardware/drivers/print/tvot-listbox)

#### OPTPF_HIDE

If set, the parameter not displayed in the treeview. Can be used with the following option types:

[TVOT_3STATES](/windows-hardware/drivers/print/tvot-3states)

[TVOT_COMBOBOX](/windows-hardware/drivers/print/tvot-combobox)

[TVOT_LISTBOX](/windows-hardware/drivers/print/tvot-listbox)

#### OPTPF_ICONID_AS_HICON

If set, the **IconID** member contains an icon handle.

If not set, the **IconID** member contains an icon resource identifier.

#### OPTPF_OVERLAY_NO_ICON

If set, CPSUI overlays its IDI_CPSUI_NO icon onto the icon identified by the **IconID** member.

#### OPTPF_OVERLAY_STOP_ICON

If set, CPSUI overlays the IDI_CPSUI_STOP icon onto the icon identified by the **IconID** member.

#### OPTPF_OVERLAY_WARNING_ICON

If set, CPSUI overlays its IDI_CPSUI_WARNING icon onto the icon identified by the **IconID** member.

#### OPTPF_USE_HDLGTEMPLATE

If set, **lParam** contains a template handle.

If not set, **lParam** contains a template resource identifier.

(Used only if **Style** is PUSHBUTTON_TYPE_DLGPROC.)

### -field Style

Push button style, used only for the [TVOT_PUSHBUTTON](/windows-hardware/drivers/print/tvot-pushbutton) option type.

### -field pData

Pointer to the parameter's value. Use of this member is dependent on the [CPSUI option type](/windows-hardware/drivers/print/cpsui-option-types).

### -field IconID

Usually identifies the icon to be associated with the option parameter, but is sometimes used for other purposes. Use of this member is dependent on the [CPSUI option type](/windows-hardware/drivers/print/cpsui-option-types).

### -field lParam

Use of this member is dependent on the [CPSUI option type](/windows-hardware/drivers/print/cpsui-option-types).

### -field dwReserved

Reserved, must be initialized to zero.

## -remarks

If the OPTPF_HIDE flag is set in all the **OPTPARAM** structures associated with an option, CPSUI hides the entire option.