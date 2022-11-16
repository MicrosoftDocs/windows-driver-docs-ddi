---
UID: NF:compstui.SetCPSUIUserData
title: SetCPSUIUserData function (compstui.h)
description: CPSUI's SetCPSUIUserData function allows CPSUI applications (including printer interface DLLs) to associate non-displayed data with a property sheet dialog box.
tech.root: print
ms.date: 11/15/2022
keywords: ["SetCPSUIUserData function"]
ms.keywords: SetCPSUIUserData, SetCPSUIUserData function [Print Devices], compstui/SetCPSUIUserData, cpsuifnc_d2f38387-ece5-4894-86d5-0ef66f62a72c.xml, print.setcpsuiuserdata
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
req.lib: Compstui.lib
req.dll: Compstui.dll
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - SetCPSUIUserData
 - compstui/SetCPSUIUserData
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Compstui.dll
api_name:
 - SetCPSUIUserData
---

## -description

CPSUI's SetCPSUIUserData function allows CPSUI applications (including printer interface DLLs) to associate non-displayed data with a property sheet dialog box.

## -parameters

### -param hDlg

Caller-supplied handle to a property sheet dialog box. For more information, see the Remarks section below.

### -param CPSUIUserData

Caller-supplied value to be stored.

## -returns

The  function returns **TRUE** if it is successful in associating the non-displayed data with the property sheet dialog box, and **FALSE** otherwise.

## -remarks

The **SetCPSUIUserData** function should be called only from within a dialog box procedure that has been associated with a dialog box by using a [**DLGPAGE**](/windows-hardware/drivers/ddi/compstui/ns-compstui-_dlgpage) or an [**EXTPUSH**](/windows-hardware/drivers/ddi/compstui/ns-compstui-_extpush) structure.

A value that is stored by calling SetCPSUIUserData can be later retrieved by calling [GetCPSUIUserData](/windows-hardware/drivers/ddi/compstui/nf-compstui-getcpsuiuserdata).

The handle specified for *hDlg* must be the handle received as input to the [dialog box procedure](/windows-hardware/drivers/print/dialog-box-procedures-and-cpsui).
