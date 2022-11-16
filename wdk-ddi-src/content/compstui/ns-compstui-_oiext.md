---
UID: NS:compstui._OIEXT
title: OIEXT (compstui.h)
description: The OIEXT structure supplies additional, optional information about a property sheet page option that is described by an OPTITEM structure.
tech.root: print
ms.date: 11/15/2022
keywords: ["OIEXT structure"]
ms.keywords: "*POIEXT, OIEXT, OIEXT structure [Print Devices], POIEXT, POIEXT structure pointer [Print Devices], _OIEXT, compstui/OIEXT, compstui/POIEXT, cpsuifnc_3abbb233-5393-4e23-a206-0474cfd6d7f1.xml, print.oiext"
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
req.typenames: OIEXT, *POIEXT
f1_keywords:
 - _OIEXT
 - compstui/_OIEXT
 - POIEXT
 - compstui/POIEXT
 - OIEXT
 - compstui/OIEXT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - compstui.h
api_name:
 - _OIEXT
 - POIEXT
 - OIEXT
---

## -description

The **OIEXT** structure supplies additional, optional information about a property sheet page option that is described by an [OPTITEM](/windows-hardware/drivers/ddi/compstui/ns-compstui-_optitem) structure.

## -struct-fields

### -field cbSize

Size, in bytes, of the **OIEXT** structure.

### -field Flags

Can contain the following bit flag:

| Flag | Description |
|---|---|
| OIEXTF_ANSI_STRING | If set, **pHelpFile** points to an ANSI string. If not set, **pHelpFile** points to a Unicode string. CPSUI does not check this flag if **pHelpFile** specifies a resource ID. |

### -field hInstCaller

Instance handle to a DLL containing string and icon resources belonging to the [OPTITEM](/windows-hardware/drivers/ddi/compstui/ns-compstui-_optitem), [**OPTTYPE**](/windows-hardware/drivers/ddi/compstui/ns-compstui-_opttype), and [**OPTPARAM**](/windows-hardware/drivers/ddi/compstui/ns-compstui-_optparam) structures associated with the OIEXT structure. If **NULL**, CPSUI obtains resources from the DLL identified by the **hInstCaller** member of a [**COMPROPSHEETUI**](/windows-hardware/drivers/ddi/compstui/ns-compstui-_compropsheetui) structure.

### -field pHelpFile

Pointer to a NULL-terminated string representing a path to a help file containing help information for the option. This can be a 32-bit pointer to a NULL-terminated string, or it can be a 16-bit string resource identifier with HIWORD set to zero. If **NULL**, CPSUI uses the help file identified by the **pHelpFile** member of a [**COMPROPSHEETUI**](/windows-hardware/drivers/ddi/compstui/ns-compstui-_compropsheetui) structure.

### -field dwReserved

Reserved, must be initialized to zero.
