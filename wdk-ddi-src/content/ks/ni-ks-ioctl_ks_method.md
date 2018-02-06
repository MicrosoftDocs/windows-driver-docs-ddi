---
UID: NI:ks.IOCTL_KS_METHOD
title: IOCTL_KS_METHOD
author: windows-driver-content
description: An application can use IOCTL_KS_METHOD to execute a method on a KS object. The application passes IOCTL_KS_METHOD with the parameters described below to the KsSynchronousDeviceControl function.
old-location: stream\ioctl_ks_method.htm
old-project: stream
ms.assetid: a1b8c406-0d83-4145-b2cc-24e1f00ab80b
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.ioctl_ks_method, IOCTL_KS_METHOD control code [Streaming Media Devices], IOCTL_KS_METHOD, ks/IOCTL_KS_METHOD, ks-ioctl_4e1471f0-3763-4828-9186-7771de6201bd.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ks.h
apiname:
-	IOCTL_KS_METHOD
product: Windows
targetos: Windows
req.typenames: 
---

# IOCTL_KS_METHOD IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


An application can use IOCTL_KS_METHOD to execute a method on a KS object. The application passes IOCTL_KS_METHOD with the parameters described below to the <a href="..\ksproxy\nf-ksproxy-kssynchronousdevicecontrol.md">KsSynchronousDeviceControl</a> function.


## -ioctlparameters




### -input-buffer

The application places a pointer to a structure of type <a href="..\ks\nf-ks-ikscontrol-ksmethod.md">KSMETHOD</a> specifying the method to invoke in the <b>InBuffer</b> parameter, and the size of the method structure at <b>InLength</b>. 


### -input-buffer-length

The size of the method structure at <b>InLength</b>. 


### -output-buffer

The client allocates and passes an output buffer if the method requires one. (This is determined by the flags set in the KSMETHOD structure.) For example, <a href="https://msdn.microsoft.com/library/windows/hardware/ff563428">KSMETHOD_STREAMALLOCATOR_ALLOC</a> provides an output buffer for the newly allocated frame.


### -output-buffer-length

Length of the output buffer.


### -in-out-buffer


<text></text>



### -inout-buffer-length


<text></text>



### -status-block

If the request is successful, the Status member is set to STATUS_SUCCESS.


## -see-also

<a href="..\ks\nf-ks-ikscontrol-ksmethod.md">KSMETHOD</a>

<a href="..\ks\nf-ks-ksmethodhandler.md">KsMethodHandler</a>

<a href="..\ks\ns-ks-ksfastmethod_item.md">KSFASTMETHOD_ITEM</a>

<a href="..\ks\ns-ks-ksmethod_set.md">KSMETHOD_SET</a>

<a href="..\ks\ns-ks-ksmethod_item.md">KSMETHOD_ITEM</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IOCTL_KS_METHOD control code%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

