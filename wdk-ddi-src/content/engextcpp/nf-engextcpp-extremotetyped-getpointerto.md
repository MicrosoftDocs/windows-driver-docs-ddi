---
UID: NF:engextcpp.ExtRemoteTyped.GetPointerTo
title: ExtRemoteTyped::GetPointerTo method
author: windows-driver-content
description: The GetPointerTo method returns typed data that is a pointer to the typed data represented by this object.
old-location: debugger\extremotetyped_getpointerto.htm
old-project: debugger
ms.assetid: 1f237e8a-c0d3-4812-a96d-4cdc6f8e31df
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: EngExtCpp_Ref_fe04e8e3-888e-4d96-9a24-4bec51f71f16.xml, ExtRemoteTyped::GetPointerTo, ExtRemoteTyped, GetPointerTo, GetPointerTo method [Windows Debugging], ExtRemoteTyped interface [Windows Debugging], GetPointerTo method, GetPointerTo method [Windows Debugging], ExtRemoteTyped interface, debugger.extremotetyped_getpointerto
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
-	engextcpp.hpp
apiname:
-	ExtRemoteTyped.GetPointerTo
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtRemoteTyped::GetPointerTo method


## -description


The <b>GetPointerTo</b> method returns typed data that is a pointer to the typed data represented by this object.


## -syntax


````
ExtRemoteTyped GetPointerTo();
````


## -parameters






## -returns



<b>GetPointerTo</b> returns a new <b>ExtRemoteData</b> object that represents typed data that is a pointer to the typed data represented by this object.



