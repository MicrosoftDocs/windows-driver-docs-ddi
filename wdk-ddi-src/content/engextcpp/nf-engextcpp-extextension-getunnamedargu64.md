---
UID: NF:engextcpp.ExtExtension.GetUnnamedArgU64
title: ExtExtension::GetUnnamedArgU64 method
author: windows-driver-content
description: The GetUnnamedArgU64 method returns the value of an unnamed expression argument from the command line used to invoke the current extension command.
old-location: debugger\getunnamedargu64.htm
old-project: debugger
ms.assetid: 43cda226-1c55-4b55-a9c9-819fb1ea9265
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: EngExtCpp_Ref_94c8c0d8-bc72-4357-bcba-f2e8598aabff.xml, ExtExtension, ExtExtension::GetUnnamedArgU64, GetUnnamedArgU64 method [Windows Debugging], ExtExtension class [Windows Debugging], GetUnnamedArgU64 method, GetUnnamedArgU64 method [Windows Debugging], ExtExtension class, debugger.getunnamedargu64, GetUnnamedArgU64
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
-	ExtExtension.GetUnnamedArgU64
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtExtension::GetUnnamedArgU64 method


## -description


The <b>GetUnnamedArgU64</b> method returns the value of an unnamed expression argument from the command line used to invoke the current extension command.


## -syntax


````
ULONG64 GetUnnamedArgU64(
  [in] ULONG Index
);
````


## -parameters




#### - Index [in]

Specifies the index of the argument.  The command-line description used in <a href="..\engextcpp\nf-engextcpp-ext_command.md">EXT_COMMAND</a> must specify that the type of this argument is string.  <i>Index</i> should be between zero and the number of unnamed arguments returned by <a href="..\engextcpp\nf-engextcpp-extextension-getnumunnamedargs.md">GetNumUnnamedArgs</a> minus one (unnamed arguments - 1).


## -returns


<b>GetUnnamedArgU64</b> returns the value of the unnamed expression argument.



## -remarks


For an overview of argument parsing in the EngExtCpp extensions framework, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff553340">Parsing Extension Arguments</a>.

This method should only be called during the execution of an extension command provided by this class.



## -see-also

<a href="..\engextcpp\nf-engextcpp-extextension-getnumunnamedargs.md">GetNumUnnamedArgs</a>

<a href="..\engextcpp\nf-engextcpp-ext_command.md">EXT_COMMAND</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543981">ExtExtension</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ExtExtension.GetUnnamedArgU64 method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

