---
UID: NF:engextcpp.ExtRemoteTyped.operator
title: ExtRemoteTyped::operator* method
author: windows-driver-content
description: The operator* overloaded operator returns the typed data that is pointed to by the typed data represented by this object.
old-location: debugger\extremotetyped_operator_.htm
old-project: debugger
ms.assetid: f7a63a6a-24fa-4c93-ac2e-c44f7984a2c8
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: EngExtCpp_Ref_3e10d850-c463-4d43-8639-7b7daf26c749.xml, ExtRemoteTyped, ExtRemoteTyped interface [Windows Debugging], operator* method, ExtRemoteTyped::operator*, debugger.extremotetyped_operator_, operator* method [Windows Debugging], operator* method [Windows Debugging], ExtRemoteTyped interface, operator*,ExtRemoteTyped.operator*
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
-	ExtRemoteTyped.operator*
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtRemoteTyped::operator* method


## -description


The <b>operator*</b> overloaded operator returns the typed data that is pointed to by the typed data represented by this object.


## -syntax


````
ExtRemoteData operator*();
````


## -parameters






## -returns



The <b>operator*</b> operator returns a new <b>ExtRemoteData</b> object that represents the typed data pointed to by the typed data represented by this object.




## -remarks



If the typed data represented by this object is an array, the first element in the array is returned.

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff544233">ExtRemoteTyped::Dereference</a> method performs the same function.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544233">ExtRemoteTyped::Dereference</a>



<a href="..\engextcpp\nl-engextcpp-extremotetyped.md">ExtRemoteTyped</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ExtRemoteTyped.operator* method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

