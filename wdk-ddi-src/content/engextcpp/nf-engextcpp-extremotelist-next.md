---
UID: NF:engextcpp.ExtRemoteList.Next
title: ExtRemoteList::Next method
author: windows-driver-content
description: The Next method changes the current item to the next item in the list.
old-location: debugger\extremotelist_next.htm
old-project: debugger
ms.assetid: a1bf6f5b-c23d-40ed-b6e2-788066fcf0fc
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ExtRemoteList, ExtRemoteList::Next, Next
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
req.alt-api: ExtRemoteList.Next
req.alt-loc: engextcpp.hpp
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
req.typenames: *PSILO_DRIVER_CAPABILITIES, SILO_DRIVER_CAPABILITIES
---

# ExtRemoteList::Next method



## -description
The <b>Next</b> method changes the current item to the next item in the list.



## -syntax

````
void Next();
````


## -parameters


## -returns
This method does not return a value.

This method does not return a value.

This method does not return a value.


## -remarks
If <b>Next</b> reaches the end of the list, subsequent calls to <a href="https://msdn.microsoft.com/library/windows/hardware/ff544136">ExtRemoteList::HasNode</a> will return <code>false</code>.


## -see-also
<dl>
<dt>
<a href="..\engextcpp\nl-engextcpp-extremotelist.md">ExtRemoteList</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544136">ExtRemoteList::HasNode</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ExtRemoteList.Next method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

