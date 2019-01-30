---
UID: NI:ks.IOCTL_KS_ENABLE_EVENT
title: IOCTL_KS_ENABLE_EVENT (ks.h)
description: An application can use IOCTL_KS_ENABLE_EVENT to request notification of a KS event type, or to determine the events supported by a KS object.
old-location: stream\ioctl_ks_enable_event.htm
tech.root: stream
ms.assetid: 194a99f4-900f-44d1-bbc3-64953e4dce21
ms.date: 04/23/2018
ms.keywords: IOCTL_KS_ENABLE_EVENT, IOCTL_KS_ENABLE_EVENT control, IOCTL_KS_ENABLE_EVENT control code [Streaming Media Devices], ks-ioctl_7cc1eab4-2a30-4998-8f7d-122150800c9a.xml, ks/IOCTL_KS_ENABLE_EVENT, stream.ioctl_ks_enable_event
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ks.h
api_name:
-	IOCTL_KS_ENABLE_EVENT
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_KS_ENABLE_EVENT IOCTL


## -description



An application can use IOCTL_KS_ENABLE_EVENT to request notification of a KS event type, or to determine the events supported by a KS object. The application specifies IOCTL_KS_ENABLE_EVENT in the <b>IoControl</b> parameter of a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff567142">KsSynchronousDeviceControl</a>.




## -ioctlparameters




### -input-buffer

The application places a pointer to a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff561744">KSEVENT</a> in the <b>InBuffer</b> parameter and the size of this structure at <b>InLength</b>. 


### -input-buffer-length

Length of <a href="https://msdn.microsoft.com/library/windows/hardware/ff561744">KSEVENT</a>.


### -output-buffer

The application places a pointer to a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff561750">KSEVENTDATA</a> in the <b>OutBuffer</b> parameter and the size of this structure at <b>OutLength</b>. 


### -output-buffer-length

Length of <a href="https://msdn.microsoft.com/library/windows/hardware/ff561750">KSEVENTDATA</a>.


### -in-out-buffer








### -inout-buffer-length








### -status-block

If the request is successful, the Status member is set to STATUS_SUCCESS.


## -remarks



To determine events supported by a KS object, specify <b>NULL</b> and 0 respectively for <b>InBuffer</b> and <b>InLength</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560802">IOCTL_KS_DISABLE_EVENT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561726">KSDPC_ITEM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561744">KSEVENT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561750">KSEVENTDATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561853">KSEVENT_ENTRY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561862">KSEVENT_ITEM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561867">KSEVENT_SET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561694">KsDisableEvent</a>
 

 

