---
UID: NF:engextcpp.ExtRemoteData.GetW32Bool
title: ExtRemoteData::GetW32Bool method
author: windows-driver-content
description: The GetW32Bool method returns a BOOL version of the ExtRemoteData object, which represents the contents of the target's memory.
old-location: debugger\extremotedata_getw32bool.htm
old-project: debugger
ms.assetid: a17812f5-4e20-4793-9352-3cabed25a6da
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: EngExtCpp_Ref_367ee79b-5fdf-41ca-b43c-f9f29b3a872c.xml, ExtRemoteData, ExtRemoteData class [Windows Debugging], GetW32Bool method, ExtRemoteData::GetW32Bool, GetW32Bool method [Windows Debugging], GetW32Bool method [Windows Debugging], ExtRemoteData class, GetW32Bool,ExtRemoteData.GetW32Bool, debugger.extremotedata_getw32bool
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
-	ExtRemoteData.GetW32Bool
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtRemoteData::GetW32Bool method


## -description


The <b>GetW32Bool</b> method returns a BOOL version of the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object, which represents the contents of the target's memory.


## -syntax


````
BOOL GetW32Bool();
````


## -parameters






## -returns



<b>GetW32Bool</b> returns the BOOL version of  the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object.




## -remarks



The size of the memory represented by the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object must be <code>sizeof(BOOL)</code>.

<div class="alert"><b>Note</b>    There are several different types that can be used to represent a Boolean value. BOOL is one of these types.  For the C++ <b>bool</b> type, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff544050">ExtRemoteData::GetStdBool</a>.  For the BOOLEAN type, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff544013">ExtRemoteData::GetBoolean</a>.</div>
<div> </div>



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544019">ExtRemoteData::GetData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544050">ExtRemoteData::GetStdBool</a>



<a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544013">ExtRemoteData::GetBoolean</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ExtRemoteData.GetW32Bool method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

