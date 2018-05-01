---
UID: NF:compstui.SetCPSUIUserData
title: SetCPSUIUserData function
author: windows-driver-content
description: CPSUI's SetCPSUIUserData function allows CPSUI applications (including printer interface DLLs) to associate nondisplayed data with a property sheet dialog box.
old-location: print\setcpsuiuserdata.htm
old-project: print
ms.assetid: 35119100-adf9-4376-bb1a-7317733fbcc5
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: SetCPSUIUserData, SetCPSUIUserData function [Print Devices], compstui/SetCPSUIUserData, cpsuifnc_d2f38387-ece5-4894-86d5-0ef66f62a72c.xml, print.setcpsuiuserdata
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	SetCPSUIUserData
product: Windows
targetos: Windows
req.typenames: 
---

# SetCPSUIUserData function


## -description


CPSUI's <code>SetCPSUIUserData</code> function allows CPSUI applications (including printer interface DLLs) to associate nondisplayed data with a property sheet dialog box.


## -parameters




### -param hDlg

Caller-supplied handle to a property sheet dialog box. For more information, see the following Remarks section.


### -param CPSUIUserData

Caller-supplied value to be stored.


## -returns



The  function returns <b>TRUE</b> if it is successful in associating the nondisplayed data with the property sheet dialog box, and <b>FALSE</b> otherwise.




## -remarks



The <code>SetCPSUIUserData</code> function should be called only from within a dialog box procedure that has been associated with a dialog box by using a <a href="https://msdn.microsoft.com/library/windows/hardware/ff547607">DLGPAGE</a> or an <a href="https://msdn.microsoft.com/library/windows/hardware/ff548795">EXTPUSH</a> structure.

A value that is stored by calling <code>SetCPSUIUserData</code> can be later retrieved by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549922">GetCPSUIUserData</a>.

The handle specified for <i>hDlg</i> must be the handle received as input to the dialog box procedure. (Dialog box procedures are described in the Microsoft Windows SDK documentation.)



