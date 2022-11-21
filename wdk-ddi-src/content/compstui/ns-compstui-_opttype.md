---
UID: NS:compstui._OPTTYPE
title: OPTTYPE (compstui.h)
description: The OPTTYPE structure is used by CPSUI applications (including printer interface DLLs) for describing the type and other characteristics of a property sheet option, if the option is specified by an OPTITEM structure.
tech.root: print
ms.date: 11/16/2022
keywords: ["OPTTYPE structure"]
ms.keywords: "*POPTTYPE, OPTTYPE, OPTTYPE structure [Print Devices], POPTTYPE, POPTTYPE structure pointer [Print Devices], _OPTTYPE, compstui/OPTTYPE, compstui/POPTTYPE, cpsuifnc_de1ff2db-9eea-4daf-bc9e-2e24a2dd5271.xml, print.opttype"
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
req.typenames: OPTTYPE, *POPTTYPE
f1_keywords:
 - _OPTTYPE
 - compstui/_OPTTYPE
 - POPTTYPE
 - compstui/POPTTYPE
 - OPTTYPE
 - compstui/OPTTYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - compstui.h
api_name:
 - _OPTTYPE
 - POPTTYPE
 - OPTTYPE
---

## -description

The **OPTTYPE** structure is used by CPSUI applications (including printer interface DLLs) for describing the type and other characteristics of a [property sheet option](/windows-hardware/drivers/print/property-sheet-options), if the option is specified by an [**OPTITEM**](./ns-compstui-_optitem.md) structure.

## -struct-fields

### -field cbSize

Size, in bytes, of the **OPTTYPE** structure.

### -field Type

Specifies the [CPSUI option type](/windows-hardware/drivers/print/cpsui-option-types).

### -field Flags

Optional bit flags that modify the option's characteristics. The following flags can be set in any combination.

#### OPTTF_NOSPACE_BEFORE_POSTFIX

CPSUI should not add a space character between the string specified by the [**OPTITEM**](./ns-compstui-_optitem.md) structure's **pName** string and the [**OPTPARAM**](./ns-compstui-_optparam.md) structure's **pData** string, when displaying the option.

Valid only if the option type is or [TVOT_SCROLLBAR](/windows-hardware/drivers/print/tvot-scrollbar) or [TVOT_TRACKBAR](/windows-hardware/drivers/print/tvot-trackbar).

#### OPTTF_TYPE_DISABLED

All the **OPTPARAM** structures to which **pOptParam** points are disabled, so that none of the parameter values are user-selectable.

### -field Count

Specifies the number of [**OPTPARAM**](./ns-compstui-_optparam.md) structures to which **pOptParam** points. This member's value is dependent on the [CPSUI option type](/windows-hardware/drivers/print/cpsui-option-types).

### -field BegCtrlID

If **pDlgPage** in [**COMPROPSHEETUI**](./ns-compstui-_compropsheetui.md) identifies a CPSUI-supplied page, or if **DlgTemplateID** in [**DLGPAGE**](./ns-compstui-_dlgpage.md) identifies a CPSUI-supplied template, **BegCtrlID** is not used.

Otherwise, **BegCtrlID** must contain the first of a sequentially numbered set of Windows control identifiers. Control identifier usage is dependent on the [CPSUI option type](/windows-hardware/drivers/print/cpsui-option-types).

### -field pOptParam

Pointer to an array of [**OPTPARAM**](./ns-compstui-_optparam.md) structures describing the parameter values that a user can select for the option.

### -field Style

Specifies flags that can be used to modify the option's display characteristics. The flags that can be specified are dependent on the [CPSUI option type](/windows-hardware/drivers/print/cpsui-option-types).

### -field wReserved

Reserved, must be initialized to zero.

### -field dwReserved

Reserved, must be initialized to zero.