---
UID: NF:engextcpp.ExtExtension.OnSessionInaccessible
title: ExtExtension::OnSessionInaccessible
author: windows-driver-content
description: The OnSessionInaccessible method is called by the engine to inform the EngExtCpp extension library when the debugging session becomes inaccessible.
old-location: debugger\onsessioninaccessible.htm
old-project: debugger
ms.assetid: ba2c158a-11be-40fe-971e-f58f19a9c1b6
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: EngExtCpp_Ref_3b2329d1-7a01-42d7-951c-777d9b93faa7.xml, ExtExtension.OnSessionInaccessible, ExtExtension::OnSessionInaccessible, OnSessionInaccessible, OnSessionInaccessible method [Windows Debugging], debugger.onsessioninaccessible
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
-	OnSessionInaccessible
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExtExtension::OnSessionInaccessible


## -description


The <b>OnSessionInaccessible</b> method is called by the engine to inform the EngExtCpp extension library when the debugging session becomes inaccessible.


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



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552310">OnSessionAccessible</a>
 

 

