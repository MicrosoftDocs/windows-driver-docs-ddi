---
UID: NF:engextcpp.ExtExtension.GetRawArgStr
title: ExtExtension::GetRawArgStr (engextcpp.h)
description: The GetRawArgStr method returns a string that represents the arguments passed to the extension command.
old-location: debugger\getrawargstr.htm
tech.root: debugger
ms.assetid: 677b56ee-3758-4f47-9f8e-fc8878d00136
ms.date: 05/03/2018
keywords: ["ExtExtension::GetRawArgStr"]
ms.keywords: EngExtCpp_Ref_1072b281-ece3-4641-93e8-60866c1e3ef4.xml, ExtExtension class [Windows Debugging],GetRawArgStr method, ExtExtension.GetRawArgStr, ExtExtension::GetRawArgStr, GetRawArgStr, GetRawArgStr method [Windows Debugging], GetRawArgStr method [Windows Debugging],ExtExtension class, debugger.getrawargstr
f1_keywords:
 - "engextcpp/ExtExtension.GetRawArgStr"
 - "ExtExtension.GetRawArgStr"
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
- engextcpp.hpp
api_name:
- ExtExtension.GetRawArgStr
targetos: Windows
req.typenames: 
---

# ExtExtension::GetRawArgStr


## -description


The <b>GetRawArgStr</b> method returns a string that represents the arguments passed to the extension command.


## -returns



<b>GetRawArgStr</b> returns a string that represents the arguments passed to the extension command.  In particular, if the extension command was called from a command line, this string contains the portion of the command line that follows the extension command.  The return value can be <b>NULL</b> or empty.




## -remarks



For an overview of argument parsing in the EngExtCpp extensions framework, see <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/parsing-extension-arguments">Parsing Extension Arguments</a>.

The string returned by this method is only meaningful during the execution of the current extension command.

This method should only be called during the execution of an extension command provided by this class.



