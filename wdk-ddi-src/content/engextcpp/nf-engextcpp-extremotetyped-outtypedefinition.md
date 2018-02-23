---
UID: NF:engextcpp.ExtRemoteTyped.OutTypeDefinition
title: ExtRemoteTyped::OutTypeDefinition method
author: windows-driver-content
description: The OutTypeDefinition method prints the type of the typed data represented by this object.
old-location: debugger\extremotetyped_outtypedefinition.htm
old-project: debugger
ms.assetid: f7d24a3b-b5a8-4924-85d9-8bf7983b95fa
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ExtRemoteTyped, debugger.extremotetyped_outtypedefinition, OutTypeDefinition method [Windows Debugging], EngExtCpp_Ref_1186a4c5-f5d3-4f87-b8d0-b4a10cc2b4e7.xml, OutTypeDefinition method [Windows Debugging], ExtRemoteTyped interface, OutTypeDefinition, ExtRemoteTyped::OutTypeDefinition, ExtRemoteTyped interface [Windows Debugging], OutTypeDefinition method
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
-	ExtRemoteTyped.OutTypeDefinition
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtRemoteTyped::OutTypeDefinition method


## -description


The <b>OutTypeDefinition</b> method prints the type of the typed data represented by this object.


## -syntax


````
void OutTypeDefinition();
````


## -parameters






## -returns



This method does not return a value.




## -remarks



The type is sent to the debugger engine's output callbacks.



