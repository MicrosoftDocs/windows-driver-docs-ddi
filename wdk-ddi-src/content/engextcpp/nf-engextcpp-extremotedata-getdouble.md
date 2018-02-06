---
UID: NF:engextcpp.ExtRemoteData.GetDouble
title: ExtRemoteData::GetDouble method
author: windows-driver-content
description: The GetDouble method returns a double version of the ExtRemoteData object, which represents the contents of the target's memory.
old-location: debugger\extremotedata_getdouble.htm
old-project: debugger
ms.assetid: f8645e92-659f-42b8-a850-49a434ec2a67
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: ExtRemoteData, debugger.extremotedata_getdouble, EngExtCpp_Ref_8776e6fd-9e13-4502-a445-da65a8fcfe41.xml, ExtRemoteData::GetDouble, ExtRemoteData class [Windows Debugging], GetDouble method, GetDouble method [Windows Debugging], GetDouble, GetDouble method [Windows Debugging], ExtRemoteData class
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	engextcpp.hpp
apiname:
-	ExtRemoteData.GetDouble
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtRemoteData::GetDouble method


## -description


The <b>GetDouble</b> method returns a <b>double</b> version of the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object, which represents the contents of the target's memory.


## -syntax


````
double GetDouble();
````


## -parameters





## -returns


<b>GetDouble</b> returns the <b>double</b> version of the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object.



## -remarks


The size of the memory represented by the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object must be <code>sizeof(double)</code>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544019">ExtRemoteData::GetData</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544028">ExtRemoteData::GetFloat</a>

<a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ExtRemoteData.GetDouble method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

