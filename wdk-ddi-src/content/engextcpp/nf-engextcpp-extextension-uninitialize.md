---
UID: NF:engextcpp.ExtExtension.Uninitialize
title: ExtExtension::Uninitialize
author: windows-driver-content
description: The Uninitialize method is called by the engine to uninitialize an EngExtCpp extension library before it is unloaded.
old-location: debugger\uninitialize.htm
tech.root: debugger
ms.assetid: 2c8f0005-523b-4223-9859-a586f73db206
ms.author: windowsdriverdev
ms.date: 5/3/2018
ms.keywords: EngExtCpp_Ref_614648b0-a948-4066-bec1-0840e2cf08ec.xml, ExtExtension class [Windows Debugging],Uninitialize method, ExtExtension.Uninitialize, ExtExtension::Uninitialize, Uninitialize, Uninitialize method [Windows Debugging], Uninitialize method [Windows Debugging],ExtExtension class, debugger.uninitialize
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
-	engextcpp.hpp
api_name:
-	ExtExtension.Uninitialize
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExtExtension::Uninitialize


## -description


The <b>Uninitialize</b> method is called by the engine to uninitialize an EngExtCpp extension library before it is unloaded.


## -parameters






## -returns



This method does not return a value.




## -remarks



If this method is defined in the extension library class <a href="https://msdn.microsoft.com/library/windows/hardware/ff544508">EXT_CLASS</a>, it can be used by the extension library to clean up before it is unloaded.

There may or may not be a debugging session active when this function is called, so you should not assume that the extension can query session information.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544508">EXT_CLASS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543981">ExtExtension</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550945">Initialize</a>
 

 

