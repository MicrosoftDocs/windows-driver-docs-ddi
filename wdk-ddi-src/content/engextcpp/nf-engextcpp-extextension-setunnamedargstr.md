---
UID: NF:engextcpp.ExtExtension.SetUnnamedArgStr
title: ExtExtension::SetUnnamedArgStr
description: The SetUnnamedArgStr method sets an unnamed string argument for the current extension command.
old-location: debugger\setunnamedargstr.htm
tech.root: debugger
ms.assetid: 96e309ca-1267-4a5d-97c6-1b15de9190d5
ms.date: 05/03/2018
ms.keywords: EngExtCpp_Ref_0d8a550a-c727-47e5-a5fe-10971e373a9d.xml, ExtExtension class [Windows Debugging],SetUnnamedArgStr method, ExtExtension.SetUnnamedArgStr, ExtExtension::SetUnnamedArgStr, SetUnnamedArgStr, SetUnnamedArgStr method [Windows Debugging], SetUnnamedArgStr method [Windows Debugging],ExtExtension class, debugger.setunnamedargstr
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
req.lib: 
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
-	ExtExtension.SetUnnamedArgStr
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExtExtension::SetUnnamedArgStr


## -description


The <b>SetUnnamedArgStr</b> method sets an unnamed string argument for the current extension command.


## -parameters




### -param Index [in]

Specifies the index of the argument.  The command-line description used in <a href="https://msdn.microsoft.com/library/windows/hardware/ff544514">EXT_COMMAND</a> must specify that the type of this argument is string.  <i>Index</i> should be between zero and the number of unnamed arguments - as specified in the command-line description used in EXT_COMMAND - minus one.


### -param Arg [in]

A string that specifies the value of the unnamed argument.  A pointer to the first non-space character is saved as the argument.


### -param OnlyIfUnset [in]

Specifies what happens if the argument is already set.  If <i>OnlyIfUnset</i> is <code>true</code> and the argument has already been set, the argument will not be changed.  If <i>OnlyIfUnset</i> is <code>false</code> and the argument has already been set, the argument will be changed.


## -returns



<b>SetUnnamedArgStr</b> returns <code>true</code> if the argument was changed; <code>false</code> otherwise.




## -remarks



For an overview of argument parsing in the EngExtCpp extensions framework, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff553340">Parsing Extension Arguments</a>.

This method should only be called during the execution of an extension command provided by this class.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544514">EXT_COMMAND</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543981">ExtExtension</a>
 

 

