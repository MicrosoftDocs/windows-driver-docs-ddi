---
UID: NC:printoem.OEMCUIPCALLBACK
title: OEMCUIPCALLBACK (printoem.h)
description: The OEMCUIPCALLBACK function type is used for defining callback functions that are specified by a user interface plug-in's IPrintOemUI::CommonUIProp method. The structure is defined in printoem.h.
tech.root: print
ms.date: 08/05/2022
keywords: ["OEMCUIPCALLBACK callback function"]
ms.keywords: OEMCUIPCALLBACK, OEMCUIPCALLBACK callback, OEMCUIPCALLBACK callback function [Print Devices], print.oemcuipcallback, print_unidrv-pscript_ui_e40ce896-2920-4839-99a8-ddc0a616dcad.xml, printoem/OEMCUIPCALLBACK
req.header: printoem.h
req.include-header: Printoem.h, Compstui.h
req.target-type: Desktop
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
req.typenames: 
f1_keywords:
 - OEMCUIPCALLBACK
 - printoem/OEMCUIPCALLBACK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - printoem.h
api_name:
 - OEMCUIPCALLBACK
---

## -description

The OEMCUIPCALLBACK function type is used for defining callback functions that are specified by a user interface plug-in's [IPrintOemUI::CommonUIProp](/windows-hardware/drivers/ddi/prcomoem/nf-prcomoem-iprintoemui-commonuiprop) method. The structure is defined in printoem.h.

## -parameters

### -param unnamedParam1

Pointer to a [CPSUICBPARAM](/windows-hardware/drivers/ddi/compstui/ns-compstui-_cpsuicbparam) structure.

### -param unnamedParam2

Pointer to an [OEMCUIPPARAM](/windows-hardware/drivers/ddi/printoem/ns-printoem-_oemcuipparam) structure.

## -returns

See the following Remarks section.

## -remarks

A callback function specified by an **IPrintOemUI::CommonUIProp** method is called when a user modifies a printer property sheet. The callback function's purpose is to process user modifications to customized option items.

When a property sheet item is modified, [CPSUI](/windows-hardware/drivers/print/common-property-sheet-user-interface) calls the printer driver's printer interface DLL. This DLL contains its own callback function, of type [_CPSUICALLBACK](/windows-hardware/drivers/ddi/compstui/nc-compstui-_cpsuicallback), which processes option values contained in its own OPTITEM structures. Then the printer interface DLL's callback function calls the user interface plug-in's callback function. If multiple user interface plug-ins are provided, each plug-in's callback function is called, in turn, in the order in which the plug-ins were installed.

The callback function receives a pointer to a [CPSUICBPARAM](/windows-hardware/drivers/ddi/compstui/ns-compstui-_cpsuicbparam) structure. The structure's **Reason** member identifies the event that caused the callback function to be called. The function also receives a pointer to the same [OEMCUIPPARAM](/windows-hardware/drivers/ddi/printoem/ns-printoem-_oemcuipparam) structure that was used when the **IPrintOemUI::CommonUIProp** method specified the callback function's address.

The CPSUICBPARAM structure's **pOptItem** and **pCurItem** members identify the modified option. The callback function can use these pointers, along with the **pOEMOptItems** and **cOEMOptItem** members of the OEMCUIPPARAM structure, to determine if the modified option is one that is owned by the user interface plug-in.

When a callback function is called, it must determine if any of its customized OPTITEM structures are affected by the specified **Reason** value. If they are, the function should process the affected options and return one of the CPSUI_ACTION-prefixed return values described for the [_CPSUICALLBACK](/windows-hardware/drivers/ddi/compstui/nc-compstui-_cpsuicallback) function type. Otherwise it should return CPSUICB_ACTION_NONE.

The following additional rules apply to callback function return values:

- If **Reason** contains CPSUICB_REASON_APPLYNOW, then the callback must return either CPSUICB_ACTION_ITEMS_APPLIED or CPSUICB_ACTION_NO_APPLY_EXIT. In the latter case, the printer driver interface immediately returns to CPSUI without calling any other user interface plug-in's callback function.

- If **Reason** contains any value except CPSUICB_REASON_APPLYNOW, then the return value must be one of the following:

  - CPSUICB_ACTION_REINIT_ITEMS

  - CPSUICB_ACTION_OPTIF_CHANGED

  - CPSUICB_ACTION_NONE

    These return values are listed in order of decreasing priority. If multiple user interface plug-ins exist, the printer interface DLL calls each one's callback function and saves the highest-priority return value, passing it back to CPSUI.
