---
UID: NF:engextcpp.ExtExtension.GetNumUnnamedArgs
title: ExtExtension::GetNumUnnamedArgs method
author: windows-driver-content
description: The GetNumUnnamedArgs method returns the number of unnamed arguments in the command line used to invoke the current extension command.
old-location: debugger\getnumunnamedargs.htm
old-project: debugger
ms.assetid: dc3ea1ba-136b-4257-9aa2-ca9649555869
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: EngExtCpp_Ref_8ca2186f-dcda-422a-948f-ead63f451ff2.xml, ExtExtension, ExtExtension class [Windows Debugging], GetNumUnnamedArgs method, ExtExtension::GetNumUnnamedArgs, GetNumUnnamedArgs method [Windows Debugging], GetNumUnnamedArgs method [Windows Debugging], ExtExtension class, GetNumUnnamedArgs,ExtExtension.GetNumUnnamedArgs, debugger.getnumunnamedargs
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
-	ExtExtension.GetNumUnnamedArgs
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtExtension::GetNumUnnamedArgs method


## -description


The <b>GetNumUnnamedArgs</b> method returns the number of unnamed arguments in the command line used to invoke the current extension command.


## -syntax


````
ULONG GetNumUnnamedArgs();
````


## -parameters






## -returns



<b>GetNumUnnamedArgs</b> returns the number of unnamed arguments.




## -remarks



The indices of the unnamed arguments returned by <b>GetNumUnnamedArgs</b> range from zero to the number of unnamed arguments minus one (unnamed args - 1).

For an overview of argument parsing in the EngExtCpp extensions framework, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff553340">Parsing Extension Arguments</a>.

This method should only be called during the execution of an extension command provided by this class.



