---
UID: NS:compstui._EXTCHKBOX
title: EXTCHKBOX (compstui.h)
description: The EXTCHKBOX structure is used by CPSUI applications (including printer interface DLLs) for specifying an extended check box, which can be added to a property sheet page option.
tech.root: print
ms.date: 11/15/2022
keywords: ["EXTCHKBOX structure"]
ms.keywords: "*PEXTCHKBOX, EXTCHKBOX, EXTCHKBOX structure [Print Devices], PEXTCHKBOX, PEXTCHKBOX structure pointer [Print Devices], _EXTCHKBOX, compstui/EXTCHKBOX, compstui/PEXTCHKBOX, cpsuifnc_3d620423-7173-4a78-b087-f8f269c5715d.xml, print.extchkbox"
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
req.typenames: EXTCHKBOX, *PEXTCHKBOX
f1_keywords:
 - _EXTCHKBOX
 - compstui/_EXTCHKBOX
 - PEXTCHKBOX
 - compstui/PEXTCHKBOX
 - EXTCHKBOX
 - compstui/EXTCHKBOX
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - compstui.h
api_name:
 - _EXTCHKBOX
 - PEXTCHKBOX
 - EXTCHKBOX
---

## -description

The **EXTCHKBOX** structure is used by CPSUI applications (including printer interface DLLs) for specifying an extended check box, which can be added to a property sheet page option.

## -struct-fields

### -field cbSize

Size, in bytes, of the **EXTCHKBOX** structure.

### -field Flags

Bit flags, which can be one of the following:

#### ECBF_CHECKNAME_AT_FRONT

If set, CPSUI displays strings in the order "pCheckedName pSeparator *SelectName*", where *SelectName* is the string associated with the option's selected value.

If not set, CPSUI displays strings in the order "*SelectName* pSeparator pCheckedName".

#### ECBF_CHECKNAME_ONLY_ENABLED

If set, CPSUI displays the pCheckedName string only if the option is checked and enabled (that is, OPTIF_ECB_CHECKED is set and OPTIF_DISABLED is clear in the **OPTITEM** structure).

If not set, CPSUI always displays the pCheckedName string if the option is checked (that is, OPTIF_ECB_CHECKED is set in the **OPTITEM** structure), even if the option is disabled.

#### ECBF_ICONID_AS_HICON

If set, the **IconID** member contains an icon handle.

If not set, the **IconID** member contains an icon resource identifier.

#### ECBF_OVERLAY_ECBICON_IF_CHECKED

If set, and if the check box is checked (that is, OPTIF_ECB_CHECKED is set in the **OPTITEM** structure), CPSUI overlays the icon identified by the **IconID** member onto the icon associated with the option item.

#### ECBF_OVERLAY_NO_ICON

If set, CPSUI overlays its IDI_CPSUI_NO icon onto the icon identified by the **IconID** member.

#### ECBF_OVERLAY_STOP_ICON

If set, CPSUI overlays the IDI_CPSUI_STOP icon onto the icon identified by the **IconID** member.

#### ECBF_OVERLAY_WARNING_ICON

If set, CPSUI overlays its IDI_CPSUI_WARNING icon onto the icon identified by the **IconID** member.

### -field pTitle

String identifier, representing the check box title. This can be a 32-bit pointer to a NULL-terminated string, or it can be a 16-bit string resource identifier with HIWORD set to zero.

### -field pSeparator

String identifier, representing a separator character to be displayed between the checked name string and the selected option string This can be a 32-bit pointer to a NULL-terminated string, or it can be a 16-bit string resource identifier with HIWORD set to zero.

### -field pCheckedName

String identifier, representing the text to be displayed when the check box is checked. This can be a 32-bit pointer to a NULL-terminated string, or it can be a 16-bit string resource identifier with HIWORD set to zero.

### -field IconID

One of the following icon identifiers:

- An icon resource identifier. This can be application-defined, or it can be one of the CPSUI-supplied, IDI_CPSUI-prefixed icon resource identifiers.

- An icon handle. If a handle is specified, ECBF_ICONID_AS_HICON must be set in the **Flags** member.

If this value is zero, an icon is not displayed.

### -field wReserved

Reserved, must be initialized to zero.

### -field dwReserved

Reserved, must be initialized to zero.

## -remarks

An extended check box is a CPSUI-defined type of check box that can be associated with an [**OPTITEM**](./ns-compstui-_optitem.md) structure. An **OPTITEM** structure can have one extended check box or one extended push button associated with it.

## -see-also

[**EXTPUSH**](./ns-compstui-_extpush.md)