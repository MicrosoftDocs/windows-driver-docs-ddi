---
UID: NF:engextcpp.ExtExtension.GetUnnamedArgStr
title: ExtExtension::GetUnnamedArgStr method
author: windows-driver-content
description: The GetUnnamedArgStr method returns an unnamed string argument from the command line used to invoke the current extension command.
old-location: debugger\getunnamedargstr.htm
old-project: debugger
ms.assetid: 2aaaee0d-eabe-4615-b888-8239f2791d80
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: GetUnnamedArgStr, EngExtCpp_Ref_68f021ae-574a-4bc5-bea2-545f59b8ea74.xml, GetUnnamedArgStr method [Windows Debugging], ExtExtension class, debugger.getunnamedargstr, ExtExtension, ExtExtension::GetUnnamedArgStr, ExtExtension class [Windows Debugging], GetUnnamedArgStr method, GetUnnamedArgStr method [Windows Debugging]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Engextcpp.hpp
apiname:
-	ExtExtension.GetUnnamedArgStr
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtExtension::GetUnnamedArgStr method


## -description


The <b>GetUnnamedArgStr</b> method returns an unnamed string argument from the command line used to invoke the current extension command.


## -syntax


````
PCSTR GetUnnamedArgStr(
  [in] ULONG Index
);
````


## -parameters




### -param Index [in]

Specifies the index of the argument.  The command-line description used in <a href="..\engextcpp\nf-engextcpp-ext_command.md">EXT_COMMAND</a> must specify that the type of this argument is string.  The value of <i>Index</i> should be between zero and the number of unnamed arguments returned by <a href="..\engextcpp\nf-engextcpp-extextension-getnumunnamedargs.md">GetNumUnnamedArgs</a> minus one (unnamed arguments - 1).


## -returns


<b>GetUnnamedArgStr</b> returns the unnamed string argument.



## -remarks


For an overview of argument parsing in the EngExtCpp extensions framework, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff553340">Parsing Extension Arguments</a>.

The string returned by <b>GetUnnamedArgStr</b> is only meaningful during the execution of the current extension command.

This method should only be called during the execution of an extension command provided by this class.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543981">ExtExtension</a>

<a href="..\engextcpp\nf-engextcpp-ext_command.md">EXT_COMMAND</a>

<a href="..\engextcpp\nf-engextcpp-extextension-getnumunnamedargs.md">GetNumUnnamedArgs</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ExtExtension.GetUnnamedArgStr method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

