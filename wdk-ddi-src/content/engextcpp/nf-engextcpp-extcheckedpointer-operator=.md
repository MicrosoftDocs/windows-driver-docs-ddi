---
UID: NF:engextcpp.ExtCheckedPointer.operator=
title: ExtCheckedPointer::operator= method
author: windows-driver-content
description: The operator= overloaded assignment operator sets the typed data represented by the ExtRemoteTyped object by copying the information from another object.
old-location: debugger\extremotetyped_operatorequals_debug_typed_data.htm
old-project: debugger
ms.assetid: 0dd00f33-1ede-43b7-97b7-55942c3f7a27
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: debugger.extremotetyped_operatorequals_debug_typed_data, ExtCheckedPointer::operator=, operator= method [Windows Debugging], operator=, ExtCheckedPointer, ExtBuffer::operator=, ExtRemoteTyped class [Windows Debugging], operator= method, ExtBuffer, operator= method [Windows Debugging], ExtRemoteTyped class
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
-	arrayofelements.hpp
apiname:
-	ExtRemoteTyped.operator=
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtCheckedPointer::operator= method


## -description


The <b>operator=</b> overloaded assignment operator sets the typed data represented by the <a href="..\engextcpp\nl-engextcpp-extremotetyped.md">ExtRemoteTyped</a> object by copying the information from another object.


## -syntax


````
ExtRemoteTyped & operator=(
  [in] const DEBUG_TYPED_DATA *Typed
);
````


## -parameters




### -param Ptr





#### - Typed [in]

A pointer to a <a href="..\wdbgexts\ns-wdbgexts-_debug_typed_data.md">DEBUG_TYPED_DATA</a> structure that describes the data and type to be assigned to this object.


## -returns


<b>operator=</b>  returns the <a href="..\engextcpp\nl-engextcpp-extremotetyped.md">ExtRemoteTyped</a> object.



## -remarks


The typed data can also be copied using the <a href="..\engextcpp\nf-engextcpp-extbuffer-copy.md">ExtRemoteTyped::Copy(Debug Typed Data)</a> or <a href="..\engextcpp\nf-engextcpp-extbuffer-copy.md">ExtRemoteTyped::Copy(ExtRemoteTyped)</a> methods.



## -see-also

<a href="..\engextcpp\nl-engextcpp-extremotetyped.md">ExtRemoteTyped</a>

<a href="..\wdbgexts\ns-wdbgexts-_debug_typed_data.md">DEBUG_TYPED_DATA</a>

<a href="..\engextcpp\nf-engextcpp-extbuffer-operator=.md">ExtRemoteTyped::Operator= (ExtRemoteTyped)</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ExtRemoteTyped.operator= method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

