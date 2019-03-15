---
UID: NF:engextcpp.ExtExtension.OnSessionActive
title: ExtExtension::OnSessionActive (engextcpp.h)
description: The OnSessionActive method is called by the engine to inform the EngExtCpp extension library when the debugging session becomes active.
old-location: debugger\onsessionactive.htm
tech.root: debugger
ms.assetid: 356675af-cc2e-4295-bb44-dc0a9377f701
ms.date: 05/03/2018
ms.keywords: EngExtCpp_Ref_251ac958-396c-414a-92a5-e1b02e453a69.xml, ExtExtension class [Windows Debugging],OnSessionActive method, ExtExtension.OnSessionActive, ExtExtension::OnSessionActive, OnSessionActive, OnSessionActive method [Windows Debugging], OnSessionActive method [Windows Debugging],ExtExtension class, debugger.onsessionactive
ms.topic: method
req.header: engextcpp.hpp
req.include-header: Engextcpp.hpp
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
- COM
api_location:
- Engextcpp.hpp
api_name:
- ExtExtension.OnSessionActive
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExtExtension::OnSessionActive


## -description


The <b>OnSessionActive</b> method is called by the engine to inform the EngExtCpp extension library when the debugging session becomes active.


## -parameters




### -param Argument [in]

Set to zero. (Reserved for future use).


## -returns



This method does not return a value.




## -remarks



The session might not be accessible.

If this method is defined in the extension library class <a href="https://msdn.microsoft.com/library/windows/hardware/ff544508">EXT_CLASS</a>, it can be used to allow the extension library to cache information about the session without the need to register event callbacks.

This method is called at the beginning of a session and, if a session has already started, after the extension library is initialized.

If a target is suspended, <a href="https://msdn.microsoft.com/library/windows/hardware/ff552310">OnSessionAccessible</a> is called instead.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544508">EXT_CLASS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543981">ExtExtension</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550945">Initialize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552310">OnSessionAccessible</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552318">OnSessionInactive</a>
 

 

