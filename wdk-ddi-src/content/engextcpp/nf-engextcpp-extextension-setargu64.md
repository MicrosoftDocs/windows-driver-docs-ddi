---
UID: NF:engextcpp.ExtExtension.SetArgU64
title: ExtExtension::SetArgU64 (engextcpp.h)
description: The SetArgU64 method sets a named expression argument for the current expression command.
old-location: debugger\setargu64.htm
tech.root: debugger
ms.assetid: 119e590c-7491-44b3-a315-d3e980f547bb
ms.date: 05/03/2018
ms.keywords: EngExtCpp_Ref_05510fa7-509e-49a2-97a3-7a1c4494350a.xml, ExtExtension class [Windows Debugging],SetArgU64 method, ExtExtension.SetArgU64, ExtExtension::SetArgU64, SetArgU64, SetArgU64 method [Windows Debugging], SetArgU64 method [Windows Debugging],ExtExtension class, debugger.setargu64
f1_keywords:
 - "engextcpp/ExtExtension.SetArgU64"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Engextcpp.hpp
api_name:
- ExtExtension.SetArgU64
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExtExtension::SetArgU64


## -description


The <b>SetArgU64</b> method sets a named expression argument for the current expression command.


## -parameters




### -param Name [in]

Specifies the name of the argument.  The command-line description used in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-ext_command">EXT_COMMAND</a> must specify that the type of this argument is expression.


### -param Arg [in]

Specifies the value of the named expression argument.


### -param OnlyIfUnset [in]

Specifies what happens if the argument is already set.  If <i>OnlyIfUnset</i> is <code>true</code> and the argument has already been set, the argument will not be changed.  If <i>OnlyIfUnset</i> is <code>false</code> and the argument has already been set, the argument will be changed.


## -returns



<b>SetArgU64</b> returns <code>true</code> if the argument was changed; <code>false</code> otherwise.




## -remarks



For an overview of argument parsing in the EngExtCpp extensions framework, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/parsing-extension-arguments">Parsing Extension Arguments</a>.

This method should only be called during the execution of an extension command provided by this class.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/engextcpp/nf-engextcpp-ext_command">EXT_COMMAND</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543981">ExtExtension</a>
 

 

