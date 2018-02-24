---
UID: NF:engextcpp.ExtRemoteData.GetUshort
title: ExtRemoteData::GetUshort method
author: windows-driver-content
description: The GetUshort method returns a USHORT version of the ExtRemoteData object, which represents the contents of the target's memory.
old-location: debugger\extremotedata_getushort.htm
old-project: Debugger
ms.assetid: e5e2061f-5133-4645-8e07-659f08473a51
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: EngExtCpp_Ref_5429785d-2f76-434d-96c6-4fa7298aa32e.xml, ExtRemoteData class [Windows Debugging], GetUshort method, GetUshort, GetUshort method [Windows Debugging], ExtRemoteData::GetUshort, ExtRemoteData, GetUshort method [Windows Debugging], ExtRemoteData class, debugger.extremotedata_getushort
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
-	ExtRemoteData.GetUshort
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtRemoteData::GetUshort method


## -description


The <b>GetUshort</b> method returns a USHORT version of the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object, which represents the contents of the target's memory.


## -syntax


````
USHORT GetUshort();
````


## -parameters






## -returns



<b>GetUshort</b> returns the USHORT version of the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object.




## -remarks



The size of the memory represented by the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object must be <code>sizeof(USHORT)</code>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544044">ExtRemoteData::GetShort</a>



<a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544044">ExtRemoteData::GetShort</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20ExtRemoteData.GetUshort method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

