---
UID: NS:printoem._USERDATA
title: USERDATA (printoem.h)
description: The USERDATA structure is used by Unidrv and Pscript to specify additional information about printer features. A USERDATA structure pointer is supplied as the UserData member for each OPTITEM structure.
tech.root: print
ms.date: 08/12/2022
keywords: ["USERDATA structure"]
ms.keywords: "*PUSERDATA, PUSERDATA, PUSERDATA structure pointer [Print Devices], USERDATA, USERDATA structure [Print Devices], _USERDATA, print.userdata, print_unidrv-pscript_ui_d0e62306-f4b7-491e-83b3-b1e2ddaddfb5.xml, printoem/PUSERDATA, printoem/USERDATA"
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
req.typenames: USERDATA, *PUSERDATA
f1_keywords:
 - _USERDATA
 - printoem/_USERDATA
 - PUSERDATA
 - printoem/PUSERDATA
 - USERDATA
 - printoem/USERDATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - printoem.h
api_name:
 - _USERDATA
 - PUSERDATA
 - USERDATA
---

## -description

The **USERDATA** structure is used by [Unidrv](/windows-hardware/drivers/) and [Pscript](/windows-hardware/drivers/) to specify additional information about printer features. A **USERDATA** structure pointer is supplied as the **UserData** member for each [**OPTITEM**](../compstui/ns-compstui-_optitem.md) structure.

## -struct-fields

### -field dwSize

Size, in bytes, of the **USERDATA** structure.

### -field dwItemID

Printer feature identifier.

### -field pKeyWordName

Pointer to a non-localized text string identifying a printer feature.

### -field dwReserved

Reserved.