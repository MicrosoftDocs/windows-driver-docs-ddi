---
UID: NF:engextcpp.EXT_COMMAND_METHOD
title: EXT_COMMAND_METHOD macro (engextcpp.h)
description: The EXT_COMMAND_METHOD macro declares an extension command from inside the definition of the EXT_CLASS class.
old-location: debugger\ext_command_method.htm
tech.root: debugger
ms.assetid: 30962127-a46f-43f5-a58e-891c5b8a867d
ms.date: 05/03/2018
ms.keywords: EXT_COMMAND_METHOD, EXT_COMMAND_METHOD function [Windows Debugging], EngExtCpp_Ref_a4a0b264-50e1-457b-a962-ca691509ea36.xml, debugger.ext_command_method, engextcpp/EXT_COMMAND_METHOD
ms.topic: macro
f1_keywords:
 - "engextcpp/EXT_COMMAND_METHOD"
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
- HeaderDef
api_location:
- engextcpp.hpp
api_name:
- EXT_COMMAND_METHOD
product:
- Windows
targetos: Windows
req.typenames: 
---

# EXT_COMMAND_METHOD macro


## -description


The EXT_COMMAND_METHOD macro declares an extension command from inside the definition of the <a href="https://docs.microsoft.com/previous-versions/ff544508(v=vs.85)">EXT_CLASS</a> class.


## -parameters




### -param _Name

The name of the extension command.  As with all extension commands, the name must consist entirely of lowercase letters.


## -remarks



This macro must be used inside the definition of the <a href="https://docs.microsoft.com/previous-versions/ff544508(v=vs.85)">EXT_CLASS</a> class.

The macro <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-ext_command">EXT_COMMAND</a> should be used to define the extension command.  As with all C++ declarations, the EXT_COMMAND_METHOD declaration should appear in the source files before the EXT_COMMAND definition.




## -see-also




<a href="https://docs.microsoft.com/previous-versions/ff544508(v=vs.85)">EXT_CLASS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-ext_command">EXT_COMMAND</a>
 

 

