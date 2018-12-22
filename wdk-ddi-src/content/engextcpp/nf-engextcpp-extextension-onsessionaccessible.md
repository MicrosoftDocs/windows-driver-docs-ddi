---
UID: NF:engextcpp.ExtExtension.OnSessionAccessible
title: ExtExtension::OnSessionAccessible
description: The OnSessionAccessible method is called by the engine to inform the EngExtCpp extension library when the debugging session becomes accessible.
old-location: debugger\onsessionaccessible.htm
tech.root: debugger
ms.assetid: 85012fde-fc8b-4728-be5f-6acf502de9bc
ms.date: 05/03/2018
ms.keywords: EngExtCpp_Ref_88df5a39-051b-4d84-840e-8caf5414a0e6.xml, ExtExtension class [Windows Debugging],OnSessionAccessible method, ExtExtension.OnSessionAccessible, ExtExtension::OnSessionAccessible, OnSessionAccessible, OnSessionAccessible method [Windows Debugging], OnSessionAccessible method [Windows Debugging],ExtExtension class, debugger.onsessionaccessible
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Engextcpp.hpp
api_name:
-	ExtExtension.OnSessionAccessible
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExtExtension::OnSessionAccessible


## -description


The <b>OnSessionAccessible</b> method is called by the engine to inform the EngExtCpp extension library when the debugging session becomes accessible.


## -parameters




### -param Argument [in]

Set to zero. (Reserved for future use).


## -returns



This method does not return a value.




## -remarks



If this method is defined in the extension library class <a href="https://msdn.microsoft.com/library/windows/hardware/ff544508">EXT_CLASS</a>, it can be used to allow the extension library to cache information about the session without the need to register event callbacks.

This method is called when a target is suspended and, if the session is already accessible, after the extension library is initialized (and <a href="https://msdn.microsoft.com/library/windows/hardware/ff552312">OnSessionActive</a> has been called).




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544508">EXT_CLASS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543981">ExtExtension</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552312">OnSessionActive</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552315">OnSessionInaccessible</a>
 

 

