---
UID: NF:engextcpp.ExtRemoteData.GetData
title: ExtRemoteData::GetData method
author: windows-driver-content
description: The GetData method returns the contents of the target's memory, represented by the ExtRemoteData object.
old-location: debugger\extremotedata_getdata.htm
old-project: debugger
ms.assetid: a68e528a-c456-4bf2-8e6b-fb5c060c58fb
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: ExtRemoteData, EngExtCpp_Ref_a440fb76-5d7c-4e77-9d1e-61c0b7002493.xml, debugger.extremotedata_getdata, ExtRemoteData class [Windows Debugging], GetData method, ExtRemoteData::GetData, GetData, GetData method [Windows Debugging], ExtRemoteData class, GetData method [Windows Debugging]
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
-	ExtRemoteData.GetData
product: Windows
targetos: Windows
req.typenames: "*PSILO_DRIVER_CAPABILITIES, SILO_DRIVER_CAPABILITIES"
---

# ExtRemoteData::GetData method


## -description


The <b>GetData</b> method returns the contents of the target's memory, represented by the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object.


## -syntax


````
ULONG64 GetData(
  [in] ULONG Request
);
````


## -parameters




### -param Request [in]

Number of bytes requested.  This must be the same as the size of the memory specified by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544006">ExtRemoteData::ExtRemoteData</a> constructor or the <a href="https://msdn.microsoft.com/a335f881-7b6f-4069-87fe-c036867b0c77">ExtRemoteData::Set(Typed)</a> or <a href="https://msdn.microsoft.com/50b4bee4-3a8c-45a1-9a3f-b416aa8a19e5">ExtRemoteData::Set(Offset Bytes)</a> methods.  If it is not the same, <b>ExtRemoteException</b> is thrown.


## -returns



<b>GetData</b> returns the cached contents of the target's memory, represented by the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object.




## -remarks



The contents of the region of memory represented by an <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object are only cached if the size of the region is less than 8 bytes.  If the size of the region is greater than 8 bytes, the <b>GetData</b> method does not return a meaningful value.

A number of convenience methods are available for various primitive types. These methods will automatically provide the size of the type and cast the return value to that type.  These methods are listed in the See Also section.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544006">ExtRemoteData::ExtRemoteData</a>



<a href="https://msdn.microsoft.com/dd6f051a-d287-4cb9-8c53-928415e0f152">GetLong64</a>



<a href="https://msdn.microsoft.com/f2781f6b-cc3e-427c-8181-908639613270">GetFloat</a>



<a href="https://msdn.microsoft.com/9f796af1-870b-4349-b86a-3c9d868662f6">GetLongPtr</a>



<a href="https://msdn.microsoft.com/a17812f5-4e20-4793-9352-3cabed25a6da">GetW32Bool</a>



<a href="https://msdn.microsoft.com/f6a55181-7e1a-4af0-ac45-1991c42cdc87">GetStdBool</a>



<a href="https://msdn.microsoft.com/f8645e92-659f-42b8-a850-49a434ec2a67">GetDouble</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983420">GetUlong</a>



<a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a>



<a href="https://msdn.microsoft.com/5e364e83-76db-44b0-b5bc-15eed53bbbdf">GetShort</a>



<a href="https://msdn.microsoft.com/1a3a870b-9f50-4430-b4f4-6d877d2fac3e">GetUlongPtr</a>



<a href="https://msdn.microsoft.com/bf916e7c-f03b-4d02-8260-bc90e8957cc9">GetChar</a>



<a href="https://msdn.microsoft.com/e5e2061f-5133-4645-8e07-659f08473a51">GetUshort</a>



<a href="https://msdn.microsoft.com/f9778881-9b53-49c5-9fe8-80f9a866b9af">GetPtr</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj983421">GetUlong64</a>



<a href="https://msdn.microsoft.com/064f50e7-bae8-4c29-9802-47efdb749652">GetLong</a>



<a href="https://msdn.microsoft.com/a335f881-7b6f-4069-87fe-c036867b0c77">ExtRemoteData::Set(Typed)</a>



<a href="https://msdn.microsoft.com/2c4b7f40-210a-44fa-b7d4-150355d6b75b">GetUchar</a>



<a href="https://msdn.microsoft.com/50b4bee4-3a8c-45a1-9a3f-b416aa8a19e5">ExtRemoteData::Set(Offset Bytes)</a>



<a href="https://msdn.microsoft.com/7a580683-ae56-4566-95b4-b4d42ae0e1ab">GetBoolean</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ExtRemoteData.GetData method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

