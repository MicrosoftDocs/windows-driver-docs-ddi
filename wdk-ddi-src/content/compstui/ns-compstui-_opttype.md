---
UID: NS:compstui._OPTTYPE
title: _OPTTYPE (compstui.h)
description: The OPTTYPE structure is used by CPSUI applications (including printer interface DLLs) for describing the type and other characteristics of a property sheet option, if the option is specified by an OPTITEM structure.
old-location: print\opttype.htm
tech.root: print
ms.assetid: 041dd438-e837-4912-bda7-de654204198b
ms.date: 04/20/2018
ms.keywords: "*POPTTYPE, OPTTYPE, OPTTYPE structure [Print Devices], POPTTYPE, POPTTYPE structure pointer [Print Devices], _OPTTYPE, compstui/OPTTYPE, compstui/POPTTYPE, cpsuifnc_de1ff2db-9eea-4daf-bc9e-2e24a2dd5271.xml, print.opttype"
ms.topic: struct
f1_keywords:
 - "compstui/OPTTYPE"
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
- OPTTYPE
product:
- Windows
targetos: Windows
req.typenames: OPTTYPE, *POPTTYPE
---

# _OPTTYPE structure


## -description


The OPTTYPE structure is used by CPSUI applications (including printer interface DLLs) for describing the type and other characteristics of a <a href="https://docs.microsoft.com/windows-hardware/drivers/print/property-sheet-options">property sheet option</a>, if the option is specified by an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/compstui/ns-compstui-_optitem">OPTITEM</a> structure.


## -struct-fields




### -field cbSize

Size, in bytes, of the OPTTYPE structure.


### -field Type

Specifies the <a href="https://docs.microsoft.com/windows-hardware/drivers/print/cpsui-option-types">CPSUI option type</a>.


### -field Flags

Optional bit flags that modify the option's characteristics. The following flags can be set in any combination.





#### OPTTF_NOSPACE_BEFORE_POSTFIX

CPSUI should not add a space character between the string specified by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/compstui/ns-compstui-_optitem">OPTITEM</a> structure's <b>pName</b> string and the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/compstui/ns-compstui-_optparam">OPTPARAM</a> structure's <b>pData</b> string, when displaying the option.

Valid only if the option type is or <a href="https://docs.microsoft.com/windows-hardware/drivers/print/tvot-scrollbar">TVOT_SCROLLBAR</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/print/tvot-trackbar">TVOT_TRACKBAR</a>.





#### OPTTF_TYPE_DISABLED

All the OPTPARAM structures to which <b>pOptParam</b> points are disabled, so that none of the parameter values are user-selectable.


### -field Count

Specifies the number of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/compstui/ns-compstui-_optparam">OPTPARAM</a> structures to which <b>pOptParam</b> points. This member's value is dependent on the <a href="https://docs.microsoft.com/windows-hardware/drivers/print/cpsui-option-types">CPSUI option type</a>.


### -field BegCtrlID

If <b>pDlgPage</b> in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/compstui/ns-compstui-_compropsheetui">COMPROPSHEETUI</a> identifies a CPSUI-supplied page, or if <b>DlgTemplateID</b> in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/compstui/ns-compstui-_dlgpage">DLGPAGE</a> identifies a CPSUI-supplied template, <b>BegCtrlID</b> is not used.

Otherwise, <b>BegCtrlID</b> must contain the first of a sequentially numbered set of Windows control identifiers. Control identifier usage is dependent on the <a href="https://docs.microsoft.com/windows-hardware/drivers/print/cpsui-option-types">CPSUI option type</a>.


### -field pOptParam

Pointer to an array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/compstui/ns-compstui-_optparam">OPTPARAM</a> structures describing the parameter values that a user can select for the option.


### -field Style

Specifies flags that can be used to modify the option's display characteristics. The flags that can be specified are dependent on the <a href="https://docs.microsoft.com/windows-hardware/drivers/print/cpsui-option-types">CPSUI option type</a>.


### -field wReserved

Reserved, must be initialized to zero.


### -field dwReserved

Reserved, must be initialized to zero.

