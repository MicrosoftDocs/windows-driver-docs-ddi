---
UID: NF:engextcpp.ExtRemoteTyped.ArrayElement
title: ExtRemoteTyped::ArrayElement method
author: windows-driver-content
description: The ArrayElement method returns the typed data in the specified array element of the typed data represented by the ExtRemoteTyped object.
old-location: debugger\extremotetyped_arrayelement.htm
old-project: debugger
ms.assetid: abe43441-3e00-4d85-ae84-dd738303ab1b
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: ArrayElement method [Windows Debugging], ArrayElement method [Windows Debugging], ExtRemoteTyped interface, ArrayElement,ExtRemoteTyped.ArrayElement, EngExtCpp_Ref_086fc0ab-cf63-4079-86d4-552dd2a1593d.xml, ExtRemoteTyped, ExtRemoteTyped interface [Windows Debugging], ArrayElement method, ExtRemoteTyped::ArrayElement, debugger.extremotetyped_arrayelement
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
-	ExtRemoteTyped.ArrayElement
product:
- Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtRemoteTyped::ArrayElement method


## -description


The <b>ArrayElement</b> method returns the typed data in the specified array element of the typed data represented by the <b>ExtRemoteTyped</b> object.


## -parameters




### -param Index [in]

The index of the array element.


## -returns



<b>ArrayElement</b> returns a new <b>ExtRemoteData</b> object that represents the typed data for the specified element of the array.




## -remarks



If the typed data represented by this object is a pointer and not an array, the pointer is treated like an array.

The <a href="https://msdn.microsoft.com/f7a63a6a-24fa-4c93-ac2e-c44f7984a2c8">ExtRemoteTyped::operator[]</a> overloaded operator performs a similar function.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544162">ExtRemoteTyped</a>



<a href="https://msdn.microsoft.com/f7a63a6a-24fa-4c93-ac2e-c44f7984a2c8">ExtRemoteTyped::operator[]</a>
 

 

