---
UID: NI:ks.IOCTL_KS_ENABLE_EVENT
title: IOCTL_KS_ENABLE_EVENT
author: windows-driver-content
description: An application can use IOCTL_KS_ENABLE_EVENT to request notification of a KS event type, or to determine the events supported by a KS object.
old-location: stream\ioctl_ks_enable_event.htm
old-project: stream
ms.assetid: 194a99f4-900f-44d1-bbc3-64953e4dce21
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.ioctl_ks_enable_event, IOCTL_KS_ENABLE_EVENT control code [Streaming Media Devices], IOCTL_KS_ENABLE_EVENT, ks/IOCTL_KS_ENABLE_EVENT, ks-ioctl_7cc1eab4-2a30-4998-8f7d-122150800c9a.xml
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
-	IOCTL_KS_ENABLE_EVENT
product: Windows
targetos: Windows
req.typenames: 
---

# IOCTL_KS_ENABLE_EVENT IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



An application can use IOCTL_KS_ENABLE_EVENT to request notification of a KS event type, or to determine the events supported by a KS object. The application specifies IOCTL_KS_ENABLE_EVENT in the <b>IoControl</b> parameter of a call to <a href="..\ksproxy\nf-ksproxy-kssynchronousdevicecontrol.md">KsSynchronousDeviceControl</a>.




## -ioctlparameters




### -input-buffer

The application places a pointer to a structure of type <a href="..\ks\nf-ks-ikscontrol-ksevent.md">KSEVENT</a> in the <b>InBuffer</b> parameter and the size of this structure at <b>InLength</b>. 


### -input-buffer-length

Length of <a href="..\ks\nf-ks-ikscontrol-ksevent.md">KSEVENT</a>.


### -output-buffer

The application places a pointer to a structure of type <a href="..\ks\ns-ks-kseventdata.md">KSEVENTDATA</a> in the <b>OutBuffer</b> parameter and the size of this structure at <b>OutLength</b>. 


### -output-buffer-length

Length of <a href="..\ks\ns-ks-kseventdata.md">KSEVENTDATA</a>.


### -in-out-buffer


<text></text>



### -inout-buffer-length


<text></text>



### -status-block

If the request is successful, the Status member is set to STATUS_SUCCESS.


## -remarks


To determine events supported by a KS object, specify <b>NULL</b> and 0 respectively for <b>InBuffer</b> and <b>InLength</b>.



## -see-also

<a href="..\ks\ns-ks-ksevent_item.md">KSEVENT_ITEM</a>

<a href="..\ks\ns-ks-kseventdata.md">KSEVENTDATA</a>

<a href="..\ks\nf-ks-ksdisableevent.md">KsDisableEvent</a>

<a href="..\ks\nf-ks-ikscontrol-ksevent.md">KSEVENT</a>

<a href="..\ks\ni-ks-ioctl_ks_disable_event.md">IOCTL_KS_DISABLE_EVENT</a>

<a href="..\ks\ns-ks-_ksevent_entry.md">KSEVENT_ENTRY</a>

<a href="..\ks\ns-ks-ksevent_set.md">KSEVENT_SET</a>

<a href="..\ks\ns-ks-ksdpc_item.md">KSDPC_ITEM</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20IOCTL_KS_ENABLE_EVENT control code%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

