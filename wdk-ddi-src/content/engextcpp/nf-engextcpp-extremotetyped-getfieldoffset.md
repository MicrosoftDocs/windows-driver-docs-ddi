---
UID: NF:engextcpp.ExtRemoteTyped.GetFieldOffset
title: ExtRemoteTyped::GetFieldOffset
description: The GetFieldOffset method returns the offset of a member from the base address of an instance of the type that is represented by this object.
old-location: debugger\extremotetyped_getfieldoffset.htm
tech.root: debugger
ms.assetid: d74d5b61-f8e8-4ee0-83d2-cfb003189ef4
ms.date: 05/03/2018
ms.keywords: EngExtCpp_Ref_167b764a-f061-46c2-97ce-71c22ddd9b6f.xml, ExtRemoteTyped interface [Windows Debugging],GetFieldOffset method, ExtRemoteTyped.GetFieldOffset, ExtRemoteTyped::GetFieldOffset, GetFieldOffset, GetFieldOffset method [Windows Debugging], GetFieldOffset method [Windows Debugging],ExtRemoteTyped interface, debugger.extremotetyped_getfieldoffset
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
-	engextcpp.hpp
api_name:
-	ExtRemoteTyped.GetFieldOffset
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExtRemoteTyped::GetFieldOffset


## -description


The <b>GetFieldOffset</b> method returns the offset of a member from the base address of an instance of the type that is represented by this object.


## -parameters




### -param Field [in]

The name of the member whose offset is requested.  Sub-members can be specified using a dot-separated path (for example, <b>mymember.mysubmember</b>).


## -returns



<b>GetFieldOffset</b> returns the offset of the member from the base address of an instance of the type.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544162">ExtRemoteTyped</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546758">GetFieldOffset</a>



<b>IDebugSymbols::GetFieldOffset</b>
 

 

