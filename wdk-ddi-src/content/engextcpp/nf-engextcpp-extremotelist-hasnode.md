---
UID: NF:engextcpp.ExtRemoteList.HasNode
title: ExtRemoteList::HasNode method
author: windows-driver-content
description: The HasNode method determines if there is a current item in the list iteration.
old-location: debugger\extremotelist_hasnode.htm
old-project: debugger
ms.assetid: 412a77c8-eb10-43c5-bc45-2c61858463a7
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: EngExtCpp_Ref_c97c7662-0bbc-4458-9b69-34805fe8c451.xml, ExtRemoteList, ExtRemoteList class [Windows Debugging], HasNode method, ExtRemoteList::HasNode, HasNode method [Windows Debugging], HasNode method [Windows Debugging], ExtRemoteList class, HasNode,ExtRemoteList.HasNode, debugger.extremotelist_hasnode
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
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtRemoteList::HasNode method


## -description


The <b>HasNode</b> method determines if there is a current item in the list iteration.


## -syntax


````
bool HasNode();
````


## -parameters






## -returns



<b>HasNode</b> returns <code>true</code> if there is a current item in the list iteration, and <code>false</code> otherwise.




## -remarks



Before you call <b>HasNode</b>, you must initialize the list for iteration by calling <a href="https://msdn.microsoft.com/d7d9163b-54bb-4753-96a3-f92eddbe25f5">StartHead</a> or <a href="https://msdn.microsoft.com/fe9aec87-a464-4ea9-b9ca-3dbb91bb4e3e">StartTail</a>.

If this method returns <code>true</code>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff544129">ExtRemoteList::GetNodeOffset</a> can be used to return the current item in the list.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544129">ExtRemoteList::GetNodeOffset</a>



<a href="..\engextcpp\nl-engextcpp-extremotelist.md">ExtRemoteList</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ExtRemoteList.HasNode method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

