---
UID: NC:compstui._CPSUICALLBACK
title: _CPSUICALLBACK (compstui.h)
description: The _CPSUICALLBACK function type is used by CPSUI applications (including printer interface DLLs) for defining a callback function intended for use as a CPSUI message handler.
old-location: print\_cpsuicallback.htm
tech.root: print
ms.assetid: 7d0f1609-5a24-4d38-9e9e-0c8e2de679a2
ms.date: 04/20/2018
ms.keywords: "_CPSUICALLBACK, _CPSUICALLBACK callback, _CPSUICALLBACK callback function [Print Devices], compstui/_CPSUICALLBACK, cpsuifnc_a5a532ac-20be-43d5-a9fb-40b918f44d51.xml, print._cpsuicallback"
ms.topic: callback
f1_keywords:
 - "compstui/_CPSUICALLBACK"
req.header: compstui.h
req.include-header: Compstui.h
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
- compstui.h
api_name:
- _CPSUICALLBACK
product:
- Windows
targetos: Windows
req.typenames: 
---

# _CPSUICALLBACK callback function


## -description


The <b>_CPSUICALLBACK</b> function type is used by CPSUI applications (including printer interface DLLs) for defining a callback function intended for use as a <a href="https://docs.microsoft.com/windows-hardware/drivers/print/cpsui-message-handler">CPSUI message handler</a>.


## -parameters




### -param pCPSUICBParam








#### - pComPropSheetUICBParam

CPSUI-supplied pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/ns-compstui-_cpsuicbparam">CPSUICBPARAM</a> structure.


## -returns



A _CPSUICALLBACK-typed callback function must return one of the values listed in the following table. Each value indicates an action that CPSUI should perform.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>CPSUICB_ACTION_ITEMS_APPLIED</b></dt>
</dl>
</td>
<td width="60%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/ns-compstui-_cpsuicbparam">CPSUICBPARAM</a> structure's <b>Reason</b> member was set to CPSUICB_REASON_APPLYNOW, and the callback function has successfully processed the current option values.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>CPSUICB_ACTION_NO_APPLY_EXIT</b></dt>
</dl>
</td>
<td width="60%">
The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/ns-compstui-_cpsuicbparam">CPSUICBPARAM</a> structure's <b>Reason</b> member was set to CPSUICB_REASON_APPLYNOW, but the callback function has detected invalid or incompatible option values. The callback function must display a dialog box telling the user of the problem.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>CPSUICB_ACTION_NONE</b></dt>
</dl>
</td>
<td width="60%">
No action by CPSUI is required.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>CPSUICB_ACTION_OPTIF_CHANGED</b></dt>
</dl>
</td>
<td width="60%">
The callback function has set the OPTIF_CHANGED flag in an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/ns-compstui-_optitem">OPTITEM</a> structure to indicate that the selected option has changed, or that another OPTIF-prefixed flag has changed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>CPSUICB_ACTION_REINIT_ITEMS</b></dt>
</dl>
</td>
<td width="60%">
The callback function has set the OPTIF_CHANGED flag in an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/ns-compstui-_optitem">OPTITEM</a> structure to indicate that <b>Flags</b> or <b>pData</b> members of the associated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/ns-compstui-_opttype">OPTTYPE</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/ns-compstui-_optparam">OPTPARAM</a> structure have changed.

</td>
</tr>
</table>
 




## -remarks



Callback functions specified using the _CPSUICALLBACK function type are supplied by applications that use <a href="https://docs.microsoft.com/windows-hardware/drivers/print/common-property-sheet-user-interface">CPSUI</a> to manage property sheet pages. If one of these callback functions is associated with a property sheet page, CPSUI calls it when user activity (such as changing the page's control focus, modifying option values, or clicking on <b>OK</b>) is detected.

A _CPSUICALLBACK-typed callback function is assigned to a property sheet page by including its address in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/ns-compstui-_compropsheetui">COMPROPSHEETUI</a> structure, which is passed to CPSUI's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/nc-compstui-pfncompropsheet">ComPropSheet</a> function when the function code is <a href="https://docs.microsoft.com/previous-versions/ff546388(v=vs.85)">CPSFUNC_ADD_PCOMPROPSHEETUI</a>.

Additionally, callback functions can be assigned to extended push buttons through the use of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/ns-compstui-_extpush">EXTPUSH</a> structures.

When one of these callback functions is called, it receives a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/ns-compstui-_cpsuicbparam">CPSUICBPARAM</a> structure. This structure describes the current option settings for the page and indicates the user event that caused the function to be called. The callback function is responsible for validating and processing the settings. It should display a dialog box if a setting (or a combination of settings) is invalid. The function's return value indicates to CPSUI whether the page needs to be redisplayed or reinitialized.

Callback functions specified with this function type cannot be used if the <b>DlgProc</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/compstui/ns-compstui-_dlgpage">DLGPAGE</a> structure specifies an application-supplied dialog box procedure. This is because _CPSUICALLBACK-typed callbacks are called from CPSUI's dialog box procedures, which are not used if the application supplies its own procedures.



