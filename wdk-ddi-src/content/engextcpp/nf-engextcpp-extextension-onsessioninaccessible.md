---
UID: NF:engextcpp.ExtExtension.OnSessionInaccessible
title: ExtExtension::OnSessionInaccessible method
author: windows-driver-content
description: The OnSessionInaccessible method is called by the engine to inform the EngExtCpp extension library when the debugging session becomes inaccessible.
old-location: debugger\onsessioninaccessible.htm
old-project: debugger
ms.assetid: ba2c158a-11be-40fe-971e-f58f19a9c1b6
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: EngExtCpp_Ref_3b2329d1-7a01-42d7-951c-777d9b93faa7.xml, ExtExtension, ExtExtension::OnSessionInaccessible, OnSessionInaccessible, OnSessionInaccessible method [Windows Debugging], debugger.onsessioninaccessible
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
-	OnSessionInaccessible
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtExtension::OnSessionInaccessible method


## -description


The <b>OnSessionInaccessible</b> method is called by the engine to inform the EngExtCpp extension library when the debugging session becomes inaccessible.


## -syntax


````
virtual void OnSessionInaccessible(
  [in] ULONG64 Argument
);
````


## -parameters




### -param Argument [in]

Set to zero. (Reserved for future use).


## -returns


This method does not return a value.



## -remarks


If this method is defined in the extension library class <a href="https://msdn.microsoft.com/library/windows/hardware/ff544508">EXT_CLASS</a>, it can be used to allow the extension library to cache information about the session without the need to register event callbacks.

This method is called when a target starts executing.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544508">EXT_CLASS</a>

<a href="..\engextcpp\nf-engextcpp-extextension-onsessionaccessible.md">OnSessionAccessible</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20OnSessionInaccessible method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

