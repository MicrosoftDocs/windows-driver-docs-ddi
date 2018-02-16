---
UID: NF:engextcpp.EXT_COMMAND_METHOD
title: EXT_COMMAND_METHOD macro
author: windows-driver-content
description: The EXT_COMMAND_METHOD macro declares an extension command from inside the definition of the EXT_CLASS class.
old-location: debugger\ext_command_method.htm
old-project: debugger
ms.assetid: 30962127-a46f-43f5-a58e-891c5b8a867d
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: EXT_COMMAND_METHOD function [Windows Debugging], engextcpp/EXT_COMMAND_METHOD, EXT_COMMAND_METHOD, debugger.ext_command_method, EngExtCpp_Ref_a4a0b264-50e1-457b-a962-ca691509ea36.xml
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
req.lib: engextcpp.hpp
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	engextcpp.hpp
apiname:
-	EXT_COMMAND_METHOD
product: Windows
targetos: Windows
req.typenames: "*PSILO_DRIVER_CAPABILITIES, SILO_DRIVER_CAPABILITIES"
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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544508">EXT_CLASS</a>



<a href="..\engextcpp\nf-engextcpp-ext_command.md">EXT_COMMAND</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20EXT_COMMAND_METHOD function%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

