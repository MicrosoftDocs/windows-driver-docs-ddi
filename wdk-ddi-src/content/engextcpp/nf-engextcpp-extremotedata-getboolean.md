---
UID: NF:engextcpp.ExtRemoteData.GetBoolean
title: ExtRemoteData::GetBoolean method
author: windows-driver-content
description: The GetBoolean method returns a Boolean version of the ExtRemoteData object, which represents the contents of the target's memory.
old-location: debugger\extremotedata_getboolean.htm
old-project: debugger
ms.assetid: 7a580683-ae56-4566-95b4-b4d42ae0e1ab
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: EngExtCpp_Ref_791b0934-9cb7-430a-8b80-d7fe4f458f49.xml, ExtRemoteData, debugger.extremotedata_getboolean, GetBoolean, GetBoolean method [Windows Debugging], ExtRemoteData class, ExtRemoteData::GetBoolean, GetBoolean method [Windows Debugging], ExtRemoteData class [Windows Debugging], GetBoolean method
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
-	ExtRemoteData.GetBoolean
product: Windows
targetos: Windows
req.typenames: "*PSILO_DRIVER_CAPABILITIES, SILO_DRIVER_CAPABILITIES"
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
<div class="alert"><b>Note</b>    There are several different types that can be used to represent a Boolean value. BOOLEAN is one of these types.  For the C++ <b>bool</b> type, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff544050">ExtRemoteData::GetStdBool</a>.  For the BOOL type, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff544081">ExtRemoteData::GetW32Bool</a>.</div><div> </div>


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544019">ExtRemoteData::GetData</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544081">ExtRemoteData::GetW32Bool</a>

<a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544050">ExtRemoteData::GetStdBool</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ExtRemoteData.GetBoolean method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

