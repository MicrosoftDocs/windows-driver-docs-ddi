---
UID: NF:engextcpp.ExtRemoteData.GetW32Bool
title: ExtRemoteData::GetW32Bool method
author: windows-driver-content
description: The GetW32Bool method returns a BOOL version of the ExtRemoteData object, which represents the contents of the target's memory.
old-location: debugger\extremotedata_getw32bool.htm
old-project: debugger
ms.assetid: a17812f5-4e20-4793-9352-3cabed25a6da
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: EngExtCpp_Ref_367ee79b-5fdf-41ca-b43c-f9f29b3a872c.xml, ExtRemoteData, ExtRemoteData class [Windows Debugging], GetW32Bool method, ExtRemoteData::GetW32Bool, GetW32Bool method [Windows Debugging], GetW32Bool method [Windows Debugging], ExtRemoteData class, GetW32Bool,ExtRemoteData.GetW32Bool, debugger.extremotedata_getw32bool
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
-	ExtRemoteData.GetW32Bool
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtRemoteData::GetW32Bool method


## -description


The <b>GetW32Bool</b> method returns a BOOL version of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544008">ExtRemoteData</a> object, which represents the contents of the target's memory.


## -parameters






## -returns



<b>GetW32Bool</b> returns the BOOL version of  the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544008">ExtRemoteData</a> object.




## -remarks



The size of the memory represented by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544008">ExtRemoteData</a> object must be <code>sizeof(BOOL)</code>.

<div class="alert"><b>Note</b>    There are several different types that can be used to represent a Boolean value. BOOL is one of these types.  For the C++ <b>bool</b> type, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff544050">ExtRemoteData::GetStdBool</a>.  For the BOOLEAN type, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff544013">ExtRemoteData::GetBoolean</a>.</div>
<div> </div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544008">ExtRemoteData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544013">ExtRemoteData::GetBoolean</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544019">ExtRemoteData::GetData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544050">ExtRemoteData::GetStdBool</a>
 

 

