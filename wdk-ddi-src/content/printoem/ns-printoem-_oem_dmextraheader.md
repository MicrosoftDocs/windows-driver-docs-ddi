---
UID: NS:printoem._OEM_DMEXTRAHEADER
title: OEM_DMEXTRAHEADER (printoem.h)
description: The OEM_DMEXTRAHEADER structure must be used to define the first members of a set of private DEVMODEW structure members.
tech.root: print
ms.date: 08/12/2022
keywords: ["OEM_DMEXTRAHEADER structure"]
ms.keywords: "*POEM_DMEXTRAHEADER, OEM_DMEXTRAHEADER, OEM_DMEXTRAHEADER structure [Print Devices], POEM_DMEXTRAHEADER, POEM_DMEXTRAHEADER structure pointer [Print Devices], _OEM_DMEXTRAHEADER, print.oem_dmextraheader, print_unidrv-pscript_ui_f356f9c1-f867-4c53-8b12-be48da73de4f.xml, printoem/OEM_DMEXTRAHEADER, printoem/POEM_DMEXTRAHEADER"
req.header: printoem.h
req.include-header: Printoem.h
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
req.typenames: OEM_DMEXTRAHEADER, *POEM_DMEXTRAHEADER
f1_keywords:
 - _OEM_DMEXTRAHEADER
 - printoem/_OEM_DMEXTRAHEADER
 - POEM_DMEXTRAHEADER
 - printoem/POEM_DMEXTRAHEADER
 - OEM_DMEXTRAHEADER
 - printoem/OEM_DMEXTRAHEADER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - printoem.h
api_name:
 - _OEM_DMEXTRAHEADER
 - POEM_DMEXTRAHEADER
 - OEM_DMEXTRAHEADER
---

## -description

The **OEM_DMEXTRAHEADER** structure must be used to define the first members of a set of private [DEVMODEW](/windows/win32/api/wingdi/ns-wingdi-devmodew) structure members.

## -struct-fields

### -field dwSize

Total size, in bytes, of the added private **DEVMODEW** structure members, including the bytes contained in the **OEM_DMEXTRAHEADER** structure.

### -field dwSignature

Unique signature value that the plug-in also returns when its [IPrintOemUI::GetInfo](../prcomoem/nf-prcomoem-iprintoemui-getinfo.md) method receives the OEMGI_GETSIGNATURE flag.

### -field dwVersion

Version number of the user interface plug-in that is defining the private **DEVMODEW** structure members. The version format is developer-defined.

## -remarks

For more information about adding **DEVMODEW** structure members, see [Providing DEVMODE Structure Additions](/windows-hardware/drivers/print/providing-devmode-structure-additions).