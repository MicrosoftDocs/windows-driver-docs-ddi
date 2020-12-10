---
UID: NF:engextcpp.ExtExtension.GetArgStr
title: ExtExtension::GetArgStr (engextcpp.h)
description: The GetArgStr method returns a named string argument from the command line used to invoke the current extension command.
old-location: debugger\getargstr.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["ExtExtension::GetArgStr"]
ms.keywords: EngExtCpp_Ref_0a1f3246-41a5-4a2f-8656-45f8c17b6418.xml, ExtExtension class [Windows Debugging],GetArgStr method, ExtExtension.GetArgStr, ExtExtension::GetArgStr, GetArgStr, GetArgStr method [Windows Debugging], GetArgStr method [Windows Debugging],ExtExtension class, debugger.getargstr
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
 - ExtExtension::GetArgStr
 - engextcpp/ExtExtension::GetArgStr
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Engextcpp.hpp
api_name:
 - ExtExtension.GetArgStr
---

# ExtExtension::GetArgStr


## -description

The <b>GetArgStr</b> method returns a named string argument from the command line used to invoke the current extension command.

## -parameters

### -param Name 

[in]
Specifies the name of the argument.  The command-line description used in <a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-ext_command">EXT_COMMAND</a> must specify that the type of this argument is string.

### -param Required 

[in]
Specifies if the argument is required.  If <i>Required</i> is <code>true</code> and the argument was not present on the command line, <b>ExtInvalidArgumentException</b> is thrown.  You do not need to set this parameter; if it is not set <i>Required</i> defaults to <code>true</code>.

## -returns

<b>GetArgStr</b> returns the named string argument.

## -remarks

For an overview of argument parsing in the EngExtCpp extensions framework, see <a href="/windows-hardware/drivers/debugger/parsing-extension-arguments">Parsing Extension Arguments</a>.

The string returned by <b>GetArgStr</b> is only meaningful during the execution of the current extension command.

This method should only be called during the execution of an extension command provided by this class.

## -see-also

<a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-ext_command">EXT_COMMAND</a>



<a href="/previous-versions/ff543981(v=vs.85)">ExtExtension</a>
