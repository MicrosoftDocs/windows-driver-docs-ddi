---
UID: NF:ksproxy.IKsObject.KsGetObjectHandle
title: IKsObject::KsGetObjectHandle (ksproxy.h)
description: The KsGetObjectHandle method retrieves a file handle to a KS object.
old-location: stream\iksobject_ksgetobjecthandle.htm
tech.root: stream
ms.assetid: 55c4f362-eb3c-4c4f-a048-7abdd270f67f
ms.date: 04/23/2018
ms.keywords: IKsObject interface [Streaming Media Devices],KsGetObjectHandle method, IKsObject.KsGetObjectHandle, IKsObject::KsGetObjectHandle, KsGetObjectHandle, KsGetObjectHandle method [Streaming Media Devices], KsGetObjectHandle method [Streaming Media Devices],IKsObject interface, ksproxy/IKsObject::KsGetObjectHandle, ksproxy_37998df5-a529-4f73-95a3-88ff3fdfcf2a.xml, stream.iksobject_ksgetobjecthandle
ms.topic: method
req.header: ksproxy.h
req.include-header: Ksproxy.h
req.target-type: DesktopMobile
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
-	ksproxy.h
api_name:
-	IKsObject.KsGetObjectHandle
product:
- Windows
targetos: Windows
req.typenames: 
---

# IKsObject::KsGetObjectHandle


## -description


The <b>KsGetObjectHandle</b> method retrieves a file handle to a KS object. 


## -parameters






## -returns



Returns a file handle to a KS object if successful; otherwise, returns null. 




## -remarks



Applications can use the handle that <b>KsGetObjectHandle</b> returns to send control-code requests to the driver that handles the KS object. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567142">KsSynchronousDeviceControl</a>
 

 

