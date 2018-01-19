---
UID: NF:ks.KSMETHOD_TYPE_IRP_STORAGE
title: KSMETHOD_TYPE_IRP_STORAGE macro
author: windows-driver-content
description: This macro accesses the type of method as described in the KSMETHOD_ITEM. If the method will be processed asynchronously using KsDispatchSpecificMethod, this storage must be maintained intact.
old-location: stream\ksmethod_type_irp_storage.htm
old-project: stream
ms.assetid: f5327cbf-e71b-4c1c-94c0-0e27afb4d7cf
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: KSMETHOD_TYPE_IRP_STORAGE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ks.h
req.include-header: Ks.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSMETHOD_TYPE_IRP_STORAGE
req.alt-loc: ks.h
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
req.typenames: 
---

# KSMETHOD_TYPE_IRP_STORAGE macro



## -description
This macro accesses the type of method as described in the <a href="..\ks\ns-ks-ksmethod_item.md">KSMETHOD_ITEM</a>. If the method will be processed asynchronously using <a href="..\ks\nf-ks-ksdispatchspecificmethod.md">KsDispatchSpecificMethod</a>, this storage must be maintained intact.



## -syntax

````
VOID KSMETHOD_TYPE_IRP_STORAGE(
  [in] IRP Irp
);
````


## -parameters

### -param Irp [in]

Specifies the IRP passed to the handler routine.


## -remarks
The relevant KSMETHOD_ITEM structure is extracted from <b>Irp-&gt;Tail.Overlay.DriverContext</b>. Parameters in <b>DriverContext</b> are initialized by <a href="..\ks\nf-ks-ksmethodhandler.md">KsMethodHandler</a> and <a href="..\ks\nf-ks-ksmethodhandlerwithallocator.md">KsMethodHandlerWithAllocator</a>.

The macro is defined as follows:


## -see-also
<dl>
<dt>
<a href="..\ks\ns-ks-ksmethod_item.md">KSMETHOD_ITEM</a>
</dt>
<dt>
<a href="..\ks\ns-ks-ksmethod_set.md">KSMETHOD_SET</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ikscontrol-ksmethod.md">KSMETHOD</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksmethodhandler.md">KsMethodHandler</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksfastmethodhandler.md">KsFastMethodHandler</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ksmethodhandlerwithallocator.md">KsMethodHandlerWithAllocator</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSMETHOD_TYPE_IRP_STORAGE macro%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

