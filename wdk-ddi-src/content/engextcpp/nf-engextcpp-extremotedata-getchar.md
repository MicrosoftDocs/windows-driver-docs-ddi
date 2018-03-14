---
UID: NF:engextcpp.ExtRemoteData.GetChar
title: ExtRemoteData::GetChar method
author: windows-driver-content
description: The GetChar method returns a CHAR version of the ExtRemoteData object, which represents the contents of the target's memory.
old-location: debugger\extremotedata_getchar.htm
old-project: debugger
ms.assetid: bf916e7c-f03b-4d02-8260-bc90e8957cc9
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: EngExtCpp_Ref_98ced053-a952-4c9f-af2b-0aab9d20e311.xml, ExtRemoteData, ExtRemoteData class [Windows Debugging], GetChar method, ExtRemoteData::GetChar, GetChar method [Windows Debugging], GetChar method [Windows Debugging], ExtRemoteData class, GetChar,ExtRemoteData.GetChar, debugger.extremotedata_getchar
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
req.lib: 
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
-	ExtRemoteData.GetChar
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtRemoteData::GetChar method


## -description


The <b>GetChar</b> method returns a CHAR version of the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object, which represents the contents of the target's memory.


## -syntax


````
CHAR GetChar();
````


## -parameters






## -returns



<b>GetChar</b> returns the CHAR version of the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object.




## -remarks



The size of the memory represented by the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object must be <code>sizeof(CHAR)</code>.




## -see-also

<a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544057">ExtRemoteData::GetUchar</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544019">ExtRemoteData::GetData</a>



 

 


