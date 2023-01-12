---
UID: NS:compstui._SETRESULT_INFO
title: SETRESULT_INFO (compstui.h)
description: The SETRESULT_INFO structure is used as an input parameter to an application's PFNPROPSHEETUI-typed callback function.
tech.root: print
ms.date: 11/16/2022
keywords: ["SETRESULT_INFO structure"]
ms.keywords: "*PSETRESULT_INFO, PSETRESULT_INFO, PSETRESULT_INFO structure pointer [Print Devices], SETRESULT_INFO, SETRESULT_INFO structure [Print Devices], _SETRESULT_INFO, compstui/PSETRESULT_INFO, compstui/SETRESULT_INFO, cpsuifnc_df5b07fc-1a38-4ae2-a994-2862d9791b10.xml, print.setresult_info"
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
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
f1_keywords:
 - _SETRESULT_INFO
 - compstui/_SETRESULT_INFO
 - PSETRESULT_INFO
 - compstui/PSETRESULT_INFO
 - SETRESULT_INFO
 - compstui/SETRESULT_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - compstui.h
api_name:
 - _SETRESULT_INFO
 - PSETRESULT_INFO
 - SETRESULT_INFO
---

## -description

The **SETRESULT_INFO** structure is used as an input parameter to an application's [PFNPROPSHEETUI](./nc-compstui-pfnpropsheetui.md)-typed callback function.

## -struct-fields

### -field cbSize

CPSUI-supplied size, in bytes, of the **SETRESULT_INFO** structure.

### -field wReserved

Reserved.

### -field hSetResult

CPSUI-supplied handle to an added property sheet page, obtained from the application. For more information, see the **Remarks** section below.

### -field Result

CPSUI-supplied handle to an added property sheet page, obtained from the application. For more information, see the **Remarks** section below.

## -remarks

When an application calls CPSUI's [ComPropSheet](./nc-compstui-pfncompropsheet.md) function, specifying a function code of [CPSFUNC_SET_RESULT](/previous-versions/ff547087(v=vs.85)), CPSUI calls all registered [PFNPROPSHEETUI](./nc-compstui-pfnpropsheetui.md)-typed functions, specifying a reason of PROPSHEETUI_REASON_SET_RESULT. When specifying this reason, CPSUI also supplies a **SETRESULT_INFO** structure.

The values contained in the structure's **hSetResult** and **Result** members are the *lParam1* and *lParam2* values, respectively, that were supplied to CPSUI's **ComPropSheet** function.

Each of the application's PFNPROPSHEETUI-typed functions is called in order, from the one most recently declared to the first one declared, until one of these functions provides a return value of less than one. At that point, CPSUI returns from its **ComPropSheet** function, providing a count of the number of PFNPROPSHEETUI-typed functions that were called.

Typically, an application's PFNPROPSHEETUI-typed function sets the **Result** member of its PROPSHEETUI_INFO structure to the value received in the **SETRESULT_INFO** structure's **Result** member. Then the function returns a value of 1 (or greater), so the next PFNPROPSHEETUI-typed function can also receive it. Each subsequently called function is associated with a page that is the parent of the page associated with the last-called function. A function can modify the contents of **SETRESULT_INFO** structure's **Result** member, causing the functions associated with parent pages to receive the new value.