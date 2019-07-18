---
UID: NS:printoem._USERDATA
title: _USERDATA (printoem.h)
description: The USERDATA structure is used by Unidrv and Pscript to specify additional information about printer features. A USERDATA structure pointer is supplied as the UserData member for each OPTITEM structure.
old-location: print\userdata.htm
tech.root: print
ms.assetid: 5d4e5454-f44f-483a-a389-c8973263fbaa
ms.date: 04/20/2018
ms.keywords: "*PUSERDATA, PUSERDATA, PUSERDATA structure pointer [Print Devices], USERDATA, USERDATA structure [Print Devices], _USERDATA, print.userdata, print_unidrv-pscript_ui_d0e62306-f4b7-491e-83b3-b1e2ddaddfb5.xml, printoem/PUSERDATA, printoem/USERDATA"
ms.topic: struct
f1_keywords:
 - "printoem/USERDATA"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- printoem.h
api_name:
- USERDATA
product:
- Windows
targetos: Windows
req.typenames: USERDATA, *PUSERDATA
---

# _USERDATA structure


## -description


The USERDATA structure is used by <a href="https://docs.microsoft.com/windows-hardware/drivers/">Unidrv</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/">Pscript</a> to specify additional information about printer features. A USERDATA structure pointer is supplied as the <b>UserData</b> member for each <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/compstui/ns-compstui-_optitem">OPTITEM</a> structure.


## -struct-fields




### -field dwSize

Size, in bytes, of the USERDATA structure.


### -field dwItemID

Printer feature identifier.


### -field pKeyWordName

Pointer to a nonlocalized text string identifying a printer feature.


### -field dwReserved

Reserved.

