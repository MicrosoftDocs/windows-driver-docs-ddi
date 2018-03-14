---
UID: NF:engextcpp.ExtRemoteData.GetFloat
title: ExtRemoteData::GetFloat method
author: windows-driver-content
description: The GetFloat method returns a float version of the ExtRemoteData object, which represents the contents of the target's memory.
old-location: debugger\extremotedata_getfloat.htm
old-project: debugger
ms.assetid: f2781f6b-cc3e-427c-8181-908639613270
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: EngExtCpp_Ref_f1ca75e4-6dea-4237-b76a-04b3af234060.xml, ExtRemoteData, ExtRemoteData class [Windows Debugging], GetFloat method, ExtRemoteData::GetFloat, GetFloat method [Windows Debugging], GetFloat method [Windows Debugging], ExtRemoteData class, GetFloat,ExtRemoteData.GetFloat, debugger.extremotedata_getfloat
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
-	ExtRemoteData.GetFloat
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtRemoteData::GetFloat method


## -description


The <b>GetFloat</b> method returns a <b>float</b> version of the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object, which represents the contents of the target's memory.


## -syntax


````
float GetFloat();
````


## -parameters






## -returns



<b>GetFloat</b> returns the <b>float</b> version of the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object.




## -remarks



The size of the memory represented by the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object must be <code>sizeof(float)</code>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544022">ExtRemoteData::GetDouble</a>



<a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544019">ExtRemoteData::GetData</a>



 

 


