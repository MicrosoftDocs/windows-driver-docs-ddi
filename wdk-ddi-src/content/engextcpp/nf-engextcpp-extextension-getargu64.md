---
UID: NF:engextcpp.ExtExtension.GetArgU64
title: ExtExtension::GetArgU64 method
author: windows-driver-content
description: The GetArgU64 method returns the value of a named expression argument from the command line used to invoke the current extension command.
old-location: debugger\getargu64.htm
old-project: debugger
ms.assetid: 44a02c77-f4a2-499f-9555-99ce6f49fac8
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: EngExtCpp_Ref_02971a20-02b8-4655-a1e5-8f287b4b0182.xml, ExtExtension, ExtExtension class [Windows Debugging], GetArgU64 method, ExtExtension::GetArgU64, GetArgU64 method [Windows Debugging], GetArgU64 method [Windows Debugging], ExtExtension class, GetArgU64,ExtExtension.GetArgU64, debugger.getargu64
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
-	ExtExtension.GetArgU64
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtExtension::GetArgU64 method


## -description


The <b>GetArgU64</b> method returns the value of a named expression argument from the command line used to invoke the current extension command.


## -syntax


````
ULONG64 GetArgU64(
  [in] PCSTR Name,
  [in] bool  Required
);
````


## -parameters




### -param Name [in]

Specifies the name of the argument.  The command-line description used in <a href="..\engextcpp\nf-engextcpp-ext_command.md">EXT_COMMAND</a> must specify that the type of this argument is expression.


### -param Required [in]

Specifies if the argument is required.  If <i>Required</i> is <code>true</code> and the argument was not present on the command line, <b>ExtInvalidArgumentException</b> is called.   You do not need to set this parameter; if it is not set <i>Required</i> defaults to <code>true</code>. 


## -returns



<b>GetArgU64</b> returns the value of the named expression argument.




## -remarks



For an overview of argument parsing in the EngExtCpp extensions framework, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff553340">Parsing Extension Arguments</a>.

This method should only be called during the execution of an extension command provided by this class.




## -see-also

<a href="..\engextcpp\nf-engextcpp-ext_command.md">EXT_COMMAND</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543981">ExtExtension</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ExtExtension.GetArgU64 method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

