---
UID: NF:engextcpp.ExtRemoteData.GetPtr
title: ExtRemoteData::GetPtr method
author: windows-driver-content
description: The GetPtr method returns a pointer from the target's memory version of the ExtRemoteData object, which represents the contents of the target's memory. The size of the unsigned integer from the target is the same size as a pointer on the target.
old-location: debugger\extremotedata_getptr.htm
old-project: debugger
ms.assetid: f9778881-9b53-49c5-9fe8-80f9a866b9af
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: EngExtCpp_Ref_6aea2145-72ce-4bdc-afb2-1fa360e643da.xml, ExtRemoteData, ExtRemoteData class [Windows Debugging], GetPtr method, ExtRemoteData::GetPtr, GetPtr method [Windows Debugging], GetPtr method [Windows Debugging], ExtRemoteData class, GetPtr,ExtRemoteData.GetPtr, debugger.extremotedata_getptr
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
-	ExtRemoteData.GetPtr
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtRemoteData::GetPtr method


## -description


The <b>GetPtr</b> method returns a pointer from the target's memory version of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544008">ExtRemoteData</a> object, which represents the contents of the target's memory. The size of the unsigned integer from the target is the same size as a pointer on the target.


## -parameters






## -returns



<b>GetPtr</b> returns a pointer from the target's memory.  As with all pointers, if the target uses 32-bit pointers, it is sign-extended to 64-bits.




## -remarks



The size of the memory represented by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544008">ExtRemoteData</a> object must be the same as the size of a pointer on the target, <code>ExtExtension::m_PtrSize</code>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544008">ExtRemoteData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544019">ExtRemoteData::GetData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544035">ExtRemoteData::GetLongPtr</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544064">ExtRemoteData::GetUlong</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544069">ExtRemoteData::GetUlong64</a>
 

 

