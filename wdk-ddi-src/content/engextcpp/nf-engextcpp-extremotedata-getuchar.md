---
UID: NF:engextcpp.ExtRemoteData.GetUchar
title: ExtRemoteData::GetUchar method
author: windows-driver-content
description: The GetUChar method returns a UCHAR version of the ExtRemoteData object, which represents the contents of the target's memory.
old-location: debugger\extremotedata_getuchar.htm
old-project: debugger
ms.assetid: 2c4b7f40-210a-44fa-b7d4-150355d6b75b
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: EngExtCpp_Ref_687a7887-560a-4565-8417-ec46cc1ee254.xml, ExtRemoteData, ExtRemoteData class [Windows Debugging], GetUchar method, ExtRemoteData::GetUchar, GetUchar method [Windows Debugging], GetUchar method [Windows Debugging], ExtRemoteData class, GetUchar,ExtRemoteData.GetUchar, debugger.extremotedata_getuchar
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
-	ExtRemoteData.GetUchar
product:
- Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtRemoteData::GetUchar method


## -description


The <b>GetUChar</b> method returns a UCHAR version of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544008">ExtRemoteData</a> object, which represents the contents of the target's memory.


## -parameters






## -returns



<b>GetUChar</b> returns the UCHAR version of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544008">ExtRemoteData</a> object.




## -remarks



The size of the memory represented by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544008">ExtRemoteData</a> object must be <code>sizeof(UCHAR)</code>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544008">ExtRemoteData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544016">ExtRemoteData::GetChar</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544019">ExtRemoteData::GetData</a>
 

 

