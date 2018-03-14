---
UID: NF:engextcpp.ExtExtension.HasUnnamedArg
title: ExtExtension::HasUnnamedArg method
author: windows-driver-content
description: The HasUnnamedArg method indicates whether a specified unnamed argument is present in the command line used to invoke the current extension command.
old-location: debugger\hasunnamedarg.htm
old-project: debugger
ms.assetid: 26917b2b-abbf-4d1b-b086-104390998a35
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: EngExtCpp_Ref_5d191b46-bac6-415e-8c02-732ce433f950.xml, ExtExtension, ExtExtension class [Windows Debugging], HasUnnamedArg method, ExtExtension::HasUnnamedArg, HasUnnamedArg method [Windows Debugging], HasUnnamedArg method [Windows Debugging], ExtExtension class, HasUnnamedArg,ExtExtension.HasUnnamedArg, debugger.hasunnamedarg
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
-	ExtExtension.HasUnnamedArg
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
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

<a href="..\engextcpp\nf-engextcpp-extextension-getnumunnamedargs.md">GetNumUnnamedArgs</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543981">ExtExtension</a>



 

 


