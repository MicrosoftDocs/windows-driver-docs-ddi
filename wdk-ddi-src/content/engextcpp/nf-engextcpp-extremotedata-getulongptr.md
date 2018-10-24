---
UID: NF:engextcpp.ExtRemoteData.GetUlongPtr
title: ExtRemoteData::GetUlongPtr
author: windows-driver-content
description: The GetUlongPtr method returns an unsigned integer version (extended to ULONG64) of the ExtRemoteData object, which represents the contents of the target's memory.
old-location: debugger\extremotedata_getulongptr.htm
tech.root: debugger
ms.assetid: 1a3a870b-9f50-4430-b4f4-6d877d2fac3e
ms.date: 05/03/2018
ms.keywords: EngExtCpp_Ref_22ba632d-a45b-40de-b8d7-269c917357d5.xml, ExtRemoteData class [Windows Debugging],GetUlongPtr method, ExtRemoteData.GetUlongPtr, ExtRemoteData::GetUlongPtr, GetUlongPtr, GetUlongPtr method [Windows Debugging], GetUlongPtr method [Windows Debugging],ExtRemoteData class, debugger.extremotedata_getulongptr
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
-	ExtRemoteData.GetUlongPtr
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExtRemoteData::GetUlongPtr


## -description


The <b>GetUlongPtr</b> method returns an unsigned integer version (extended to ULONG64) of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544008">ExtRemoteData</a> object, which represents the contents of the target's memory. The size of the unsigned integer from the target is the same size as a pointer on the target.


## -parameters






## -returns



<b>GetUlongPtr</b> returns an unsigned integer version of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544008">ExtRemoteData</a> object, extended to ULONG64.




## -remarks



The size of the memory represented by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544008">ExtRemoteData</a> object must be the same as the size of a pointer on the target, <code>ExtExtension::m_PtrSize</code>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544008">ExtRemoteData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544019">ExtRemoteData::GetData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544035">ExtRemoteData::GetLongPtr</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544064">ExtRemoteData::GetUlong</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544069">ExtRemoteData::GetUlong64</a>
 

 

