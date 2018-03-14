---
UID: NF:engextcpp.ExtExtension.SetArgStr
title: ExtExtension::SetArgStr method
author: windows-driver-content
description: The SetArgStr method sets a named string argument for the current expression command.
old-location: debugger\setargstr.htm
old-project: debugger
ms.assetid: a133cc3d-7d28-436a-b2f7-0f6171ed379f
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: EngExtCpp_Ref_768f449e-fa81-4759-a16d-a8dfe1d3bf61.xml, ExtExtension, ExtExtension class [Windows Debugging], SetArgStr method, ExtExtension::SetArgStr, SetArgStr method [Windows Debugging], SetArgStr method [Windows Debugging], ExtExtension class, SetArgStr,ExtExtension.SetArgStr, debugger.setargstr
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
-	ExtExtension.SetArgStr
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtExtension::SetArgStr method


## -description


The <b>SetArgStr</b> method sets a named string argument for the current expression command.


## -syntax


````
bool SetArgStr(
  [in] PCSTR Name,
  [in] PCSTR Arg,
  [in] bool  OnlyIfUnset
);
````


## -parameters




### -param Name [in]

Specifies the name of the argument.  The command-line description used in <a href="..\engextcpp\nf-engextcpp-ext_command.md">EXT_COMMAND</a> must specify that the type of this argument is string.


### -param Arg [in]

A string that specifies the value of the named argument.  A pointer to the first non-space character is saved as the argument.  In this case, <i>Arg</i> must not be <b>NULL</b>.


### -param OnlyIfUnset [in]

Specifies what happens if the argument is already set.  If <i>OnlyIfUnset</i> is <code>true</code> and the argument has already been set, the argument will not be changed.  If <i>OnlyIfUnset</i> is <code>false</code> and the argument has already been set, the argument will be changed.


## -returns



<b>SetArgStr</b> returns <code>true</code> if the argument was changed; <code>false</code> otherwise.




## -remarks



For an overview of argument parsing in the EngExtCpp extensions framework, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff553340">Parsing Extension Arguments</a>.

This method should only be called during the execution of an extension command provided by this class.




## -see-also

<a href="..\engextcpp\nf-engextcpp-ext_command.md">EXT_COMMAND</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543981">ExtExtension</a>



 

 


