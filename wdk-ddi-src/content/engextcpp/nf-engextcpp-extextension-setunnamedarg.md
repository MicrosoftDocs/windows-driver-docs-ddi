---
UID: NF:engextcpp.ExtExtension.SetUnnamedArg
title: ExtExtension::SetUnnamedArg method
author: windows-driver-content
description: The SetUnnamedArg method sets an unnamed argument for the current extension command.
old-location: debugger\setunnamedarg.htm
old-project: debugger
ms.assetid: cf518a6b-275f-4f9c-9aa8-e2e96c468ff9
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: EngExtCpp_Ref_662530e0-caca-43f0-8b46-b21c8a1f00da.xml, ExtExtension, ExtExtension class [Windows Debugging], SetUnnamedArg method, ExtExtension::SetUnnamedArg, SetUnnamedArg method [Windows Debugging], SetUnnamedArg method [Windows Debugging], ExtExtension class, SetUnnamedArg,ExtExtension.SetUnnamedArg, debugger.setunnamedarg
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
-	Engextcpp.hpp
api_name:
-	ExtExtension.SetUnnamedArg
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtExtension::SetUnnamedArg method


## -description


The <b>SetUnnamedArg</b> method sets an unnamed argument for the current extension command.


## -syntax


````
bool SetUnnamedArg(
  [in]           ULONG   Index,
  [in, optional] PCSTR   StrArg,
  [in]           ULONG64 NumArg,
  [in]           bool    OnlyIfUnset
);
````


## -parameters




### -param Index [in]

Specifies the index of the argument.  <i>Index</i> should be between zero and the number of unnamed arguments, as specified in the command-line description used in <a href="..\engextcpp\nf-engextcpp-ext_command.md">EXT_COMMAND</a>, minus one (unnamed arguments - 1).


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



For an overview of argument parsing in the EngExtCpp extensions framework, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff553340">Parsing Extension Arguments</a>.

This method should only be called during the execution of an extension command provided by this class.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543981">ExtExtension</a>



<a href="..\engextcpp\nf-engextcpp-ext_command.md">EXT_COMMAND</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ExtExtension.SetUnnamedArg method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

