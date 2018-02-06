---
UID: NF:engextcpp.ExtExtension.OnSessionActive
title: ExtExtension::OnSessionActive method
author: windows-driver-content
description: The OnSessionActive method is called by the engine to inform the EngExtCpp extension library when the debugging session becomes active.
old-location: debugger\onsessionactive.htm
old-project: debugger
ms.assetid: 356675af-cc2e-4295-bb44-dc0a9377f701
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: EngExtCpp_Ref_251ac958-396c-414a-92a5-e1b02e453a69.xml, OnSessionActive method [Windows Debugging], OnSessionActive, ExtExtension, ExtExtension class [Windows Debugging], OnSessionActive method, ExtExtension::OnSessionActive, debugger.onsessionactive, OnSessionActive method [Windows Debugging], ExtExtension class
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.lib: engextcpp.hpp
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Engextcpp.hpp
apiname:
-	ExtExtension.OnSessionActive
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtExtension::OnSessionActive method


## -description


The <b>OnSessionActive</b> method is called by the engine to inform the EngExtCpp extension library when the debugging session becomes active.


## -syntax


````
virtual void OnSessionActive(
  [in] ULONG64 Argument
);
````


## -parameters




### -param Argument [in]

Set to zero. (Reserved for future use).


## -returns


This method does not return a value.



## -remarks


The session might not be accessible.

If this method is defined in the extension library class <a href="https://msdn.microsoft.com/library/windows/hardware/ff544508">EXT_CLASS</a>, it can be used to allow the extension library to cache information about the session without the need to register event callbacks.

This method is called at the beginning of a session and, if a session has already started, after the extension library is initialized.

If a target is suspended, <a href="..\engextcpp\nf-engextcpp-extextension-onsessionaccessible.md">OnSessionAccessible</a> is called instead.



## -see-also

<a href="..\engextcpp\nf-engextcpp-extextension-onsessioninactive.md">OnSessionInactive</a>

<a href="..\engextcpp\nf-engextcpp-extextension-onsessionaccessible.md">OnSessionAccessible</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543981">ExtExtension</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544508">EXT_CLASS</a>

<a href="..\engextcpp\nf-engextcpp-extextension-initialize.md">Initialize</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ExtExtension.OnSessionActive method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

