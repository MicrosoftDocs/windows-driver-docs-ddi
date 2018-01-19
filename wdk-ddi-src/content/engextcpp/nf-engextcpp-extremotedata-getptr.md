---
UID: NF:engextcpp.ExtRemoteData.GetPtr
title: ExtRemoteData::GetPtr method
author: windows-driver-content
description: The GetPtr method returns a pointer from the target's memory version of the ExtRemoteData object, which represents the contents of the target's memory. The size of the unsigned integer from the target is the same size as a pointer on the target.
old-location: debugger\extremotedata_getptr.htm
old-project: debugger
ms.assetid: f9778881-9b53-49c5-9fe8-80f9a866b9af
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ExtRemoteData, ExtRemoteData::GetPtr, GetPtr
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
req.alt-api: ExtRemoteData.GetPtr
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

# ExtRemoteData::GetPtr method



## -description
The <b>GetPtr</b> method returns a pointer from the target's memory version of the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object, which represents the contents of the target's memory. The size of the unsigned integer from the target is the same size as a pointer on the target.



## -syntax

````
ULONG64 GetPtr();
````


## -parameters


## -returns
<b>GetPtr</b> returns a pointer from the target's memory.  As with all pointers, if the target uses 32-bit pointers, it is sign-extended to 64-bits.

<b>GetPtr</b> returns a pointer from the target's memory.  As with all pointers, if the target uses 32-bit pointers, it is sign-extended to 64-bits.

<b>GetPtr</b> returns a pointer from the target's memory.  As with all pointers, if the target uses 32-bit pointers, it is sign-extended to 64-bits.


## -remarks
The size of the memory represented by the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object must be the same as the size of a pointer on the target, <code>ExtExtension::m_PtrSize</code>.


## -see-also
<dl>
<dt>
<a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544019">ExtRemoteData::GetData</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544035">ExtRemoteData::GetLongPtr</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544064">ExtRemoteData::GetUlong</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544069">ExtRemoteData::GetUlong64</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ExtRemoteData.GetPtr method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

