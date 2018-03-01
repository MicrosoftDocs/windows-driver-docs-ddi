---
UID: NF:engextcpp.ExtRemoteTyped.operator[]
title: ExtRemoteTyped::operator[] method
author: windows-driver-content
description: The operator[] overloaded operator returns the typed data in the specified array element of the typed data represented by this object.
old-location: debugger\extremotetyped_operatorarray_long.htm
old-project: debugger
ms.assetid: b75a0cec-fda6-45a3-ac60-915fc5862456
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: ExtRemoteTyped, ExtRemoteTyped class [Windows Debugging], operator[] method, ExtRemoteTyped::Operator[], ExtRemoteTyped::operator[], debugger.extremotetyped_operatorarray_long, operator[] method [Windows Debugging], operator[] method [Windows Debugging], ExtRemoteTyped class, operator[],ExtRemoteTyped.operator[]
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
-	ExtRemoteTyped.operator[]
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtRemoteTyped::operator[] method


## -description


The <b>operator[]</b> overloaded operator returns the typed data in the specified array element of the typed data represented by this object.


## -syntax


````
ExtRemoteTyped operator[](
  [in] LONG Index
);
````


## -parameters




### -param Index [in]

The index of the array element.


## -returns



The <b>operator[]</b> operator returns a new <b>ExtRemoteTyped</b> object that represents the typed data for the specified element of the array.




## -remarks



If the typed data represented by this object is a pointer and not an array, the pointer is treated like an array.

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff544211">ExtRemoteTyped::ArrayElement</a> performs a similar function.




## -see-also

<a href="..\engextcpp\nf-engextcpp-extremotetyped-operator[].md">ExtRemoteTyped::Operator[] (ULONG64)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544211">ExtRemoteTyped::ArrayElement</a>



<a href="..\engextcpp\nf-engextcpp-extremotetyped-operator[].md">ExtRemoteTyped::Operator[] (ULONG)</a>



<a href="..\engextcpp\nf-engextcpp-extremotetyped-operator[].md">ExtRemoteTyped::Operator[] (LONG64)</a>



<a href="..\engextcpp\nl-engextcpp-extremotetyped.md">ExtRemoteTyped</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ExtRemoteTyped.operator[] method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

