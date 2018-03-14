---
UID: NF:engextcpp.ExtExtension.SetArgU64
title: ExtExtension::SetArgU64 method
author: windows-driver-content
description: The SetArgU64 method sets a named expression argument for the current expression command.
old-location: debugger\setargu64.htm
old-project: debugger
ms.assetid: 119e590c-7491-44b3-a315-d3e980f547bb
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: EngExtCpp_Ref_05510fa7-509e-49a2-97a3-7a1c4494350a.xml, ExtExtension, ExtExtension class [Windows Debugging], SetArgU64 method, ExtExtension::SetArgU64, SetArgU64 method [Windows Debugging], SetArgU64 method [Windows Debugging], ExtExtension class, SetArgU64,ExtExtension.SetArgU64, debugger.setargu64
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
-	ExtExtension.SetArgU64
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtExtension::SetArgU64 method


## -description


The <b>SetArgU64</b> method sets a named expression argument for the current expression command.


## -syntax


````
bool SetArgU64(
  [in] PCSTR   Name,
  [in] ULONG64 Arg,
  [in] bool    OnlyIfUnset
);
````


## -parameters




### -param Name [in]

Specifies the name of the argument.  The command-line description used in <a href="..\engextcpp\nf-engextcpp-ext_command.md">EXT_COMMAND</a> must specify that the type of this argument is expression.


### -param Arg [in]

Specifies the value of the named expression argument.


### -param OnlyIfUnset [in]

Specifies what happens if the argument is already set.  If <i>OnlyIfUnset</i> is <code>true</code> and the argument has already been set, the argument will not be changed.  If <i>OnlyIfUnset</i> is <code>false</code> and the argument has already been set, the argument will be changed.


## -returns



<b>SetArgU64</b> returns <code>true</code> if the argument was changed; <code>false</code> otherwise.




## -remarks



For an overview of argument parsing in the EngExtCpp extensions framework, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff553340">Parsing Extension Arguments</a>.

This method should only be called during the execution of an extension command provided by this class.




## -see-also

<a href="..\engextcpp\nf-engextcpp-ext_command.md">EXT_COMMAND</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543981">ExtExtension</a>



 

 


