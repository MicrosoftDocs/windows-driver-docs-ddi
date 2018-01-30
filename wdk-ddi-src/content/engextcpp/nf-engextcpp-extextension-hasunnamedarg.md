---
UID: NF:engextcpp.ExtExtension.HasUnnamedArg
title: ExtExtension::HasUnnamedArg method
author: windows-driver-content
description: The HasUnnamedArg method indicates whether a specified unnamed argument is present in the command line used to invoke the current extension command.
old-location: debugger\hasunnamedarg.htm
old-project: debugger
ms.assetid: 26917b2b-abbf-4d1b-b086-104390998a35
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: debugger.hasunnamedarg, HasUnnamedArg method [Windows Debugging], HasUnnamedArg, ExtExtension, EngExtCpp_Ref_5d191b46-bac6-415e-8c02-732ce433f950.xml, ExtExtension::HasUnnamedArg, HasUnnamedArg method [Windows Debugging], ExtExtension class, ExtExtension class [Windows Debugging], HasUnnamedArg method
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
-	ExtExtension.HasUnnamedArg
product: Windows
targetos: Windows
req.typenames: DXVA_VideoSample32
---

# ExtExtension::HasUnnamedArg method


## -description


The <b>HasUnnamedArg</b> method indicates whether a specified unnamed argument is present in the command line used to invoke the current extension command.


## -syntax


````
bool HasUnnamedArg(
  [in] ULONG Index
);
````


## -parameters




### -param Index [in]

Specifies the index of the argument.  <i>Index</i> should be between zero and the number of unnamed arguments returned by <a href="..\engextcpp\nf-engextcpp-extextension-getnumunnamedargs.md">GetNumUnnamedArgs</a> minus one (unnamed arguments - 1).


## -returns


<i>HasUnnamedArg</i> returns <code>true</code> if the argument is present; <code>false</code> if it is not present.



## -remarks


This method will work for all types of unnamed arguments. For an overview of argument parsing in the EngExtCpp extensions framework, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff553340">Parsing Extension Arguments</a>.

This method should only be called during the execution of an extension command provided by this class.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543981">ExtExtension</a>

<a href="..\engextcpp\nf-engextcpp-extextension-getnumunnamedargs.md">GetNumUnnamedArgs</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ExtExtension.HasUnnamedArg method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

