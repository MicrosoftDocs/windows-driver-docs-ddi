---
UID: NF:engextcpp.ExtExtension.HasCharArg
title: ExtExtension::HasCharArg (engextcpp.h)
description: The HasCharArg method indicates whether a specified single-character named argument is present in the command line used to invoke the current extension command.
old-location: debugger\haschararg.htm
tech.root: debugger
ms.assetid: 24d9a231-2c04-43da-aa20-9e10f7633532
ms.date: 05/03/2018
ms.keywords: EngExtCpp_Ref_1ef6d849-e279-4705-b0fe-8147fbd7daf8.xml, ExtExtension class [Windows Debugging],HasCharArg method, ExtExtension.HasCharArg, ExtExtension::HasCharArg, HasCharArg, HasCharArg method [Windows Debugging], HasCharArg method [Windows Debugging],ExtExtension class, debugger.haschararg
f1_keywords:
 - "engextcpp/ExtExtension.HasCharArg"
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
- ExtExtension.HasCharArg
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExtExtension::HasCharArg


## -description


The <b>HasCharArg</b> method indicates whether a specified single-character named argument is present in the command line used to invoke the current extension command.


## -parameters




### -param Name [in]

Specifies the name of the argument.


## -returns



<b>HasCharArg</b> returns <code>true</code> if the argument is present; <code>false</code> if it is not present.




## -remarks



This method will work for all types of named arguments.  In particular, it can be used to detect the presence of a named argument of Boolean type.

This is a convenience method and is restricted to arguments whose name is a single character.  For arguments whose names are longer than a single character, use <a href="https://docs.microsoft.com/previous-versions/windows/hardware/previsioning-framework/ff549721(v=vs.85)">HasArg</a>.

For an overview of argument parsing in the EngExtCpp extensions framework, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/parsing-extension-arguments">Parsing Extension Arguments</a>.

This method should only be called during the execution of an extension command provided by this class.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543981">ExtExtension</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/previsioning-framework/ff549721(v=vs.85)">HasArg</a>
 

 

