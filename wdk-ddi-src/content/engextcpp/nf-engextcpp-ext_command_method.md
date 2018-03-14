---
UID: NF:engextcpp.EXT_COMMAND_METHOD
title: EXT_COMMAND_METHOD macro
author: windows-driver-content
description: The EXT_COMMAND_METHOD macro declares an extension command from inside the definition of the EXT_CLASS class.
old-location: debugger\ext_command_method.htm
old-project: debugger
ms.assetid: 30962127-a46f-43f5-a58e-891c5b8a867d
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: EXT_COMMAND_METHOD, EXT_COMMAND_METHOD function [Windows Debugging], EngExtCpp_Ref_a4a0b264-50e1-457b-a962-ca691509ea36.xml, debugger.ext_command_method, engextcpp/EXT_COMMAND_METHOD
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
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
-	HeaderDef
api_location:
-	engextcpp.hpp
api_name:
-	EXT_COMMAND_METHOD
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# EXT_COMMAND_METHOD macro


## -description


The EXT_COMMAND_METHOD macro declares an extension command from inside the definition of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544508">EXT_CLASS</a> class.


## -syntax


````
 EXT_COMMAND_METHOD(
    _Name
);
````


## -parameters




### -param _Name

The name of the extension command.  As with all extension commands, the name must consist entirely of lowercase letters.


## -remarks



This macro must be used inside the definition of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544508">EXT_CLASS</a> class.

The macro <a href="..\engextcpp\nf-engextcpp-ext_command.md">EXT_COMMAND</a> should be used to define the extension command.  As with all C++ declarations, the EXT_COMMAND_METHOD declaration should appear in the source files before the EXT_COMMAND definition.




## -see-also

<a href="..\engextcpp\nf-engextcpp-ext_command.md">EXT_COMMAND</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544508">EXT_CLASS</a>



 

 


