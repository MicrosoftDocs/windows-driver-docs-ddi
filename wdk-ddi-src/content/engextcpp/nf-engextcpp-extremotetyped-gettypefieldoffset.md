---
UID: NF:engextcpp.ExtRemoteTyped.GetTypeFieldOffset
title: ExtRemoteTyped::GetTypeFieldOffset method
author: windows-driver-content
description: The GetTypeFieldOffset static method returns the offset of a member within a structure.
old-location: debugger\extremotetyped_gettypefieldoffset.htm
old-project: debugger
ms.assetid: 5f966bf0-2dc3-4422-bfec-09d1b136f9f0
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: EngExtCpp_Ref_f916dec8-a1be-4180-aa87-33136677949f.xml, ExtRemoteTyped, ExtRemoteTyped interface [Windows Debugging], GetTypeFieldOffset method, ExtRemoteTyped::GetTypeFieldOffset, GetTypeFieldOffset method [Windows Debugging], GetTypeFieldOffset method [Windows Debugging], ExtRemoteTyped interface, GetTypeFieldOffset,ExtRemoteTyped.GetTypeFieldOffset, debugger.extremotetyped_gettypefieldoffset
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
req.lib: engextcpp.hpp
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
-	ExtRemoteTyped.GetTypeFieldOffset
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtRemoteTyped::GetTypeFieldOffset method


## -description


The <b>GetTypeFieldOffset</b> static method returns the offset of a member within a structure.


## -syntax


````
static ULONG GetTypeFieldOffset(
  [in] PCSTR Type,
  [in] PCSTR Field
);
````


## -parameters




### -param Type [in]

The name of the type of the structure. This can be qualified with a module name, for example, <b>mymodule!mystruct</b>.


### -param Field [in]

The name of the member in the structure.  You can specify sub-members  by using a dot operator (.) (for example, <b>mymember.mysubmember</b>).


## -returns



<b>GetTypeFieldOffset</b> returns the number of bytes between the address of an instance of the structure and address of the instance's member.



