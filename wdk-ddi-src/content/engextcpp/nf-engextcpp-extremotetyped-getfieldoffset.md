---
UID: NF:engextcpp.ExtRemoteTyped.GetFieldOffset
title: ExtRemoteTyped::GetFieldOffset method
author: windows-driver-content
description: The GetFieldOffset method returns the offset of a member from the base address of an instance of the type that is represented by this object.
old-location: debugger\extremotetyped_getfieldoffset.htm
old-project: debugger
ms.assetid: d74d5b61-f8e8-4ee0-83d2-cfb003189ef4
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: EngExtCpp_Ref_167b764a-f061-46c2-97ce-71c22ddd9b6f.xml, ExtRemoteTyped, ExtRemoteTyped interface [Windows Debugging], GetFieldOffset method, ExtRemoteTyped::GetFieldOffset, GetFieldOffset method [Windows Debugging], GetFieldOffset method [Windows Debugging], ExtRemoteTyped interface, GetFieldOffset,ExtRemoteTyped.GetFieldOffset, debugger.extremotetyped_getfieldoffset
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
-	engextcpp.hpp
api_name:
-	ExtRemoteTyped.GetFieldOffset
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtRemoteTyped::GetFieldOffset method


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
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ExtRemoteTyped.GetFieldOffset method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

