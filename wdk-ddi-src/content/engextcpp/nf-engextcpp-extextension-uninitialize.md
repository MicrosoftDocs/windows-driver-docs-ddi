---
UID: NF:engextcpp.ExtExtension.Uninitialize
title: ExtExtension::Uninitialize method
author: windows-driver-content
description: The Uninitialize method is called by the engine to uninitialize an EngExtCpp extension library before it is unloaded.
old-location: debugger\uninitialize.htm
old-project: debugger
ms.assetid: 2c8f0005-523b-4223-9859-a586f73db206
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: EngExtCpp_Ref_614648b0-a948-4066-bec1-0840e2cf08ec.xml, ExtExtension, ExtExtension class [Windows Debugging], Uninitialize method, ExtExtension::Uninitialize, Uninitialize method [Windows Debugging], Uninitialize method [Windows Debugging], ExtExtension class, Uninitialize,ExtExtension.Uninitialize, debugger.uninitialize
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	engextcpp.hpp
api_name:
-	ExtExtension.Uninitialize
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtExtension::Uninitialize method


## -description


The <b>Uninitialize</b> method is called by the engine to uninitialize an EngExtCpp extension library before it is unloaded.


## -syntax


````
virtual void Uninitialize();
````


## -parameters






## -returns



This method does not return a value.




## -remarks



If this method is defined in the extension library class <a href="https://msdn.microsoft.com/library/windows/hardware/ff544508">EXT_CLASS</a>, it can be used by the extension library to clean up before it is unloaded.

There may or may not be a debugging session active when this function is called, so you should not assume that the extension can query session information.




## -see-also

<a href="..\engextcpp\nf-engextcpp-extextension-initialize.md">Initialize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544508">EXT_CLASS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543981">ExtExtension</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ExtExtension.Uninitialize method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

