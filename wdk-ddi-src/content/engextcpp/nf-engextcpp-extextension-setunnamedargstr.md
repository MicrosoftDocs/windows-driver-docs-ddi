---
UID: NF:engextcpp.ExtExtension.SetUnnamedArgStr
title: ExtExtension::SetUnnamedArgStr method
author: windows-driver-content
description: The SetUnnamedArgStr method sets an unnamed string argument for the current extension command.
old-location: debugger\setunnamedargstr.htm
old-project: debugger
ms.assetid: 96e309ca-1267-4a5d-97c6-1b15de9190d5
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: EngExtCpp_Ref_0d8a550a-c727-47e5-a5fe-10971e373a9d.xml, ExtExtension, ExtExtension class [Windows Debugging], SetUnnamedArgStr method, ExtExtension::SetUnnamedArgStr, SetUnnamedArgStr method [Windows Debugging], SetUnnamedArgStr method [Windows Debugging], ExtExtension class, SetUnnamedArgStr,ExtExtension.SetUnnamedArgStr, debugger.setunnamedargstr
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
-	ExtExtension.SetUnnamedArgStr
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtExtension::SetUnnamedArgStr method


## -description


The <b>SetUnnamedArgStr</b> method sets an unnamed string argument for the current extension command.


## -syntax


````
bool SetUnnamedArgStr(
  [in] ULONG Index,
  [in] PCSTR Arg,
  [in] bool  OnlyIfUnset
);
````


## -parameters




### -param Index [in]

Specifies the index of the argument.  The command-line description used in <a href="..\engextcpp\nf-engextcpp-ext_command.md">EXT_COMMAND</a> must specify that the type of this argument is string.  <i>Index</i> should be between zero and the number of unnamed arguments - as specified in the command-line description used in EXT_COMMAND - minus one.


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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543981">ExtExtension</a>



<a href="..\engextcpp\nf-engextcpp-ext_command.md">EXT_COMMAND</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ExtExtension.SetUnnamedArgStr method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

