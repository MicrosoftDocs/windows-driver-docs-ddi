---
UID: NF:wdffileobject.WdfFileObjectGetFlags
title: WdfFileObjectGetFlags function
author: windows-driver-content
description: The WdfFileObjectGetFlags method returns the flags that a specified framework file object contains.
old-location: wdf\wdffileobjectgetflags.htm
old-project: wdf
ms.assetid: f2f30acb-cab7-444a-8b86-6001a8a325b9
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfFileObjectGetFlags, DFFileObjectRef_5f2f8f12-9a16-4fb5-88ae-ee726a278cc5.xml, WdfFileObjectGetFlags method, kmdf.wdffileobjectgetflags, PFN_WDFFILEOBJECTGETFLAGS, wdf.wdffileobjectgetflags, wdffileobject/WdfFileObjectGetFlags
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdffileobject.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <=DISPATCH_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	LibDef
apilocation: 
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname: 
-	WdfFileObjectGetFlags
product: Windows
targetos: Windows
req.typenames: *PWDF_FILE_INFORMATION_CLASS, WDF_FILE_INFORMATION_CLASS
req.product: Windows 10 or later.
---

# WdfFileObjectGetFlags function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfFileObjectGetFlags</b> method returns the flags that a specified framework file object contains.


## -syntax


````
ULONG WdfFileObjectGetFlags(
  _In_ WDFFILEOBJECT FileObject
);
````


## -parameters




### -param FileObject [in]

A handle to a framework file object.


## -returns


<b>WdfFileObjectGetFlags</b> returns a bitwise OR of file object flags. The flag names have a format of FO_<i>XXX</i> and are defined in <i>Wdm.h</i>. 

A bug check occurs if the driver supplies an invalid object handle.





## -remarks


For more information about framework file objects, see <a href="https://msdn.microsoft.com/93ec5dd7-8ef0-4cea-9253-ea5d7869d4b8">Framework File Objects</a>.


