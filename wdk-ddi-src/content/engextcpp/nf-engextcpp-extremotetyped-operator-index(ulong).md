---
UID: NF:engextcpp.ExtRemoteTyped.operator-index(ULONG)
title: ExtRemoteTyped::operator[](ULONG)
author: windows-driver-content
description: The operator[] overloaded operator returns the typed data in the specified array element of the typed data represented by this object.
old-location: debugger\extremotetyped_operatorarray_ulong.htm
tech.root: debugger
ms.assetid: d264f2a1-20fa-4bd3-9db5-f253cc5ad0e6
ms.date: 05/03/2018
ms.keywords: ExtRemoteTyped class [Windows Debugging],operator[] method, ExtRemoteTyped.operator[], ExtRemoteTyped.operator[](ULONG), ExtRemoteTyped::operator[], ExtRemoteTyped::operator[](ULONG), debugger.extremotetyped_operatorarray_ulong, operator[], operator[] method [Windows Debugging], operator[] method [Windows Debugging],ExtRemoteTyped class
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
-	ExtRemoteTyped.operator[]
product:
-	Windows
targetos: Windows
req.typenames: 
---

# ExtRemoteTyped::operator[](ULONG)


## -description


The <b>operator[]</b> overloaded operator returns the typed data in the specified array element of the typed data represented by this object.


## -parameters




### -param Index [in]

The index of the array element.


## -returns



The <b>operator[]</b> operator returns a new <b>ExtRemoteTyped</b> object that represents the typed data for the specified element of the array.




## -remarks



If the typed data represented by this object is a pointer and not an array, the pointer is treated like an array.

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff544211">ExtRemoteTyped::ArrayElement</a> performs a similar function.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544162">ExtRemoteTyped</a>



<b>ExtRemoteTyped::ArrayElement</b>



<a href="https://msdn.microsoft.com/b75a0cec-fda6-45a3-ac60-915fc5862456">ExtRemoteTyped::Operator[] (LONG)</a>



<a href="https://msdn.microsoft.com/1c2a78ca-5820-40d5-936a-99d50661c982">ExtRemoteTyped::Operator[] (LONG64)</a>



<a href="https://msdn.microsoft.com/60bf48e2-8f44-4ed3-8c35-499e764fcca9">ExtRemoteTyped::Operator[] (ULONG64)</a>
 

 

