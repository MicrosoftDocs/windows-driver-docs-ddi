---
UID: NF:engextcpp.ExtRemoteData.GetUlong
title: ExtRemoteData::GetUlong method
author: windows-driver-content
description: The GetUlong method returns a ULONG version of the ExtRemoteData object, which represents the contents of the target's memory.
old-location: debugger\extremotedata_getulong.htm
old-project: debugger
ms.assetid: ce25b52e-5ac7-470d-902b-f45350718dff
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: EngExtCpp_Ref_41a112c3-0350-4e54-981c-b5c11697ef2d.xml, ExtRemoteData, ExtRemoteData class [Windows Debugging], GetUlong method, ExtRemoteData::GetUlong, GetUlong method [Windows Debugging], GetUlong method [Windows Debugging], ExtRemoteData class, GetUlong,ExtRemoteData.GetUlong, debugger.extremotedata_getulong
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	engextcpp.hpp
api_name:
-	ExtRemoteData.GetUlong
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtRemoteData::GetUlong method


## -description


The <b>GetUlong</b> method returns a ULONG version of the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object, which represents the contents of the target's memory.


## -syntax


````
ULONG GetUlong();
````


## -parameters






## -returns



<b>GetUlong</b> returns the ULONG version of the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object.




## -remarks



The size of the memory represented by the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object must be <code>sizeof(ULONG)</code>.




## -see-also

<a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544064">ExtRemoteData::GetUlong</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544033">ExtRemoteData::GetLong64</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544019">ExtRemoteData::GetData</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ExtRemoteData.GetUlong method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

