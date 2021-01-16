---
UID: NF:engextcpp.ExtExtension.HasArg
title: ExtExtension::HasArg (engextcpp.h)
description: The HasArg method indicates whether a specified named argument is present in the command line used to invoke the current extension command.
old-location: debugger\hasarg.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["ExtExtension::HasArg"]
ms.keywords: EngExtCpp_Ref_a4d457bf-6e64-46d7-892a-5ddda81c7f9d.xml, ExtExtension class [Windows Debugging],HasArg method, ExtExtension.HasArg, ExtExtension::HasArg, HasArg, HasArg method [Windows Debugging], HasArg method [Windows Debugging],ExtExtension class, debugger.hasarg
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
targetos: Windows
req.typenames: 
f1_keywords:
 - ExtExtension::HasArg
 - engextcpp/ExtExtension::HasArg
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Engextcpp.hpp
api_name:
 - ExtExtension::HasArg
---

# ExtExtension::HasArg


## -description

The <b>HasArg</b> method indicates whether a specified named argument is present in the command line used to invoke the current extension command.

## -parameters

### -param Name 

[in]
Specifies the name of the argument.

## -returns

<b>HasArg</b> returns <code>true</code> if the argument is present; <code>false</code> if it is not present.

## -remarks

This method will work for all types of named arguments.  In particular, it can be used to detect the presence of a named argument of Boolean type.

If the name of the argument is a single character, the convenience method <a href="/previous-versions/windows/hardware/previsioning-framework/ff549727(v=vs.85)">HasCharArg</a> can be used instead.

For an overview of argument parsing in the EngExtCpp extensions framework, see <a href="/windows-hardware/drivers/debugger/parsing-extension-arguments">Parsing Extension Arguments</a>.

This method should only be called during the execution of an extension command provided by this class.

## -see-also

<a href="/previous-versions/ff543981(v=vs.85)">ExtExtension</a>



<a href="/previous-versions/windows/hardware/previsioning-framework/ff549727(v=vs.85)">HasCharArg</a>

