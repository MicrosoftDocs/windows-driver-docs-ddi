---
UID: NF:engextcpp.ExtRemoteTyped.OutTypeName
title: ExtRemoteTyped::OutTypeName method
author: windows-driver-content
description: The OutTypeName method prints the type name of the typed data represented by this object.
old-location: debugger\extremotetyped_outtypename.htm
old-project: debugger
ms.assetid: fda88a3d-4cdf-4be1-87a7-29e312453686
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ExtRemoteTyped interface [Windows Debugging], OutTypeName method, EngExtCpp_Ref_1dd0e308-16ca-4b91-8ad6-7c2d4c7d8da8.xml, OutTypeName, ExtRemoteTyped, OutTypeName method [Windows Debugging], ExtRemoteTyped::OutTypeName, debugger.extremotetyped_outtypename, OutTypeName method [Windows Debugging], ExtRemoteTyped interface
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
-	ExtRemoteTyped.OutTypeName
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtRemoteTyped::OutTypeName method


## -description


The <b>OutTypeName</b> method prints the type name of the typed data represented by this object.


## -syntax


````
void OutTypeName();
````


## -parameters






## -returns



This method does not return a value.




## -remarks



The type name is sent to the debugger engine's output callbacks.



