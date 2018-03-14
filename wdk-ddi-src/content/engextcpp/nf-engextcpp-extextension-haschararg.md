---
UID: NF:engextcpp.ExtExtension.HasCharArg
title: ExtExtension::HasCharArg method
author: windows-driver-content
description: The HasCharArg method indicates whether a specified single-character named argument is present in the command line used to invoke the current extension command.
old-location: debugger\haschararg.htm
old-project: debugger
ms.assetid: 24d9a231-2c04-43da-aa20-9e10f7633532
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: EngExtCpp_Ref_1ef6d849-e279-4705-b0fe-8147fbd7daf8.xml, ExtExtension, ExtExtension class [Windows Debugging], HasCharArg method, ExtExtension::HasCharArg, HasCharArg method [Windows Debugging], HasCharArg method [Windows Debugging], ExtExtension class, HasCharArg,ExtExtension.HasCharArg, debugger.haschararg
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
-	ExtExtension.HasCharArg
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtExtension::HasCharArg method


## -description


The <b>HasCharArg</b> method indicates whether a specified single-character named argument is present in the command line used to invoke the current extension command.


## -syntax


````
bool HasCharArg(
  [in] CHAR Name
);
````


## -parameters




### -param Name [in]

Specifies the name of the argument.


## -returns



<b>HasCharArg</b> returns <code>true</code> if the argument is present; <code>false</code> if it is not present.




## -remarks



This method will work for all types of named arguments.  In particular, it can be used to detect the presence of a named argument of Boolean type.

This is a convenience method and is restricted to arguments whose name is a single character.  For arguments whose names are longer than a single character, use <a href="..\engextcpp\nf-engextcpp-extextension-hasarg.md">HasArg</a>.

For an overview of argument parsing in the EngExtCpp extensions framework, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff553340">Parsing Extension Arguments</a>.

This method should only be called during the execution of an extension command provided by this class.




## -see-also

<a href="..\engextcpp\nf-engextcpp-extextension-hasarg.md">HasArg</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543981">ExtExtension</a>



 

 


