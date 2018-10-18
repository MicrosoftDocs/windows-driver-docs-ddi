---
UID: NC:engextcpp.ExtExtension.ExtKnownStructMethod
title: ExtExtension::* ExtKnownStructMethod
author: windows-driver-content
description: The ExtKnownStructMethod callback method is called by the engine to format an instance of a structure for output on a single line.
old-location: debugger\extknownstructmethod.htm
tech.root: debugger
ms.assetid: 33199207-9bb1-4761-9492-15d6287c90df
ms.date: 5/3/2018
ms.keywords: "* ExtKnownStructMethod, EngExtCpp_Ref_bd64fb5a-ca77-4195-b5ba-6d647c133353.xml, ExtExtension::* ExtKnownStructMethod, ExtKnownStructMethod, ExtKnownStructMethod callback, ExtKnownStructMethod callback function [Windows Debugging], debugger.extknownstructmethod, engextcpp/ExtKnownStructMethod"
ms.topic: callback
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
-	UserDefined
api_location:
-	Engextcpp.hpp
api_name:
-	ExtKnownStructMethod
product:
-	Windows
targetos: Windows
req.typenames: 
---

# ExtExtension::* ExtKnownStructMethod callback function


## -description


The <b>ExtKnownStructMethod</b> callback method is called by the engine to format an instance of a structure for output on a single line.


## -parameters




### -param TypeName [in]

Specifies the name of the type of the structure pointed to by <i>Offset</i>.  This is the same as the <b>TypeName</b> field of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543985">ExtKnownStruct</a> structure used to register this callback method.


### -param Flags [in]

Specifies bit flags that indicate how the output should be formatted.  Currently, this is set to DEBUG_KNOWN_STRUCT_GET_SINGLE_LINE_OUTPUT, which indicates that the output should be formatted for output on a single line.


### -param Offset [in]

Specifies the location in the target's memory of the instance of the structure to be formatted for output.


## -remarks



The debugger engine expects the output to be formatted for printing on a single line, hence it does not expect the formatted structure to have any line breaks.

The formatted output from this method should be placed in the buffer <b>m_AppendBuffer</b> -- a member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff543981">ExtExtension</a>.

Instances of this callback method are registered with the engine by using an instance of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543985">ExtKnownStruct</a> structure that is placed into the array <b>m_KnownStructs</b> (a member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff543981">ExtExtension</a>) by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550945">Initialize</a> method.  The <b>ExtKnownStruct</b> structure also specifies the name of the type of structure this method formats.

When the debugger engine calls a known structure method, it wraps the call in a <b>try / except</b> block.  This protects the engine from some types of bugs in the extension code; but, because the extension calls are executed in the same thread as the engine, they can still cause it to crash.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543981">ExtExtension</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543985">ExtKnownStruct</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550945">Initialize</a>
 

 

