---
UID: NF:engextcpp.ExtExtension.HasArg
title: ExtExtension::HasArg (engextcpp.h)
description: The HasArg method indicates whether a specified named argument is present in the command line used to invoke the current extension command.
old-location: debugger\hasarg.htm
tech.root: debugger
ms.assetid: c71aa196-a25a-4d5c-a464-426d14a6aa72
ms.date: 05/03/2018
ms.keywords: EngExtCpp_Ref_a4d457bf-6e64-46d7-892a-5ddda81c7f9d.xml, ExtExtension class [Windows Debugging],HasArg method, ExtExtension.HasArg, ExtExtension::HasArg, HasArg, HasArg method [Windows Debugging], HasArg method [Windows Debugging],ExtExtension class, debugger.hasarg
ms.topic: method
f1_keywords:
 - "engextcpp/ExtExtension.HasArg"
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
- ExtExtension.HasArg
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExtExtension::HasArg


## -description


The <b>HasArg</b> method indicates whether a specified named argument is present in the command line used to invoke the current extension command.


## -parameters




### -param Name [in]

Specifies the name of the argument.


## -returns



<b>HasArg</b> returns <code>true</code> if the argument is present; <code>false</code> if it is not present.




## -remarks



This method will work for all types of named arguments.  In particular, it can be used to detect the presence of a named argument of Boolean type.

If the name of the argument is a single character, the convenience method <a href="https://docs.microsoft.com/previous-versions/windows/hardware/previsioning-framework/ff549727(v=vs.85)">HasCharArg</a> can be used instead.

For an overview of argument parsing in the EngExtCpp extensions framework, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/parsing-extension-arguments">Parsing Extension Arguments</a>.

This method should only be called during the execution of an extension command provided by this class.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543981">ExtExtension</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/previsioning-framework/ff549727(v=vs.85)">HasCharArg</a>
 

 

