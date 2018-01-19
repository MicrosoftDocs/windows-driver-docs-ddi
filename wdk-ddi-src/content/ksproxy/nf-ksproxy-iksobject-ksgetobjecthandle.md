---
UID: NF:ksproxy.IKsObject.KsGetObjectHandle
title: IKsObject::KsGetObjectHandle method
author: windows-driver-content
description: The KsGetObjectHandle method retrieves a file handle to a KS object.
old-location: stream\iksobject_ksgetobjecthandle.htm
old-project: stream
ms.assetid: 55c4f362-eb3c-4c4f-a048-7abdd270f67f
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: IKsObject, IKsObject::KsGetObjectHandle, KsGetObjectHandle
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: ksproxy.h
req.include-header: Ksproxy.h
req.target-type: DesktopMobile
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IKsObject.KsGetObjectHandle
req.alt-loc: ksproxy.h
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
req.typenames: PIPE_STATE
---

# IKsObject::KsGetObjectHandle method



## -description
The <b>KsGetObjectHandle</b> method retrieves a file handle to a KS object. 



## -syntax

````
HANDLE KsGetObjectHandle();
````


## -parameters


## -returns
Returns a file handle to a KS object if successful; otherwise, returns null. 

Returns a file handle to a KS object if successful; otherwise, returns null. 

Returns a file handle to a KS object if successful; otherwise, returns null. 


## -remarks
Applications can use the handle that <b>KsGetObjectHandle</b> returns to send control-code requests to the driver that handles the KS object. 


## -see-also
<dl>
<dt>
<a href="..\ksproxy\nf-ksproxy-kssynchronousdevicecontrol.md">KsSynchronousDeviceControl</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IKsObject::KsGetObjectHandle method%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

