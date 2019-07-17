---
UID: NF:engextcpp.ExtExtension.OnSessionInactive
title: ExtExtension::OnSessionInactive (engextcpp.h)
description: The OnSessionInactive method is called by the engine to inform the EngExtCpp extension library when the debugging session becomes inactive.
old-location: debugger\onsessioninactive.htm
tech.root: debugger
ms.assetid: 6f9b7636-8808-4783-bba7-70b31ae08238
ms.date: 05/03/2018
ms.keywords: EngExtCpp_Ref_2d9d9c48-9c19-4aa7-b0c5-852643eadcee.xml, ExtExtension class [Windows Debugging],OnSessionInactive method, ExtExtension.OnSessionInactive, ExtExtension::OnSessionInactive, OnSessionInactive, OnSessionInactive method [Windows Debugging], OnSessionInactive method [Windows Debugging],ExtExtension class, debugger.onsessioninactive
ms.topic: method
f1_keywords:
 - "engextcpp/ExtExtension.OnSessionInactive"
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
- ExtExtension.OnSessionInactive
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExtExtension::OnSessionInactive


## -description


The <b>OnSessionInactive</b> method is called by the engine to inform the EngExtCpp extension library when the debugging session becomes inactive.


## -parameters




### -param Argument [in]

Set to zero. (Reserved for future use).


## -returns



This method does not return a value.




## -remarks



If this method is defined in the extension library class <a href="https://docs.microsoft.com/previous-versions/ff544508(v=vs.85)">EXT_CLASS</a>, it can be used to allow the extension library to cache information about the session without the need to register event callbacks.

This method is called at the end of a session.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/ff544508(v=vs.85)">EXT_CLASS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543981">ExtExtension</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/previsioning-framework/ff552312(v=vs.85)">OnSessionActive</a>
 

 

