---
UID: NF:engextcpp.ExtRemoteData.GetUshort
title: ExtRemoteData::GetUshort method
author: windows-driver-content
description: The GetUshort method returns a USHORT version of the ExtRemoteData object, which represents the contents of the target's memory.
old-location: debugger\extremotedata_getushort.htm
old-project: debugger
ms.assetid: e5e2061f-5133-4645-8e07-659f08473a51
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: EngExtCpp_Ref_5429785d-2f76-434d-96c6-4fa7298aa32e.xml, ExtRemoteData, ExtRemoteData class [Windows Debugging], GetUshort method, ExtRemoteData::GetUshort, GetUshort method [Windows Debugging], GetUshort method [Windows Debugging], ExtRemoteData class, GetUshort,ExtRemoteData.GetUshort, debugger.extremotedata_getushort
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
-	ExtRemoteData.GetUshort
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtRemoteData::GetUshort method


## -description


The <b>GetUshort</b> method returns a USHORT version of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544008">ExtRemoteData</a> object, which represents the contents of the target's memory.


## -parameters






## -returns



<b>GetUshort</b> returns the USHORT version of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544008">ExtRemoteData</a> object.




## -remarks



The size of the memory represented by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544008">ExtRemoteData</a> object must be <code>sizeof(USHORT)</code>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544008">ExtRemoteData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544019">ExtRemoteData::GetData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544044">ExtRemoteData::GetShort</a>
 

 

