---
UID: NF:engextcpp.ExtExtension.Uninitialize
title: ExtExtension::Uninitialize (engextcpp.h)
description: The Uninitialize method is called by the engine to uninitialize an EngExtCpp extension library before it is unloaded.
old-location: debugger\uninitialize.htm
tech.root: debugger
ms.assetid: 2c8f0005-523b-4223-9859-a586f73db206
ms.date: 05/03/2018
keywords: ["ExtExtension::Uninitialize"]
ms.keywords: EngExtCpp_Ref_614648b0-a948-4066-bec1-0840e2cf08ec.xml, ExtExtension class [Windows Debugging],Uninitialize method, ExtExtension.Uninitialize, ExtExtension::Uninitialize, Uninitialize, Uninitialize method [Windows Debugging], Uninitialize method [Windows Debugging],ExtExtension class, debugger.uninitialize
f1_keywords:
 - "engextcpp/ExtExtension.Uninitialize"
 - "ExtExtension.Uninitialize"
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
- engextcpp.hpp
api_name:
- ExtExtension.Uninitialize
targetos: Windows
req.typenames: 
---

# ExtExtension::Uninitialize


## -description


The <b>Uninitialize</b> method is called by the engine to uninitialize an EngExtCpp extension library before it is unloaded.


## -returns



This method does not return a value.




## -remarks



If this method is defined in the extension library class <a href="https://docs.microsoft.com/previous-versions/ff544508(v=vs.85)">EXT_CLASS</a>, it can be used by the extension library to clean up before it is unloaded.

There may or may not be a debugging session active when this function is called, so you should not assume that the extension can query session information.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/ff544508(v=vs.85)">EXT_CLASS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543981">ExtExtension</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/previsioning-framework/ff550945(v=vs.85)">Initialize</a>
 

 

