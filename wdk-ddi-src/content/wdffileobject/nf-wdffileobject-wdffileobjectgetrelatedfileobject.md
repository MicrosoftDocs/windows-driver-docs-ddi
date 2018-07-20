---
UID: NF:wdffileobject.WdfFileObjectGetRelatedFileObject
title: WdfFileObjectGetRelatedFileObject function
author: windows-driver-content
description: The WdfFileObjectGetRelatedFileObject method retrieves the related file object to a framework file object.
old-location: wdf\wdffileobjectgetrelatedfileobject.htm
tech.root: wdf
ms.assetid: EB00FF6B-144B-4256-A362-D593FD4CFC98
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WdfFileObjectGetRelatedFileObject, WdfFileObjectGetRelatedFileObject method, wdf.wdffileobjectgetrelatedfileobject, wdffileobject/WdfFileObjectGetRelatedFileObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdffileobject.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: WUDFx02000.lib
req.dll: WUDFx02000.dll; TBD
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	WUDFx02000.dll
api_name:
-	WdfFileObjectGetRelatedFileObject
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfFileObjectGetRelatedFileObject function


## -description


<p class="CCE_Message">[Applies to UMDF only]

The <b>WdfFileObjectGetRelatedFileObject</b> method retrieves the related file object to a framework file object.


## -parameters




### -param FileObject [in]

A handle to a framework file object.


## -returns



<b>WdfFileObjectGetRelatedFileObject</b> returns a handle to the related file object to a framework file object.




## -remarks



Use of related file objects is technology-specific. For example, <a href="https://msdn.microsoft.com/dcd28218-b3bf-4e5d-b1a7-6910103afb96">kernel streaming</a> uses related file objects to represent the parent filters of child pins.

For more information about related file objects, see the <a href="https://msdn.microsoft.com/0ac5c19a-b3ec-4f1e-a018-2c11cc18e58d">GetRelatedFileObject</a> member of the kernel-mode <a href="https://msdn.microsoft.com/library/windows/hardware/ff545834">FILE_OBJECT</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547310">WdfFileObjectGetFileName</a>
 

 

