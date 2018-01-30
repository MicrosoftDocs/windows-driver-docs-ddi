---
UID: NF:engextcpp.ExtRemoteData.GetLong64
title: ExtRemoteData::GetLong64 method
author: windows-driver-content
description: The GetLong64 method returns a LONG64 version of the ExtRemoteData object, which represents the contents of the target's memory.
old-location: debugger\extremotedata_getlong64.htm
old-project: debugger
ms.assetid: dd6f051a-d287-4cb9-8c53-928415e0f152
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: ExtRemoteData::GetLong64, debugger.extremotedata_getlong64, ExtRemoteData, GetLong64 method [Windows Debugging], GetLong64 method [Windows Debugging], ExtRemoteData class, GetLong64, ExtRemoteData class [Windows Debugging], GetLong64 method, EngExtCpp_Ref_4b2bf03d-7a55-4cee-826b-2b384972392f.xml
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
-	ExtRemoteData.GetLong64
product: Windows
targetos: Windows
req.typenames: DXVA_VideoSample32
---

# ExtRemoteData::GetLong64 method


## -description


The <b>GetLong64</b> method returns a LONG64 version of the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object, which represents the contents of the target's memory.


## -syntax


````
LONG64 GetLong64();
````


## -parameters





## -returns


<b>GetLong64</b> returns the LONG64 version of the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object.



## -remarks


The size of the memory represented by the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object must be <code>sizeof(LONG64)</code>.



## -see-also

<a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544019">ExtRemoteData::GetData</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544064">ExtRemoteData::GetUlong</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544033">ExtRemoteData::GetLong64</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ExtRemoteData.GetLong64 method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

