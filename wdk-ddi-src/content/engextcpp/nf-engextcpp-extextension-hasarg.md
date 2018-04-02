---
UID: NF:engextcpp.ExtExtension.HasArg
title: ExtExtension::HasArg method
author: windows-driver-content
description: The HasArg method indicates whether a specified named argument is present in the command line used to invoke the current extension command.
old-location: debugger\hasarg.htm
old-project: debugger
ms.assetid: c71aa196-a25a-4d5c-a464-426d14a6aa72
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: EngExtCpp_Ref_a4d457bf-6e64-46d7-892a-5ddda81c7f9d.xml, ExtExtension, ExtExtension class [Windows Debugging], HasArg method, ExtExtension::HasArg, HasArg method [Windows Debugging], HasArg method [Windows Debugging], ExtExtension class, HasArg,ExtExtension.HasArg, debugger.hasarg
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
-	ExtExtension.HasArg
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtExtension::HasArg method


## -description


The <b>HasArg</b> method indicates whether a specified named argument is present in the command line used to invoke the current extension command.


## -parameters




### -param Name [in]

Specifies the name of the argument.


## -returns



<b>HasArg</b> returns <code>true</code> if the argument is present; <code>false</code> if it is not present.




## -remarks



This method will work for all types of named arguments.  In particular, it can be used to detect the presence of a named argument of Boolean type.

If the name of the argument is a single character, the convenience method <a href="https://msdn.microsoft.com/library/windows/hardware/ff549727">HasCharArg</a> can be used instead.

For an overview of argument parsing in the EngExtCpp extensions framework, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff553340">Parsing Extension Arguments</a>.

This method should only be called during the execution of an extension command provided by this class.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543981">ExtExtension</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549727">HasCharArg</a>
 

 

