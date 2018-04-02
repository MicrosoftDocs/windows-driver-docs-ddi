---
UID: NS:winsplp.MESSAGEBOX_PARAMS
title: MESSAGEBOX_PARAMS
author: windows-driver-content
description: The MESSAGEBOX_PARAMS structure is used by the SplPromptUIInUsersSession function to hold information about the appearance and behavior of a message box.
old-location: print\messagebox_params.htm
old-project: print
ms.assetid: 28a94e25-9beb-46a1-9e9d-9fe4823372be
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PMESSAGEBOX_PARAMS, MESSAGEBOX_PARAMS, MESSAGEBOX_PARAMS structure [Print Devices], PMESSAGEBOX_PARAMS, PMESSAGEBOX_PARAMS structure pointer [Print Devices], print.messagebox_params, spoolfnc_c70908b4-e8de-4e3e-810d-d76cf2104d91.xml, winsplp/MESSAGEBOX_PARAMS, winsplp/PMESSAGEBOX_PARAMS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: winsplp.h
req.include-header: Winsplp.h
req.target-type: Windows
req.target-min-winverclnt: This structure is available in Windows XP and later operating systems.
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	winsplp.h
api_name:
-	MESSAGEBOX_PARAMS
product:
- Windows
targetos: Windows
req.typenames: MESSAGEBOX_PARAMS, *PMESSAGEBOX_PARAMS
req.product: Windows 10 or later.
---

# MESSAGEBOX_PARAMS structure


## -description


The MESSAGEBOX_PARAMS structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562679">SplPromptUIInUsersSession</a> function to hold information about the appearance and behavior of a message box.


## -struct-fields




### -field cbSize

Specifies the size, in bytes, of this structure.


### -field pTitle

Pointer to a null-terminated string that is used in the title bar of the message box.


### -field pMessage

Pointer to a null-terminated string that contains the message to display.


### -field Style

Specifies the contents and behavior of the message box. For a complete list of the values to which this member can be set, see the description of the <b>MessageBox</b> function in the Microsoft Windows SDK documentation.


### -field dwTimeout

Specifies the time, in seconds, to wait for the user's response, provided that the <b>bWait</b> member is <b>TRUE</b>.


### -field bWait

Specifies whether the <b>SplPromptUIInUsersSession</b> function should wait for a user's response. If <b>bWait</b> is <b>TRUE</b>, <b>SplPromptUIInUsersSession</b> does not return until either the user responds or the time-out interval elapses. If <b>dwTimeout</b> is zero, <b>SplPromptUIInUsersSession</b> does not return until the user responds. If <b>bWait</b> is <b>FALSE</b>, the function returns immediately with *<i>pResponse</i> set to IDASYNC. 


## -remarks



One member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562645">SHOWUIPARAMS</a> structure is a MESSAGEBOX_PARAMS structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff562645">SHOWUIPARAMS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff562679">SplPromptUIInUsersSession</a>
 

 

