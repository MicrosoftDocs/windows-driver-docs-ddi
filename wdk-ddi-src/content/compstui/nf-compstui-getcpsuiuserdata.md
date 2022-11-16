---
UID: NF:compstui.GetCPSUIUserData
title: GetCPSUIUserData function (compstui.h)
description: CPSUI's GetCPSUIUserData function retrieves data that was previously stored using the SetCPSUIUserData function.
tech.root: print
ms.date: 11/15/2022
keywords: ["GetCPSUIUserData function"]
ms.keywords: GetCPSUIUserData, GetCPSUIUserData function [Print Devices], compstui/GetCPSUIUserData, cpsuifnc_78057e6d-1a47-4b92-9d43-881ab0935169.xml, print.getcpsuiuserdata
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
 - GetCPSUIUserData
 - compstui/GetCPSUIUserData
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Compstui.dll
api_name:
 - GetCPSUIUserData
---

## -description

CPSUI's **GetCPSUIUserData** function retrieves data that was previously stored using the [SetCPSUIUserData](/windows-hardware/drivers/ddi/compstui/nf-compstui-setcpsuiuserdata) function.

## -parameters

### -param hDlg

Caller-supplied handle to a property sheet dialog box. For more information, see the **Remarks** section below.

## -returns

If the operation succeeds, the function returns the value that was previously supplied to [SetCPSUIUserData](/windows-hardware/drivers/ddi/compstui/nf-compstui-setcpsuiuserdata); otherwise the function returns zero.

## -remarks

The **GetCPSUIUserData** function should only be called from within a dialog box procedure that has been associated with a dialog box by using a [DLGPAGE](/windows-hardware/drivers/ddi/compstui/ns-compstui-_dlgpage) or an [EXTPUSH](/windows-hardware/drivers/ddi/compstui/ns-compstui-_extpush) structure.

The handle specified for *hDlg* must be the handle received as input to the dialog box procedure. For more information, see [Dialog box programming considerations](/windows/win32/dlgbox/dlgbox-programming-considerations).
