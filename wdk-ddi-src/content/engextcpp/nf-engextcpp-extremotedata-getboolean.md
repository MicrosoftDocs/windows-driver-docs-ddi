---
UID: NF:engextcpp.ExtRemoteData.GetBoolean
title: ExtRemoteData::GetBoolean method
author: windows-driver-content
description: The GetBoolean method returns a Boolean version of the ExtRemoteData object, which represents the contents of the target's memory.
old-location: debugger\extremotedata_getboolean.htm
old-project: debugger
ms.assetid: 7a580683-ae56-4566-95b4-b4d42ae0e1ab
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: EngExtCpp_Ref_791b0934-9cb7-430a-8b80-d7fe4f458f49.xml, ExtRemoteData, ExtRemoteData class [Windows Debugging], GetBoolean method, ExtRemoteData::GetBoolean, GetBoolean method [Windows Debugging], GetBoolean method [Windows Debugging], ExtRemoteData class, GetBoolean,ExtRemoteData.GetBoolean, debugger.extremotedata_getboolean
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
-	ExtRemoteData.GetBoolean
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtRemoteData::GetBoolean method


## -description


The <b>GetBoolean</b> method returns a Boolean version of the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object, which represents the contents of the target's memory.


## -syntax


````
BOOLEAN GetBoolean();
````


## -parameters






## -returns



<b>GetBoolean</b> returns the BOOLEAN version of the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object.




## -remarks



The size of the memory represented by the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object must be <code>sizeof(BOOLEAN)</code>.

<div class="alert"><b>Note</b>    There are several different types that can be used to represent a Boolean value. BOOLEAN is one of these types.  For the C++ <b>bool</b> type, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff544050">ExtRemoteData::GetStdBool</a>.  For the BOOL type, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff544081">ExtRemoteData::GetW32Bool</a>.</div>
<div> </div>



## -see-also

<a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544050">ExtRemoteData::GetStdBool</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544081">ExtRemoteData::GetW32Bool</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544019">ExtRemoteData::GetData</a>



 

 


