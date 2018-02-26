---
UID: NF:engextcpp.ExtRemoteList.GetNodeOffset
title: ExtRemoteList::GetNodeOffset method
author: windows-driver-content
description: The GetNodeOffset method returns the address of the current list item.
old-location: debugger\extremotelist_getnodeoffset.htm
old-project: debugger
ms.assetid: 20c4ec7e-6dc1-4a4f-99d1-bb53213771a5
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , ,, ., :, E, EngExtCpp_Ref_efff4521-d480-48a4-8466-f7db3c052aa1.xml, ExtRemoteList, ExtRemoteList class [Windows Debugging], GetNodeOffset method, ExtRemoteList::GetNodeOffset, G, GetNodeOffset method [Windows Debugging], GetNodeOffset method [Windows Debugging], ExtRemoteList class, GetNodeOffset,ExtRemoteList.GetNodeOffset, L, N, O, R, d, debugger.extremotelist_getnodeoffset, e, f, i, m, o, s, t, x"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	engextcpp.hpp
apiname:
-	ExtRemoteList.GetNodeOffset
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtRemoteList::GetNodeOffset method


## -description


The <b>GetNodeOffset</b> method returns the address of the current list item.


## -syntax


````
ULONG64 GetNodeOffset();
````


## -parameters






## -returns



<b>GetNodeOffset</b> returns the location, in the target's memory, of the current item for the current list iteration.



