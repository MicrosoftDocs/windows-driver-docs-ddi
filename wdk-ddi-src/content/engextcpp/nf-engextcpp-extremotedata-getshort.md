---
UID: NF:engextcpp.ExtRemoteData.GetShort
title: ExtRemoteData::GetShort method
author: windows-driver-content
description: The GetShort method returns a SHORT version of the ExtRemoteData object, which represents the contents of the target's memory.
old-location: debugger\extremotedata_getshort.htm
old-project: debugger
ms.assetid: 5e364e83-76db-44b0-b5bc-15eed53bbbdf
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: EngExtCpp_Ref_c2fffdd2-e899-4f87-bd00-415bafa3b84f.xml, ExtRemoteData, ExtRemoteData class [Windows Debugging], GetShort method, ExtRemoteData::GetShort, GetShort method [Windows Debugging], GetShort method [Windows Debugging], ExtRemoteData class, GetShort,ExtRemoteData.GetShort, debugger.extremotedata_getshort
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
-	ExtRemoteData.GetShort
product:
- Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtRemoteData::GetShort method


## -description


The <b>GetShort</b> method returns a SHORT version of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544008">ExtRemoteData</a> object, which represents the contents of the target's memory.


## -parameters






## -returns



<b>GetShort</b> returns the SHORT version of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544008">ExtRemoteData</a> object.




## -remarks



The size of the memory represented by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544008">ExtRemoteData</a> object must be <code>sizeof(SHORT)</code>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544008">ExtRemoteData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544019">ExtRemoteData::GetData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544077">ExtRemoteData::GetUshort</a>
 

 

