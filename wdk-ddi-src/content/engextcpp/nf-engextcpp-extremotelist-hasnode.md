---
UID: NF:engextcpp.ExtRemoteList.HasNode
title: ExtRemoteList::HasNode
author: windows-driver-content
description: The HasNode method determines if there is a current item in the list iteration.
old-location: debugger\extremotelist_hasnode.htm
tech.root: debugger
ms.assetid: 412a77c8-eb10-43c5-bc45-2c61858463a7
ms.author: windowsdriverdev
ms.date: 5/3/2018
ms.keywords: EngExtCpp_Ref_c97c7662-0bbc-4458-9b69-34805fe8c451.xml, ExtRemoteList class [Windows Debugging],HasNode method, ExtRemoteList.HasNode, ExtRemoteList::HasNode, HasNode, HasNode method [Windows Debugging], HasNode method [Windows Debugging],ExtRemoteList class, debugger.extremotelist_hasnode
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
-	ExtRemoteList.HasNode
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExtRemoteList::HasNode


## -description


The <b>HasNode</b> method determines if there is a current item in the list iteration.


## -parameters






## -returns



<b>HasNode</b> returns <code>true</code> if there is a current item in the list iteration, and <code>false</code> otherwise.




## -remarks



Before you call <b>HasNode</b>, you must initialize the list for iteration by calling <a href="https://msdn.microsoft.com/d7d9163b-54bb-4753-96a3-f92eddbe25f5">StartHead</a> or <a href="https://msdn.microsoft.com/fe9aec87-a464-4ea9-b9ca-3dbb91bb4e3e">StartTail</a>.

If this method returns <code>true</code>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff544129">ExtRemoteList::GetNodeOffset</a> can be used to return the current item in the list.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544114">ExtRemoteList</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544129">ExtRemoteList::GetNodeOffset</a>
 

 

