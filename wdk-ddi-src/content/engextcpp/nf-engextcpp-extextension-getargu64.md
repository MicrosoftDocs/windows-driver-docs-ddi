---
UID: NF:engextcpp.ExtExtension.GetArgU64
title: ExtExtension::GetArgU64 (engextcpp.h)
description: The GetArgU64 method returns the value of a named expression argument from the command line used to invoke the current extension command.
old-location: debugger\getargu64.htm
tech.root: debugger
ms.date: 05/03/2018
keywords: ["ExtExtension::GetArgU64"]
ms.keywords: EngExtCpp_Ref_02971a20-02b8-4655-a1e5-8f287b4b0182.xml, ExtExtension class [Windows Debugging],GetArgU64 method, ExtExtension.GetArgU64, ExtExtension::GetArgU64, GetArgU64, GetArgU64 method [Windows Debugging], GetArgU64 method [Windows Debugging],ExtExtension class, debugger.getargu64
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
 - ExtExtension::GetArgU64
 - engextcpp/ExtExtension::GetArgU64
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Engextcpp.hpp
api_name:
 - ExtExtension::GetArgU64
---

# ExtExtension::GetArgU64


## -description

The <b>GetArgU64</b> method returns the value of a named expression argument from the command line used to invoke the current extension command.

## -parameters

### -param Name [in]


Specifies the name of the argument.  The command-line description used in <a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-ext_command">EXT_COMMAND</a> must specify that the type of this argument is expression.

### -param Required [in]


Specifies if the argument is required.  If <i>Required</i> is <code>true</code> and the argument was not present on the command line, <b>ExtInvalidArgumentException</b> is called.   You do not need to set this parameter; if it is not set <i>Required</i> defaults to <code>true</code>.

## -returns

<b>GetArgU64</b> returns the value of the named expression argument.

## -remarks

For an overview of argument parsing in the EngExtCpp extensions framework, see <a href="/windows-hardware/drivers/debugger/parsing-extension-arguments">Parsing Extension Arguments</a>.

This method should only be called during the execution of an extension command provided by this class.

## -see-also

<a href="/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-ext_command">EXT_COMMAND</a>



<a href="/previous-versions/ff543981(v=vs.85)">ExtExtension</a>

