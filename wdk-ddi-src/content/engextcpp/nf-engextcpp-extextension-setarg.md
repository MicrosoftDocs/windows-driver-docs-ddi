---
UID: NF:engextcpp.ExtExtension.SetArg
title: ExtExtension::SetArg method
author: windows-driver-content
description: The SetArg method sets a named argument for the current extension command.
old-location: debugger\setarg.htm
old-project: debugger
ms.assetid: 02d43054-27e9-4f2f-8d0a-506cf052f24f
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: EngExtCpp_Ref_20376f38-03cf-4e1c-a4af-6b318a425ebc.xml, ExtExtension, ExtExtension class [Windows Debugging], SetArg method, ExtExtension::SetArg, SetArg method [Windows Debugging], SetArg method [Windows Debugging], ExtExtension class, SetArg,ExtExtension.SetArg, debugger.setarg
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
-	ExtExtension.SetArg
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtExtension::SetArg method


## -description


The <b>SetArg</b> method sets a named argument for the current extension command.


## -parameters




### -param Name [in]

Specifies the name of the argument.


### -param StrArg [in, optional]

A string that specifies the value of the named argument.

If the argument is of type <b>string</b>, a pointer to the first non-space character is saved as the argument.  In this case, <i>StrArg</i> must not be <b>NULL</b>.

If the argument is of type <b>expression</b>, <i>StrArg</i> is evaluated using the default expression evaluator and the value becomes the value of the argument.  In this case, <i>StrArg</i> can be <b>NULL</b> and <i>NumArg</i> is used instead.

If the argument is of type <b>Boolean</b>, <i>StrArg</i> is ignored and can be <b>NULL</b>.


### -param NumArg [in]

Specifies the value of a named expression argument.  <i>NumArg</i> is only used if the type of the argument is an expression and <i>StrArg</i> is <b>NULL</b>.


### -param OnlyIfUnset [in]

Specifies what happens if the argument is already set.  If <i>OnlyIfUnset</i> is <code>true</code> and the argument has already been set, the argument will not be changed.  If <i>OnlyIfUnset</i> is <code>false</code> and the argument has already been set, the argument will be changed.


## -returns



<b>SetArg</b> returns <code>true</code> if the argument was changed; <code>false</code> otherwise.




## -remarks



For an overview of argument parsing in the EngExtCpp extensions framework, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff553340">Parsing Extension Arguments</a>.

This method should only be called during the execution of an extension command provided by this class.



