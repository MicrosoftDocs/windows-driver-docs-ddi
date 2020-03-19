---
UID: NS:compstui._OIEXT
title: _OIEXT (compstui.h)
description: The OIEXT structure supplies additional, optional information about a property sheet page option that is described by an OPTITEM structure.
old-location: print\oiext.htm
tech.root: print
ms.assetid: 932e5520-0ebf-4cfa-893a-a7eb969cb697
ms.date: 04/20/2018
keywords: ["_OIEXT structure"]
ms.keywords: "*POIEXT, OIEXT, OIEXT structure [Print Devices], POIEXT, POIEXT structure pointer [Print Devices], _OIEXT, compstui/OIEXT, compstui/POIEXT, cpsuifnc_3abbb233-5393-4e23-a206-0474cfd6d7f1.xml, print.oiext"
f1_keywords:
 - "compstui/OIEXT"
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
- OIEXT
product:
- Windows
targetos: Windows
req.typenames: OIEXT, *POIEXT
---

# _OIEXT structure


## -description


The OIEXT structure supplies additional, optional information about a property sheet page option that is described by an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/ns-compstui-_optitem">OPTITEM</a> structure.


## -struct-fields




### -field cbSize

Size, in bytes, of the OIEXT structure.


### -field Flags

Can contain the following bit flag:

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
OIEXTF_ANSI_STRING

</td>
<td>
If set, <b>pHelpFile</b> points to an ANSI string.

If not set, <b>pHelpFile</b> points to a Unicode string.

CPSUI does not check this flag if <b>pHelpFile</b> specifies a resource ID.

</td>
</tr>
</table>
 


### -field hInstCaller

Instance handle to a DLL containing string and icon resources belonging to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/ns-compstui-_optitem">OPTITEM</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/ns-compstui-_opttype">OPTTYPE</a>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/ns-compstui-_optparam">OPTPARAM</a> structures associated with the OIEXT structure. If <b>NULL</b>, CPSUI obtains resources from the DLL identified by the <b>hInstCaller</b> member of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/ns-compstui-_compropsheetui">COMPROPSHEETUI</a> structure.


### -field pHelpFile

Pointer to a NULL-terminated string representing a path to a help file containing help information for the option. This can be a 32-bit pointer to a NULL-terminated string, or it can be a 16-bit string resource identifier with HIWORD set to zero. If <b>NULL</b>, CPSUI uses the help file identified by the <b>pHelpFile</b> member of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/ns-compstui-_compropsheetui">COMPROPSHEETUI</a> structure.


### -field dwReserved

Reserved, must be initialized to zero.

