---
UID: NF:engextcpp.ExtRemoteData.ExtRemoteData
title: ExtRemoteData::ExtRemoteData method
author: windows-driver-content
description: The ExtRemoteData constructor creates a new instance of the ExtRemoteData class.
old-location: debugger\extremotedata_extremotedata.htm
old-project: debugger
ms.assetid: c463169e-5e18-44bb-b954-8a99d24edd0c
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: EngExtCpp_Ref_8e376094-9e23-4ea4-81e3-c47e6695a687.xml, ExtRemoteData, ExtRemoteData class [Windows Debugging], ExtRemoteData constructor, ExtRemoteData constructor [Windows Debugging], ExtRemoteData constructor [Windows Debugging], ExtRemoteData class, ExtRemoteData,ExtRemoteData.ExtRemoteData, ExtRemoteData::ExtRemoteData, debugger.extremotedata_extremotedata
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
-	ExtRemoteData.ExtRemoteData
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtRemoteData::ExtRemoteData method


## -description


The <b>ExtRemoteData</b> constructor creates a new instance of the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> class.


## -syntax


````
ExtRemoteData();
````


## -parameters






## -remarks



If a memory region is specified, the contents of the region are read from the target and cached.  The data can be retrieved using <a href="https://msdn.microsoft.com/library/windows/hardware/ff544019">ExtRemoteData::GetData</a> or one of the ExtRemoteTyped::Get<i>Xxx</i> methods.

The constructor is called by the <a href="https://msdn.microsoft.com/a335f881-7b6f-4069-87fe-c036867b0c77">ExtRemoteData::Set(Typed)</a> or <a href="https://msdn.microsoft.com/50b4bee4-3a8c-45a1-9a3f-b416aa8a19e5">ExtRemoteData::Set(Offset Bytes)</a> methods and the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544019">ExtRemoteData::GetData</a> method.




## -see-also

<a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData::ExtRemoteData (Name, Offset, Bytes)</a>



<a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData::ExtRemoteData (Offset, Bytes)</a>



<a href="https://msdn.microsoft.com/a335f881-7b6f-4069-87fe-c036867b0c77">ExtRemoteData::Set(Typed)</a>



<a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544019">ExtRemoteData::GetData</a>



<a href="https://msdn.microsoft.com/50b4bee4-3a8c-45a1-9a3f-b416aa8a19e5">ExtRemoteData::Set(Offset Bytes)</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ExtRemoteData.ExtRemoteData constructor%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

