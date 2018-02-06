---
UID: NF:wdfrequest.WdfRequestGetRequestorMode
title: WdfRequestGetRequestorMode function
author: windows-driver-content
description: The WdfRequestGetRequestorMode method returns the processor access mode of the originator of a specified I/O request.
old-location: wdf\wdfrequestgetrequestormode.htm
old-project: wdf
ms.assetid: 63fc77c8-756c-4872-b608-539d8419154b
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: DFRequestObjectRef_3c672bff-3d8a-402a-8a0c-19eb4d39e37e.xml, kmdf.wdfrequestgetrequestormode, wdf.wdfrequestgetrequestormode, WdfRequestGetRequestorMode, WdfRequestGetRequestorMode method, wdfrequest/WdfRequestGetRequestorMode, PFN_WDFREQUESTGETREQUESTORMODE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname:
-	WdfRequestGetRequestorMode
product: Windows
targetos: Windows
req.typenames: WDF_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfRequestGetRequestorMode function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRequestGetRequestorMode</b> method returns the processor access mode of the originator of a specified I/O request.


## -syntax


````
KPROCESSOR_MODE WdfRequestGetRequestorMode(
  _In_ WDFREQUEST Request
);
````


## -parameters




### -param Request [in]

A handle to a framework request object.


## -returns


<b>WdfRequestGetRequestorMode</b> returns <b>KernelMode</b> if the originator of the I/O request is executing in kernel mode. Otherwise, this method returns <b>UserMode</b>. The <b>KernelMode</b> and <b>UserMode</b> constants are defined in <i>wdm.h</i>.

A bug check occurs if the driver supplies an invalid object handle.





## -remarks


For more information about <b>WdfRequestGetRequestorMode</b>, see <a href="https://msdn.microsoft.com/a686ea00-6987-480a-a4ce-892e1efbed87">Obtaining Information About an I/O Request</a>.


