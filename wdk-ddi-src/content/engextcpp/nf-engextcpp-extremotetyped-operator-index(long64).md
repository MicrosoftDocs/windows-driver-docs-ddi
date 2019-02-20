---
UID: NF:engextcpp.ExtRemoteTyped.operator-index(LONG64)
title: ExtRemoteTyped::operator[](LONG64) (engextcpp.h)
description: The operator[] overloaded operator returns the typed data in the specified array element of the typed data represented by this object.
old-location: debugger\extremotetyped_operatorarray_long64.htm
tech.root: debugger
ms.assetid: 1c2a78ca-5820-40d5-936a-99d50661c982
ms.date: 05/03/2018
ms.keywords: ExtRemoteTyped class [Windows Debugging],operator[] method, ExtRemoteTyped.operator[], ExtRemoteTyped.operator[](LONG64), ExtRemoteTyped::operator[], ExtRemoteTyped::operator[](LONG64), debugger.extremotetyped_operatorarray_long64, operator[], operator[] method [Windows Debugging], operator[] method [Windows Debugging],ExtRemoteTyped class
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

# ExtRemoteTyped::operator (LONG64)


## -description


The <b>operator[]</b> overloaded operator returns the typed data in the specified array element of the typed data represented by this object.


## -parameters




### -param Index [in]

The index of the array element.


## -returns



The <b>operator[]</b> operator returns a new <b>ExtRemoteTyped</b> object that represents the typed data for the specified element of the array.




## -remarks



If the typed data represented by this object is a pointer and not an array, the pointer is treated like an array.

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotetyped-arrayelement">ExtRemoteTyped::ArrayElement</a> performs a similar function.




## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nl-engextcpp-extremotetyped">ExtRemoteTyped</a>


<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotetyped-arrayelement">ExtRemoteTyped::ArrayElement</a> 


<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotetyped-operator-index(ulong)">ExtRemoteTyped::Operator[] (ULONG)</a>


<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ddi/content/engextcpp/nf-engextcpp-extremotetyped-operator-index(ulong64)">ExtRemoteTyped::Operator[] (ULONG64)</a>
 

 

