---
UID: NF:engextcpp.ExtRemoteData.Read
title: ExtRemoteData::Read method
author: windows-driver-content
description: The Read method reads the contents of the target's memory, represented by the ExtRemoteData object, and then caches the data.
old-location: debugger\extremotedata_read.htm
old-project: debugger
ms.assetid: 3068cbcf-c15b-43e1-bd53-857efea65d83
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: Read method [Windows Debugging], ExtRemoteData class, ExtRemoteData::Read, ExtRemoteData, Read method [Windows Debugging], debugger.extremotedata_read, ExtRemoteData class [Windows Debugging], Read method, Read, EngExtCpp_Ref_69230a7b-f83c-46fc-88c4-134b506540af.xml
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
-	ExtRemoteData.Read
product: Windows
targetos: Windows
req.typenames: "*PSILO_DRIVER_CAPABILITIES, SILO_DRIVER_CAPABILITIES"
---

# ExtRemoteData::Read method


## -description


The <b>Read</b> method reads the contents of the target's memory, represented by the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object, and then caches the data.


## -syntax


````
void Read();
````


## -parameters






## -returns



This method does not return a value.




## -remarks



When the region of memory is specified either by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544006">ExtRemoteData::ExtRemoteData</a> constructor or by the <a href="https://msdn.microsoft.com/a335f881-7b6f-4069-87fe-c036867b0c77">ExtRemoteData::Set(Typed)</a> or <a href="https://msdn.microsoft.com/50b4bee4-3a8c-45a1-9a3f-b416aa8a19e5">ExtRemoteData::Set(Offset Bytes)</a> methods, the contents are automatically read from the target and cached.  This method only needs to be called if the memory on the target might have changed.

The data can be retrieved using <a href="https://msdn.microsoft.com/library/windows/hardware/ff544019">ExtRemoteData::GetData</a> or one of the typed "get" methods.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544006">ExtRemoteData::ExtRemoteData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544019">ExtRemoteData::GetData</a>



<a href="https://msdn.microsoft.com/a335f881-7b6f-4069-87fe-c036867b0c77">ExtRemoteData::Set(Typed)</a>



<a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a>



<a href="https://msdn.microsoft.com/50b4bee4-3a8c-45a1-9a3f-b416aa8a19e5">ExtRemoteData::Set(Offset Bytes)</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ExtRemoteData.Read method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

