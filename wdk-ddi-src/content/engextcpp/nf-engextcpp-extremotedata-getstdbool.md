---
UID: NF:engextcpp.ExtRemoteData.GetStdBool
title: ExtRemoteData::GetStdBool method
author: windows-driver-content
description: The GetStdBool method returns a bool version of the ExtRemoteData object, which represents the contents of the target's memory.
old-location: debugger\extremotedata_getstdbool.htm
old-project: Debugger
ms.assetid: f6a55181-7e1a-4af0-ac45-1991c42cdc87
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: ExtRemoteData class [Windows Debugging], GetStdBool method, GetStdBool method [Windows Debugging], debugger.extremotedata_getstdbool, ExtRemoteData::GetStdBool, GetStdBool method [Windows Debugging], ExtRemoteData class, ExtRemoteData, GetStdBool, EngExtCpp_Ref_65fe8202-99dc-45b3-9b38-5fca10341b1b.xml
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
-	ExtRemoteData.GetStdBool
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtRemoteData::GetStdBool method


## -description


The <b>GetStdBool</b> method returns a <b>bool</b> version of the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object, which represents the contents of the target's memory.


## -syntax


````
bool GetStdBool();
````


## -parameters






## -returns



The <b>bool</b> version ofthe <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object.




## -remarks



The size of the memory represented by the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object must be <code>sizeof(bool)</code>.

<div class="alert"><b>Note</b>    There are several different types that can be used to represent a Boolean value. <b>bool</b> is one of these types.  For the BOOLEAN type, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff544013">ExtRemoteData::GetBoolean</a>.  For the BOOL type, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff544081">ExtRemoteData::GetW32Bool</a>.</div>
<div> </div>



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544019">ExtRemoteData::GetData</a>



<a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544081">ExtRemoteData::GetW32Bool</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544013">ExtRemoteData::GetBoolean</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20ExtRemoteData.GetStdBool method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

