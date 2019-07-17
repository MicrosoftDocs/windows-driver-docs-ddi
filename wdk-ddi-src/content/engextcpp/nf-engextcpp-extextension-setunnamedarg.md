---
UID: NF:engextcpp.ExtExtension.SetUnnamedArg
title: ExtExtension::SetUnnamedArg (engextcpp.h)
description: The SetUnnamedArg method sets an unnamed argument for the current extension command.
old-location: debugger\setunnamedarg.htm
tech.root: debugger
ms.assetid: cf518a6b-275f-4f9c-9aa8-e2e96c468ff9
ms.date: 05/03/2018
ms.keywords: EngExtCpp_Ref_662530e0-caca-43f0-8b46-b21c8a1f00da.xml, ExtExtension class [Windows Debugging],SetUnnamedArg method, ExtExtension.SetUnnamedArg, ExtExtension::SetUnnamedArg, SetUnnamedArg, SetUnnamedArg method [Windows Debugging], SetUnnamedArg method [Windows Debugging],ExtExtension class, debugger.setunnamedarg
ms.topic: method
f1_keywords:
 - "engextcpp/ExtExtension.SetUnnamedArg"
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
- ExtExtension.SetUnnamedArg
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExtExtension::SetUnnamedArg


## -description


The <b>SetUnnamedArg</b> method sets an unnamed argument for the current extension command.


## -parameters




### -param Index [in]

Specifies the index of the argument.  <i>Index</i> should be between zero and the number of unnamed arguments, as specified in the command-line description used in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-ext_command">EXT_COMMAND</a>, minus one (unnamed arguments - 1).


### -param StrArg [in, optional]

A string that specifies the value of the unnamed argument.

If the argument is of type <b>string</b>, a pointer to the first non-space character is saved as the argument.  In this case, <i>StrArg</i> must not be <b>NULL</b>.

If the argument is of type <b>expression</b>, <i>StrArg</i> is evaluated using the default expression evaluator and the value returned by the default expression evaluator becomes the value of the argument.  In this case, <i>StrArg</i> can be <b>NULL</b> and <i>NumArg</i> should be used instead.

If the argument is of type <b>Boolean</b>, <i>StrArg</i> is ignored and can be <b>NULL</b>.


### -param NumArg [in]

Specifies the value of an unnamed expression argument.  <i>NumArg</i> is only used if the argument is of type <b>expression</b> and <i>StrArg</i> is <b>NULL</b>.


### -param OnlyIfUnset [in]

Specifies what happens if the argument is already set.  If <i>OnlyIfUnset</i> is <code>true</code> and the argument has already been set, the argument will not be changed.  If <i>OnlyIfUnset</i> is <code>false</code> and the argument has already been set, the argument will be changed.


## -returns



<b>SetUnnamedArg</b> returns <code>true</code> if the argument was changed; <code>false</code> otherwise.




## -remarks



For an overview of argument parsing in the EngExtCpp extensions framework, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/parsing-extension-arguments">Parsing Extension Arguments</a>.

This method should only be called during the execution of an extension command provided by this class.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-ext_command">EXT_COMMAND</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543981">ExtExtension</a>
 

 

