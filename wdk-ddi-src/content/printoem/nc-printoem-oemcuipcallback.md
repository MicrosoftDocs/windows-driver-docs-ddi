---
UID: NC:printoem.OEMCUIPCALLBACK
title: OEMCUIPCALLBACK (printoem.h)
description: The OEMCUIPCALLBACK function type is used for defining callback functions that are specified by a user interface plug-in's IPrintOemUI::CommonUIProp method. The structure is defined in printoem.h.
old-location: print\oemcuipcallback.htm
tech.root: print
ms.assetid: d740bed2-ba3c-4834-8bda-3512ac8da1d5
ms.date: 04/20/2018
ms.keywords: OEMCUIPCALLBACK, OEMCUIPCALLBACK callback, OEMCUIPCALLBACK callback function [Print Devices], print.oemcuipcallback, print_unidrv-pscript_ui_e40ce896-2920-4839-99a8-ddc0a616dcad.xml, printoem/OEMCUIPCALLBACK
ms.topic: callback
f1_keywords:
 - "printoem/OEMCUIPCALLBACK"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- printoem.h
api_name:
- OEMCUIPCALLBACK
product:
- Windows
targetos: Windows
req.typenames: 
---

# OEMCUIPCALLBACK callback function


## -description


The OEMCUIPCALLBACK function type is used for defining callback functions that are specified by a user interface plug-in's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/prcomoem/nf-prcomoem-iprintoemui-commonuiprop">IPrintOemUI::CommonUIProp</a> method. The structure is defined in printoem.h.


## -parameters




### -param Arg1


### -param Arg2








#### - pCPSUICBParam

Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/compstui/ns-compstui-_cpsuicbparam">CPSUICBPARAM</a> structure.


#### - pOEMCUIPParam

Pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printoem/ns-printoem-_oemcuipparam">OEMCUIPPARAM</a> structure.


## -returns



See the following Remarks section.




## -remarks



A callback function specified by an <b>IPrintOemUI::CommonUIProp</b> method is called when a user modifies a printer property sheet. The callback function's purpose is to process user modifications to customized option items.

When a property sheet item is modified, <a href="https://docs.microsoft.com/windows-hardware/drivers/print/common-property-sheet-user-interface">CPSUI</a> calls the printer driver's printer interface DLL. This DLL contains its own callback function, of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/compstui/nc-compstui-_cpsuicallback">_CPSUICALLBACK</a>, which processes option values contained in its own OPTITEM structures. Then the printer interface DLL's callback function calls the user interface plug-in's callback function. If multiple user interface plug-ins are provided, each plug-in's callback function is called, in turn, in the order in which the plug-ins were installed.

The callback function receives a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/compstui/ns-compstui-_cpsuicbparam">CPSUICBPARAM</a> structure. The structure's <b>Reason</b> member identifies the event that caused the callback function to be called. The function also receives a pointer to the same <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/printoem/ns-printoem-_oemcuipparam">OEMCUIPPARAM</a> structure that was used when the <b>IPrintOemUI::CommonUIProp</b> method specified the callback function's address.

The CPSUICBPARAM structure's <b>pOptItem</b> and <b>pCurItem</b> members identify the modified option. The callback function can use these pointers, along with the <b>pOEMOptItems</b> and <b>cOEMOptItem</b> members of the OEMCUIPPARAM structure, to determine if the modified option is one that is owned by the user interface plug-in.

When a callback function is called, it must determine if any of its customized OPTITEM structures are affected by the specified <b>Reason</b> value. If they are, the function should process the affected options and return one of the CPSUI_ACTION-prefixed return values described for the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/compstui/nc-compstui-_cpsuicallback">_CPSUICALLBACK</a> function type. Otherwise it should return CPSUICB_ACTION_NONE.

The following additional rules apply to callback function return values:

<ul>
<li>
If <b>Reason</b> contains CPSUICB_REASON_APPLYNOW, then the callback must return either CPSUICB_ACTION_ITEMS_APPLIED or CPSUICB_ACTION_NO_APPLY_EXIT. In the latter case, the printer driver interface immediately returns to CPSUI without calling any other user interface plug-in's callback function.

</li>
<li>
If <b>Reason</b> contains any value except CPSUICB_REASON_APPLYNOW, then the return value must be one of the following:<dl>
<dd>CPSUICB_ACTION_REINIT_ITEMS</dd>
<dd>CPSUICB_ACTION_OPTIF_CHANGED</dd>
<dd>CPSUICB_ACTION_NONE</dd>
</dl>


These return values are listed in order of decreasing priority. If multiple user interface plug-ins exist, the printer interface DLL calls each one's callback function and saves the highest-priority return value, passing it back to CPSUI.

</li>
</ul>


