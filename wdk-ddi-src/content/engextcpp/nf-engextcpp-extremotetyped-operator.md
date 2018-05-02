---
UID: NF:engextcpp.ExtRemoteTyped.operator
title: ExtRemoteTyped::operator
author: windows-driver-content
description: The operator* overloaded operator returns the typed data that is pointed to by the typed data represented by this object.
old-location: debugger\extremotetyped_operator_.htm
old-project: debugger
ms.assetid: f7a63a6a-24fa-4c93-ac2e-c44f7984a2c8
ms.author: windowsdriverdev
ms.date: 4/24/2018
ms.keywords: EngExtCpp_Ref_3e10d850-c463-4d43-8639-7b7daf26c749.xml, ExtRemoteTyped interface [Windows Debugging],operator* method, ExtRemoteTyped.operator, ExtRemoteTyped.operator*, ExtRemoteTyped.operator*(), ExtRemoteTyped::operator, ExtRemoteTyped::operator*, debugger.extremotetyped_operator_, operator*, operator* method [Windows Debugging], operator* method [Windows Debugging],ExtRemoteTyped interface
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
-	ExtRemoteTyped.operator*
product:
- Windows
targetos: Windows
req.typenames: 
---

# ExtRemoteTyped::operator


## -description


The <b>operator*</b> overloaded operator returns the typed data that is pointed to by the typed data represented by this object.


## -parameters






## -returns



The <b>operator*</b> operator returns a new <b>ExtRemoteData</b> object that represents the typed data pointed to by the typed data represented by this object.




## -remarks



If the typed data represented by this object is an array, the first element in the array is returned.

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff544233">ExtRemoteTyped::Dereference</a> method performs the same function.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544162">ExtRemoteTyped</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544233">ExtRemoteTyped::Dereference</a>
 

 

