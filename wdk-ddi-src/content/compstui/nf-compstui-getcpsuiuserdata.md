---
UID: NF:compstui.GetCPSUIUserData
title: GetCPSUIUserData function
description: CPSUI's GetCPSUIUserData function retrieves data that was previously stored using the SetCPSUIUserData function.
old-location: print\getcpsuiuserdata.htm
tech.root: print
ms.assetid: 2a0a74cd-2dcf-4485-8941-7f205dcecede
ms.date: 04/20/2018
ms.keywords: GetCPSUIUserData, GetCPSUIUserData function [Print Devices], compstui/GetCPSUIUserData, cpsuifnc_78057e6d-1a47-4b92-9d43-881ab0935169.xml, print.getcpsuiuserdata
ms.topic: function
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Compstui.dll
api_name:
-	GetCPSUIUserData
product:
- Windows
targetos: Windows
req.typenames: 
---

# GetCPSUIUserData function


## -description


CPSUI's <b>GetCPSUIUserData</b> function retrieves data that was previously stored using the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562624">SetCPSUIUserData</a> function.


## -parameters




### -param hDlg

Caller-supplied handle to a property sheet dialog box. For more information, see the following Remarks section.


## -returns



If the operation succeeds, the function returns the value that was previously supplied to <a href="https://msdn.microsoft.com/library/windows/hardware/ff562624">SetCPSUIUserData</a>; otherwise the function returns zero.




## -remarks



The <b>GetCPSUIUserData</b> function should only be called from within a dialog box procedure that has been associated with a dialog box by using a <a href="https://msdn.microsoft.com/library/windows/hardware/ff547607">DLGPAGE</a> or an <a href="https://msdn.microsoft.com/library/windows/hardware/ff548795">EXTPUSH</a> structure.

The handle specified for <i>hDlg</i> must be the handle received as input to the dialog box procedure. (Dialog box procedures are described in the Microsoft Windows SDK documentation.)



