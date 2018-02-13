---
UID: NF:engextcpp.ExtRemoteData.GetUlongPtr
title: ExtRemoteData::GetUlongPtr method
author: windows-driver-content
description: The GetUlongPtr method returns an unsigned integer version (extended to ULONG64) of the ExtRemoteData object, which represents the contents of the target's memory.
old-location: debugger\extremotedata_getulongptr.htm
old-project: debugger
ms.assetid: 1a3a870b-9f50-4430-b4f4-6d877d2fac3e
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: EngExtCpp_Ref_22ba632d-a45b-40de-b8d7-269c917357d5.xml, GetUlongPtr method [Windows Debugging], ExtRemoteData class, ExtRemoteData, ExtRemoteData::GetUlongPtr, GetUlongPtr method [Windows Debugging], debugger.extremotedata_getulongptr, ExtRemoteData class [Windows Debugging], GetUlongPtr method, GetUlongPtr
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
-	ExtRemoteData.GetUlongPtr
product: Windows
targetos: Windows
req.typenames: "*PSILO_DRIVER_CAPABILITIES, SILO_DRIVER_CAPABILITIES"
---

# ExtRemoteData::GetUlongPtr method


## -description


The <b>GetUlongPtr</b> method returns an unsigned integer version (extended to ULONG64) of the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object, which represents the contents of the target's memory. The size of the unsigned integer from the target is the same size as a pointer on the target.


## -syntax


````
ULONG64 GetUlongPtr();
````


## -parameters






## -returns



<b>GetUlongPtr</b> returns an unsigned integer version of the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object, extended to ULONG64.




## -remarks



The size of the memory represented by the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object must be the same as the size of a pointer on the target, <code>ExtExtension::m_PtrSize</code>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544069">ExtRemoteData::GetUlong64</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544035">ExtRemoteData::GetLongPtr</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544064">ExtRemoteData::GetUlong</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544019">ExtRemoteData::GetData</a>



<a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ExtRemoteData.GetUlongPtr method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

