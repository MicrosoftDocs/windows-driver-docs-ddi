---
UID: NF:engextcpp.ExtExtension.GetUnnamedArgU64
title: ExtExtension::GetUnnamedArgU64 (engextcpp.h)
description: The GetUnnamedArgU64 method returns the value of an unnamed expression argument from the command line used to invoke the current extension command.
old-location: debugger\getunnamedargu64.htm
tech.root: debugger
ms.assetid: 43cda226-1c55-4b55-a9c9-819fb1ea9265
ms.date: 05/03/2018
ms.keywords: EngExtCpp_Ref_94c8c0d8-bc72-4357-bcba-f2e8598aabff.xml, ExtExtension class [Windows Debugging],GetUnnamedArgU64 method, ExtExtension.GetUnnamedArgU64, ExtExtension::GetUnnamedArgU64, GetUnnamedArgU64, GetUnnamedArgU64 method [Windows Debugging], GetUnnamedArgU64 method [Windows Debugging],ExtExtension class, debugger.getunnamedargu64
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Engextcpp.hpp
api_name:
- ExtExtension.GetUnnamedArgU64
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExtExtension::GetUnnamedArgU64


## -description


The <b>GetUnnamedArgU64</b> method returns the value of an unnamed expression argument from the command line used to invoke the current extension command.


## -parameters




### -param Index [in]

Specifies the index of the argument.  The command-line description used in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-ext_command">EXT_COMMAND</a> must specify that the type of this argument is string.  <i>Index</i> should be between zero and the number of unnamed arguments returned by <a href="https://docs.microsoft.com/previous-versions/windows/hardware/previsioning-framework/ff548001(v=vs.85)">GetNumUnnamedArgs</a> minus one (unnamed arguments - 1).


## -returns



<b>GetUnnamedArgU64</b> returns the value of the unnamed expression argument.




## -remarks



For an overview of argument parsing in the EngExtCpp extensions framework, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/parsing-extension-arguments">Parsing Extension Arguments</a>.

This method should only be called during the execution of an extension command provided by this class.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-ext_command">EXT_COMMAND</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543981">ExtExtension</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/previsioning-framework/ff548001(v=vs.85)">GetNumUnnamedArgs</a>
 

 

